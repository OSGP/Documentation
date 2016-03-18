## SetConfiguration messages

### Description

Request to push configuration settings to a device.

Response communicates status.

### Message definitions

``` json
message SetConfigurationRequest {
    optional LightType lightType = 1;
    optional DaliConfiguration daliConfiguration = 2;                                    // Contains specific configuration for DALI controllers.
    optional RelayConfiguration relayConfiguration = 3;                                  // Contains specific configuration for Relay.
    optional uint32 shortTermHistoryIntervalMinutes = 4; 
    optional LinkType preferredLinkType = 5;
    optional MeterType meterType = 6;
    optional uint32 longTermHistoryInterval = 7; 
    optional LongTermIntervalType longTermHistoryIntervalType = 8;
    optional uint32 timeSyncFrequency = 9 [default = 86400];                             // Time synch frequency (seconds).
    optional bytes deviceFixIpValue = 10; // [(nanopb).max_count = 4];                   // The fixed IP address of this device.
    optional bool isDhcpEnabled = 11 [default = true];                                   // Is DHCP enabled for this device?
    optional uint32 communicationTimeout = 12 [default = 20];                            // Communication Timeouts (seconds) (wait for answer, socket establish, or server response = comm watchdog for local mode).
    optional uint32 communicationNumberOfRetries = 13 [default = 3];                     // Communication number of retries.
    optional uint32 communicationPauseTimeBetweenConnectionTrials = 14 [default = 60];   // Time between communication attempts.
    optional bytes ospgIpAddress = 15; // [(nanopb).max_count = 4];                      // The IP address of the platform.
    optional uint32 osgpPortNumber = 16;                                                 // The port number of the platform.
    optional bool isTestButtonEnabled = 17 [default = true];                             // Is the test button enabled for this device?
    optional bool isAutomaticSummerTimingEnabled = 18 [default = true];                  // Is the automatic summer timing enabled for this device?
    optional sint32 astroGateSunRiseOffset = 19 [default = 0];                           // The calculated sunrise time modified by this value. Time is moved earlier (if offset is negative) or later (if offset is positive). In seconds.
    optional sint32 astroGateSunSetOffset = 20 [default = 0];                            // The calculated sunset time modified by this value. Time is moved earlier (if offset is negative) or later (if offset is positive). In seconds.
    repeated uint32 switchingDelay = 21; // [(nanopb).max_count = 4];                    // Switching delay (seconds), array of 4 values. Default 0, 0, 0, 0.
    repeated RelayMatrix relayLinking = 22;                                              // Relay linking is a software linking, to may link each relay with each other relay. It is a matrix. Example, if relay 1 is linked with relay 3, if relay 1 will be switched (by OSGP or local by internal scheduler), the relay 3 will switch automatically (on or off, as it set) without new command.
    optional bool relayRefreshing = 23 [default = true];                                 // Is relayRefreshing enabled for this device? Set minutely the nominal relay state and status according to active schedule after power outage and missed switching or anti manipulation.
    optional string summerTimeDetails = 24 [default = '0360100']; //[default = '0360100',(nanopb).max_count = 7]; // The time point for DST for Europe is not identical in every country. It should be added as parameters the weekday, month and time point for DST/summer and winter.
    optional string winterTimeDetails = 25 [default = '1060200']; //[default = '1060200',(nanopb).max_count = 7]; // The time point for DST for Europe is not identical in every country. It should be added as parameters the weekday, month and time point for DST/summer and winter.
}
// summerTimeDetails string, winterTimeDetails:
//MMWHHmi
//
//where: (note, north hemisphere summer begins at the end of march)
//MM: month
//W:  day of the week (0- Monday, 6- Sunday)
//HH: hour of the changing time
//mi: minutes of the changing time

message SetConfigurationResponse {
    required Status status = 1;
}

```

### Datatypes

