# GetConfiguration

## Description

Request to fetch the current configuration of a device.

Response communicates if the request was executed. If 'status = OK' then the optional fields will be partly populated. Note that DaliConfiguration is only present for devices with 'lightType = DALI', which are of device type PSLD. Note that RelayConfiguration is only present for devices with 'lightType = RELAY \| ONE\_TO\_TEN\_VOLT \| ONE\_TO\_TEN\_VOLT\_REVERSE', which are of device type SSLD.

## Message definitions

```javascript
message GetConfigurationRequest {
    optional bool present = 1 [default = true];
}

message GetConfigurationResponse {
    required Status status = 1;
    optional LightType lightType = 2;
    optional DaliConfiguration daliConfiguration = 3;                                    // Contains specific configuration for DALI controllers.
    optional RelayConfiguration relayConfiguration = 4;                                  // Contains specific configuration for Relay.
    optional uint32 shortTermHistoryIntervalMinutes = 5; 
    optional LinkType preferredLinkType = 6;
    optional MeterType meterType = 7;
    optional uint32 longTermHistoryInterval = 8; 
    optional LongTermIntervalType longTermHistoryIntervalType = 9;
    optional uint32 timeSyncFrequency = 10 [default = 86400];                            // Time synch frequency (seconds).
    optional bytes deviceFixIpValue = 11; // [(nanopb).max_count = 4];                   // The fixed IP address of this device.
    optional bytes netMask = 12; // [(nanopb).max_count = 4];                            // Network mask for fixed IP address.
    optional bytes gateWay = 13; // [(nanopb).max_count = 4];                            // Gateway address for fixed IP address.
    optional bool isDhcpEnabled = 14 [default = true];                                   // Is DHCP enabled for this device?
    optional bool isTlsEnabled = 15;                                                     // Defines if TLS is enabled.
    optional uint32 oslpBindPortNumber = 16;                                             // The port used for TLS connections.
    optional string commonNameString = 17 [default = 'TLS Test']; //[default = 'TLS Test',(nanopb).max_count = 25]; // The common name (CN) used when isTlsEnabled equals true.
    optional uint32 communicationTimeout = 18 [default = 20];                            // Communication Timeouts (seconds) (wait for answer, socket establish, or server response = comm watchdog for local mode).
    optional uint32 communicationNumberOfRetries = 19 [default = 3];                     // Communication number of retries.
    optional uint32 communicationPauseTimeBetweenConnectionTrials = 20 [default = 60];   // Time between communication attempts.
    optional bytes ospgIpAddress = 21; // [(nanopb).max_count = 4];                      // The IP address of the platform.
    optional uint32 osgpPortNumber = 22;                                                 // The port number of the platform.
    optional bool isTestButtonEnabled = 23 [default = true];                             // Is the test button enabled for this device?
    optional bool isAutomaticSummerTimingEnabled = 24 [default = true];                  // Is the automatic summer timing enabled for this device?
    optional sint32 astroGateSunRiseOffset = 25 [default = 0];                           // The calculated sunrise time modified by this value. Time is moved earlier (if offset is negative) or later (if offset is positive). In seconds.
    optional sint32 astroGateSunSetOffset = 26 [default = 0];                            // The calculated sunset time modified by this value. Time is moved earlier (if offset is negative) or later (if offset is positive). In seconds.
    repeated uint32 switchingDelay = 27; // [(nanopb).max_count = 4];                    // Switching delay (seconds), array of 4 values. Default 0, 0, 0, 0.
    repeated RelayMatrix relayLinking = 28;                                              // Relay linking is a software linking, to may link each relay with each other relay. It is a matrix. Example, if relay 1 is linked with relay 3, if relay 1 will be switched (by OSGP or local by internal scheduler), the relay 3 will switch automatically (on or off, as it set) without new command.
    optional bool relayRefreshing = 29 [default = true];                                 // Is relayRefreshing enabled for this device? Set minutely the nominal relay state and status according to active schedule after power outage and missed switching or anti manipulation.
    optional string summerTimeDetails = 30 [default = '0360100']; //[default = '0360100',(nanopb).max_count = 7]; // The time point for DST for Europe is not identical in every country. It should be added as parameters the weekday, month and time point for DST/summer and winter.
    optional string winterTimeDetails = 31 [default = '1060200']; //[default = '1060200',(nanopb).max_count = 7]; // The time point for DST for Europe is not identical in every country. It should be added as parameters the weekday, month and time point for DST/summer and winter.
}
```

## Datatypes

