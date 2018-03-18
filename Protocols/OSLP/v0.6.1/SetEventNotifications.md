## SetEventNotifications messages

### Description

Request which contains the EventNotification mask.

Response communicates status.

### Message definitions

``` json
message SetEventNotificationsRequest {
    required uint32 NotificationMask = 1; // Bitmask for max 32 events, using NotificationBit for bit positions.
}

message SetEventNotificationsResponse {
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
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:dev="http://www.alliander.com/schemas/osgp/devicemanagement/2014/10">
   <soapenv:Header>
   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
   <com:UserName>liander gebruiker</com:UserName>
   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <dev:SetEventNotificationsRequest>
         <!--type: Identification-->
         <dev:DeviceIdentification>device-01</dev:DeviceIdentification>
         <dev:EventNotifications>DIAG_EVENTS</dev:EventNotifications>
         <dev:EventNotifications>HARDWARE_FAILURE</dev:EventNotifications>
         <dev:EventNotifications>LIGHT_EVENTS</dev:EventNotifications>
         <dev:EventNotifications>TARIFF_EVENTS</dev:EventNotifications>
         <dev:EventNotifications>MONITOR_EVENTS</dev:EventNotifications>
         <dev:EventNotifications>FIRMWARE_EVENTS</dev:EventNotifications>
         <dev:EventNotifications>COMM_EVENTS</dev:EventNotifications>
         <dev:EventNotifications>SECURITY_EVENTS</dev:EventNotifications>
      </dev:SetEventNotificationsRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetEventNotificationsAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/devicemanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160104145052565</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetEventNotificationsAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:dev="http://www.alliander.com/schemas/osgp/devicemanagement/2014/10">
   <soapenv:Header>
   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
   <com:UserName>liander gebruiker</com:UserName>
   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <dev:SetEventNotificationsAsyncRequest>
         <dev:AsyncRequest>
            <!--type: CorrelationUid-->
            <com:CorrelationUid>LianderNetManagement|||device-01|||20160104145052565</com:CorrelationUid>
            <!--type: Identification-->
            <com:DeviceId>device-01</com:DeviceId>
         </dev:AsyncRequest>
      </dev:SetEventNotificationsAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetEventNotificationsResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/devicemanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetEventNotificationsResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP SetEventNotificationsRequest sent to 'device-01' to set EventNotifications:
``` json
setEventNotificationsRequest {
  NotificationMask: 255
}
```

OSLP SetEventNotificationsResponse sent to platform:
``` json
setEventNotificationsResponse {
  status: OK
}
```