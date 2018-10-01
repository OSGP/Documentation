## UpdateDeviceSslCertification messages

### Description

Request to download a new SSL certificate from the certificate server. The device will be given the domain name and URL where the certificate is located.

### IEC61850 Fields

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|**DESCRIPTION**|
|---|---|---|---|---|
|CSLC.CARepl|CF|url|VisString255|Set new CA file download URL here, device will download the new CA file and then replace the old CA file at startT.|
|CSLC.CARepl|CF|startT|VisString32|Device will switch CA file at this Timestamp.|

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" 
xmlns:ns1="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:UpdateDeviceSslCertificationRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
         <ns1:Certification>
            <ns1:certificateDomain>cert-server</ns1:certificateDomain>
            <ns1:certificateUrl>/certs/new-cert.pem</ns1:certificateUrl>
         </ns1:Certification>
      </ns1:UpdateDeviceSslCertificationRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:UpdateDeviceSslCertificationAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20181001092825280</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:UpdateDeviceSslCertificationAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" 
xmlns:ns1="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:UpdateDeviceSslCertificationAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20181001092825280</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:UpdateDeviceSslCertificationAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:UpdateDeviceSslCertificationResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:UpdateDeviceSslCertificationResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

IEC61850 platform message of the data sent to the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: UpdateSslCertificate {
  CSLC.CARepl[CF].url: cert-server/certs/new-cert.pem
  CSLC.CARepl[CF].startT: 2018-10-01 11:36:08
}
```

IEC61850 protocol Adapter logging:
``` json
2018-10-01 09:28:25.800] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: UPDATE_DEVICE_SSL_CERTIFICATION with message priority: 4
2018-10-01 09:28:25.847] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: UPDATE_DEVICE_SSL_CERTIFICATION for domain: CORE 1.0
2018-10-01 09:28:25.847] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-10-01 09:28:25.847] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-10-01 09:28:25.852] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-10-01 09:28:25.871] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-10-01 09:28:25.926] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-10-01 09:28:25.932] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-10-01 09:28:25.960] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-10-01T09:28:25.847Z, end time: 2018-10-01T09:28:25.960Z, total time in milliseconds: 113
2018-10-01 09:28:25.968] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850UpdateSslCertificateCommand@apply:44 - Reading the certificate authority url
2018-10-01 09:28:25.968] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.CARepl
2018-10-01 09:28:25.983] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850UpdateSslCertificateCommand@apply:64 - Updating the certificate download url to cert-server/certs/new-cert.pem
2018-10-01 09:28:25.983] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing cert-server/certs/new-cert.pem to url
2018-10-01 09:28:26.003] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Clock
2018-10-01 09:28:26.018] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850UpdateSslCertificateCommand@apply:78 - Updating the certificate download start time to: Mon Oct 01 11:36:08 UTC 2018
2018-10-01 09:28:26.018] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeDate:139 - Device: KAI-0000000053, writing Mon Oct 01 11:36:08 UTC 2018 to startT
2018-10-01 09:28:26.036] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-10-01 09:28:26.037] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
2018-10-01 09:28:26.037] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: UPDATE_DEVICE_SSL_CERTIFICATION with message priority: 4
2018-10-01 09:28:26.040] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: UPDATE_DEVICE_SSL_CERTIFICATION, Start time: 2018-10-01T09:28:25.847Z, end time: 2018-10-01T09:28:26.037Z, total time in milliseconds: 190
2018-10-01 09:28:26.040] [osgp-tst-03] [Thread-557] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:366 - associationClosed() for device: KAI-0000000053, IOException: Connection disconnected by client
2018-10-01 09:28:26.040] [osgp-tst-03] [Thread-557] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:371 - No event notifications received from device: KAI-000000005
```
