## GetStatus messages

### Description

Request which queries the device for the status of all relays, the type of configuration, and the event notification mask set on the device.

Response which returns the result of the request and, if 'result = OK', contains the current status for all of the relays and other information.

### IEC61850 Fields

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|
|---|---|---|---|
|SWDeviceGenericIO/XSWC1.Pos|ST|stVal|BOOLEAN|
|SWDeviceGenericIO/XSWC2.Pos|ST|stVal|BOOLEAN|
|SWDeviceGenericIO/XSWC3.Pos|ST|stVal|BOOLEAN|
|SWDeviceGenericIO/CSLC.EvnBuf|CF|enbEvnType|VisString32|
|SWDeviceGenericIO/CSLC.SWCf|CF|LT|VisString64|


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
  XSWC2.Pos[ST]: false
  CSLC.SWCf[CF]: RELAY
  XSWC3.Pos[ST]: false
  XSWC1.Pos[ST]: false
  CSLC.EvnBuf[CF]: 1FFFFFF
}
```
