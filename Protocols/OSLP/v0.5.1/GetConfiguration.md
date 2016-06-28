## GetConfiguration messages

### Description

Request to fetch the current configuration of a device.

Response communicates if the request was executed. If 'status = OK' then the optional fields will be partly populated.
Note that DaliConfiguration is only present for devices with 'lightType = DALI', which are of device type PSLD.
Note that RelayConfiguration is only present for devices with 'lightType = RELAY | ONE_TO_TEN_VOLT | ONE_TO_TEN_VOLT_REVERSE', which are of device type SSLD.

### Message definitions

``` json
message GetConfigurationRequest {
    optional bool present = 1 [default = true];
}

message GetConfigurationResponse {
    required Status status = 1;
    optional LightType lightType = 2;
    optional DaliConfiguration daliConfiguration = 3; // contains specific configuration for DALI controllers
    optional RelayConfiguration relayConfiguration = 4; // contains specific configuration for Relay
    optional uint32 shortTermHistoryIntervalMinutes = 5; 
    optional LinkType preferredLinkType = 6;
    optional MeterType meterType = 7;
    optional uint32 longTermHistoryInterval = 8; 
    optional LongTermIntervalType longTermHistoryIntervalType = 9; 
}
```

### Datatypes

``` json
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}

enum LightType {
    LT_NOT_SET = 0;
    RELAY = 1;
    ONE_TO_TEN_VOLT = 2;
    ONE_TO_TEN_VOLT_REVERSE = 3;
    DALI = 4;
}

message DaliConfiguration {
    optional bytes numberOfLights = 1; // [(nanopb).max_size = 1]; // number of lights connected to DALI controller
    repeated IndexAddressMap addressMap = 2; // [(nanopb).max_count = 4];
}

message RelayConfiguration {
    repeated IndexAddressMap addressMap = 1; // [(nanopb).max_count = 6];
}

message IndexAddressMap {
    required bytes index = 1; // [(nanopb).max_size = 1]; // external index, for example 1
    required bytes address = 2; // [(nanopb).max_size = 1]; // internal address, for example 2
    required RelayType relayType = 3;
}

enum RelayType {
    RT_NOT_SET = 0;
    LIGHT = 1;
    TARIFF = 2;
}

enum LinkType {
    LINK_NOT_SET = 0;
    GPRS = 1;
    CDMA = 2;
    ETHERNET = 3;
}

enum MeterType {
    MT_NOT_SET = 0;
    P1 = 1;
    PULSE = 2;
    AUX = 3;
}

enum LongTermIntervalType {
    LT_INT_NOT_SET = 0;
    DAYS = 1;
    MONTHS = 2;
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
      <ns2:GetConfigurationRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:DeviceIdentification>device-01</ns2:DeviceIdentification>
      </ns2:GetConfigurationRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetConfigurationAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106142402254</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetConfigurationAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.alliander.com/schemas/osp/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.alliander.com/schemas/osp/common">WEB_OWNER</ApplicationName>
      <UserName xmlns="http://www.alliander.com/schemas/osp/common">liander gebruiker</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetConfigurationAsyncRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106142402254</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:GetConfigurationAsyncRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetConfigurationResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:Configuration>
            <ns2:LightType>RELAY</ns2:LightType>
            <ns2:RelayConfiguration>
               <ns2:RelayMap>
                  <ns2:Index>1</ns2:Index>
                  <ns2:Address>1</ns2:Address>
                  <ns2:RelayType>LIGHT</ns2:RelayType>
               </ns2:RelayMap>
            </ns2:RelayConfiguration>
            <ns2:ShortTermHistoryIntervalMinutes>15</ns2:ShortTermHistoryIntervalMinutes>
            <ns2:PreferredLinkType>ETHERNET</ns2:PreferredLinkType>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:LongTermHistoryInterval>1</ns2:LongTermHistoryInterval>
            <ns2:LongTermHistoryIntervalType>DAYS</ns2:LongTermHistoryIntervalType>
         </ns2:Configuration>
      </ns2:GetConfigurationResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP GetConfigurationRequest message sent to 'device-01':
``` json
getConfigurationRequest {
}
```

OSLP GetConfigurationResponse message sent to platform:
``` json
getConfigurationResponse {
  status: OK
  lightType: RELAY
  relayConfiguration {
    addressMap {
      index: "\001"
      address: "\001"
      relayType: LIGHT
    }
  }
  shortTermHistoryIntervalMinutes: 15
  preferredLinkType: ETHERNET
  meterType: P1
  longTermHistoryInterval: 1
  longTermHistoryIntervalType: DAYS
}
```