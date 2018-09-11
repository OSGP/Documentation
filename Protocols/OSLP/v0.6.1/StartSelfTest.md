## StartSelfTest messages

### Description

Request that notifies the device to switch all relays on.

Response communicates status.

### Message definitions

``` json
message StartSelfTestRequest {
    optional bool present = 1 [default = true];
}

message StartSelfTestResponse {
    required Status status = 1;
}
```

### Data types

``` json
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:dev="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10">
   <soapenv:Header>
   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
   <com:UserName>liander gebruiker</com:UserName>
   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <dev:StartDeviceTestRequest>
         <dev:DeviceIdentification>device-01</dev:DeviceIdentification>
      </dev:StartDeviceTestRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:StartDeviceTestAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160104155530194</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:StartDeviceTestAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:dev="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10">
   <soapenv:Header>
   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
   <com:UserName>liander gebruiker</com:UserName>
   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <dev:StartDeviceTestAsyncRequest>
         <dev:AsyncRequest>
            <com:CorrelationUid>LianderNetManagement|||device-01|||20160104155530194</com:CorrelationUid>
            <com:DeviceId>device-01</com:DeviceId>
         </dev:AsyncRequest>
      </dev:StartDeviceTestAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:StartDeviceTestResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:StartDeviceTestResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP StartSelfTestRequest message sent to 'device-01':
``` json
startSelfTestRequest {
}
```

OSLP StartSelfTestResponse message sent to platform:
``` json
startSelfTestResponse {
  status: OK
}
```