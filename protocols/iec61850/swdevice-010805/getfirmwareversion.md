# GetFirmwareVersion

## Description

Request which queries the device for its current firmware version.

Response which returns the result of the request and, if 'result = OK' contains the firmware version.

## IEC61850 Fields

| **ATTRIBUTE** | **FC** | **SUB ATTRIBUTE** | **DATATYPE** | **DESCRIPTION** |
| :--- | :--- | :--- | :--- | :--- |
| SWDeviceGenericIO/CSLC.FuncFwDw | ST | curVer | VisString32 | Current functional firmware version. |
| SWDeviceGenericIO/CSLC.ScyFwDw | ST | curVer | VisString32 | Current security firmware version. |

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:fman="http://www.opensmartgridplatform.org/schemas/firmwaremanagement">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>Sander</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <fman:GetFirmwareVersionRequest xmlns:fman="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
         <!--type: Identification-->
         <fman:DeviceIdentification>KAI-0000000053</fman:DeviceIdentification>
      </fman:GetFirmwareVersionRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetFirmwareVersionAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180924135200412</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetFirmwareVersionAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:fman="http://www.opensmartgridplatform.org/schemas/firmwaremanagement">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>Sander</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <fman:GetFirmwareVersionAsyncRequest xmlns:fman="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
         <fman:AsyncRequest>
            <!--type: CorrelationUid-->
            <com:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180924135200412</com:CorrelationUid>
            <!--type: Identification-->
            <com:DeviceId>KAI-0000000053</com:DeviceId>
         </fman:AsyncRequest>
      </fman:GetFirmwareVersionAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetFirmwareVersionResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:FirmwareVersion>
            <ns2:FirmwareModuleType>FUNCTIONAL</ns2:FirmwareModuleType>
            <ns2:Version>01_21_01A</ns2:Version>
         </ns2:FirmwareVersion>
         <ns2:FirmwareVersion>
            <ns2:FirmwareModuleType>SECURITY</ns2:FirmwareModuleType>
            <ns2:Version>01_06_02A</ns2:Version>
         </ns2:FirmwareVersion>
      </ns2:GetFirmwareVersionResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of the data received from the device:

```javascript
LogicalDevice: SWDeviceGenericIO
messageType: GetFirmwareVersion {
  CSLC.FuncFwDw[ST].curVer: 01_21_01A
  CSLC.ScyFwDw[ST].curVer: 01_06_02A
}
```

IEC61850 protocol adapter logging:

```text
2018-10-01 14:50:18.281] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: GET_FIRMWARE_VERSION for domain: CORE 1.0
2018-10-01 14:50:18.281] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-10-01 14:50:18.281] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-10-01 14:50:18.287] [dev-box] [iec61850RequestsMessageListenerContainer-2] WARN o.o.c.db.api.iec61850.entities.Ssld@createDefaultConfiguration:99 - DeviceType is SSLD, returning default list of DeviceOutputSetting: 1 TARIFF, 2 & 3 & 4 LIGHT
2018-10-01 14:50:18.290] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:79 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3, 4=4}
2018-10-01 14:50:18.297] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 1 and max retry count: 1
2018-10-01 14:50:18.391] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-10-01 14:50:18.394] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /home/dev/Sources/SmartSocietyServices/Configuration/iec61850-server-models/SWDevice-010805.icd
2018-10-01 14:50:18.436] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-10-01T14:50:18.281Z, end time: 2018-10-01T14:50:18.436Z, total time in milliseconds: 155
2018-10-01 14:50:18.438] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.c.Iec61850GetFirmwareVersionCommand@apply:45 - Reading the functional firmware version
2018-10-01 14:50:18.438] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.FuncFwDw
2018-10-01 14:50:18.467] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, curVer has value 01_21_01A
2018-10-01 14:50:18.469] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.c.Iec61850GetFirmwareVersionCommand@apply:60 - Reading the security firmware version
2018-10-01 14:50:18.469] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.ScyFwDw
2018-10-01 14:50:18.501] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, curVer has value 01_06_02A
2018-10-01 14:50:18.502] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-10-01 14:50:18.502] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.p.CommonGetFirmwareRequestMessageProcessor@handleDeviceResponse:80 - Override for handleDeviceResponse() by CommonGetFirmwareRequestMessageProcessor
2018-10-01 14:50:18.502] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:110 - Sending protocol response message [correlationUid=LianderNetManagement|||KAI-0000000053|||20181001145017865, device=KAI-0000000053, messageType=GET_FIRMWARE_VERSION, messagePriority=4]
2018-10-01 14:50:18.504] [dev-box] [Thread-67] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:365 - associationClosed() for device: KAI-0000000053, IOException: Connection disconnected by client
2018-10-01 14:50:18.504] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: GET_FIRMWARE_VERSION, Start time: 2018-10-01T14:50:18.281Z, end time: 2018-10-01T14:50:18.504Z, total time in milliseconds: 223
2018-10-01 14:50:18.504] [dev-box] [Thread-67] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:370 - No event notifications received from device: KAI-0000000053
```

