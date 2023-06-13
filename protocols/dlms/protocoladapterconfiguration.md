<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# DLMS adapter configuration

A specific protocol adapter can be used for a specific protocol 
The protocol-adapter that will be used by the device, is configured in the protocol_info field of the device.
The following steps are required to configure and use a specific protocol-adapter:
1. Create a protocol-adapter that listens to a specific queue
2. Add a protocol-info record that uses this queue for the requests
3. Configure the device in osgp-core, so that it will use this new protocol-info

## 1. osgp-protocol-adapter-dlms

Configure the name of the JMS queue on which the protocol adpater will listen for requests.

```
jms.dlms.requests.queue=protocol-dlms.1_0.osgp-core.1_0.cdma.requests
```

## 2. osgp-core

### Protocol Info table

By using a different outgoing_requests_property_prefix value, osgp-core can use a separate JMS queue for the requests.

| Column | Example value | Description |
| :--- | :--- | :--- |
| id | 1 | Auto generated ID |
| protocol | SMR_CDMA | Identifier of the configuration |
| protocol_version | 5.1 | Version identifier of the configuration |
| incoming_requests_property_prefix | jms.protocol.dlms.incoming.requests | Property prefix of the JMS queue for incoming requests |
| outgoing_requests_property_prefix | jms.protocol.dlms.outgoing.cdma.requests | Property prefix of the JMS queue for outgoing requests |
| incoming_responses_property_prefix | jms.protocol.dlms.incoming.responses | Property prefix of the JMS queue for incoming responses |
| outgoing_responses_property_prefix | jms.protocol.dlms.outgoing.cdma.responses | Property prefix of the JMS queue for outgoing responses |

### osgp-core.properties

The property with the prefix specified in the protocol-info table must be configured in the osgp-core.properties file
The value is the name of the JMS queue. This is the same name as the name of the JMS queue specified in the osgp-protocol-adapter-dlms

```
jms.protocol.dlms.outgoing.cdma.requests.queue=protocol-dlms.1_0.osgp-core.1_0.cdma.requests
```

## 3. Connecting the device to the protocol-info

A device can be configured to use the specific protocol adapter, by pointing it to the new protocol_info record 

| Column | Example value | Description |
| :--- | :--- | :--- |
| device_identification | E0049007469584219 | Identification of the device |
| protocol_info_id | 1 | Reference to id in Protocol Info table |
