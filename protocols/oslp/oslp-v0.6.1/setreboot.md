# SetReboot

## Description

Request which notifies the device to reboot immediately. After a reboot, the device will switch its relays according to its schedule. Any ad hoc changes to relays will be lost.

Response communicates status.

## Message definitions

```javascript
message SetRebootRequest {
    optional bool present = 1 [default = true];
}

message SetRebootResponse {
    required Status status = 1;
}
```

## Data types

```javascript
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/adhocmanagement/2014/10" xmlns:com="http://www.opensmartgridplatform.org/schemas/common" xmlns:adh="http://www.opensmartgridplatform.org/schemas/adhocmanagement">
   <soapenv:Header>
       <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
       <com:UserName>liander gebruiker</com:UserName>
       <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetRebootRequest>
         <!--type: Identification-->
         <ns1:DeviceIdentification>device-01</ns1:DeviceIdentification>
      </ns1:SetRebootRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns3:SetRebootAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/adhocmanagement/2014/10">
         <ns3:AsyncResponse>
            <ns2:CorrelationUid>LianderNetManagement|||device-01|||20160104153201024</ns2:CorrelationUid>
            <ns2:DeviceId>device-01</ns2:DeviceId>
         </ns3:AsyncResponse>
      </ns3:SetRebootAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/adhocmanagement/2014/10" xmlns:com="http://www.opensmartgridplatform.org/schemas/common" xmlns:adh="http://www.opensmartgridplatform.org/schemas/adhocmanagement">
   <soapenv:Header>
   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
   <com:UserName>liander gebruiker</com:UserName>
   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetRebootAsyncRequest>
         <ns1:AsyncRequest>
            <!--type: CorrelationUid-->
            <ns:CorrelationUid>LianderNetManagement|||device-01|||20160104153201024</ns:CorrelationUid>
            <!--type: Identification-->
            <ns:DeviceId>device-01</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetRebootAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns3:SetRebootResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/adhocmanagement/2014/10">
         <ns3:Result>OK</ns3:Result>
      </ns3:SetRebootResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP SetRebootRequest message sent to 'device-01':

```javascript
setRebootRequest {
}
```

OSLP SetRebootResponse sent to platform:

```javascript
setRebootResponse {
  status: OK
}
```

