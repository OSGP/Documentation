# SetLight

## Description

Request that notifies the device to switch on or off one or several light relays, optionally with a dim-value per relay. If optional value 'index' is omitted, all relays configured as light are switched. In that case, all light relays will switch using only 1 LightValue instance for 'values'. In case the value 'index' is included, multiple instances of LightValue can be used \(up to 6\), each indicating a particular relay. If optional value 'dimValue' is omitted, then default values of 0 and 100 will be assumed for either 'on = false' or 'on = true'.

Response communicates status.

## Message definitions

```javascript
message SetLightRequest {
    repeated LightValue values = 1; // [(nanopb).max_count = 6];
}

message SetLightResponse {
    required Status status = 1;
}
```

## Data types

```javascript
message LightValue {
    optional bytes index = 1; // [(nanopb).max_size = 1]; // index number of connected light (DALI), none means all connected ligts.
    required bool on = 2;
    optional bytes dimValue = 3; // [(nanopb).max_size = 1]; // 1 - 100 %
}

enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

## Example

Soap requests and responses sent to and from platform:

```markup
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.opensmartgridplatform.org/schemas/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.opensmartgridplatform.org/schemas/common">WEB_OWNER</ApplicationName>
      <UserName xmlns="http://www.opensmartgridplatform.org/schemas/common">liander gebruiker</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:SetLightRequest xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:DeviceIdentification>device-01</ns2:DeviceIdentification>
         <ns2:LightValue>
            <ns2:On>true</ns2:On>
         </ns2:LightValue>
      </ns2:SetLightRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:SetLightAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160105121022551</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetLightAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.opensmartgridplatform.org/schemas/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.opensmartgridplatform.org/schemas/common">WEB_OWNER</ApplicationName>
      <UserName xmlns="http://www.opensmartgridplatform.org/schemas/common">liander gebruiker</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:SetLightAsyncRequest xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160105121022551</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:SetLightAsyncRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:SetLightResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetLightResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP SetLightRequest sent to 'device-01':

```javascript
setLightRequest {
  values {
    on: true
  }
}
```

OSLP SetLightResponse sent to platform:

```javascript
setLightResponse {
  status: OK
}
```

