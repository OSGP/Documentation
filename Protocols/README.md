## Protocols
The open smart grid platform supported protocols can be found in this section. Feel free to add your own protocol or improve an existing protocol adapter.

### Protocol Adapters

Protocol Adapter components translate a message from domain adapter components into a protocol message for a smart device. Protocol Adapter components send the protocol message to a smart device using a network connection. The response from the smart device is translated into a domain response message which will be sent to the Core components (which will route it to the domain adapter which issued the request).

#### OSLP

For the OSLP implementation, 2 components are used. The first component is the protocol adapter for the protocol. It can translate message into the protocol message for SSLD's. Second there's the signing-server component. It is responsible for signing the protocol message using the private key of the platform. The components communicate using a queue-pair. The singing-server can handle multiple protocol adapter instances by utilizing a reply-to queue per protocol adapter instance. Since the protocol adapter component needs to be reachable from a network, it is a requirement that the private key may not be used by the protocol adapter directly. The singing-server component  can be deployed in such a way that no network access is available to this component, as the only coupling needed are the queues / the message broker.

#### DLMS

The DLMS implementation is work in progress.

#### IEC61850

The IEC61850 implementation is work in progress.
