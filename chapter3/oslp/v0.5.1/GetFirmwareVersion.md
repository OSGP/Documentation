## GetFirmwareVersion messages

### Description

Request which notifies the device to sent the current firmware version.

Response containing the firmware version.

### Message definitions

``` json
message GetFirmwareVersionRequest {
    optional bool present = 1 [default = true];
}

message GetFirmwareVersionResponse {
    required string firmwareVersion = 1; // [(nanopb).max_size = 7]; // RXX
}
```

### Datatypes

``` json

```

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:fman="http://www.alliander.com/schemas/osgp/firmwaremanagement">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>KevinSmeets</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <fman:GetFirmwareVersionRequest xmlns:fman="http://www.alliander.com/schemas/osgp/common/firmwaremanagement/2014/10">
         <!--type: Identification-->
         <fman:DeviceIdentification>device-01</fman:DeviceIdentification>
      </fman:GetFirmwareVersionRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetFirmwareVersionAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160104150323405</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetFirmwareVersionAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:fman="http://www.alliander.com/schemas/osgp/firmwaremanagement">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>liander gebruiker</com:UserName>
      <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <fman:GetFirmwareVersionAsyncRequest xmlns:fman="http://www.alliander.com/schemas/osgp/common/firmwaremanagement/2014/10">
         <fman:AsyncRequest>
            <!--type: CorrelationUid-->
            <com:CorrelationUid>LianderNetManagement|||device-01|||20160104150323405</com:CorrelationUid>
            <!--type: Identification-->
            <com:DeviceId>device-01</com:DeviceId>
         </fman:AsyncRequest>
      </fman:GetFirmwareVersionAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetFirmwareVersionResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:FirmwareVersion>R01</ns2:FirmwareVersion>
      </ns2:GetFirmwareVersionResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP GetFirmwareRequest message sent to 'device-01':
``` json
getFirmwareVersionRequest {
}
```

OSLP GetFirmwareResponse message sent to platform:
``` json
getFirmwareVersionResponse {
  firmwareVersion: "R01"
}
```