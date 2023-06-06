<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# RegisterDevice

## Description

The device registration is a 2 step process. First RegisterDeviceRequest is sent from device to platform. Second are writing GPS coordinates to the device and disabling the device registration flag.

Request that notifies the platform that a device wants to register. During the registration the device identification \(serial number\) and the IP address are sent to the platform.

Response writes GPS coordinates and disables registration flag.

## IEC61850 Fields

| **ATTRIBUTE** | **FC** | **SUB ATTRIBUTE** | **DATATYPE** | **DESCRIPTION** |
| :--- | :--- | :--- | :--- | :--- |
| CSLC.Reg | CF | ntfEnb | BOOLEAN | Enable/Disable device registration. |
| CSLC.Atnm | CF | lon | FLOAT32 | Longitude. |
| CSLC.Atnm | CF | lat | FLOAT32 | Latitude. |

## Plain text registration message

```javascript
0000000053,84.30.69.148
```

IEC61850 platform messages of the data sent to the device:

```javascript
LogicalDevice: SWDeviceGenericIO
messageType: LocationInformation {
  CSLC.Atnm[CF].lon: 52.37875
  CSLC.Atnm[CF].lat:  5.95558
}
messageType: DisableRegistration {
  CSLC.Reg[CF].ntfEnb: false
}
```

IEC61850 protocol adapter logging:

