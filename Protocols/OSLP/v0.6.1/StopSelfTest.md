## StopSelfTest messages

### Description

Request that notifies the device to switch all relays off.

Response communicates status and the result of the test.

### Message definitions

``` json
message StopSelfTestRequest {
    optional bool present = 1 [default = true];
}

message StopSelfTestResponse {
    required Status status = 1;
    required bytes selfTestResult = 2; // [(nanopb).max_size = 1];
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
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:dev="http://www.alliander.com/schemas/osgp/deviceinstallation/2014/10">
   <soapenv:Header>
   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
   <com:UserName>liander gebruiker</com:UserName>
   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <dev:StopDeviceTestRequest>
         <dev:DeviceIdentification>device-01</dev:DeviceIdentification>
      </dev:StopDeviceTestRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:StopDeviceTestAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/deviceinstallation/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160104160800238</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:StopDeviceTestAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:dev="http://www.alliander.com/schemas/osgp/deviceinstallation/2014/10">
   <soapenv:Header>
   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
   <com:UserName>liander gebruiker</com:UserName>
   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <dev:StopDeviceTestAsyncRequest>
         <dev:AsyncRequest>
            <com:CorrelationUid>LianderNetManagement|||device-01|||20160104160800238</com:CorrelationUid>
            <com:DeviceId>device-01</com:DeviceId>
         </dev:AsyncRequest>
      </dev:StopDeviceTestAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:StopDeviceTestResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/deviceinstallation/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:StopDeviceTestResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP StopSelfTestRequest sent to 'device-01':
``` json
stopSelfTestRequest {
}
```

OSLP StopSelfTestResponse sent to platform:
``` json
stopSelfTestResponse {
  status: OK
  selfTestResult: "\000"
}
```