## 3.2 Development Guide per Component

### 3.2.1 Web Service Adapters

The web service adapters use Spring Web Service, contract first. JAXB is used to generate Java classes from the XSD's. All SOAP operations are bound to an endpoint. The incoming SOAP requests are authenticated by organization identification (plus certificates). Organization authorizations are checked for the desired operation. If the request is OK, a JMS message is sent to a domain adapter component.

### 3.2.2 Domain Adapters

Domain adapters contain business logic and persistence. Domain adapters process and forward the JMS message to the Core component.

### 3.2.3 Domain Components

Domain components contain entities and value objects.

### 3.2.4 Core

The Core component routes messages from domain adapter components to protocol adapter components and vice versa. Further, it offers read-only database access for protocol adapter components.

### 3.2.5 Protocol Adapters

Protocol Adapter components translate a message from domain adapter components into a protocol message for a smart device. Protocol Adapter components send the protocol message to a smart device using a network connection. The response from the smart device is translated into a domain response message which will be sent to the Core components (which will route it to the domain adapter that issued the request).
