### Description of each of the platform components

#### Web applications

If one of the web apps is open source, we might write something on this and it's APIs as well.

**Application Layering**

The use of layers improves the separation of responsibilities. Each application contains the following layers:

- Presentation layer: responsible for providing information to users (persons and/or systems) and the handling of user requests
- Application layer: responsible for executing system tasks including authorisation control
- Domain layer: responsible for the representation of the problem domain.
- Infrastructure: responsible for technical matters supporting other layers. For instance persistence, messaging, etc

**Layers:**
 ![alt text](./layers.png "Layers")

1. Audit logger
2. Webservices
3. Functions
4. Queue
5. Worklow engine
6. Protocol framework
7. Protocol implementations
8. Workflow engine
9. Queue
10. Communication


#### HTTPS/SOAP communication

//TODO

#### Web services

//TODO

#### Business logic

//TODO

#### Core

//TODO

#### Open protocols

- TLS (Transport Layer Security encryption)
- SSL (Secure Sockets Layer encryption)
- OSLP (Open Street Light Protocol).

At the moment only the OSLP protocol is supported but other protocols can easily be added to the platform.

The Open Street Light Protocol is based on Google Protocol Buffers and is used for communicating with SSLD devices (and device simulators).

#### Smart devices

//TODO ? This one may be left out ?
