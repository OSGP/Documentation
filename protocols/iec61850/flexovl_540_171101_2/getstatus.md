# GetStatus

## Description

Request which queries the device for the status of the digital input.

Response which returns the result of the request and, if 'result = OK', contains the current status for the digital input.

## IEC61850 Fields

| **ATTRIBUTE** | **FC** | **SUB ATTRIBUTE** | **DATATYPE** | **DESCRIPTION** |
| :--- | :--- | :--- | :--- | :--- |
| SPGGIO2.Ind | ST | stVal | BOOLEAN | Current state of the digital input. |

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
xmlns:ns1="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
      <ns:MessagePriority>9</ns:MessagePriority>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:GetStatusRequest>
         <ns1:DeviceIdentification>LichtmeterNoord</ns1:DeviceIdentification>
      </ns1:GetStatusRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetStatusAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||LichtmeterNoord|||20181001155341143</ns3:CorrelationUid>
            <ns3:DeviceId>LichtmeterNoord</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetStatusAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" 
xmlns:ns1="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:GetStatusAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||LichtmeterNoord|||20181001155341143</ns:CorrelationUid>
            <ns:DeviceId>?</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:GetStatusAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetStatusResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:DeviceStatus>
            <ns2:LightValues>
               <ns2:Index>2</ns2:Index>
               <ns2:On>true</ns2:On>
               <ns2:DimValue>-1</ns2:DimValue>
            </ns2:LightValues>
            <ns2:PreferredLinkType>ETHERNET</ns2:PreferredLinkType>
            <ns2:ActualLinkType>ETHERNET</ns2:ActualLinkType>
            <ns2:LightType>ONE_TO_TWENTY_FOUR_VOLT</ns2:LightType>
         </ns2:DeviceStatus>
      </ns2:GetStatusResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of the data read from the device:

```javascript
LogicalDevice: SWDeviceGenericIO 
messageType: GetLightSensorStatus {
  SPGGIO2.Ind[ST].stVal: false
}
```

IEC61850 protocol Adapter logging:

```javascript
2018-10-01 15:53:41.468] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: GET_LIGHT_SENSOR_STATUS with message priority: 9
2018-10-01 15:53:41.468] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: GET_LIGHT_STATUS for domain: PUBLIC_LIGHTING 1.0
2018-10-01 15:53:41.468] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-10-01 15:53:41.469] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@testIfConnectionIsCachedAndAlive:202 - Trying to find connection in cache for deviceIdentification: LichtmeterNoord
2018-10-01 15:53:41.469] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@testIfConnectionIsCachedAndAlive:206 - Connection found for deviceIdentification: LichtmeterNoord
2018-10-01 15:53:41.469] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@testIfConnectionIsCachedAndAlive:211 - Testing if connection is alive using AA1TH01LD0/LLN0.NamPlt for deviceIdentification: LichtmeterNoord
2018-10-01 15:53:41.469] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@testIfConnectionIsCachedAndAlive:224 - Connection is still active for deviceIdentification: LichtmeterNoord
2018-10-01 15:53:41.472] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.Iec61850LmdDeviceService@getStatus:63 - Iec61850LmdDeviceService.getStatus() called for LMD: LichtmeterNoord of type: LMD with digital input: 2
2018-10-01 15:53:41.473] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: LichtmeterNoord, ObjectReference: AA1TH01LD0/SPGGIO2.Ind
2018-10-01 15:53:41.473] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.c.Iec61850GetLightSensorStatusCommand@apply:89 - device: LichtmeterNoord, indNode: AA1TH01LD0/SPGGIO2.Ind [ST]
AA1TH01LD0/SPGGIO2.Ind.stVal: false
AA1TH01LD0/SPGGIO2.Ind.q: 0x00 0x00
AA1TH01LD0/SPGGIO2.Ind.t: Thu Jan 01 00:00:00 UTC 1970
2018-10-01 15:53:41.473] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.c.Iec61850GetLightSensorStatusCommand@apply:93 - device: LichtmeterNoord, stVal: AA1TH01LD0/SPGGIO2.Ind.stVal: false
2018-10-01 15:53:41.473] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: LichtmeterNoord
2018-10-01 15:53:41.473] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.m.p.PublicLightingGetLightSensorStatusRequestMessageProcessor@handleDeviceResponse:93 - Override for handleDeviceResponse() by PublicLightingGetLightSensorStatusRequestMessageProcessor
2018-10-01 15:53:41.474] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.m.LmdDeviceRequestMessageProcessor@handleGetStatusDeviceResponse:65 - Handling getStatusDeviceResponse for device: LichtmeterNoord
2018-10-01 15:53:41.474] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: LichtmeterNoord of message type: GET_LIGHT_STATUS with message priority: 9
2018-10-01 15:53:41.474] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.Iec61850LmdDeviceService@enableReporting:125 - Trying to enable reporting for device: LichtmeterNoord
2018-10-01 15:53:41.474] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: LichtmeterNoord, ObjectReference: AA1TH01LD0/LLN0.rcb_A
2018-10-01 15:53:41.474] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.c.Iec61850EnableReportingCommand@enableUnbufferedReportingOnLightMeasurementDevice:146 - reportingEnabled for unbuffered reports: true
2018-10-01 15:53:41.474] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-23] INFO o.o.a.p.i.i.n.s.c.Iec61850EnableReportingCommand@enableUnbufferedReportingOnLightMeasurementDevice:149 - Unbuffered reporting is already enabled for device: LichtmeterNoord
```

