## SetTransition messages

### Description

Request which notifies the device that it should switch all relays configured as light relays according to a [light schedule-entry](SetSchedule.md).
The optional 'time' value can be used to indicate a switch time.
If the optional 'time' value is omitted the device should switch immediately.

Response communicates status.

### Message definitions

``` json
message SetTransitionRequest {
    required TransitionType transitionType = 1; // Night-Day or Day-Night transition
    optional string time = 2; // [(nanopb).max_size = 7]; // - format hhmmss UTC
}

message SetTransitionResponse {
    required Status status = 1;
}
```

### Data types

``` json
enum TransitionType {
    NIGHT_DAY = 0;
    DAY_NIGHT = 1;
}

enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:adh="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:com="http://www.opensmartgridplatform.org/schemas/publiclighting/2014/10">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>liander gebruiker</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <adh:SetTransitionRequest>
         <adh:DeviceIdentification>device-01</adh:DeviceIdentification>
         <adh:TransitionType>NIGHT_DAY</adh:TransitionType>
         <!--Optional:-->
         <adh:Time>07:55:01</adh:Time>
      </adh:SetTransitionRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetTransitionAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106155501582</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetTransitionAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:adh="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>liander gebruiker</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <adh:SetTransitionAsyncRequest>
         <adh:AsyncRequest>
            <com:CorrelationUid>LianderNetManagement|||device-01|||20160106155501582</com:CorrelationUid>
            <com:DeviceId>device-01</com:DeviceId>
         </adh:AsyncRequest>
      </adh:SetTransitionAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetTransitionResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetTransitionResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP SetTransitionRequest sent to 'device-01':
``` json
setTransitionRequest {
  transitionType: NIGHT_DAY
  time: "075501"
}
```

OSLP SetTransitionResponse sent to platform:
``` json
setTransitionResponse {
  status: OK
}
```