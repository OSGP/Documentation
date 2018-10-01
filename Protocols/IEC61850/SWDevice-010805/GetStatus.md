## GetStatus messages

### Description

Request which queries the device for the status of all relays, the type of configuration, and the event notification mask set on the device.

Response which returns the result of the request and, if 'result = OK', contains the current status for all of the relays and other information.

### IEC61850 Fields

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|**DESCRIPTION**|
|---|---|---|---|---|
|SWDeviceGenericIO/XSWC1.Pos|ST|stVal|BOOLEAN|Current switch status for relay 1|
|SWDeviceGenericIO/XSWC2.Pos|ST|stVal|BOOLEAN|Current switch status for relay 2|
|SWDeviceGenericIO/XSWC3.Pos|ST|stVal|BOOLEAN|Current switch status for relay 3|
|SWDeviceGenericIO/CSLC.EvnBuf|CF|enbEvnType|VisString32|Bitmask indicating which event notification types are enabled|
|SWDeviceGenericIO/CSLC.SWCf|CF|LT|VisString64|Device light type, always "RELAY"|

### Example

Soap requests and responses sent to and from platform:
``` xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.opensmartgridplatform.org/schemas/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.opensmartgridplatform.org/schemas/common">SoapUI</ApplicationName>
      <UserName xmlns="http://www.opensmartgridplatform.org/schemas/common">Sander</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetStatusRequest xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:DeviceIdentification>KAI-0000000053</ns2:DeviceIdentification>
      </ns2:GetStatusRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetStatusAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180924111517726</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetStatusAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.opensmartgridplatform.org/schemas/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.opensmartgridplatform.org/schemas/common">SoapUI</ApplicationName>
      <UserName xmlns="http://www.opensmartgridplatform.org/schemas/common">Sander</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetStatusAsyncRequest xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180924111517726</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053|</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:GetStatusAsyncRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetStatusResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:DeviceStatus>
            <ns2:LightValues>
               <ns2:Index>2</ns2:Index>
               <ns2:On>false</ns2:On>
            </ns2:LightValues>
            <ns2:LightValues>
               <ns2:Index>3</ns2:Index>
               <ns2:On>false</ns2:On>
            </ns2:LightValues>
            <ns2:PreferredLinkType>ETHERNET</ns2:PreferredLinkType>
            <ns2:ActualLinkType>ETHERNET</ns2:ActualLinkType>
            <ns2:LightType>RELAY</ns2:LightType>
            <ns2:EventNotifications>DIAG_EVENTS</ns2:EventNotifications>
            <ns2:EventNotifications>LIGHT_EVENTS</ns2:EventNotifications>
            <ns2:EventNotifications>TARIFF_EVENTS</ns2:EventNotifications>
            <ns2:EventNotifications>MONITOR_EVENTS</ns2:EventNotifications>
            <ns2:EventNotifications>FIRMWARE_EVENTS</ns2:EventNotifications>
            <ns2:EventNotifications>COMM_EVENTS</ns2:EventNotifications>
            <ns2:EventNotifications>SECURITY_EVENTS</ns2:EventNotifications>
         </ns2:DeviceStatus>
      </ns2:GetStatusResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of the data read from the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: GetStatus {
  XSWC2.Pos[ST].stVal: false
  CSLC.SWCf[CF].LT: RELAY
  XSWC3.Pos[ST].stVal: false
  XSWC1.Pos[ST].stVal: false
  CSLC.EvnBuf[CF].enbEvnType: 1FFFFFF
}
```

IEC61850 protocol Adapter logging:
``` json
2018-10-01 13:31:42.182] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: GET_LIGHT_STATUS for domain: PUBLIC_LIGHTING 1.0
2018-10-01 13:31:42.182] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-10-01 13:31:42.182] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-10-01 13:31:42.316] [dev-box] [iec61850RequestsMessageListenerContainer-2] WARN o.o.c.db.api.iec61850.entities.Ssld@createDefaultConfiguration:99 - DeviceType is SSLD, returning default list of DeviceOutputSetting: 1 TARIFF, 2 & 3 & 4 LIGHT
2018-10-01 13:31:42.326] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:79 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3, 4=4}
2018-10-01 13:31:42.335] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 1 and max retry count: 1
2018-10-01 13:31:42.428] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-10-01 13:31:42.434] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-10-01 13:31:42.513] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-10-01T13:31:42.182Z, end time: 2018-10-01T13:31:42.513Z, total time in milliseconds: 331
2018-10-01 13:31:42.533] [dev-box] [iec61850RequestsMessageListenerContainer-2] WARN o.o.c.db.api.iec61850.entities.Ssld@createDefaultConfiguration:99 - DeviceType is SSLD, returning default list of DeviceOutputSetting: 1 TARIFF, 2 & 3 & 4 LIGHT
2018-10-01 13:31:42.533] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.Pos
2018-10-01 13:31:42.564] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:62 - Got status of relay 1 => off
2018-10-01 13:31:42.565] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.Pos
2018-10-01 13:31:42.596] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:62 - Got status of relay 2 => off
2018-10-01 13:31:42.596] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.Pos
2018-10-01 13:31:42.626] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:62 - Got status of relay 3 => off
2018-10-01 13:31:42.626] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC4.Pos
2018-10-01 13:31:42.656] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:62 - Got status of relay 4 => off
2018-10-01 13:31:42.656] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.EvnBuf
2018-10-01 13:31:42.688] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, enbEvnType has value 1FFFFFF
2018-10-01 13:31:42.688] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:74 - Got EvnBuf.enbEvnType filter 1FFFFFF
2018-10-01 13:31:42.691] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.SWCf
2018-10-01 13:31:42.725] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, LT has value RELAY
2018-10-01 13:31:42.725] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-10-01 13:31:42.727] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.p.PublicLightingGetStatusRequestMessageProcessor@handleDeviceResponse:68 - Override for handleDeviceResponse() by PublicLightingGetStatusRequestMessageProcessor
2018-10-01 13:31:42.727] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.SsldDeviceRequestMessageProcessor@handleGetStatusDeviceResponse:66 - Handling getStatusDeviceResponse for device: KAI-0000000053
2018-10-01 13:31:42.728] [dev-box] [iec61850RequestsMessageListenerContainer-2] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:110 - Sending protocol response message [correlationUid=LianderNetManagement|||KAI-0000000053|||20181001133141570, device=KAI-0000000053, messageType=GET_LIGHT_STATUS, messagePriority=4]
```
