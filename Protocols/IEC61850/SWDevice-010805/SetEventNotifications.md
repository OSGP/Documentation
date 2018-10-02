## SetEventNotifications messages

### Description

Request which commands a device to set its EventNotification mask.

Response which returns the result of the request.

### Message definitions

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|**DESCRIPTION**|
|---|---|---|---|---|
|CSLC.EvnBuf|CF|enbEvnType|VisString32|Bitmask indicating which event notification types are enabled, to enable all event types use: "1FFFFFF".|

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetEventNotificationsRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
         <ns1:EventNotifications>DIAG_EVENTS</ns1:EventNotifications>
         <ns1:EventNotifications>HARDWARE_FAILURE</ns1:EventNotifications>
         <ns1:EventNotifications>LIGHT_EVENTS</ns1:EventNotifications>
         <ns1:EventNotifications>TARIFF_EVENTS</ns1:EventNotifications>
         <ns1:EventNotifications>MONITOR_EVENTS</ns1:EventNotifications>
         <ns1:EventNotifications>FIRMWARE_EVENTS</ns1:EventNotifications>
         <ns1:EventNotifications>COMM_EVENTS</ns1:EventNotifications>
         <ns1:EventNotifications>SECURITY_EVENTS</ns1:EventNotifications>
      </ns1:SetEventNotificationsRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetEventNotificationsAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180927074508777</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetEventNotificationsAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetEventNotificationsAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180927074508777</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetEventNotificationsAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetEventNotificationsResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetEventNotificationsResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of data written to the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: SetEventNoficationFilter {
  CSLC.EvnBuf[CF].enbEvnType: 1FFFFFF
}
```

IEC61850 protocol adapter logging:
```
2018-09-27 07:45:09.181] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: SET_EVENT_NOTIFICATIONS with message priority: 4
2018-09-27 07:45:09.225] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: SET_EVENT_NOTIFICATIONS for domain: CORE 1.0
2018-09-27 07:45:09.225] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-09-27 07:45:09.225] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-09-27 07:45:09.231] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-09-27 07:45:09.233] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-09-27 07:45:09.282] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-27 07:45:09.282] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-09-27 07:45:09.306] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-09-27T07:45:09.226Z, end time: 2018-09-27T07:45:09.305Z, total time in milliseconds: 79
2018-09-27 07:45:09.313] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetEventNotificationFilterCommand@apply:37 - Setting the event notification filter
2018-09-27 07:45:09.313] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.EvnBuf
2018-09-27 07:45:09.329] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetEventNotificationFilterCommand@apply:44 - Updating the enabled EventType filter to 1FFFFFF
2018-09-27 07:45:09.329] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing 1FFFFFF to enbEvnType
2018-09-27 07:45:09.348] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-27 07:45:09.349] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
2018-09-27 07:45:09.349] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: SET_EVENT_NOTIFICATIONS with message priority: 4
2018-09-27 07:45:09.349] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: SET_EVENT_NOTIFICATIONS, Start time: 2018-09-27T07:45:09.226Z, end time: 2018-09-27T07:45:09.349Z, total time in milliseconds: 123
```