```javascript
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

message RelayMatrix {
    required bytes masterRelayIndex = 1;  // [(nanopb).max_count = 1];
    required bool masterRelayOn = 2; // [(nanopb).max_count = 1];
    optional bytes indicesOfControlledRelaysOn = 3; // [(nanopb).max_count = 4];  // IndexNumber of output Relay to switch ON if Master Relay state changes as determined by masterRelayOn.
    optional bytes indicesOfControlledRelaysOff = 4; // [(nanopb).max_count = 4]; // IndexNumber of output Relay to switch OFF if Master Relay sate changes as determined by MasterRelayOff.
}
```

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:con="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>Kevin</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <con:GetConfigurationRequest>
         <con:DeviceIdentification>device-01</con:DeviceIdentification>
      </con:GetConfigurationRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetConfigurationAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20161007142028655</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetConfigurationAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:con="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>Kevin</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <con:GetConfigurationAsyncRequest>
         <con:AsyncRequest>
            <com:CorrelationUid>LianderNetManagement|||device-01|||20161007142028655</com:CorrelationUid>
            <com:DeviceId>device-01</com:DeviceId>
         </con:AsyncRequest>
      </con:GetConfigurationAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetConfigurationResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:Configuration>
            <ns2:LightType>RELAY</ns2:LightType>
            <ns2:RelayConfiguration>
               <ns2:RelayMap>
                  <ns2:Index>1</ns2:Index>
                  <ns2:Address>1</ns2:Address>
                  <ns2:RelayType>TARIFF</ns2:RelayType>
               </ns2:RelayMap>
               <ns2:RelayMap>
                  <ns2:Index>2</ns2:Index>
                  <ns2:Address>2</ns2:Address>
                  <ns2:RelayType>LIGHT</ns2:RelayType>
               </ns2:RelayMap>
               <ns2:RelayMap>
                  <ns2:Index>3</ns2:Index>
                  <ns2:Address>3</ns2:Address>
                  <ns2:RelayType>LIGHT</ns2:RelayType>
               </ns2:RelayMap>
               <ns2:RelayMap>
                  <ns2:Index>4</ns2:Index>
                  <ns2:Address>4</ns2:Address>
                  <ns2:RelayType>LIGHT</ns2:RelayType>
               </ns2:RelayMap>
            </ns2:RelayConfiguration>
            <ns2:PreferredLinkType>ETHERNET</ns2:PreferredLinkType>
            <ns2:TimeSyncFrequency>86400</ns2:TimeSyncFrequency>
            <ns2:DeviceFixedIp>
               <ns2:IpAddress>192.168.0.100</ns2:IpAddress>
               <ns2:NetMask>255.255.255.0</ns2:NetMask>
               <ns2:GateWay>192.168.0.1</ns2:GateWay>
            </ns2:DeviceFixedIp>
            <ns2:DhcpEnabled>false</ns2:DhcpEnabled>
            <ns2:TlsEnabled>true</ns2:TlsEnabled>
            <ns2:TlsPortNumber>1234</ns2:TlsPortNumber>
            <ns2:CommonNameString>TLS Test</ns2:CommonNameString>
            <ns2:CommunicationTimeout>30</ns2:CommunicationTimeout>
            <ns2:CommunicationNumberOfRetries>5</ns2:CommunicationNumberOfRetries>
            <ns2:CommunicationPauseTimeBetweenConnectionTrials>120</ns2:CommunicationPauseTimeBetweenConnectionTrials>
            <ns2:OsgpIpAddress>168.63.97.65</ns2:OsgpIpAddress>
            <ns2:OsgpPortNumber>12122</ns2:OsgpPortNumber>
            <ns2:TestButtonEnabled>false</ns2:TestButtonEnabled>
            <ns2:AutomaticSummerTimingEnabled>false</ns2:AutomaticSummerTimingEnabled>
            <ns2:AstroGateSunRiseOffset>-15</ns2:AstroGateSunRiseOffset>
            <ns2:AstroGateSunSetOffset>15</ns2:AstroGateSunSetOffset>
            <ns2:SwitchingDelays>1</ns2:SwitchingDelays>
            <ns2:SwitchingDelays>2</ns2:SwitchingDelays>
            <ns2:SwitchingDelays>3</ns2:SwitchingDelays>
            <ns2:SwitchingDelays>4</ns2:SwitchingDelays>
            <ns2:RelayLinking>
               <ns2:MasterRelayIndex>2</ns2:MasterRelayIndex>
               <ns2:MasterRelayOn>false</ns2:MasterRelayOn>
               <ns2:IndicesOfControlledRelaysOn>3</ns2:IndicesOfControlledRelaysOn>
               <ns2:IndicesOfControlledRelaysOn>4</ns2:IndicesOfControlledRelaysOn>
               <ns2:IndicesOfControlledRelaysOff>3</ns2:IndicesOfControlledRelaysOff>
               <ns2:IndicesOfControlledRelaysOff>4</ns2:IndicesOfControlledRelaysOff>
            </ns2:RelayLinking>
            <ns2:RelayRefreshing>false</ns2:RelayRefreshing>
            <ns2:SummerTimeDetails>2016-03-27T01:00:00.000+01:00</ns2:SummerTimeDetails>
            <ns2:WinterTimeDetails>2016-10-30T02:00:00.000+02:00</ns2:WinterTimeDetails>
         </ns2:Configuration>
      </ns2:GetConfigurationResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP GetConfigurationRequest message sent to 'device-01':

```javascript
getConfigurationRequest {
}
```

OSLP GetConfigurationResponse message sent to platform:

```javascript
getConfigurationResponse {
  status: OK
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
  meterType: MT_NOT_SET
  longTermHistoryInterval: 1
  longTermHistoryIntervalType: LT_INT_NOT_SET
  timeSyncFrequency: 86400
  deviceFixIpValue: "\300\250\000d"
  netMask: "\377\377\377\000"
  gateWay: "\300\250\000\001"
  isDhcpEnabled: false
  isTlsEnabled: true
  oslpBindPortNumber: 1234
  commonNameString: "TLS Test"
  communicationTimeout: 30
  communicationNumberOfRetries: 5
  communicationPauseTimeBetweenConnectionTrials: 120
  ospgIpAddress: "\250?aA"
  osgpPortNumber: 12122
  isTestButtonEnabled: false
  isAutomaticSummerTimingEnabled: false
  astroGateSunRiseOffset: -15
  astroGateSunSetOffset: 15
  switchingDelay: 1
  switchingDelay: 2
  switchingDelay: 3
  switchingDelay: 4
  relayLinking {
    masterRelayIndex: "\002"
    masterRelayOn: false
    indicesOfControlledRelaysOn: "\003\004"
    indicesOfControlledRelaysOff: "\003\004"
  }
  relayRefreshing: false
  summerTimeDetails: "0360100"
  winterTimeDetails: "1060200"
}
```

