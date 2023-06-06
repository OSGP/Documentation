<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# UpdateFirmware

## Description

Request which commands a device to download and install new firmware. The request contains a URL defining the location of the new firmware image. The device should download the firmware from that location.

Response which returns the result of the request.

## IEC61850 Fields

| **ATTRIBUTE** | **FC** | **SUB ATTRIBUTE** | **DATATYPE** | **DESCRIPTION** |
| :--- | :--- | :--- | :--- | :--- |
| CSLC.FuncFwDw | CF | url | VisString255 | Functional firmware. Set new firmware file download URL here, device will download the new firmware file and then replace the old firmware file at startT. |
| CSLC.FuncFwDw | CF | startT | Timestamp | Functional firmware. Device will try to install new firmware file at this Timestamp \(date + time\). |
| CSLC.ScyFwDw | CF | url | VisString255 | Security firmware. Set new firmware file download URL here, device will download the new firmware file and then replace the old firmware file at startT. |
| CSLC.ScyFwDw | CF | startT | Timestamp | Security firmware. Device will try to install new firmware file at this Timestamp \(date + time\). |

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
      xmlns:ns1="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:UpdateFirmwareRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
         <ns1:FirmwareIdentification>KAI-SSLD-V2</ns1:FirmwareIdentification>
         <ns1:FirmwareModuleType>FUNCTIONAL</ns1:FirmwareModuleType>
      </ns1:UpdateFirmwareRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:UpdateFirmwareAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180926075721482</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:UpdateFirmwareAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:UpdateFirmwareAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180926075721482</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:UpdateFirmwareAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:UpdateFirmwareResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:UpdateFirmwareResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of the data written to the device:

```javascript
LogicalDevice: SWDeviceGenericIO
messageType: UpdateFirmware {
  CSLC.FuncFwDw[CF].startT: 2018-09-26 10:04:52
  CSLC.FuncFwDw[CF].url: https://168.63.97.65:63443/firmware/KAI-SSLD-V2
}
```

IEC61850 protocol adapter logging:

```text
2018-09-26 07:57:21.971] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: UPDATE_FIRMWARE with message priority: 4
2018-09-26 07:57:21.972] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: UPDATE_FIRMWARE for domain: CORE 1.0
2018-09-26 07:57:21.972] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-09-26 07:57:21.972] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-09-26 07:57:21.976] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-09-26 07:57:21.977] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-09-26 07:57:22.029] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-26 07:57:22.030] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-09-26 07:57:22.087] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-09-26T07:57:21.972Z, end time: 2018-09-26T07:57:22.087Z, total time in milliseconds: 115
2018-09-26 07:57:22.087] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850UpdateFirmwareCommand@updateFunctionalFirmware:80 - Reading the functional firmware node for device: KAI-0000000053
2018-09-26 07:57:22.087] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.FuncFwDw
2018-09-26 07:57:22.103] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, url has value https://127.0.0.3:8443/firmware/TST/TSTMOD/generated-no-file.txt
2018-09-26 07:57:22.103] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850UpdateFirmwareCommand@updateFunctionalFirmware:89 - Current functional firmware download url: https://127.0.0.3:8443/firmware/TST/TSTMOD/generated-no-file.txt, start time: Mon Sep 03 15:02:04 UTC 2018 for device: KAI-0000000053
2018-09-26 07:57:22.103] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850UpdateFirmwareCommand@updateFunctionalFirmware:93 - Updating the functional firmware download url to: https://168.63.97.65:63443/firmware/KAI-SSLD-V2 for device: KAI-0000000053
2018-09-26 07:57:22.103] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing https://168.63.97.65:63443/firmware/KAI-SSLD-V2 to url
2018-09-26 07:57:22.122] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Clock
2018-09-26 07:57:22.138] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850UpdateFirmwareCommand@updateFunctionalFirmware:101 - Updating the functional firmware download start time to: Wed Sep 26 10:04:52 UTC 2018 for device: KAI-0000000053
2018-09-26 07:57:22.138] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeDate:139 - Device: KAI-0000000053, writing Wed Sep 26 10:04:52 UTC 2018 to startT
2018-09-26 07:57:22.155] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-26 07:57:22.156] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
2018-09-26 07:57:22.156] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: UPDATE_FIRMWARE with message priority: 4
2018-09-26 07:57:22.156] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: UPDATE_FIRMWARE, Start time: 2018-09-26T07:57:21.972Z, end time: 2018-09-26T07:57:22.156Z, total time in milliseconds: 184
```

