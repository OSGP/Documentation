# Developer's Guide

## Tool Used

- Apache ActiveMQ: Open source messaging server, used to relay messages between components of OSGP. ActiveMQ is an open source message broker written in Java together with a full Java Message Service (JMS) client. It provides "Enterprise Features" which in this case means fostering the communication from more than one client or server.
- Apache HTTP server: Webserver, used as front for Apache Tomcat.
- Apache JMeter: Application designed to load test functional behaviour and measure performance.
- Apache Tomcat: Provides a "pure Java" HTTP web server environment for Java code to run in.
- Bower:Package manager for Javascript packages. Web sites are made of lots of things - frameworks, libraries, assets, utilities, and rainbows. Bower manages all these things for you.
- CheckStyle: Tool for checking compliance to Java coding standard.
- Eclipse: IDE for developing software.
- FileZilla: FTP application.
- Fitnesse: A test tool, used to write behaviour driven tests.
- FindBugs: Tool for finding possible bugs.
- Git: Version control system for the front-end applications.
- GivWenZen: BDD extension for Fitnesse.
- NodeJS: Tooling suite with various Javascript tools.
- Notepad++: A free source code editor.
- NPM: Package manager for the NodeJS Javascript applications.
- PGAdmin: PostgreSQL administration and management tools.
- PMD: Source code analyzer.
- Protobuf	(Google Protocol Buffers): A language-neutral, platform-neutral, extensible way of serializing structured data for use in communications protocols, data storage, and more.
- Putty: A free and open-source terminal emulator, serial console and network file transfer application.
- SourceTree:SourceTree is a powerful Git and Mercurial desktop client for developers on Mac or Windows.
- Vim: Source code editor.
- Yeoman:	AngularJS web-app development tool, generates boilerplate code to get started quickly.

## Code Guidelines and Code Tests


## Continuous Integration

- Jenkins	An open source continuous integration tool written in Java.
- SonarQube: SonarQube is an open platform to manage code quality.

## Technical Conventions and Rules for New Code


## Development Guide per Component


## Installation Script

To get started quickly, an [installation script](https://github.com/OSGP/Config) has been created.

### Creating a virtual machine using [Virtual Box](https://www.virtualbox.org/)

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

### Installing [Ubuntu](http://www.ubuntu.com/desktop)

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

### Starting Ubuntu for the First Time

![alt text](./installation-script-screenshots/28.png)

![alt text](./installation-script-screenshots/29.png)

![alt text](./installation-script-screenshots/30.png)

### Updating the Software

![alt text](./installation-script-screenshots/31.png)

![alt text](./installation-script-screenshots/32.png)

![alt text](./installation-script-screenshots/33.png)

### Installing Virtual Box Guest Additions

![alt text](./installation-script-screenshots/34.png)

![alt text](./installation-script-screenshots/35.png)

![alt text](./installation-script-screenshots/36.png)

### Installing Virtual Box Guest Additions, Again

In case the Virtual Box version is not the latest, there might be a problem with the Virtual Box Guest Additions.
To fix it, use the latest version of Virtual Box Guest Additions.

![alt text](./installation-script-screenshots/37.png)

![alt text](./installation-script-screenshots/38.png)

![alt text](./installation-script-screenshots/39.png)

### Ubuntu installed and Virtual Box Guest Additons Up and Running

Optionally, Shared Clipboard and Drag 'n' Drop can be set to Bidirectional.

![alt text](./installation-script-screenshots/40.png)

![alt text](./installation-script-screenshots/41.png)

### Downloading the Puppet Scripts From Our [Config GitHub Repository](https://github.com/OSGP/Config)

Make sure to check the development branch for the latest version!

![alt text](./installation-script-screenshots/42.png)

![alt text](./installation-script-screenshots/43.png)

![alt text](./installation-script-screenshots/44.png)

![alt text](./installation-script-screenshots/45.png)

![alt text](./installation-script-screenshots/46.png)

### Start with Installing Puppet

![alt text](./installation-script-screenshots/47.png)

![alt text](./installation-script-screenshots/48.png)

### Using Puppet to Setup the Development Environment

![alt text](./installation-script-screenshots/49.png)

![alt text](./installation-script-screenshots/50.png)

![alt text](./installation-script-screenshots/51.png)

![alt text](./installation-script-screenshots/52.png)

### Importing Maven Project into Eclipse

![alt text](./installation-script-screenshots/54.png)

![alt text](./installation-script-screenshots/55.png)

![alt text](./installation-script-screenshots/56.png)

![alt text](./installation-script-screenshots/57.png)

![alt text](./installation-script-screenshots/58.png)

![alt text](./installation-script-screenshots/59.png)

![alt text](./installation-script-screenshots/60.png)

![alt text](./installation-script-screenshots/61.png)

### Creating an Apache Tomcat7 Server

![alt text](./installation-script-screenshots/62.png)

![alt text](./installation-script-screenshots/63.png)

![alt text](./installation-script-screenshots/64.png)

![alt text](./installation-script-screenshots/65.png)

![alt text](./installation-script-screenshots/66.png)

![alt text](./installation-script-screenshots/67.png)

### Creating Sym Link to Maven Settings

![alt text](./installation-script-screenshots/68.png)

### Setting Up Apache Tomcat7 Server Context

![alt text](./installation-script-screenshots/69.png)

![alt text](./installation-script-screenshots/70.png)

### Deploying All OSGP Components to Apache Tomcat7 Server

![alt text](./installation-script-screenshots/71.png)

### Starting Apache ActiveMQ

![alt text](./installation-script-screenshots/72.png)

### Starting Apache Tomcat7 Server

![alt text](./installation-script-screenshots/73.png)

### Starting pgAdmin III and Connection to PostgreSQL

![alt text](./installation-script-screenshots/74.png)

![alt text](./installation-script-screenshots/75.png)

![alt text](./installation-script-screenshots/76.png)

### Creating the 'test-org' Organization

![alt text](./installation-script-screenshots/77.png)

![alt text](./installation-script-screenshots/78.png)

### Installing SoapUI

![alt text](./installation-script-screenshots/79.png)

![alt text](./installation-script-screenshots/80.png)

![alt text](./installation-script-screenshots/81.png)

![alt text](./installation-script-screenshots/82.png)

![alt text](./installation-script-screenshots/83.png)

![alt text](./installation-script-screenshots/84.png)

### Setting Up SoapUI 

![alt text](./installation-script-screenshots/85.png)

![alt text](./installation-script-screenshots/86.png)

![alt text](./installation-script-screenshots/87.png)

![alt text](./installation-script-screenshots/88.png)

### First SOAP Requests to Add a Device to OSGP

![alt text](./installation-script-screenshots/89.png)

![alt text](./installation-script-screenshots/90.png)

![alt text](./installation-script-screenshots/91.png)

### Opening Device Simulater to Add a Device

![alt text](./installation-script-screenshots/92.png)

![alt text](./installation-script-screenshots/93.png)

![alt text](./installation-script-screenshots/94.png)

![alt text](./installation-script-screenshots/95.png)

### Registering a Device

![alt text](./installation-script-screenshots/96.png)

![alt text](./installation-script-screenshots/97.png)

### Using 'SetLight' SOAP Request to Switch the Light On

![alt text](./installation-script-screenshots/98.png)

![alt text](./installation-script-screenshots/99.png)

![alt text](./installation-script-screenshots/100.png)