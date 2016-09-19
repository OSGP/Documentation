## Web Services

The Web Services layer contains the web services that are used to communicate with the Platform. The Open Source Smart Grid Platform uses the Simple Object Access Protocol (SOAP) to expose it's interfaces. The Web Services Adapter receives requests and sends those to the Domain Adapter. An incoming request is converted to a Domain Object, and put on the MessageQueue of the Domain layer. The Web Services layer also has a queue for incoming responses from the Domain adapter.

Each domain of the Platform has it's own web services:

#### Generic
- Core - osgp-adapter-ws-core: Contains the Core(common) web services.
- Admin - osgp-adapter-ws-admin: Contains the Admin web services.
- Shared - osgp-adapter-ws-shared: Contains shared endpoints (such as header authorization)
- Database - osgp-adapter-ws-db: Contains repositories for persistence.

#### Domain
- Public Lighting - osgp-adapter-ws-publiclighting: Contains the Public Lighting web services.
- Smart Metering - osgp-adapter-ws-smartmetering: Contains the Smart Metering web services.
- Tariff Swithcing - osgp-adapter-ws-tariffswitching: Contains the Tariff Switching web services.

For a description of the WSDL's see the [Domain Chapter](../../Domains/README.md).

### General Package structure
A description of the general package structure of a web service component.

#### application
- config: Contains the configuration files for the Component. Uses the property files in /etc/osp/.
-- ApplicationContext
-- AdapterInitializer
-- MessagingConfig
-- PersistenceConfig
-- WebServiceConfig
- exceptionhandling: Exceptions are defined here.
- mapping: Custom Orika converters.
- services: Contains services this domain uses, such as AdHocManagement. These are called by the endpoints and basically convert the request to a Domain Object and put the request on the domain message queue using the JMS classes.

#### endpoints
- EndPoints for the webServices: Contain a reference to a service, which handles the request further.

#### infra
- jms: contains the JMS classes such as:
-- MessageSender(s)
-- MessageType
-- ResponseMessageFinder

#### webapp
The WSDL and schema definitions can be found under main/webapp/WEB_INF/wsdl.

### Using the Open Smart Grid Platform Web Services

Clients for OSGP can use the SOAP Web service. To be able to use the SOAP Web service, the client has to be configured to use the Java Keystore. Also, the client has to send organisation identification, user name and application name as part of the SOAP Header for each request. The organisation identification has to match with a certificate that has been signed with the main CA certificate. The organisation identification has to match with a known organisation identification within the Platform.

For more information with regard to accessing the Web Services and/or adding a Organization Certificate to the Open Smart Grid Platform, please see the [Installation Manual](../../Userguide/Installation/Installationguide.md)

When using the SOAP Web service, there are 2 flows that can occur:
- some calls are synchronous: a response is returned immediately;
- other calls are a-synchronous: an initial response contains a correlation id, which can be used to obtain the actual response.