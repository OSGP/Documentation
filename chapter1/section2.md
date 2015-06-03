## 1.2 Description of each of the platform components

### 1.2.1 Web applications

If one of the web apps is open source, we might write something on this and its APIs as well.

### 1.2.2 Application Layering

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


### 1.2.3 HTTPS/SOAP communication

//TODO

### 1.2.4 Web services

//TODO

### 1.2.5 Business logic

//TODO

### 1.2.6 Core

//TODO

### 1.2.7 Open protocols

- TLS (Transport Layer Security encryption)
- SSL (Secure Sockets Layer encryption)
- OSLP (Open Street Light Protocol).

At the moment only the OSLP protocol is supported but other protocols can easily be added to the platform.

The Open Street Light Protocol is based on Google Protocol Buffers and is used for communication with SSLD devices (and device simulators).

### 1.2.8 Smart devices

//TODO ? This one may be left out ?
