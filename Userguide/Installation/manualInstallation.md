### Manual Installation

This chapter describes the steps for a manual installation (eg. not using the vagrant script and puppet scripts). This  chapter is for developers who would like to have more control over the installation procedure.

#### Note
 - Skip this chapter if you followed the Vagrant installation! You can continue with next chapter: [Setup the Open Smart grid Platform](./SetupOSGP.md)

### Operating System
The Open Smart Grid Platform runs on a Linux environment. It is recommended to set up a machine running Ubuntu 14.04.


### Software and tools

The Open Smart Grid platform needs the following software and tools installed/downloaded:
- **Java 7** openjdk-7
- **PostgreSQL** and **PGAdmin 3**
- **Git**
- **Maven**
- **ActiveMQ**
- **Tomcat 7**
- **Apache HTTPD**
- **SoapUi**
- **Eclipse EE Luna**
- **Google Protocol Buffers**: **protobuf-compiler**, **libprotoc7** and **libprotobuf7**
- **[PostgreSql JDBC driver JRE 7](https://jdbc.postgresql.org/download/postgresql-9.4.1209.jre7.jar)**

### Settings

#### User
It is recommeded to create a 'dev' user, because some scripts contain hard coded references to this 'dev' user. It is possible to skip this step, but then some of the scripts will have to be adjusted manually.

##### Tomcat 7
- Place the PostgreSql JDBC driver jar in the Tomcat7 lib directory.
- Change permissions of Tomcat 7 Config files to 644 in the Tomcat 7 conf directory.

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
- Make sure the JAVA_HOME var is set, and points to openjdk-7.

### Cloning Sources
Clone the following repo's, it is recommeded to create a ```Sources/OSGP``` directory in ```/home/dev/``` since some scripts contain hard coded references to those folders.
```shell
git clone https://github.com/OSGP/Config.git /home/dev/Sources/OSGP/Config
git clone https://github.com/OSGP/Shared.git /home/dev/Sources/OSGP/Shared
git clone https://github.com/OSGP/Platform.git /home/dev/Sources/OSGP/Platform
git clone https://github.com/OSGP/Protocol-Adapter-OSLP.git /home/dev/Sources/OSGP/Protocol-Adapter-OSLP
git clone https://github.com/OSGP/Protocol-Adapter-DLMS.git /home/dev/Sources/OSGP/Protocol-Adapter-DLMS
```
Make sure you are on the development branch (default).

Initialiaze the Git submodules in Platform, Protocol-Adapter-OSLP and Protocol-Adapter-DLMS ny running the following command in each directory:
```shell
git submodule update --init --recursive
```

### Creating directories and symlinks
Create the following directories:
- ```/var/log/osp/logs```
- ```/etc/osp/```

Make the dev user (or equivelant) the owner of the log directory with rwx permission. Give the other users read and execute permission.

Execute the script ```/home/dev/Sources/OSGP/Config/scripts/create-symlinks.sh```

****Note**** This script uses hard coded references to ```/home/dev/Sources/OSGP/*```, if you used a different user, please edit the script before executing it.

The script will make symlinks to certificates, and to the Maven settings file in ~/.m2

### Initiating the Database
To create the database run the following command (Change /home/dev/ in case of no dev user)
```shell
sudo -u postgres /usr/bin/psql -p 5432 -f /home/dev/Sources/OSGP/Config/sql/create-users-and-databases.sql
```

And create a backup of the pg_hba.conf file
```shell
cp -p /etc/postgresql/9.3/main/pg_hba.conf /etc/postgresql/9.3/main/pg_hba.backup
```

Finally, reload the postgresql service:
```shell
service postgresql reload
```

### Set up the Open Smart Grid Platform

Continue with setting up the Open Smart Grid Platform by following the [Set up the Open Smart Grid Platform Guide](http://documentation.opensmartgridplatform.org/Userguide/Installation/setupOSGP.html)


