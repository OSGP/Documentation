## GetPowerUsageHistory messages

### Description

Request to fetch current power usage data from the registers of the device.

Response contains status and the power usage data.

### Message definitions

``` json
message GetPowerUsageHistoryRequest {
    required TimePeriod timePeriod = 1;
    optional uint32 page = 2;
    required HistoryTermType termType = 3;
}

message GetPowerUsageHistoryResponse {
    required Status status = 1;
    repeated PowerUsageData powerUsageData = 2; // [(nanopb).max_count = 20]; 
    optional PageInfo pageInfo = 3;
}
```

### Datatypes

``` json
message TimePeriod {
    required string startTime = 1; // [(nanopb).max_size = 15];     // - format YYYYMMDDhhmmss UTC
    required string endTime = 2; // [(nanopb).max_size = 15];   // - format YYYYMMDDhhmmss UTC
}

enum HistoryTermType {
    Short = 0;
    Long = 1;
}

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

message PageInfo {
    required uint32 currentPage = 1; // Pages start from 1
    required uint32 pageSize = 2;
    required uint32 totalPages = 3;
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
      <ns2:GetPowerUsageHistoryRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:DeviceIdentification>device-01</ns2:DeviceIdentification>
         <ns2:TimePeriod>
            <ns2:StartTime>2016-01-04T00:00:00.000+01:00</ns2:StartTime>
            <ns2:EndTime>2016-01-05T00:00:00.000+01:00</ns2:EndTime>
         </ns2:TimePeriod>
         <ns2:HistoryTermType>SHORT</ns2:HistoryTermType>
      </ns2:GetPowerUsageHistoryRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetPowerUsageHistoryAsyncResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106185428497</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetPowerUsageHistoryAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.alliander.com/schemas/osp/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.alliander.com/schemas/osp/common">WEB_OWNER</ApplicationName>
      <UserName xmlns="http://www.alliander.com/schemas/osp/common">liander gebruiker</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetPowerUsageHistoryAsyncRequest xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106185428497</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:GetPowerUsageHistoryAsyncRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetPowerUsageHistoryResponse xmlns:ns2="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.alliander.com/schemas/osgp/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T22:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>55229</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2370</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7110</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>99897</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>99897</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>99897</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>99897</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T21:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>52868</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2360</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7080</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>99219</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>99219</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>99219</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>99219</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T20:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>50408</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2391</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7173</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>98603</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>98603</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>98603</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>98603</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T19:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>48017</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2390</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7170</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>98030</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>98030</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>98030</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>98030</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T18:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>45612</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2387</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7161</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>97408</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>97408</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>97408</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>97408</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T17:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>43214</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2397</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7191</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>96866</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>96866</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>96866</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>96866</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T16:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>40843</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2356</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7068</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>96239</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>96239</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>96239</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>96239</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T15:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>38454</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2388</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7164</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>95656</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>95656</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>95656</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>95656</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T14:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>36001</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2398</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7194</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>95029</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>95029</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>95029</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>95029</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T13:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>33612</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2388</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7164</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>94475</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>94475</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>94475</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>94475</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T12:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>31207</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2392</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7176</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>93871</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>93871</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>93871</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>93871</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T11:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>28842</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2364</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7092</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>93232</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>93232</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>93232</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>93232</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T10:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>26425</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2374</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7122</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>92662</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>92662</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>92662</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>92662</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T09:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>24028</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2396</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7188</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>92067</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>92067</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>92067</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>92067</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T08:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>21634</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2365</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7095</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>91472</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>91472</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>91472</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>91472</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T07:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>19254</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2379</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7137</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>90858</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>90858</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>90858</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>90858</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T06:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>16837</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2362</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7086</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>90219</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>90219</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>90219</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>90219</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T05:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>14472</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2364</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7092</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>89674</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>89674</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>89674</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>89674</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T04:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>12011</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2388</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7164</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>89009</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>89009</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>89009</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>89009</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T03:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>9654</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2356</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7068</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>88433</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>88433</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>88433</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>88433</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T02:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>7216</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2383</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7149</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>87893</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>87893</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>87893</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>87893</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T01:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>4833</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2382</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7146</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>87280</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>87280</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>87280</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>87280</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-04T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>2410</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2389</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7167</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>86613</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>86613</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>86613</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>86613</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2016-01-03T23:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>P1</ns2:MeterType>
            <ns2:TotalConsumedEnergy>13</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>2396</ns2:ActualConsumedPower>
            <ns2:PsldData>
               <ns2:TotalLightingHours>7188</ns2:TotalLightingHours>
            </ns2:PsldData>
            <ns2:SsldData>
               <ns2:actualCurrent1>10</ns2:actualCurrent1>
               <ns2:actualCurrent2>20</ns2:actualCurrent2>
               <ns2:actualCurrent3>30</ns2:actualCurrent3>
               <ns2:actualPower1>10</ns2:actualPower1>
               <ns2:actualPower2>20</ns2:actualPower2>
               <ns2:actualPower3>30</ns2:actualPower3>
               <ns2:averagePowerFactor1>10</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>20</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>30</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>1</ns2:index>
                  <ns2:totalLightingMinutes>86018</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>86018</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>86018</ns2:totalLightingMinutes>
               </ns2:relayData>
               <ns2:relayData>
                  <ns2:index>4</ns2:index>
                  <ns2:totalLightingMinutes>86018</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
      </ns2:GetPowerUsageHistoryResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP GetPowerUsageHistoryRequest sent to 'device-01':
``` json
getPowerUsageHistoryRequest {
  timePeriod {
    startTime: "20160103230000"
    endTime: "20160104230000"
  }
  page: 1
  termType: Short
}