``` json
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

message RelayMatrix {
    required bytes masterRelayIndex = 1;  // [(nanopb).max_count = 1];
    required bool masterRelayOn = 2; // [(nanopb).max_count = 1];
    optional bytes indicesOfControlledRelaysOn = 3; // [(nanopb).max_count = 4];  // IndexNumber of output Relay to switch ON if Master Relay state changes as determined by masterRelayOn.
    optional bytes indicesOfControlledRelaysOff = 4; // [(nanopb).max_count = 4]; // IndexNumber of output Relay to switch OFF if Master Relay sate changes as determined by MasterRelayOff.
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
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:ns1="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:com="http://www.alliander.com/schemas/osgp/common" xmlns:con="http://www.alliander.com/schemas/osgp/configurationmanagement">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetConfigurationRequest>
         <ns1:DeviceIdentification>device-01</ns1:DeviceIdentification>
         <!--Optional:-->
         <ns1:Configuration>
            <!--Optional:-->
            <ns1:LightType>RELAY</ns1:LightType>
            <!--Optional: DaliConfiguration-->
            <!--Optional:-->
            <ns1:RelayConfiguration>
               <!--0 to 6 repetitions:-->
               <ns1:RelayMap>
                  <ns1:Index>1</ns1:Index>
                  <ns1:Address>1</ns1:Address>
                  <ns1:RelayType>LIGHT</ns1:RelayType>
                  <!--Optional:-->
                  <ns1:alias>Lights on all night.</ns1:alias>
               </ns1:RelayMap>
               <ns1:RelayMap>
                  <ns1:Index>2</ns1:Index>
                  <ns1:Address>2</ns1:Address>
                  <ns1:RelayType>LIGHT</ns1:RelayType>
                  <!--Optional:-->
                  <ns1:alias>Lights on during the evening and morning.</ns1:alias>
               </ns1:RelayMap>
               <ns1:RelayMap>
                  <ns1:Index>3</ns1:Index>
                  <ns1:Address>3</ns1:Address>
                  <ns1:RelayType>TARIFF</ns1:RelayType>
                  <!--Optional:-->
                  <ns1:alias>Low tariff from 23:00 until 07:00.</ns1:alias>
               </ns1:RelayMap>
            </ns1:RelayConfiguration>
            <!--Optional:-->
            <ns1:ShortTermHistoryIntervalMinutes>15</ns1:ShortTermHistoryIntervalMinutes>
            <!--Optional:-->
            <ns1:PreferredLinkType>CDMA</ns1:PreferredLinkType>
            <!--Optional:-->
            <!--<ns1:MeterType>MT_NOT_SET</ns1:MeterType>-->
            <!--Optional:-->
            <ns1:LongTermHistoryInterval>1</ns1:LongTermHistoryInterval>
            <!--Optional:-->
            <ns1:LongTermHistoryIntervalType>DAYS</ns1:LongTermHistoryIntervalType>
            <!--Optional:-->
            <ns1:TimeSyncFrequency>86400</ns1:TimeSyncFrequency>
            <!--Optional:-->
            <ns1:DeviceFixIpValue>127.0.0.1</ns1:DeviceFixIpValue>
            <!--Optional:-->
            <ns1:IsDhcpEnabled>true</ns1:IsDhcpEnabled>
            <!--Optional:-->
            <ns1:CommunicationTimeout>30</ns1:CommunicationTimeout>
            <!--Optional:-->
            <ns1:CommunicationNumberOfRetries>3</ns1:CommunicationNumberOfRetries>
            <!--Optional:-->
            <ns1:CommunicationPauseTimeBetweenConnectionTrials>60</ns1:CommunicationPauseTimeBetweenConnectionTrials>
            <!--Optional:-->
            <ns1:OspgIpAddress>168.63.97.65</ns1:OspgIpAddress>
            <!--Optional:-->
            <ns1:OsgpPortNumber>12122</ns1:OsgpPortNumber>
            <!--Optional:-->
            <ns1:IsTestButtonEnabled>true</ns1:IsTestButtonEnabled>
            <!--Optional:-->
            <ns1:IsAutomaticSummerTimingEnabled>true</ns1:IsAutomaticSummerTimingEnabled>
            <!--Optional:-->
            <ns1:AstroGateSunRiseOffset>-30</ns1:AstroGateSunRiseOffset>
            <!--Optional:-->
            <ns1:AstroGateSunSetOffset>30</ns1:AstroGateSunSetOffset>
            <!--0 to 4 repetitions:-->
            <ns1:SwitchingDelays>100</ns1:SwitchingDelays>
            <ns1:SwitchingDelays>200</ns1:SwitchingDelays>
            <ns1:SwitchingDelays>300</ns1:SwitchingDelays>
            <ns1:SwitchingDelays>400</ns1:SwitchingDelays>
            <!--Zero or more repetitions:-->
            <ns1:RelayLinking>
               <ns1:MasterRelayIndex>1</ns1:MasterRelayIndex>
               <ns1:MasterRelayOn>false</ns1:MasterRelayOn>
               <!--0 to 4 repetitions:-->
               <ns1:IndicesOfControlledRelaysOff>2</ns1:IndicesOfControlledRelaysOff>
            </ns1:RelayLinking>
            <!--Optional:-->
            <ns1:RelayRefreshing>true</ns1:RelayRefreshing>
            <!--Optional:-->
            <ns1:SummerTimeDetails>2016-03-27T01:00:00.000+01:00</ns1:SummerTimeDetails>
            <!--Optional:-->
            <ns1:WinterTimeDetails>2016-10-30T02:00:00.000+02:00</ns1:WinterTimeDetails>
         </ns1:Configuration>
         <!--Optional:-->
         <!--<ns1:scheduled_time>?</ns1:scheduled_time>-->
      </ns1:SetConfigurationRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:SetConfigurationAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106183638291</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetConfigurationAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.alliander.com/schemas/osp/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.alliander.com/schemas/osp/common">SoapUI</ApplicationName>
      <UserName xmlns="http://www.alliander.com/schemas/osp/common">Kevin</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:SetConfigurationAsyncRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106183638291</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:SetConfigurationAsyncRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:SetConfigurationResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetConfigurationResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP SetConfigurationRequest sent to 'device-01':
``` json
setConfigurationRequest {
  lightType: RELAY
  relayConfiguration {
    addressMap {
      index: "\001"
      address: "\001"
      relayType: LIGHT
    }
    addressMap {
      index: "\002"
      address: "\002"
      relayType: LIGHT
    }
    addressMap {
      index: "\003"
      address: "\003"
      relayType: TARIFF
    }
  }
  shortTermHistoryIntervalMinutes: 15
  preferredLinkType: CDMA
  longTermHistoryInterval: 1
  longTermHistoryIntervalType: DAYS
  timeSyncFrequency: 86400
  deviceFixIpValue: \000\000\001"
  isDhcpEnabled: true
  communicationTimeout: 30
  communicationNumberOfRetries: 3
  communicationPauseTimeBetweenConnectionTrials: 60
  ospgIpAddress: "\250?aA"
  osgpPortNumber: 12122
  isTestButtonEnabled: true
  isAutomaticSummerTimingEnabled: true
  astroGateSunRiseOffset: -30
  astroGateSunSetOffset: 30
  switchingDelay: 100
  switchingDelay: 200
  switchingDelay: 300
  switchingDelay: 400
  relayLinking {
    masterRelayIndex: "\001"
    masterRelayOn: false
    indicesOfControlledRelaysOn: ""
    indicesOfControlledRelaysOff: "\002"
  }
  relayRefreshing: true
  summerTimeDetails: "0360000"
  winterTimeDetails: "1060000"
}
```

OSLP SetConfigurationResponse sent to platform:
``` json
setConfigurationResponse {
  status: OK
}
```
