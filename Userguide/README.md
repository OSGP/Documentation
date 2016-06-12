# CHAPTER 2. User's Guide

 Sys Admins who are tasked with keeping OSGP running on a environment, can find some information in this chapter.

## 2.1 Get Started

To get started with OSGP, please read our [Introduction](../INTRO.md). The Introduction offers an excellent overview of the Platform and its features.

A next step could be to have a look at the WSDL's to understand which functions are present per functional domain. Depending on the functional domain one is interested in, one could also have a look at the Protocol Adapter and device simulator for the domain.

### 2.1.1 Installation

If a full installation is desired, have a look at our [Installation Script](https://github.com/OSGP/Config) within the Config repository. This can be used to setup a development environment which can be used to start the Platform and run it. Installation on one or several servers can be derived from the steps within the Installation Script. 


## 2.2 FAQ

- **How to start everything up?** Make sure that PostgreSQL is running. Make sure that Apache HTTPD web server and Apache ActiveMQ are running. Then start Apache Tomcat application server.
- **Where are the log files?** The Apache Tomcat application server logs can be found in /var/log/tomcat7. The Apache HTTPD web server logs can be found in /var/log/httpd. The PostgreSQL log files can be found in /var/lib/pgsql/9.3/data/pg_log.
- **Help: SELinux is preventing < something >?** Make sure to set SELinux to 'permissive' mode. Then try again and it should work as SELinux will no longer enforce the current policy. Later, one can use the SELinux tools to create a proper policy that allows everything that was prevented before.
- **How to add or update a component?** Make sure to place the properties file(s) for the component in /etc/osp. Add the locations of the properties file(s) to Apache Tomcat context.xml file. Add the war file to /usr/share/tomcat7/webapps. Restart Apache Tomcat.
- **How to configure a component?** Most (if not all) components of OSGP are de-coupled using queues. Configure the broker URL in the properties file and take notice of the queues that a component uses/needs. Make sure to double check the connectionstring for PostgreSQL.
- **How to configure URL's for a component?** In this case the Apache HTTPD vhost needs to be updated. The vhost config file can be found in /etc/httpd/conf.d. We use redirects from HTTP to HTTPS and AJP proxy to send the requests to Apache Tomcat.
- **How to check up on Apache ActiveMQ?** Apache ActiveMQ offers a web interface (the default port is 8161). Using the web interface one can check the queues and especially the dead letter queue (DLQ).
- _If your question is not in this list, please fire an [issue on github ](https://github.com/OSGP/Config/issues/new?title=Question:My%20Title&)_

## 2.3 Using Apps (Clients for OSGP)

Client for OSGP can use the SOAP Web service. To be able to use the SOAP Web service, the client has to be configured to use the Java Keystore. Also, the client has to send organisation identification, user name and application name as part of the SOAP Header for each request. The organisation identification has to match with a certificate that has been signed with the main CA certificate. The organisation identification has to match with a known organisation identification within the Platform.

When using the SOAP Web service, there are 2 flows that can occur:
- some calls are synchronous: a response is returned immediately;
- other calls are a-synchronous: an initial response contains a correlation id, which can be used to obtain the actual response.

## 2.4 Maintenance

There's not much maintenance that needs to be performed. Archiving some old log files, checking up on available disk space and creating a backup of the databases. Looking into the queues to see if there are not handled messages in dead letter queue.

## 2.5 Tooling

The only tools you need to keep an OSGP server running are SSH/PuTTY, FileZilla, pgAdmin-III and SoapUI.

