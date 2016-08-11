# CHAPTER 2. User's Guide

 Sys Admins who are tasked with keeping OSGP running on a environment, can find some information in this chapter.

## Get Started

To get started with OSGP, please read our [Introduction](../INTRO.md). The Introduction offers an excellent overview of the Platform and its features.

A next step could be to have a look at the WSDL's to understand which functions are present per functional domain. Depending on the functional domain one is interested in, one could also have a look at the Protocol Adapter and device simulator for the domain.

### Installation

If a full installation is desired, have a look at our [Installation Guide](./Installation/Installationguide.md). This can be used to setup a development environment which can be used to start the Platform and run it. Installation on one or several servers can be derived from the steps within the Installation Script. 

## Using Apps (Clients for OSGP)

Client for OSGP can use the SOAP Web service. To be able to use the SOAP Web service, the client has to be configured to use the Java Keystore. Also, the client has to send organisation identification, user name and application name as part of the SOAP Header for each request. The organisation identification has to match with a certificate that has been signed with the main CA certificate. The organisation identification has to match with a known organisation identification within the Platform.

When using the SOAP Web service, there are 2 flows that can occur:
- some calls are synchronous: a response is returned immediately;
- other calls are a-synchronous: an initial response contains a correlation id, which can be used to obtain the actual response.

## Maintenance

There's not much maintenance that needs to be performed. Archiving some old log files, checking up on available disk space and creating a backup of the databases. Looking into the queues to see if there are not handled messages in dead letter queue.

## Tooling

The only tools you need to keep an OSGP server running are SSH/PuTTY, FileZilla, pgAdmin-III and SoapUI.