```text
2018-09-28 06:24:43.590] [osgp-tst-04] [New I/O server boss #9] INFO o.o.a.p.i.a.config.Iec61850Config@getPipeline:120 - Created new IEC61850 handler pipeline for server
2018-09-28 06:24:43.591] [osgp-tst-04] [New I/O server boss #9] INFO o.j.n.handler.logging.LoggingHandler@info:48 - [id: 0x2838b6a7, /84.241.206.116:51773 => /172.16.1.5:50001] OPEN
2018-09-28 06:24:43.591] [osgp-tst-04] [New I/O server boss #9] INFO o.o.a.p.i.i.n.Iec61850ChannelHandlerServer@channelOpen:34 - 674805415 Channel opened
2018-09-28 06:24:43.592] [osgp-tst-04] [New I/O worker #4] INFO o.j.n.handler.logging.LoggingHandler@info:48 - [id: 0x2838b6a7, /84.241.206.116:51773 => /172.16.1.5:50001] BOUND: /172.16.1.5:50001
2018-09-28 06:24:43.593] [osgp-tst-04] [New I/O worker #4] INFO o.j.n.handler.logging.LoggingHandler@info:48 - [id: 0x2838b6a7, /84.241.206.116:51773 => /172.16.1.5:50001] CONNECTED: /84.241.206.116:51773
2018-09-28 06:25:38.173] [osgp-tst-04] [New I/O worker #4] INFO o.j.n.handler.logging.LoggingHandler@info:48 - [id: 0x2838b6a7, /84.241.206.116:51773 => /172.16.1.5:50001] RECEIVED: BigEndianHeapChannelBuffer(ridx=0, widx=25, cap=25)
+-------------------------------------------------+
| 0 1 2 3 4 5 6 7 8 9 a b c d e f |
+--------+-------------------------------------------------+----------------+
|00000000| 30 30 30 30 30 30 30 30 35 33 2c 38 34 2e 33 30 |0000000053,84.30|
|00000010| 2e 36 39 2e 31 34 38 0d 0a |.69.148.. |
+--------+-------------------------------------------------+----------------+
2018-09-28 06:25:49.131] [osgp-tst-04] [New I/O worker #4] INFO o.j.n.handler.logging.LoggingHandler@info:48 - [id: 0x2838b6a7, /84.241.206.116:51773 :> /172.16.1.5:50001] DISCONNECTED
2018-09-28 06:25:49.131] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.RegisterDeviceRequestDecoder@decodeLast:41 - Decoding bytes received at channel disconnect.
2018-09-28 06:25:49.170] [osgp-tst-04] [ActiveMQ Task-1] INFO o.a.a.t.failover.FailoverTransport@doReconnect:1055 - Successfully connected to tcp://localhost:61616
2018-09-28 06:25:49.217] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.Iec61850ChannelHandlerServer@processRegistrationMessage:75 - Using testDeviceId: KAI-0000000053 and testDeviceIp: 84.30.69.148
2018-09-28 06:25:49.218] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.Iec61850ChannelHandlerServer@processRegistrationMessage:87 - Sending register device request to OSGP with correlation ID: 497d5a374fff414cbf2b7e42e2a9d702
2018-09-28 06:25:49.218] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.m.OsgpRequestMessageSender@send:34 - Sending request message to OSGP.
2018-09-28 06:25:49.220] [osgp-tst-04] [ActiveMQ Task-1] INFO o.a.a.t.failover.FailoverTransport@doReconnect:1055 - Successfully connected to tcp://localhost:61616
2018-09-28 06:25:49.268] [osgp-tst-04] [protocolLogItemRequestsMessageListenerContainer-2] INFO o.o.l.i.j.ProtocolLogItemRequestMessageListener@onMessage:38 - Received protocol log item request message off type [IEC61850_LOG_ITEM]
2018-09-28 06:25:49.296] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-09-28 06:25:49.302] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-09-28 06:25:49.307] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 0 and max retry count: 0
2018-09-28 06:25:49.327] [osgp-tst-04] [DefaultMessageListenerContainer-1] INFO o.o.c.i.j.p.i.ProtocolRequestMessageListener@onMessage:46 - Received message of type: REGISTER_DEVICE
2018-09-28 06:25:49.327] [osgp-tst-04] [DefaultMessageListenerContainer-1] INFO o.o.c.i.j.p.i.m.RegisterDeviceMessageProcessor@processMessage:53 - Received message of messageType: REGISTER_DEVICE organisationIdentification: no-organisation deviceIdentification: KAI-0000000053
2018-09-28 06:25:49.329] [osgp-tst-04] [DefaultMessageListenerContainer-1] INFO o.o.c.i.j.p.i.m.RegisterDeviceMessageProcessor@updateRegistrationData:92 - updateRegistrationData called for device: KAI-0000000053 ipAddress: 84.30.69.148, deviceType: SSLD hasSchedule: true.
2018-09-28 06:25:49.360] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-28 06:25:49.361] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-09-28 06:25:49.398] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-09-28T06:25:49.297Z, end time: 2018-09-28T06:25:49.398Z, total time in milliseconds: 101
2018-09-28 06:25:49.400] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Reg
2018-09-28 06:25:49.419] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.s.c.Iec61850DisableRegistrationCommand@disableRegistration:30 - Registration disabled for device: KAI-0000000053
2018-09-28 06:25:49.421] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.a.s.DeviceRegistrationService@setLocationInformation:122 - Ssld found for device: KAI-0000000053 longitude: 52.37875, latitude: 5.95558
2018-09-28 06:25:49.422] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Atnm
2018-09-28 06:25:49.646] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.s.c.Iec61850SetGpsCoordinatesCommand@setGpsCoordinates:32 - longitude: 52.37875, latitude: 5.95558 written for device: KAI-0000000053
2018-09-28 06:25:49.647] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.a.s.DeviceRegistrationService@apply:98 - Reporting disabled for device: KAI-0000000053
2018-09-28 06:25:49.647] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.Iec61850ChannelHandlerServer@processRegistrationMessage:93 - Disabled registration for device: KAI-0000000053, at IP address: 84.30.69.148
2018-09-28 06:25:49.649] [osgp-tst-04] [Thread-185] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:366 - associationClosed() for device: KAI-0000000053, IOException: Connection disconnected by client
2018-09-28 06:25:49.649] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.Iec61850ChannelHandlerServer@channelDisconnected:40 - 674805415 Channel disconnected
2018-09-28 06:25:49.649] [osgp-tst-04] [Thread-185] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:371 - No event notifications received from device: KAI-0000000053
2018-09-28 06:25:49.649] [osgp-tst-04] [New I/O worker #4] INFO o.j.n.handler.logging.LoggingHandler@info:48 - [id: 0x2838b6a7, /84.241.206.116:51773 :> /172.16.1.5:50001] UNBOUND
2018-09-28 06:25:49.649] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.Iec61850ChannelHandlerServer@channelUnbound:52 - 674805415 Channel unbound
2018-09-28 06:25:49.649] [osgp-tst-04] [New I/O worker #4] INFO o.j.n.handler.logging.LoggingHandler@info:48 - [id: 0x2838b6a7, /84.241.206.116:51773 :> /172.16.1.5:50001] CLOSED
2018-09-28 06:25:49.649] [osgp-tst-04] [New I/O worker #4] INFO o.o.a.p.i.i.n.Iec61850ChannelHandlerServer@channelClosed:46 - 674805415 Channel closed
```

