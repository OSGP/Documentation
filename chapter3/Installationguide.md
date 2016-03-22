## 3.3 Installation Script

To get started quickly, an [Installation Script](https://github.com/OSGP/Config) has been created.
Below, all steps involved in using the script are shown in screenshots.
These are the steps:
- Creating a Virtual Machine (or skip this step if a 'real' installation is preferred)
- Installing Ubuntu
- Starting Ubuntu and Updating the Software
- If a Virtual Machine is used, install Virtual Box Guest Addtions
- Downloading the Puppet Scripts
- Start with Installing Puppet
- Using Puppet to Setup the Development Environment
- Importing Maven Projects into Eclipse
- Creating an Apache Tomcat7 Server
- Creating Sym Link to Maven Settings
- Setting Up Apache Tomcat7 Server Context
- Deploying All OSGP Components to Apache Tomcat7 Server
- Starting Apache ActiveMQ
- Starting Apache Tomcat7 Server
- Starting pgAdmin III and Connect to PostgreSQL
- Creating the 'test-org' Organization
- Installing SoapUI
- Setting Up SoapUI
- First SOAP Requests to Add a Device to OSGP
- Opening Device Simulator to Add a Device
- Registering a Device
- Using 'SetLight' SOAP Request to Switch the Light On

It is recommended to take a look at the [readme.md in the config repository](https://github.com/OSGP/Config/blob/development/README.md)!

### 3.3.1 Creating a Virtual Machine using [Virtual Box](https://www.virtualbox.org/)

! tip
 - Remember to enable Virtualization in your system BIOS. 
 - Also disable Hyper-V in Windows (can be found in Windows Features)
If you can't create 64 bit versions of the VM try these tips.

![alt text](./installation-script-screenshots/01.png)

![alt text](./installation-script-screenshots/02.png)

![alt text](./installation-script-screenshots/03.png)

![alt text](./installation-script-screenshots/04.png)

![alt text](./installation-script-screenshots/05.png)

![alt text](./installation-script-screenshots/06.png)

![alt text](./installation-script-screenshots/07.png)

![alt text](./installation-script-screenshots/08.png)

![alt text](./installation-script-screenshots/09.png)

![alt text](./installation-script-screenshots/10.png)

![alt text](./installation-script-screenshots/11.png)

### 3.3.2 Installing [Ubuntu](http://www.ubuntu.com/desktop)

![alt text](./installation-script-screenshots/12.png)

![alt text](./installation-script-screenshots/13.png)

![alt text](./installation-script-screenshots/14.png)

![alt text](./installation-script-screenshots/15.png)

![alt text](./installation-script-screenshots/16.png)

![alt text](./installation-script-screenshots/17.png)

![alt text](./installation-script-screenshots/18.png)

![alt text](./installation-script-screenshots/19.png)

![alt text](./installation-script-screenshots/20.png)

![alt text](./installation-script-screenshots/21.png)

![alt text](./installation-script-screenshots/22.png)

![alt text](./installation-script-screenshots/23.png)

![alt text](./installation-script-screenshots/24.png)

![alt text](./installation-script-screenshots/25.png)

![alt text](./installation-script-screenshots/26.png)

![alt text](./installation-script-screenshots/27.png)

### 3.3.3 Starting Ubuntu for the First Time

![alt text](./installation-script-screenshots/28.png)

![alt text](./installation-script-screenshots/29.png)

![alt text](./installation-script-screenshots/30.png)

### 3.3.4 Updating the Software

Find the Software Updater link on the left icon menu bar. Click it to start Ubuntu Software update.

![alt text](./installation-script-screenshots/31.png)

![alt text](./installation-script-screenshots/32.png)

![alt text](./installation-script-screenshots/33.png)

### 3.3.5 Installing Virtual Box Guest Additions

![alt text](./installation-script-screenshots/34.png)

![alt text](./installation-script-screenshots/35.png)

![alt text](./installation-script-screenshots/36.png)

### 3.3.6 Installing Virtual Box Guest Additions, Again

In case the Virtual Box version is not the latest, there might be a problem with the Virtual Box Guest Additions.
To fix it, use the latest version of Virtual Box Guest Additions.

![alt text](./installation-script-screenshots/37.png)

![alt text](./installation-script-screenshots/38.png)

![alt text](./installation-script-screenshots/39.png)

### 3.3.7 Ubuntu installed and Virtual Box Guest Additons Up and Running

Optionally, Shared Clipboard and Drag 'n' Drop can be set to Bidirectional.

![alt text](./installation-script-screenshots/40.png)

![alt text](./installation-script-screenshots/41.png)

### 3.3.8 Downloading the Puppet Scripts From Our [Config GitHub Repository](https://github.com/OSGP/Config)

Make sure to check the development branch for the latest version!

![alt text](./installation-script-screenshots/42.png)

![alt text](./installation-script-screenshots/43.png)

![alt text](./installation-script-screenshots/44.png)

![alt text](./installation-script-screenshots/45.png)

![alt text](./installation-script-screenshots/46.png)

### 3.3.9 Start with Installing Puppet

![alt text](./installation-script-screenshots/47.png)

![alt text](./installation-script-screenshots/48.png)

### 3.3.10 Using Puppet to Setup the Development Environment

![alt text](./installation-script-screenshots/49.png)

![alt text](./installation-script-screenshots/50.png)

![alt text](./installation-script-screenshots/51.png)

![alt text](./installation-script-screenshots/52.png)

### 3.3.11 Importing Maven Projects into Eclipse
Open eclipse (the executable can be found in the folder /home/dev/Downloads/eclipse*/eclipse) and import the projects: File -> Import -> Existing Maven Projects, browse to folder /home/dev/Sources and start with the Shared project, then the Platform project, then the Protocol-Adapter-OSLP project and then the Protocol-Adapter-DLMS project.

![alt text](./installation-script-screenshots/54.png)

![alt text](./installation-script-screenshots/55.png)

![alt text](./installation-script-screenshots/56.png)

![alt text](./installation-script-screenshots/57.png)

![alt text](./installation-script-screenshots/58.png)

![alt text](./installation-script-screenshots/59.png)

![alt text](./installation-script-screenshots/60.png)
Show the 'Debug' and 'Git' perspectives.
![alt text](./installation-script-screenshots/61.png)

### 3.3.12 Creating an Apache Tomcat7 Server
In the 'Debug' perspective, go to the 'Servers' view and add a new Apache Tomcat7 server, Tomcat7 is available in the folder /home/dev/Downloads/apache-tomcat-7.0.61.

![alt text](./installation-script-screenshots/62.png)

![alt text](./installation-script-screenshots/63.png)

![alt text](./installation-script-screenshots/64.png)
After adding the server, double click on the Tomcat server in the 'Servers' view and set the following configuration: under 'Timeouts' set 'Start' to 600 and 'Stop' to 300.
![alt text](./installation-script-screenshots/65.png)

Click on 'Open launch configuration', click on the 'Arguments' tab and add the following at the end of the 'VM arguments' '''string: -Xms512m -Xmx2048m -Xss512k -XX:MaxPermSize=1024m -XX:+CMSClassUnloadingEnabled -XX:+UseConcMarkSweepGC -Dcom.sun.management.jmxremote=true'''
![alt text](./installation-script-screenshots/66.png)

![alt text](./installation-script-screenshots/67.png)

### 3.3.13 Creating Sym Link to Maven Settings
Create a symlink to the Maven setting file using this command: 
'''sudo ln -s /home/dev/Sources/Config/maven/settings.xml /home/dev/.m2 '''
![alt text](./installation-script-screenshots/68.png)

### 3.3.14 Setting Up Apache Tomcat7 Server Context
Setup the Tomcat7 context.xml in the eclipse Servers folder, by copying the entries in /home/dev/Sources/Config/tomcat/context.xml to map configuration file names to file paths.
![alt text](./installation-script-screenshots/69.png)

![alt text](./installation-script-screenshots/70.png)

### 3.3.15 Deploying All OSGP Components to Apache Tomcat7 Server
Continue by adding the Maven Projects to the Tomcat server by right clicking on the Tomcat server and choosing 'Add and Remove', followed by clicking on the 'Add =All' button.
![alt text](./installation-script-screenshots/71.png)
At this point, eclipse's auto-build should have built the projects, and the Tomcat server has been setup.

### 3.3.16 Starting Apache ActiveMQ
Continue with starting Apache ActiveMQ (the executable can be found in the folder /home/dev/Downloads/apache-activemq-*/bin/linux-x86-64): by opening a terminal and use the command: '''sudo ./activemq console''' to start ActiveMQ as a terminal process (this way, ActiveMQ doesn't detach from the terminal and starts running as a daemon).
![alt text](./installation-script-screenshots/72.png)

### 3.3.17 Starting Apache Tomcat7 Server
With ActiveMQ running, the Tomcat7 server can be started.
![alt text](./installation-script-screenshots/73.png)

### 3.3.18 Starting pgAdmin III and Connect to PostgreSQL
Open pgAdminIII and configure a connection: choose the 'Add a connection to a server.' and fill out the fields using Host localhost, Port 5432, Username osp_admin and Password 1234.

![alt text](./installation-script-screenshots/74.png)

![alt text](./installation-script-screenshots/75.png)

![alt text](./installation-script-screenshots/76.png)

### 3.3.19 Creating the 'test-org' Organization
Run the script (/home/dev/Sources/Config/sql/create-test-org.sql) to insert 'test-org' organization into the organisation table of the osgp_core database.

'''
psql -U osp_admin -d osgp_core -f /home/dev/Sources/Config/sql/create-test-org.sql
'''
![alt text](./installation-script-screenshots/77.png)

![alt text](./installation-script-screenshots/78.png)

### 3.3.20 Installing SoapUI

![alt text](./installation-script-screenshots/79.png)

![alt text](./installation-script-screenshots/80.png)

![alt text](./installation-script-screenshots/81.png)

![alt text](./installation-script-screenshots/82.png)

![alt text](./installation-script-screenshots/83.png)

![alt text](./installation-script-screenshots/84.png)

### 3.3.21 Setting Up SoapUI 

![alt text](./installation-script-screenshots/85.png)

![alt text](./installation-script-screenshots/86.png)

![alt text](./installation-script-screenshots/87.png)

![alt text](./installation-script-screenshots/88.png)

### 3.3.22 First SOAP Requests to Add a Device to OSGP

![alt text](./installation-script-screenshots/89.png)

![alt text](./installation-script-screenshots/90.png)

![alt text](./installation-script-screenshots/91.png)

### 3.3.23 Opening Device Simulator to Add a Device

![alt text](./installation-script-screenshots/92.png)

![alt text](./installation-script-screenshots/93.png)

![alt text](./installation-script-screenshots/94.png)

![alt text](./installation-script-screenshots/95.png)

### 3.3.24 Registering a Device

![alt text](./installation-script-screenshots/96.png)

![alt text](./installation-script-screenshots/97.png)

### 3.3.25 Using 'SetLight' SOAP Request to Switch the Light On

![alt text](./installation-script-screenshots/98.png)

![alt text](./installation-script-screenshots/99.png)

![alt text](./installation-script-screenshots/100.png)

**AND YOUR DONE!! :)**
