## Description of each of the platform components


### Application Layering

The use of layers improves the separation of responsibilities. Each application contains the following layers:

- Presentation layer: responsible for providing information to users (persons and/or systems) and the handling of user requests
- Application layer: responsible for executing system tasks including authorization control
- Domain layer: responsible for the representation of the problem domain.
- Infrastructure: responsible for technical matters supporting other layers. For instance persistence, messaging, etc

**Layers:**

 ![Open smart grid platform layers](./OSGP-components.png "Layers")


### Authentication and authorization

The web server is configured with a SSL certificate to encrypt the incoming and outgoing communication. The SOAP Web service (Spring Framework web service) uses a Java Keystore and a certificate for each organization. Only organizations that are know within the platform and are authorized to use the web service.

### Application integration layer

For the several functional domains separate SOAP Web services are offered. This separation offers authorization per functional domain. Each of the web service components send a queue message to the corresponding domain component.

WSDL
A separate WSDL is implemented for each functional cluster. All SOAP operations have a request object parameter and return a response object. For Synchronized Webservices  the result is immediately included in the response.
For asynchronous web services the response contains a correlation ID. This Correlation ID  is to be used by the requester to receive the actual result from the platform. The following diagram is an example of such an asynchronous request.

![Web request example](./a-sync-web-service-request.png "A-Sync Web Service Request")

Furthermore each SOAP message has a header which contains the user's organisation ID. This table displays an overview of the WSDL's including operations and fields in the request and response objects.

SOAP vs REST
SOAP is chosen in the open smart grid platform webservices over REST for the following reasons:
- REST is resources/data oriented (put, get, delete) while the open smart grid platform is function/method oriented
- SOAP has the advantage of having a contract (WSDL)
- SOAP has extensive security features that are being used in the open smart grid platform to meet the high security demands/requirements requested by e.g. the energy utilities
- Energy companies are generally not progressive in terms of technology. SOAP is acceptable for energy companies and REST is sometimes seen as new and insecure.
The benefits of REST (e.g. speed / less overhead) does not outweigh the benefits of SOAP. More general information on this topic can be found [online](http://spf13.com/post/soap-vs-rest). Contributions to make REST available on the open smart grid platform is welcome.


### Domain logic layer

For each functional domain business logic is implemented using a separate domain component. Common functionality like authorization should be abstracted to a shared component. Domain components receive queue messages from web service components and send queue messages to the open smart grid platform core component.

More information on the specific domains can be found in the [domain chapter](../Domains/README.md)

### Open Smart Grid Platform Core Services

The open smart grid platform core component receives queue messages from domain components. These messages from domain components are forwarded to a protocol adapter project. The open smart grid platform core component also offers logic for a protocol adapter project to send the response of a smart device back to a domain project.
The Core component routes messages from domain adapter components to protocol adapter components and vice versa. The core layer also contains a workflow engine.

The internal databasemodel in the core layer:
![alt text](./Core-datamodel/OSGP-core-model.png "Core model")
![alt text](./Core-datamodel/OSGP-core-logging-and-monitor-model.png "Logging and monitor model")
![alt text](./Core-datamodel/OSGP-core-OSLP-device-model.png "Device model")


_Image, Overview of platform data model_
![alt text](./data-model.png "Data Model")

Data model explanation:

| **Table** | **Description** |
| --- | --- |
| devices | Devices table |
| device\_authorisation | Authorisation table, function group column concerns the device functions (AD\_HOC, INSTALLATION, etc) |
| organization | Organization table, function group column concerns the platform functions (ADMIN of USER) |
| event | Events table |
| oslp\_log\_item | Table for logging of OSLP messages. |
| webservice monitor log item | Audit record for tracking webservice activity. |

The platform will store as less data as possible
Generic (and domain specific) devices attributes are stored in core DB

### Protocol Layer

The open smart grid platform supports multiple protocols.

- OSLP (Open Street Light Protocol)
- DLMS/COSEM
- IEC61850

The protocols can use of the of the security layers:
- TLS (Transport Layer Security encryption)
- SSL (Secure Sockets Layer encryption)

Other protocols can easily be added to the platform. Protocols based on open standards are prefered (if possible).
A full list of current supported protocols can be found in the [protocols chapter](../Protocols/README.md).

Protocol specific device attributes are stored in protocol adapter DB

### Queues
Queues are used to connect open smart grid platform components with each other.

 ![Example how a queue works](./Queues.png "Queues")

* Transactions on messages to and from the queues
* Messages are persistence on the queues
* Queues are clustered for reliability and speed
* By using queues, the open smart grid platform can be stateless


### Smart devices

The open smart grid platform can connect to any device as long as the device supports one of the supported protocols.
Smart devices can receive messages from or send messages to protocol adapter components. In case of SSLD's this is done using TCP/IP over mobile internet connections (GPRS/CDMA). The communication is encrypted using public key cryptography.