pages 2 to 11 have been skipped ...

getPowerUsageHistoryRequest {
  timePeriod {
    startTime: "20160103230000"
    endTime: "20160104230000"
  }
  page: 12
  termType: Short
}
```

OSLP GetPowerUsageHistoryResponse sent to platform:
``` json
getPowerUsageHistoryResponse {
  status: OK
  powerUsageData {
    recordTime: "20160104220000"
    meterType: P1
    totalConsumedEnergy: 55229
    actualConsumedPower: 2370
    psldData {
      totalLightingHours: 7110
    }
    ssldData {
      actualCurrent1: 10
      actualCurrent2: 20
      actualCurrent3: 30
      actualPower1: 10
      actualPower2: 20
      actualPower3: 30
      averagePowerFactor1: 10
      averagePowerFactor2: 20
      averagePowerFactor3: 30
      relayData {
        index: "\001"
        totalLightingMinutes: 99897
      }
      relayData {
        index: "\002"
        totalLightingMinutes: 99897
      }
      relayData {
        index: "\003"
        totalLightingMinutes: 99897
      }
      relayData {
        index: "\004"
        totalLightingMinutes: 99897
      }
    }
  }
  powerUsageData {
    recordTime: "20160104210000"
    meterType: P1
    totalConsumedEnergy: 52868
    actualConsumedPower: 2360
    psldData {
      totalLightingHours: 7080
    }
    ssldData {
      actualCurrent1: 10
      actualCurrent2: 20
      actualCurrent3: 30
      actualPower1: 10
      actualPower2: 20
      actualPower3: 30
      averagePowerFactor1: 10
      averagePowerFactor2: 20
      averagePowerFactor3: 30
      relayData {
        index: "\001"
        totalLightingMinutes: 99219
      }
      relayData {
        index: "\002"
        totalLightingMinutes: 99219
      }
      relayData {
        index: "\003"
        totalLightingMinutes: 99219
      }
      relayData {
        index: "\004"
        totalLightingMinutes: 99219
      }
    }
  }
  pageInfo {
    currentPage: 1
    pageSize: 2
    totalPages: 12
  }
}

pages 2 to 11 have been skipped ...

getPowerUsageHistoryResponse {
  status: OK
  powerUsageData {
    recordTime: "20160104000000"
    meterType: P1
    totalConsumedEnergy: 2410
    actualConsumedPower: 2389
    psldData {
      totalLightingHours: 7167
    }
    ssldData {
      actualCurrent1: 10
      actualCurrent2: 20
      actualCurrent3: 30
      actualPower1: 10
      actualPower2: 20
      actualPower3: 30
      averagePowerFactor1: 10
      averagePowerFactor2: 20
      averagePowerFactor3: 30
      relayData {
        index: "\001"
        totalLightingMinutes: 86613
      }
      relayData {
        index: "\002"
        totalLightingMinutes: 86613
      }
      relayData {
        index: "\003"
        totalLightingMinutes: 86613
      }
      relayData {
        index: "\004"
        totalLightingMinutes: 86613
      }
    }
  }
  powerUsageData {
    recordTime: "20160103230000"
    meterType: P1
    totalConsumedEnergy: 13
    actualConsumedPower: 2396
    psldData {
      totalLightingHours: 7188
    }
    ssldData {
      actualCurrent1: 10
      actualCurrent2: 20
      actualCurrent3: 30
      actualPower1: 10
      actualPower2: 20
      actualPower3: 30
      averagePowerFactor1: 10
      averagePowerFactor2: 20
      averagePowerFactor3: 30
      relayData {
        index: "\001"
        totalLightingMinutes: 86018
      }
      relayData {
        index: "\002"
        totalLightingMinutes: 86018
      }
      relayData {
        index: "\003"
        totalLightingMinutes: 86018
      }
      relayData {
        index: "\004"
        totalLightingMinutes: 86018
      }
    }
  }
  pageInfo {
    currentPage: 12
    pageSize: 2
    totalPages: 12
  }
}
```