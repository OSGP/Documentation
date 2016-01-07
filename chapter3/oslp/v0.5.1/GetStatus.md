## GetStatus messages

### Description

Request that requires the device to send the status of all relays, current network link and preferred network link, the type of configuration (PSLD vs SSLD), and the event notification mask which has been set.

Response which confirms the GetStatusRequest has been executed and returns the current status for all of the relays and other information or rejects the GetStatusRequest.

### Message definitions

``` json
message GetStatusRequest {
    optional bool present = 1 [default = true];
}

message GetStatusResponse {
    required Status status = 1;
    repeated LightValue value = 2; // [(nanopb).max_count = 6];
    required LinkType preferredLinktype = 3;
    required LinkType actualLinktype = 4;
    required LightType lightType = 5;
    required uint32 eventNotificationMask = 6; // Bitmask for max 32 events, using NotificationBit for bit positions.
}
```

### Datatypes

``` json
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}

message LightValue {
    optional bytes index = 1; // [(nanopb).max_size = 1]; // index number of connected light (DALI), none means all connected ligts.
    required bool on = 2;
    optional bytes dimValue = 3; // [(nanopb).max_size = 1]; // 1 - 100 %
}

enum LinkType {
    LINK_NOT_SET = 0;
    GPRS = 1;
    CDMA = 2;
    ETHERNET = 3;
}

enum LightType {
    LT_NOT_SET = 0;
    RELAY = 1;
    ONE_TO_TEN_VOLT = 2;
    ONE_TO_TEN_VOLT_REVERSE = 3;
    DALI = 4;
}
```

### Example

Soap requests and responses sent to and from platform:
``` xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.alliander.com/schemas/osp/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.alliander.com/schemas/osp/common">WEB_OWNER</ApplicationName>
      <UserName xmlns="http://www.alliander.com/schemas/osp/common">liander gebruiker</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetStatusRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:DeviceIdentification>device-01</ns2:DeviceIdentification>
      </ns2:GetStatusRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetStatusAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106133844686</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetStatusAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.alliander.com/schemas/osp/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.alliander.com/schemas/osp/common">WEB_OWNER</ApplicationName>
      <UserName xmlns="http://www.alliander.com/schemas/osp/common">liander gebruiker</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetStatusAsyncRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106133844686</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:GetStatusAsyncRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetStatusResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:DeviceStatus>
            <ns2:LightValues>
               <ns2:Index>1</ns2:Index>
               <ns2:On>true</ns2:On>
            </ns2:LightValues>
            <ns2:PreferredLinkType>ETHERNET</ns2:PreferredLinkType>
            <ns2:ActualLinkType>ETHERNET</ns2:ActualLinkType>
            <ns2:LightType>RELAY</ns2:LightType>
            <ns2:EventNotifications>DIAG_EVENTS</ns2:EventNotifications>
            <ns2:EventNotifications>HARDWARE_FAILURE</ns2:EventNotifications>
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

OSLP GetStatusRequest sent to 'device-01':
``` json
getStatusRequest {
}
```

OSLP GetStatusResponse sent to platform:
``` json
getStatusResponse {
  status: OK
  value {
    index: "\001"
    on: true
  }
  preferredLinktype: ETHERNET
  actualLinktype: ETHERNET
  lightType: RELAY
  eventNotificationMask: 255
}
```