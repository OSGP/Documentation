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
    optional bytes netMask = 11; // [(nanopb).max_count = 4];                            // Network mask for fixed IP address.
    optional bytes gateWay = 12; // [(nanopb).max_count = 4];                            // Gateway address for fixed IP address.
    optional bool isDhcpEnabled = 13 [default = true];                                   // Is DHCP enabled for this device?
    optional bool isTlsEnabled = 14;                                                     // Defines if TLS is enabled.
    optional uint32 oslpBindPortNumber = 15;                                             // The port used for TLS connections.
    optional string commonNameString = 16 [default = 'TLS Test']; //[default = 'TLS Test',(nanopb).max_count = 25]; // The common name (CN) used when isTlsEnabled equals true.
    optional uint32 communicationTimeout = 17 [default = 20];                            // Communication Timeouts (seconds) (wait for answer, socket establish, or server response = comm watchdog for local mode).
    optional uint32 communicationNumberOfRetries = 18 [default = 3];                     // Communication number of retries.
    optional uint32 communicationPauseTimeBetweenConnectionTrials = 19 [default = 60];   // Time between communication attempts.
    optional bytes ospgIpAddress = 20; // [(nanopb).max_count = 4];                      // The IP address of the platform.
    optional uint32 osgpPortNumber = 21;                                                 // The port number of the platform.
    optional bool isTestButtonEnabled = 22 [default = true];                             // Is the test button enabled for this device?
    optional bool isAutomaticSummerTimingEnabled = 23 [default = true];                  // Is the automatic summer timing enabled for this device?
    optional sint32 astroGateSunRiseOffset = 24 [default = 0];                           // The calculated sunrise time modified by this value. Time is moved earlier (if offset is negative) or later (if offset is positive). In seconds.
    optional sint32 astroGateSunSetOffset = 25 [default = 0];                            // The calculated sunset time modified by this value. Time is moved earlier (if offset is negative) or later (if offset is positive). In seconds.
    repeated uint32 switchingDelay = 26; // [(nanopb).max_count = 4];                    // Switching delay (seconds), array of 4 values. Default 0, 0, 0, 0.
    repeated RelayMatrix relayLinking = 27;                                              // Relay linking is a software linking, to may link each relay with each other relay. It is a matrix. Example, if relay 1 is linked with relay 3, if relay 1 will be switched (by OSGP or local by internal scheduler), the relay 3 will switch automatically (on or off, as it set) without new command.
    optional bool relayRefreshing = 28 [default = true];                                 // Is relayRefreshing enabled for this device? Set minutely the nominal relay state and status according to active schedule after power outage and missed switching or anti manipulation.
    optional string summerTimeDetails = 29 [default = '0360100']; //[default = '0360100',(nanopb).max_count = 7]; // The time point for DST for Europe is not identical in every country. It should be added as parameters the weekday, month and time point for DST/summer and winter.
    optional string winterTimeDetails = 30 [default = '1060200']; //[default = '1060200',(nanopb).max_count = 7]; // The time point for DST for Europe is not identical in every country. It should be added as parameters the weekday, month and time point for DST/summer and winter.
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
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:con="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>Kevin</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <con:SetConfigurationRequest>
         <!--type: Identification-->
         <con:DeviceIdentification>device-01</con:DeviceIdentification>
         <!--Optional:-->
         <con:Configuration>
            <!--Optional:-->
            <!--type: LightType - enumeration: [RELAY,ONE_TO_TEN_VOLT,ONE_TO_TEN_VOLT_REVERSE,DALI]-->
            <con:LightType>RELAY</con:LightType>
            <!--Optional:-->
            <con:RelayConfiguration>
               <!--0 to 6 repetitions:-->
               <con:RelayMap>
                  <!--anonymous type-->
                  <con:Index>1</con:Index>
                  <!--anonymous type-->
                  <con:Address>1</con:Address>
                  <!--type: RelayType - enumeration: [LIGHT,TARIFF,TARIFF_REVERSED]-->
                  <con:RelayType>TARIFF</con:RelayType>
               </con:RelayMap>
               <con:RelayMap>
                  <!--anonymous type-->
                  <con:Index>2</con:Index>
                  <!--anonymous type-->
                  <con:Address>2</con:Address>
                  <!--type: RelayType - enumeration: [LIGHT,TARIFF,TARIFF_REVERSED]-->
                  <con:RelayType>LIGHT</con:RelayType>
               </con:RelayMap>
               <con:RelayMap>
                  <!--anonymous type-->
                  <con:Index>3</con:Index>
                  <!--anonymous type-->
                  <con:Address>3</con:Address>
                  <!--type: RelayType - enumeration: [LIGHT,TARIFF,TARIFF_REVERSED]-->
                  <con:RelayType>LIGHT</con:RelayType>
               </con:RelayMap>
               <con:RelayMap>
                  <!--anonymous type-->
                  <con:Index>4</con:Index>
                  <!--anonymous type-->
                  <con:Address>4</con:Address>
                  <!--type: RelayType - enumeration: [LIGHT,TARIFF,TARIFF_REVERSED]-->
                  <con:RelayType>LIGHT</con:RelayType>
               </con:RelayMap>
            </con:RelayConfiguration>
            <!--Optional:-->
            <!--type: int-->
            <con:ShortTermHistoryIntervalMinutes>15</con:ShortTermHistoryIntervalMinutes>
            <!--Optional:-->
            <!--type: LinkType - enumeration: [GPRS,CDMA,ETHERNET]-->
            <con:PreferredLinkType>ETHERNET</con:PreferredLinkType>
            <!--Optional:-->
            <!--type: MeterType - enumeration: [P1,PULSE,AUX]-->
            <con:MeterType>PULSE</con:MeterType>
            <!--Optional:-->
            <!--type: int-->
            <con:LongTermHistoryInterval>1</con:LongTermHistoryInterval>
            <!--Optional:-->
            <!--type: LongTermIntervalType - enumeration: [DAYS,MONTHS]-->
            <con:LongTermHistoryIntervalType>DAYS</con:LongTermHistoryIntervalType>

            <con:TimeSyncFrequency>864000</con:TimeSyncFrequency>
            <con:DeviceFixedIp>
               <con:IpAddress>192.168.0.110</con:IpAddress>
               <con:NetMask>255.255.255.0</con:NetMask>
               <con:GateWay>192.168.0.1</con:GateWay>
            </con:DeviceFixedIp>
            <con:DhcpEnabled>false</con:DhcpEnabled>
            <con:TlsEnabled>false</con:TlsEnabled>
            <con:TlsPortNumber>1234</con:TlsPortNumber>
            <con:CommonNameString>TLS Test</con:CommonNameString>

            <con:CommunicationTimeout>15</con:CommunicationTimeout>
            <con:CommunicationNumberOfRetries>2</con:CommunicationNumberOfRetries>
            <con:CommunicationPauseTimeBetweenConnectionTrials>120</con:CommunicationPauseTimeBetweenConnectionTrials>
            <con:OsgpIpAddress>192.168.100.42</con:OsgpIpAddress>
            <con:OsgpPortNumber>12122</con:OsgpPortNumber>
            <con:TestButtonEnabled>false</con:TestButtonEnabled>
            <con:AutomaticSummerTimingEnabled>false</con:AutomaticSummerTimingEnabled>
            <con:AstroGateSunRiseOffset>-15</con:AstroGateSunRiseOffset>
            <con:AstroGateSunSetOffset>15</con:AstroGateSunSetOffset>
            
            <!-- List of SwitchingDelay type, one delay per relay, max 4 entries -->
            <con:SwitchingDelays>100</con:SwitchingDelays>
            <con:SwitchingDelays>200</con:SwitchingDelays>
            <con:SwitchingDelays>300</con:SwitchingDelays>
            <con:SwitchingDelays>400</con:SwitchingDelays>
            
            <!-- List of RelayMatrix type -->
            <con:RelayLinking>
                <con:MasterRelayIndex>1</con:MasterRelayIndex>
                <con:MasterRelayOn>true</con:MasterRelayOn>
                <!-- List of RelayMatrixIndex, max 4 entries containing a single index between 1 and 4 -->
                <con:IndicesOfControlledRelaysOn>1</con:IndicesOfControlledRelaysOn>
                <con:IndicesOfControlledRelaysOn>2</con:IndicesOfControlledRelaysOn>
                <con:IndicesOfControlledRelaysOn>3</con:IndicesOfControlledRelaysOn>
                <con:IndicesOfControlledRelaysOn>4</con:IndicesOfControlledRelaysOn>
                <!-- List of RelayMatrixIndex, max 4 entries containing a single index between 1 and 4 -->
                <con:IndicesOfControlledRelaysOff>1</con:IndicesOfControlledRelaysOff>
                <con:IndicesOfControlledRelaysOff>2</con:IndicesOfControlledRelaysOff>
                <con:IndicesOfControlledRelaysOff>3</con:IndicesOfControlledRelaysOff>
                <con:IndicesOfControlledRelaysOff>4</con:IndicesOfControlledRelaysOff>
            </con:RelayLinking>
            <con:RelayLinking>
                <con:MasterRelayIndex>2</con:MasterRelayIndex>
                <con:MasterRelayOn>true</con:MasterRelayOn>
                <!-- List of RelayMatrixIndex, max 4 entries containing a single index between 1 and 4 -->
                <con:IndicesOfControlledRelaysOn>3</con:IndicesOfControlledRelaysOn>
                <!-- List of RelayMatrixIndex, max 4 entries containing a single index between 1 and 4 -->
                <con:IndicesOfControlledRelaysOff>3</con:IndicesOfControlledRelaysOff>
            </con:RelayLinking>
            <con:RelayRefreshing>true</con:RelayRefreshing>
            <con:SummerTimeDetails>2016-03-27T01:00:00.000+01:00</con:SummerTimeDetails>
            <con:WinterTimeDetails>2016-10-30T02:00:00.000+02:00</con:WinterTimeDetails>
            
         </con:Configuration>
         <!--Optional:-->
         <!--type: timestamp-->
         <!--<con:scheduled_time>2015-01-04T15:49:59Z</con:scheduled_time>-->

      </con:SetConfigurationRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetConfigurationAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20161007141853727</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetConfigurationAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:con="http://www.alliander.com/schemas/osgp/configurationmanagement/2014/10">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>Kevin</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <con:SetConfigurationAsyncRequest>
         <con:AsyncRequest>
            <com:CorrelationUid>LianderNetManagement|||device-01|||20161007141521031</com:CorrelationUid>
            <com:DeviceId>device-01</com:DeviceId>
         </con:AsyncRequest>
      </con:SetConfigurationAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
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
      relayType: TARIFF
    }
    addressMap {
      index: "\002"
      address: "\002"
      relayType: LIGHT
    }
    addressMap {
      index: "\003"
      address: "\003"
      relayType: LIGHT
    }
    addressMap {
      index: "\004"
      address: "\004"
      relayType: LIGHT
    }
  }
  shortTermHistoryIntervalMinutes: 15
  preferredLinkType: ETHERNET
  meterType: PULSE
  longTermHistoryInterval: 1
  longTermHistoryIntervalType: DAYS
  timeSyncFrequency: 864000
  deviceFixIpValue: "\300\250\000n"
  netMask: "\377\377\377\000"
  gateWay: "\300\250\000\001"
  isDhcpEnabled: false
  isTlsEnabled: false
  oslpBindPortNumber: 1234
  commonNameString: "TLS Test"
  communicationTimeout: 15
  communicationNumberOfRetries: 2
  communicationPauseTimeBetweenConnectionTrials: 120
  ospgIpAddress: "\300\250d*"
  osgpPortNumber: 12122
  isTestButtonEnabled: false
  isAutomaticSummerTimingEnabled: false
  astroGateSunRiseOffset: -15
  astroGateSunSetOffset: 15
  switchingDelay: 100
  switchingDelay: 200
  switchingDelay: 300
  switchingDelay: 400
  relayLinking {
    masterRelayIndex: "\001"
    masterRelayOn: true
    indicesOfControlledRelaysOn: "\001\002\003\004"
    indicesOfControlledRelaysOff: "\001\002\003\004"
  }
  relayLinking {
    masterRelayIndex: "\002"
    masterRelayOn: true
    indicesOfControlledRelaysOn: "\003"
    indicesOfControlledRelaysOff: "\003"
  }
  relayRefreshing: true
  summerTimeDetails: "0360100"
  winterTimeDetails: "1060200"
}
```

OSLP SetConfigurationResponse sent to platform:
``` json
setConfigurationResponse {
  status: OK
}
```
