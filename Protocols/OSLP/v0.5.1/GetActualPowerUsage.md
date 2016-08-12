## GetActualPowerUsage messages

### Description

Request to fetch current power usage data from the registers of the device.

Response contains status and the power usage data.

### Message definitions

``` json
message GetActualPowerUsageRequest {
    optional bool present = 1 [default = true];
}

message GetActualPowerUsageResponse {
    required Status status = 1;
    required PowerUsageData powerUsageData = 2;
}
```

### Datatypes

``` json
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}

message PowerUsageData {
    required string recordTime = 1; // [(nanopb).max_size = 15];    // Record time - format YYYYMMDDhhmmss UTC
    required MeterType meterType = 2;                               // Meter type (P1, Pulse, Aux)
    required uint64 totalConsumedEnergy = 3;                        // Electricity delivered to client (Tariff I + Tarrif II) in 0,001 kWh
    required uint32 actualConsumedPower = 4;                        // Actual Electricity power delivered in W
    optional PsldData psldData = 5;
    optional SsldData ssldData = 6;
}

enum MeterType {
    MT_NOT_SET = 0;
    P1 = 1;
    PULSE = 2;
    AUX = 3;
}

message PsldData {
    required uint32 totalLightingHours = 1;     // Total lighting hours
}

message SsldData {
    required uint32 actualCurrent1 = 1;             // Instantaneous current L1 in mA
    required uint32 actualCurrent2 = 2;             // Instantaneous current L2 in mA
    required uint32 actualCurrent3 = 3;             // Instantaneous current L3 in mA
    required uint32 actualPower1 = 4;               // Instantaneous active power L1 in W
    required uint32 actualPower2 = 5;               // Instantaneous active power L2 in W
    required uint32 actualPower3 = 6;               // Instantaneous active power L3 in W
    required uint32 averagePowerFactor1 = 7;        // Power factor L1 (in 1/2^32) in steps of 0.1, 10 equals a power factor of 1
    required uint32 averagePowerFactor2 = 8;        // Power factor L2 (in 1/2^32) in steps of 0.1, 10 equals a power factor of 1
    required uint32 averagePowerFactor3 = 9;        // Power factor L3 (in 1/2^32) in steps of 0.1, 10 equals a power factor of 1
    repeated RelayData relayData = 10;   // [(nanopb).max_count = 4]; // Measurement data per relay 
}

message RelayData {
    required bytes index = 1; // [(nanopb).max_size = 1]; // external index, for example 1
    required uint32 totalLightingMinutes = 2;       // Total lighting minutes for lighting relay
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
      <ns2:GetActualPowerUsageRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:DeviceIdentification>device-01</ns2:DeviceIdentification>
      </ns2:GetActualPowerUsageRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetActualPowerUsageAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106184845385</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetActualPowerUsageAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.alliander.com/schemas/osp/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.alliander.com/schemas/osp/common">WEB_OWNER</ApplicationName>
      <UserName xmlns="http://www.alliander.com/schemas/osp/common">liander gebruiker</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetActualPowerUsageAsyncRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106184845385</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:GetActualPowerUsageAsyncRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetActualPowerUsageResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:GetActualPowerUsageResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP GetActualPowerUsageRequest sent to 'device-01':
``` json
getActualPowerUsageRequest {
}
```

OSLP GetActualPowerUsageResponse sent to platform:
``` json
getActualPowerUsageResponse {
  status: OK
  powerUsageData {
    recordTime: "20160106184847"
    meterType: P1
    totalConsumedEnergy: 96
    actualConsumedPower: 48
    psldData {
      totalLightingHours: 144
    }
    ssldData {
      actualCurrent1: 1
      actualCurrent2: 2
      actualCurrent3: 3
      actualPower1: 1
      actualPower2: 2
      actualPower3: 3
      averagePowerFactor1: 1
      averagePowerFactor2: 2
      averagePowerFactor3: 3
      relayData {
        index: "\001"
        totalLightingMinutes: 480
      }
      relayData {
        index: "\002"
        totalLightingMinutes: 480
      }
      relayData {
        index: "\003"
        totalLightingMinutes: 480
      }
      relayData {
        index: "\004"
        totalLightingMinutes: 480
      }
    }
  }
}
```