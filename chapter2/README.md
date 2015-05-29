# User's Manual

 Sys Admin's who are tasked with keeping OSGP running on a environment, can find some information in this chapter.

## Get Started

To get started with OSGP, please read our [Introduction](../INTRO.md). The Introduction offers an excellent overview of the Platform and its features.

A next step could be to have a look at the WSDL's to understand which functions are present per functional domain. Depending on the functional domain one is interested in, one could also have a look at the Protocol Adapter and device simulator for the domain.

### Installation

If a full installation is desired, have a look at our [Installation Script](https://github.com/OSGP/Config) within the Config repository. This can be used to setup a development environment which can be used to start the Platform and run it. Installation on one or several servers can be derived from the steps within the Installation Script. 

### Configuration

We have prepared a full set of configuration (properties files, certificates, key store, ...) which is available in our [Config repository](https://github.com/OSGP/Config). This configuration can be used to setup a trial environment. In case one wants to set up an environment 

# FAQ

- **How to start everything up?** Make sure that PostgreSQL is running. Make sure that Apache HTTPD web server and Apache ActiveMQ are running. Then start Apache Tomcat application server.
- **Where are the log files?** The Apache Tomcat application server logs can be found in /var/log/tomcat7. The Apache HTTPD web server logs can be found in /var/log/httpd. The PostgreSQL log files can be found in /var/lib/pgsql/9.3/data/pg_log.
-  **Help: SELinux is preventing < something >?** Make sure to set SELinux to 'permissive' mode. Then try again and it should work as SELinux will no longer enforce the current policy. Later, one can use the SELinux tools to create a proper policy that allows everything that was prevented before.

## Using Apps (Clients for OSGP)

Client for OSGP can use the SOAP Web service. To be able to use the SOAP Web service, the client has to be configured to use the Java Keystore. Also, the client has to send organisation identification, user name and application name as part of the SOAP Header for each request. The organisation identification has to match with a certificate that has been signed with the main CA certificate. The organisation identification has to match with a known organisation identification within the Platform.

When using the SOAP Web service, there are 2 flows that can occur:
- some calls are synchronous: a response is returned immediately;
- other calls are a-synchronous: an initial response contains a correlation id, which can be used to obtain the actual response.

## Maintenance

There's not much maintenance that needs to be performed. Archiving some old log files, checking up on available disk space and creating a backup of the databases. Looking into the queues to see if there are unhandled messages in dead letter queue.

## Tooling

SSH/PuTTY, FileZilla, pgAdmin-III and SoapUI should be everything needed to maintain a server running OSGP.

