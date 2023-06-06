<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# SetTransition

## Description

Request which informs a device of a daylight transiton: it has become dark \(sunset\) or light \(sunrise\). The device will switch the relays, which have schedule entries for transition messages. See [light schedule-entry](setschedule.md) for more information regarding switch schedules.

Response which returns the result of the request.

## IEC61850 Fields

| **ATTRIBUTE** | **FC** | **SUB ATTRIBUTE** | **DATATYPE** | **DESCRIPTION** |
| :--- | :--- | :--- | :--- | :--- |
| CSLC.Sensor | CO | Oper.ctlVal | BOOLEAN | Flag indicating transition type, true = DAY\_NIGHT, false = NIGHT\_DAY. |

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetTransitionRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
         <ns1:TransitionType>NIGHT_DAY</ns1:TransitionType>
         <ns1:Time>08:00:00</ns1:Time>
      </ns1:SetTransitionRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetTransitionAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180926091217778</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetTransitionAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetTransitionAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180926091217778</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetTransitionAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetTransitionResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>NOT FOUND</ns2:Result>
      </ns2:SetTransitionResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of the data written to the device:

```javascript
LogicalDevice: SWDeviceGenericIO
messageType: SetTransition {
  CSLC.Sensor[CO].Oper.ctlVal: false
}
```

IEC61850 protocol adapter logging:

```text
2018-09-26 09:12:18.111] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: SET_TRANSITION with message priority: 4
2018-09-26 09:12:18.111] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: SET_TRANSITION for domain: PUBLIC_LIGHTING 1.0
2018-09-26 09:12:18.111] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-09-26 09:12:18.111] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-09-26 09:12:18.116] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-09-26 09:12:18.121] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-09-26 09:12:18.167] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-26 09:12:18.167] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-09-26 09:12:18.224] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-09-26T09:12:18.112Z, end time: 2018-09-26T09:12:18.224Z, total time in milliseconds: 112
2018-09-26 09:12:18.224] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850TransitionCommand@transitionDevice:37 - device: KAI-0000000053, transition: NIGHT_DAY
2018-09-26 09:12:18.224] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] WARN o.o.a.p.i.i.n.s.c.Iec61850TransitionCommand@transitionDevice:42 - device: KAI-0000000053, setting date/time 1970-01-01T08:00:00.000Z for transition NIGHT_DAY not supported
2018-09-26 09:12:18.224] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Sensor
2018-09-26 09:12:18.239] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850TransitionCommand@apply:54 - device: KAI-0000000053, sensorNode: SWDeviceGenericIO/CSLC.Sensor [CO]
SWDeviceGenericIO/CSLC.Sensor.Oper [CO]
SWDeviceGenericIO/CSLC.Sensor.Oper.ctlVal: true
SWDeviceGenericIO/CSLC.Sensor.Oper.origin [CO]
SWDeviceGenericIO/CSLC.Sensor.Oper.origin.orCat: 0
SWDeviceGenericIO/CSLC.Sensor.Oper.origin.orIdent: []
SWDeviceGenericIO/CSLC.Sensor.Oper.ctlNum: 0
SWDeviceGenericIO/CSLC.Sensor.Oper.T: Thu Jan 01 00:00:00 UTC 1970
SWDeviceGenericIO/CSLC.Sensor.Oper.Test: false
SWDeviceGenericIO/CSLC.Sensor.Oper.Check: 0x0
2018-09-26 09:12:18.239] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850TransitionCommand@apply:57 - device: KAI-0000000053, oper: SWDeviceGenericIO/CSLC.Sensor.Oper [CO]
SWDeviceGenericIO/CSLC.Sensor.Oper.ctlVal: true
SWDeviceGenericIO/CSLC.Sensor.Oper.origin [CO]
SWDeviceGenericIO/CSLC.Sensor.Oper.origin.orCat: 0
SWDeviceGenericIO/CSLC.Sensor.Oper.origin.orIdent: []
SWDeviceGenericIO/CSLC.Sensor.Oper.ctlNum: 0
SWDeviceGenericIO/CSLC.Sensor.Oper.T: Thu Jan 01 00:00:00 UTC 1970
SWDeviceGenericIO/CSLC.Sensor.Oper.Test: false
SWDeviceGenericIO/CSLC.Sensor.Oper.Check: 0x0
2018-09-26 09:12:18.239] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850TransitionCommand@apply:60 - device: KAI-0000000053, ctlVal: SWDeviceGenericIO/CSLC.Sensor.Oper.ctlVal: true
2018-09-26 09:12:18.239] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850TransitionCommand@apply:63 - device: KAI-0000000053, set ctlVal to false in order to transition the device
2018-09-26 09:12:18.255] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-26 09:12:18.255] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
2018-09-26 09:12:18.256] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: SET_TRANSITION with message priority: 4
2018-09-26 09:12:18.256] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/LLN0.evn_rpn01
2018-09-26 09:12:18.256] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@setSqNum:62 - First new SqNum for report listener for device: KAI-0000000053 is: 0
2018-09-26 09:12:18.270] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850EnableReportingCommand@enableReportingOnDeviceWithoutUsingSequenceNumber:79 - Allowing device KAI-0000000053 to send reports containing events
2018-09-26 09:12:38.270] [osgp-tst-03] [Timer-45] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/LLN0.evn_rpn01
2018-09-26 09:12:38.305] [osgp-tst-03] [Timer-45] INFO o.o.a.p.i.i.n.s.c.Iec61850ClearReportCommand@clearReportOnDevice:32 - Cleared event buffer for device: KAI-0000000053
2018-09-26 09:12:38.307] [osgp-tst-03] [Timer-45] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: SET_TRANSITION, Start time: 2018-09-26T09:12:18.112Z, end time: 2018-09-26T09:12:38.307Z, total time in milliseconds: 20195
```

