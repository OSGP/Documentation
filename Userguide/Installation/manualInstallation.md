### Manual Installation

This chapter describes the steps for a manual installation (eg. not using the vagrant script and puppet scripts). This  chapter is for developers who would like to have more control over the installation procedure.

With the increased control come increased risks of things not working with the versions or configuration of the software involved with the OSGP environment. If you run into issues, you may find clues in the puppet scripts about versions and modifications to the configuration of installed software.

#### Note
 - Skip this chapter if you followed the Vagrant installation! You can continue with next chapter: [Setup the Open Smart grid Platform](./SetupOSGP.md)

### Operating System
The Open Smart Grid Platform runs on a Linux environment. It is recommended to set up a machine running Ubuntu.


### Software and tools

The Open Smart Grid platform needs the following software and tools installed/downloaded:
- **Java 8** openjdk-8
- **PostgreSQL** and **pgAdmin 3**
- **Git**
- **Maven**
- **ActiveMQ**
- **Tomcat**
- **Apache HTTPD**
- **SoapUi**
- **Eclipse IDE for Java EE Developers**
- **Google Protocol Buffers**: **protobuf-compiler**, **libprotoc7** and **libprotobuf7**
- **[PostgreSQL JDBC driver](https://jdbc.postgresql.org/download/postgresql-42.2.4.jar)**

### Settings

#### User
It is recommended to create a 'dev' user, because some scripts contain hard coded references to this 'dev' user. It is possible to skip this step, but then some of the scripts will have to be adjusted manually.

##### Tomcat
- Place the PostgreSQL JDBC driver jar in the Tomcat lib directory.
- Change permissions of Tomcat Config files to 644 in the Tomcat conf directory.

##### Apache HTTPD
- Enable mod_ssl by running the following command:
```shell
a2enmod ssl
```
- Enable proxy_ajp by running the following command:
```shell
a2enmod proxy_ajp
```

#### Java
- Make sure the JAVA_HOME var is set, and points to openjdk-8.

### Cloning Sources
Clone the following repo's, it is recommended to create a ```Sources/OSGP``` directory in ```/home/dev/``` since some scripts contain hard coded references to those folders.
```shell
git clone https://github.com/OSGP/Config.git /home/dev/Sources/OSGP/Config
git clone https://github.com/OSGP/open-smart-grid-platform.git /home/dev/Sources/OSGP/open-smart-grid-platform
git clone https://github.com/OSGP/Documentation.git /home/dev/Sources/OSGP/Documentation
```
Make sure you are on the development branch (default).

### Creating directories and symlinks
Create the following directories:
- ```/var/log/osp/logs```
- ```/etc/osp/```

Make the dev user (or equivalent) the owner of the log directory with rwx permission. Give the other users read and execute permission.

Execute the script ```/home/dev/Sources/OSGP/Config/scripts/create-symlinks.sh```

****Note**** This script uses hard coded references to ```/home/dev/Sources/OSGP/*```, if you used a different user, please edit the script before executing it.

The script will make symlinks to certificates, to Apache HTTP server configuration and copy configuration settings as samples to locations where these properties may be overridden.

### Initiating the Database
To create the database run the following command (Change /home/dev/ in case of no dev user)
```shell
sudo -u postgres /usr/bin/psql -p 5432 -f /home/dev/Sources/OSGP/Config/sql/create-users-and-databases.sql
```

And create a backup of the pg_hba.conf file (modify if your version of PostgreSQL is different)
```shell
cp -p /etc/postgresql/9.4/main/pg_hba.conf /etc/postgresql/9.4/main/pg_hba.backup
```

Finally, reload the postgresql service:
```shell
service postgresql reload
```

### Set up the Open Smart Grid Platform

Continue with setting up the Open Smart Grid Platform by following the [Set up the Open Smart Grid Platform Guide](https://documentation.gxf.lfenergy.org/Userguide/Installation/setupOSGP.html)
