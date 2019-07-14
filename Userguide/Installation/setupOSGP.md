### Setting Up the Open Smart Grid Platform Development environment
This chapter describes all the steps needed to finalize the open smart grid platform development environment.

### Importing Maven Projects into Eclipse
Open Eclipse by clicking the shortcut on the Desktop and import the projects.

Go to File -> Import -> Existing Maven Projects, browse to folder `/home/dev/Sources/OSGP`

Import the projects from location `/home/dev/Sources/OSGP/open-smart-grid-platform`.

### Creating an Apache Tomcat Server

In Eclipse go to Window -> Open Perspective -> Debug
![alt text](./installation-script-screenshots/16.png)

In the 'Debug' perspective, go to the 'Servers' view and add a new Apache Tomcat server, Tomcat is available in the folder `/home/dev/Tools/tomcat` (or in another location if you didn't set up a VM using Vagrant, the latest version usually works fine).

Click on Next
![alt text](./installation-script-screenshots/tomcat-1-define-server.png)

Click on Finish
![alt text](./installation-script-screenshots/tomcat-2-edit-server-runtime.png)

![alt text](./installation-script-screenshots/tomcat-3-created.png)
After adding the server, double click on the Tomcat server in the 'Servers' view and set the following configuration: under 'Timeouts' set 'Start' to 600 and 'Stop' to 30.
![alt text](./installation-script-screenshots/tomcat-4-timeouts.png)

Click on 'Open launch configuration', click on the 'Arguments' tab and add the following at the end of the 'VM arguments':
`-Xms512m -Xmx2048m -Xss512k -XX:MaxMetaspaceSize=1024m -XX:+CMSClassUnloadingEnabled -XX:+UseConcMarkSweepGC -Dcom.sun.management.jmxremote=true`
![alt text](./installation-script-screenshots/tomcat-5-launch-configuration-old.png)

![alt text](./installation-script-screenshots/tomcat-6-launch-configuration-new.png)

### Setting Up Apache Tomcat Server Context
All modules contain their own context.xml. In the module specific context.xml are the environment variables defined where the global and module specific configuration files are located. Default they will point to a location in */etc/osp/*.

If you want to deviate from this, you might set up the context.xml in Tomcat to be able to redirect in one file to different locations.  This is optional and not required.
In order to use a custom context.xml, copy the entries in `/home/dev/Sources/OSGP/Config/tomcat/context.xml.sample` to the Tomcat context.xml in the eclipse Servers folder, to map configuration file names to file paths.
![alt text](./installation-script-screenshots/context.xml.sample.png)

![alt text](./installation-script-screenshots/context.xml.png)

### Deploying all Open Smart Grid Platform components to Apache Tomcat Server
Continue by adding the Maven Projects to the Tomcat server by right clicking on the Tomcat server and choosing 'Add and Remove'. Select all available resources, except for osgp-protocol-simulator-61850 (which is for advanced use and requires additional configuration), then click the 'Add' button.
![alt text](./installation-script-screenshots/add-resources.png)
At this point, eclipse's auto-build should have built the projects, and the Tomcat server has been setup.

### Starting Apache ActiveMQ
Continue with starting Apache ActiveMQ. If you installed an environment as described with Vagrant, you can double click the ActiveMQ shortcut on the desktop.

Alternatively you can open a terminal and run the executable manually by using the following command:
(the executable can be found in the folder `/home/dev/Tools/activemq/bin/linux-x86-64`)
```shell
sudo ./activemq console
```

This starts ActiveMQ as a terminal process (this way, ActiveMQ doesn't detach from the terminal and starts running as a daemon).
![alt text](./installation-script-screenshots/31.png)

### Starting Apache Tomcat Server
With ActiveMQ running, the Tomcat server can be started. Go to Eclipse, go to the Servers tab in the Debug view, and right click on the Tomcat server and select 'Start'.
![alt text](./installation-script-screenshots/tomcat-7-tomcat-started.png)

### Starting pgAdmin III and Connect to PostgreSQL
Open pgAdminIII and configure a connection: choose the 'Add a connection to a server.' and fill out the fields using
- Host: localhost
- Port: 5432
- Username: osp_admin
- Password: 1234

![alt text](./installation-script-screenshots/33.png)

![alt text](./installation-script-screenshots/34.png)

![alt text](./installation-script-screenshots/35.png)

### Creating the 'test-org' Organization (in database osgp-core)
Run the script in `/home/dev/Sources/OSGP/Config/sql/create-test-org.sql` to insert 'test-org' organization into the organisation table of the osgp_core database.

```shell
psql -U osp_admin -h localhost -d osgp_core -f /home/dev/Sources/OSGP/Config/sql/create-test-org.sql
```

If asked for a password, enter ```1234```

![alt text](./installation-script-screenshots/36.png)

Go back to PgAdmin III, expand servers, select localhost -> databases -> osgp_core -> Schemas -> public -> Tables. Right click the organisation table and select to view data for the top 100 rows. Confirm that the test-org organisation has been added to the Database.

![alt text](./installation-script-screenshots/37.png)

Now that everything has been set up, continue to the next chapter to start testing the Platform by sending it some requests.
