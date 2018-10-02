## GetPowerUsageHistory messages

### Description

Request to fetch the power usage data from the registers of the device.

Response contains status and the power usage data, for the requested time period.

### IEC61850 Fields

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|**DESCRIPTION**|
|---|---|---|---|---|
|CSLC.OnItvB|ST|itvX.itv|INT32|Duration the relay was ON in minutes.|
|CSLC.OnItvB|ST|itvX.day|TIMESTAMP|Date (at midnight) of the record.|
|CSLC.OnItvB|ST|lastIdx|INT32|Indicates the last record of the cyclic buffer.|

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:ns1="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10">
   <soapenv:Header>
      <ns2:ApplicationName xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10">SoapUI</ns2:ApplicationName>
      <ns2:UserName xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10">Kevin</ns2:UserName>
      <ns2:OrganisationIdentification xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10">LianderNetManagement</ns2:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns2:GetPowerUsageHistoryRequest xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/devicemonitoring/2014/10">
         <ns2:DeviceIdentification>KAI-0000000053</ns2:DeviceIdentification>
         <ns2:TimePeriod>
            <ns2:StartTime>2018-09-01T00:00:00.000Z</ns2:StartTime>
            <ns2:EndTime>2018-09-30T00:00:00.000Z</ns2:EndTime>
         </ns2:TimePeriod>
         <ns2:HistoryTermType>LONG</ns2:HistoryTermType>
      </ns2:GetPowerUsageHistoryRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetPowerUsageHistoryAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180928151558848</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetPowerUsageHistoryAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:ns1="http://www.alliander.com/schemas/osgp/publiclighting/devicemonitoring/2014/10">
   <soapenv:Header>
      <ns2:ApplicationName xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10">SoapUI</ns2:ApplicationName>
      <ns2:UserName xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10">Kevin</ns2:UserName>
      <ns2:OrganisationIdentification xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10">LianderNetManagement</ns2:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns2:GetPowerUsageHistoryAsyncRequest xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/devicemonitoring/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">LianderNetManagement|||KAI-0000000053|||20180928151558848</ns3:CorrelationUid>
            <ns3:DeviceId xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">?</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:GetPowerUsageHistoryAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetPowerUsageHistoryResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/devicemonitoring/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-01T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>706</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-02T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>706</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-03T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>706</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-04T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>706</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-05T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>707</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-06T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>707</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-07T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>708</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-08T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>708</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-09T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>708</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-10T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>708</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-11T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>709</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-12T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>768</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-13T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>1010</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-14T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>709</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-15T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>710</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-16T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>710</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-17T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>711</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-18T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>711</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-19T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>711</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-20T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>711</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-21T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>839</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-22T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>712</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-23T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>713</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-24T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>713</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-25T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>720</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-26T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>434</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-27T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>381</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-28T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>2</ns2:index>
                  <ns2:totalLightingMinutes>43</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-01T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>706</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-02T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>706</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-03T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>706</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-04T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>706</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-05T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>707</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-06T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>707</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-07T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>708</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-08T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>708</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-09T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>708</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-10T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>708</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-11T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>709</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-12T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>768</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-13T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>1010</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-14T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>709</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-15T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>710</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-16T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>710</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-17T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>711</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-18T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>711</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-19T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>711</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-20T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>711</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-21T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>839</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-22T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>712</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-23T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>713</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-24T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>713</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-25T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>720</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-26T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>847</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-27T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>714</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
         <ns2:PowerUsageData>
            <ns2:RecordTime>2018-09-28T00:00:00.000Z</ns2:RecordTime>
            <ns2:MeterType>AUX</ns2:MeterType>
            <ns2:TotalConsumedEnergy>0</ns2:TotalConsumedEnergy>
            <ns2:ActualConsumedPower>0</ns2:ActualConsumedPower>
            <ns2:SsldData>
               <ns2:actualCurrent1>0</ns2:actualCurrent1>
               <ns2:actualCurrent2>0</ns2:actualCurrent2>
               <ns2:actualCurrent3>0</ns2:actualCurrent3>
               <ns2:actualPower1>0</ns2:actualPower1>
               <ns2:actualPower2>0</ns2:actualPower2>
               <ns2:actualPower3>0</ns2:actualPower3>
               <ns2:averagePowerFactor1>0</ns2:averagePowerFactor1>
               <ns2:averagePowerFactor2>0</ns2:averagePowerFactor2>
               <ns2:averagePowerFactor3>0</ns2:averagePowerFactor3>
               <ns2:relayData>
                  <ns2:index>3</ns2:index>
                  <ns2:totalLightingMinutes>317</ns2:totalLightingMinutes>
               </ns2:relayData>
            </ns2:SsldData>
         </ns2:PowerUsageData>
      </ns2:GetPowerUsageHistoryResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

IEC61850 platform message of the data sent to the device:
``` json
LogicalDevice: SWDeviceGenericIO 
messageType: GetPowerUsageHistory {
  CSLC.OnItvB[ST].itv34.itv: 700
  CSLC.OnItvB[ST].itv59.day: 2018-09-11
  CSLC.OnItvB[ST].itv16.day: 2018-09-28
  CSLC.OnItvB[ST].itv42.itv: 703
  CSLC.OnItvB[ST].itv24.day: 2018-08-07
  CSLC.OnItvB[ST].itv60.itv: 768
  CSLC.OnItvB[ST].itv50.day: 2018-09-02
  CSLC.OnItvB[ST].itv5.day: 2018-09-17
  CSLC.OnItvB[ST].itv5.itv: 711
  CSLC.OnItvB[ST].itv26.day: 2018-08-09
  CSLC.OnItvB[ST].itv34.day: 2018-08-17
  CSLC.OnItvB[ST].itv59.itv: 709
  CSLC.OnItvB[ST].itv16.itv: 317
  CSLC.OnItvB[ST].itv42.day: 2018-08-25
  CSLC.OnItvB[ST].itv50.itv: 706
  CSLC.OnItvB[ST].itv24.itv: 698
  CSLC.OnItvB[ST].itv60.day: 2018-09-12
  CSLC.OnItvB[ST].itv14.day: 2018-09-26
  CSLC.OnItvB[ST].itv28.itv: 699
  CSLC.OnItvB[ST].itv44.day: 2018-08-27
  CSLC.OnItvB[ST].itv30.day: 2018-08-13
  CSLC.OnItvB[ST].itv57.day: 2018-09-09
  CSLC.OnItvB[ST].itv32.itv: 701
  CSLC.OnItvB[ST].itv3.day: 2018-09-15
  CSLC.OnItvB[ST].itv28.day: 2018-08-11
  CSLC.OnItvB[ST].itv14.itv: 847
  CSLC.OnItvB[ST].itv32.day: 2018-08-15
  CSLC.OnItvB[ST].itv30.itv: 700
  CSLC.OnItvB[ST].itv44.itv: 702
  CSLC.OnItvB[ST].itv57.itv: 708
  CSLC.OnItvB[ST].itv26.itv: 739
  CSLC.OnItvB[ST].itv3.itv: 710
  CSLC.OnItvB[ST].itv39.itv: 702
  CSLC.OnItvB[ST].itv46.day: 2018-08-29
  CSLC.OnItvB[ST].itv56.itv: 708
  CSLC.OnItvB[ST].itv2.itv: 709
  CSLC.OnItvB[ST].itv54.day: 2018-09-06
  CSLC.OnItvB[ST].itv20.day: 2018-08-03
  CSLC.OnItvB[ST].itv11.day: 2018-09-23
  CSLC.OnItvB[ST].itv37.day: 2018-08-20
  CSLC.OnItvB[ST].itv39.day: 2018-08-22
  CSLC.OnItvB[ST].itv46.itv: 704
  CSLC.OnItvB[ST].itv56.day: 2018-09-08
  CSLC.OnItvB[ST].itv54.itv: 707
  CSLC.OnItvB[ST].itv29.itv: 700
  CSLC.OnItvB[ST].itv2.day: 2018-09-14
  CSLC.OnItvB[ST].itv29.day: 2018-08-12
  CSLC.OnItvB[ST].itv11.itv: 713
  CSLC.OnItvB[ST].itv20.itv: 697
  CSLC.OnItvB[ST].itv37.itv: 701
  CSLC.OnItvB[ST].itv52.day: 2018-09-04
  CSLC.OnItvB[ST].itv9.itv: 839
  CSLC.OnItvB[ST].itv48.day: 2018-08-31
  CSLC.OnItvB[ST].itv7.day: 2018-09-19
  CSLC.OnItvB[ST].itv35.day: 2018-08-18
  CSLC.OnItvB[ST].itv22.day: 2018-08-05
  CSLC.OnItvB[ST].itv9.day: 2018-09-21
  CSLC.OnItvB[ST].itv52.itv: 706
  CSLC.OnItvB[ST].itv18.day: 2018-08-01
  CSLC.OnItvB[ST].itv18.itv: 696
  CSLC.OnItvB[ST].itv48.itv: 705
  CSLC.OnItvB[ST].itv7.itv: 711
  CSLC.OnItvB[ST].itv35.itv: 701
  CSLC.OnItvB[ST].itv22.itv: 698
  CSLC.OnItvB[ST].itv33.day: 2018-08-16
  CSLC.OnItvB[ST].itv41.day: 2018-08-24
  CSLC.OnItvB[ST].itv17.itv: 696
  CSLC.OnItvB[ST].itv43.itv: 704
  CSLC.OnItvB[ST].itv25.itv: 699
  CSLC.OnItvB[ST].itv51.itv: 706
  CSLC.OnItvB[ST].itv6.itv: 711
  CSLC.OnItvB[ST].itv33.itv: 700
  CSLC.OnItvB[ST].itv19.itv: 697
  CSLC.OnItvB[ST].itv17.day: 2018-07-31
  CSLC.OnItvB[ST].itv41.itv: 703
  CSLC.OnItvB[ST].itv43.day: 2018-08-26
  CSLC.OnItvB[ST].lastIdx: 15
  CSLC.OnItvB[ST].itv51.day: 2018-09-03
  CSLC.OnItvB[ST].itv6.day: 2018-09-18
  CSLC.OnItvB[ST].itv25.day: 2018-08-08
  CSLC.OnItvB[ST].itv27.day: 2018-08-10
  CSLC.OnItvB[ST].itv58.itv: 708
  CSLC.OnItvB[ST].itv15.itv: 714
  CSLC.OnItvB[ST].itv45.itv: 704
  CSLC.OnItvB[ST].itv31.day: 2018-08-14
  CSLC.OnItvB[ST].itv13.day: 2018-09-25
  CSLC.OnItvB[ST].itv4.itv: 710
  CSLC.OnItvB[ST].itv15.day: 2018-09-27
  CSLC.OnItvB[ST].itv45.day: 2018-08-28
  CSLC.OnItvB[ST].itv27.itv: 699
  CSLC.OnItvB[ST].itv58.day: 2018-09-10
  CSLC.OnItvB[ST].itv31.itv: 700
  CSLC.OnItvB[ST].itv13.itv: 720
  CSLC.OnItvB[ST].itv4.day: 2018-09-16
  CSLC.OnItvB[ST].itv55.itv: 708
  CSLC.OnItvB[ST].itv1.day: 2018-09-13
  CSLC.OnItvB[ST].itv12.itv: 713
  CSLC.OnItvB[ST].itv47.itv: 705
  CSLC.OnItvB[ST].itv38.itv: 702
  CSLC.OnItvB[ST].itv21.itv: 698
  CSLC.OnItvB[ST].itv21.day: 2018-08-04
  CSLC.OnItvB[ST].itv12.day: 2018-09-24
  CSLC.OnItvB[ST].itv55.day: 2018-09-07
  CSLC.OnItvB[ST].itv47.day: 2018-08-30
  CSLC.OnItvB[ST].itv1.itv: 1010
  CSLC.OnItvB[ST].itv38.day: 2018-08-21
  CSLC.OnItvB[ST].itv10.itv: 712
  CSLC.OnItvB[ST].itv40.itv: 703
  CSLC.OnItvB[ST].itv53.itv: 707
  CSLC.OnItvB[ST].itv19.day: 2018-08-02
  CSLC.OnItvB[ST].itv49.itv: 706
  CSLC.OnItvB[ST].itv8.itv: 711
  CSLC.OnItvB[ST].itv23.itv: 698
  CSLC.OnItvB[ST].itv36.itv: 701
  CSLC.OnItvB[ST].itv40.day: 2018-08-23
  CSLC.OnItvB[ST].itv53.day: 2018-09-05
  CSLC.OnItvB[ST].itv36.day: 2018-08-19
  CSLC.OnItvB[ST].itv8.day: 2018-09-20
  CSLC.OnItvB[ST].itv49.day: 2018-09-01
  CSLC.OnItvB[ST].itv10.day: 2018-09-22
  CSLC.OnItvB[ST].itv23.day: 2018-08-06
}
```

IEC61850 protocol Adapter logging:
``` json
2018-09-28 15:15:59.369] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: GET_POWER_USAGE_HISTORY with message priority: 4
2018-09-28 15:15:59.419] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: GET_POWER_USAGE_HISTORY for domain: PUBLIC_LIGHTING 1.0
2018-09-28 15:15:59.419] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-09-28 15:15:59.419] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-09-28 15:15:59.424] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-09-28 15:15:59.429] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-09-28 15:15:59.482] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-28 15:15:59.482] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-09-28 15:15:59.557] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-09-28T15:15:59.419Z, end time: 2018-09-28T15:15:59.557Z, total time in milliseconds: 138
2018-09-28 15:15:59.572] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@apply:54 - device: KAI-0000000053, ignoring HistoryTermType (LONG) determining power usage history
2018-09-28 15:15:59.573] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.OnItvB
2018-09-28 15:15:59.590] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv45: SWDeviceGenericIO/XSWC2.OnItvB.itv45 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv45.itv: 696
SWDeviceGenericIO/XSWC2.OnItvB.itv45.day: Tue Jul 31 00:00:00 UTC 2018
2018-09-28 15:15:59.590] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv45.itv: 696
2018-09-28 15:15:59.590] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv45.day: 2018-07-31T00:00:00.000Z
2018-09-28 15:15:59.592] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv45, date: 2018-07-31T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.592] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv46: SWDeviceGenericIO/XSWC2.OnItvB.itv46 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv46.itv: 696
SWDeviceGenericIO/XSWC2.OnItvB.itv46.day: Wed Aug 01 00:00:00 UTC 2018
2018-09-28 15:15:59.592] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv46.itv: 696
2018-09-28 15:15:59.592] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv46.day: 2018-08-01T00:00:00.000Z
2018-09-28 15:15:59.592] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv46, date: 2018-08-01T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.592] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv47: SWDeviceGenericIO/XSWC2.OnItvB.itv47 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv47.itv: 697
SWDeviceGenericIO/XSWC2.OnItvB.itv47.day: Thu Aug 02 00:00:00 UTC 2018
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv47.itv: 697
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv47.day: 2018-08-02T00:00:00.000Z
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv47, date: 2018-08-02T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv48: SWDeviceGenericIO/XSWC2.OnItvB.itv48 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv48.itv: 398
SWDeviceGenericIO/XSWC2.OnItvB.itv48.day: Fri Aug 03 00:00:00 UTC 2018
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv48.itv: 398
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv48.day: 2018-08-03T00:00:00.000Z
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv48, date: 2018-08-03T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv49: SWDeviceGenericIO/XSWC2.OnItvB.itv49 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv49.itv: 698
SWDeviceGenericIO/XSWC2.OnItvB.itv49.day: Sat Aug 04 00:00:00 UTC 2018
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv49.itv: 698
2018-09-28 15:15:59.593] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv49.day: 2018-08-04T00:00:00.000Z
2018-09-28 15:15:59.594] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv49, date: 2018-08-04T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.594] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv50: SWDeviceGenericIO/XSWC2.OnItvB.itv50 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv50.itv: 698
SWDeviceGenericIO/XSWC2.OnItvB.itv50.day: Sun Aug 05 00:00:00 UTC 2018
2018-09-28 15:15:59.600] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv50.itv: 698
2018-09-28 15:15:59.600] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv50.day: 2018-08-05T00:00:00.000Z
2018-09-28 15:15:59.600] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv50, date: 2018-08-05T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.600] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv51: SWDeviceGenericIO/XSWC2.OnItvB.itv51 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv51.itv: 698
SWDeviceGenericIO/XSWC2.OnItvB.itv51.day: Mon Aug 06 00:00:00 UTC 2018
2018-09-28 15:15:59.600] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv51.itv: 698
2018-09-28 15:15:59.600] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv51.day: 2018-08-06T00:00:00.000Z
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv51, date: 2018-08-06T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv52: SWDeviceGenericIO/XSWC2.OnItvB.itv52 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv52.itv: 698
SWDeviceGenericIO/XSWC2.OnItvB.itv52.day: Tue Aug 07 00:00:00 UTC 2018
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv52.itv: 698
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv52.day: 2018-08-07T00:00:00.000Z
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv52, date: 2018-08-07T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv53: SWDeviceGenericIO/XSWC2.OnItvB.itv53 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv53.itv: 699
SWDeviceGenericIO/XSWC2.OnItvB.itv53.day: Wed Aug 08 00:00:00 UTC 2018
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv53.itv: 699
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv53.day: 2018-08-08T00:00:00.000Z
2018-09-28 15:15:59.601] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv53, date: 2018-08-08T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.602] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv54: SWDeviceGenericIO/XSWC2.OnItvB.itv54 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv54.itv: 739
SWDeviceGenericIO/XSWC2.OnItvB.itv54.day: Thu Aug 09 00:00:00 UTC 2018
2018-09-28 15:15:59.602] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv54.itv: 739
2018-09-28 15:15:59.602] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv54.day: 2018-08-09T00:00:00.000Z
2018-09-28 15:15:59.602] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv54, date: 2018-08-09T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.602] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv55: SWDeviceGenericIO/XSWC2.OnItvB.itv55 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv55.itv: 699
SWDeviceGenericIO/XSWC2.OnItvB.itv55.day: Fri Aug 10 00:00:00 UTC 2018
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv55.itv: 699
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv55.day: 2018-08-10T00:00:00.000Z
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv55, date: 2018-08-10T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv56: SWDeviceGenericIO/XSWC2.OnItvB.itv56 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv56.itv: 699
SWDeviceGenericIO/XSWC2.OnItvB.itv56.day: Sat Aug 11 00:00:00 UTC 2018
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv56.itv: 699
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv56.day: 2018-08-11T00:00:00.000Z
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv56, date: 2018-08-11T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv57: SWDeviceGenericIO/XSWC2.OnItvB.itv57 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv57.itv: 700
SWDeviceGenericIO/XSWC2.OnItvB.itv57.day: Sun Aug 12 00:00:00 UTC 2018
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv57.itv: 700
2018-09-28 15:15:59.603] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv57.day: 2018-08-12T00:00:00.000Z
2018-09-28 15:15:59.604] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv57, date: 2018-08-12T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.604] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv58: SWDeviceGenericIO/XSWC2.OnItvB.itv58 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv58.itv: 700
SWDeviceGenericIO/XSWC2.OnItvB.itv58.day: Mon Aug 13 00:00:00 UTC 2018
2018-09-28 15:15:59.604] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv58.itv: 700
2018-09-28 15:15:59.604] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv58.day: 2018-08-13T00:00:00.000Z
2018-09-28 15:15:59.604] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv58, date: 2018-08-13T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.604] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv59: SWDeviceGenericIO/XSWC2.OnItvB.itv59 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv59.itv: 700
SWDeviceGenericIO/XSWC2.OnItvB.itv59.day: Tue Aug 14 00:00:00 UTC 2018
2018-09-28 15:15:59.604] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv59.itv: 700
2018-09-28 15:15:59.609] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv59.day: 2018-08-14T00:00:00.000Z
2018-09-28 15:15:59.609] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv59, date: 2018-08-14T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv60: SWDeviceGenericIO/XSWC2.OnItvB.itv60 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv60.itv: 701
SWDeviceGenericIO/XSWC2.OnItvB.itv60.day: Wed Aug 15 00:00:00 UTC 2018
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv60.itv: 701
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv60.day: 2018-08-15T00:00:00.000Z
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv60, date: 2018-08-15T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv1: SWDeviceGenericIO/XSWC2.OnItvB.itv1 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv1.itv: 700
SWDeviceGenericIO/XSWC2.OnItvB.itv1.day: Thu Aug 16 00:00:00 UTC 2018
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv1.itv: 700
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv1.day: 2018-08-16T00:00:00.000Z
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv1, date: 2018-08-16T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.610] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv2: SWDeviceGenericIO/XSWC2.OnItvB.itv2 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv2.itv: 700
SWDeviceGenericIO/XSWC2.OnItvB.itv2.day: Fri Aug 17 00:00:00 UTC 2018
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv2.itv: 700
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv2.day: 2018-08-17T00:00:00.000Z
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv2, date: 2018-08-17T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv3: SWDeviceGenericIO/XSWC2.OnItvB.itv3 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv3.itv: 701
SWDeviceGenericIO/XSWC2.OnItvB.itv3.day: Sat Aug 18 00:00:00 UTC 2018
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv3.itv: 701
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv3.day: 2018-08-18T00:00:00.000Z
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv3, date: 2018-08-18T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv4: SWDeviceGenericIO/XSWC2.OnItvB.itv4 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv4.itv: 701
SWDeviceGenericIO/XSWC2.OnItvB.itv4.day: Sun Aug 19 00:00:00 UTC 2018
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv4.itv: 701
2018-09-28 15:15:59.611] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv4.day: 2018-08-19T00:00:00.000Z
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv4, date: 2018-08-19T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv5: SWDeviceGenericIO/XSWC2.OnItvB.itv5 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv5.itv: 701
SWDeviceGenericIO/XSWC2.OnItvB.itv5.day: Mon Aug 20 00:00:00 UTC 2018
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv5.itv: 701
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv5.day: 2018-08-20T00:00:00.000Z
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv5, date: 2018-08-20T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv6: SWDeviceGenericIO/XSWC2.OnItvB.itv6 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv6.itv: 702
SWDeviceGenericIO/XSWC2.OnItvB.itv6.day: Tue Aug 21 00:00:00 UTC 2018
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv6.itv: 702
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv6.day: 2018-08-21T00:00:00.000Z
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv6, date: 2018-08-21T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv7: SWDeviceGenericIO/XSWC2.OnItvB.itv7 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv7.itv: 702
SWDeviceGenericIO/XSWC2.OnItvB.itv7.day: Wed Aug 22 00:00:00 UTC 2018
2018-09-28 15:15:59.612] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv7.itv: 702
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv7.day: 2018-08-22T00:00:00.000Z
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv7, date: 2018-08-22T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv8: SWDeviceGenericIO/XSWC2.OnItvB.itv8 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv8.itv: 703
SWDeviceGenericIO/XSWC2.OnItvB.itv8.day: Thu Aug 23 00:00:00 UTC 2018
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv8.itv: 703
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv8.day: 2018-08-23T00:00:00.000Z
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv8, date: 2018-08-23T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv9: SWDeviceGenericIO/XSWC2.OnItvB.itv9 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv9.itv: 703
SWDeviceGenericIO/XSWC2.OnItvB.itv9.day: Fri Aug 24 00:00:00 UTC 2018
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv9.itv: 703
2018-09-28 15:15:59.613] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv9.day: 2018-08-24T00:00:00.000Z
2018-09-28 15:15:59.619] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv9, date: 2018-08-24T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.619] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv10: SWDeviceGenericIO/XSWC2.OnItvB.itv10 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv10.itv: 703
SWDeviceGenericIO/XSWC2.OnItvB.itv10.day: Sat Aug 25 00:00:00 UTC 2018
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv10.itv: 703
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv10.day: 2018-08-25T00:00:00.000Z
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv10, date: 2018-08-25T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv11: SWDeviceGenericIO/XSWC2.OnItvB.itv11 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv11.itv: 704
SWDeviceGenericIO/XSWC2.OnItvB.itv11.day: Sun Aug 26 00:00:00 UTC 2018
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv11.itv: 704
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv11.day: 2018-08-26T00:00:00.000Z
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv11, date: 2018-08-26T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv12: SWDeviceGenericIO/XSWC2.OnItvB.itv12 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv12.itv: 304
SWDeviceGenericIO/XSWC2.OnItvB.itv12.day: Mon Aug 27 00:00:00 UTC 2018
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv12.itv: 304
2018-09-28 15:15:59.620] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv12.day: 2018-08-27T00:00:00.000Z
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv12, date: 2018-08-27T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv13: SWDeviceGenericIO/XSWC2.OnItvB.itv13 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv13.itv: 704
SWDeviceGenericIO/XSWC2.OnItvB.itv13.day: Tue Aug 28 00:00:00 UTC 2018
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv13.itv: 704
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv13.day: 2018-08-28T00:00:00.000Z
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv13, date: 2018-08-28T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv14: SWDeviceGenericIO/XSWC2.OnItvB.itv14 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv14.itv: 704
SWDeviceGenericIO/XSWC2.OnItvB.itv14.day: Wed Aug 29 00:00:00 UTC 2018
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv14.itv: 704
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv14.day: 2018-08-29T00:00:00.000Z
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv14, date: 2018-08-29T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv15: SWDeviceGenericIO/XSWC2.OnItvB.itv15 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv15.itv: 705
SWDeviceGenericIO/XSWC2.OnItvB.itv15.day: Thu Aug 30 00:00:00 UTC 2018
2018-09-28 15:15:59.621] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv15.itv: 705
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv15.day: 2018-08-30T00:00:00.000Z
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv15, date: 2018-08-30T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv16: SWDeviceGenericIO/XSWC2.OnItvB.itv16 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv16.itv: 705
SWDeviceGenericIO/XSWC2.OnItvB.itv16.day: Fri Aug 31 00:00:00 UTC 2018
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv16.itv: 705
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv16.day: 2018-08-31T00:00:00.000Z
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 2, skip entry for itv16, date: 2018-08-31T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv17: SWDeviceGenericIO/XSWC2.OnItvB.itv17 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv17.itv: 706
SWDeviceGenericIO/XSWC2.OnItvB.itv17.day: Sat Sep 01 00:00:00 UTC 2018
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv17.itv: 706
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv17.day: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.622] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv17, date: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.630] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv18: SWDeviceGenericIO/XSWC2.OnItvB.itv18 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv18.itv: 706
SWDeviceGenericIO/XSWC2.OnItvB.itv18.day: Sun Sep 02 00:00:00 UTC 2018
2018-09-28 15:15:59.630] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv18.itv: 706
2018-09-28 15:15:59.630] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv18.day: 2018-09-02T00:00:00.000Z
2018-09-28 15:15:59.631] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv18, date: 2018-09-02T00:00:00.000Z
2018-09-28 15:15:59.631] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv19: SWDeviceGenericIO/XSWC2.OnItvB.itv19 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv19.itv: 706
SWDeviceGenericIO/XSWC2.OnItvB.itv19.day: Mon Sep 03 00:00:00 UTC 2018
2018-09-28 15:15:59.631] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv19.itv: 706
2018-09-28 15:15:59.631] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv19.day: 2018-09-03T00:00:00.000Z
2018-09-28 15:15:59.631] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv19, date: 2018-09-03T00:00:00.000Z
2018-09-28 15:15:59.631] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv20: SWDeviceGenericIO/XSWC2.OnItvB.itv20 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv20.itv: 706
SWDeviceGenericIO/XSWC2.OnItvB.itv20.day: Tue Sep 04 00:00:00 UTC 2018
2018-09-28 15:15:59.631] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv20.itv: 706
2018-09-28 15:15:59.631] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv20.day: 2018-09-04T00:00:00.000Z
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv20, date: 2018-09-04T00:00:00.000Z
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv21: SWDeviceGenericIO/XSWC2.OnItvB.itv21 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv21.itv: 707
SWDeviceGenericIO/XSWC2.OnItvB.itv21.day: Wed Sep 05 00:00:00 UTC 2018
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv21.itv: 707
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv21.day: 2018-09-05T00:00:00.000Z
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv21, date: 2018-09-05T00:00:00.000Z
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv22: SWDeviceGenericIO/XSWC2.OnItvB.itv22 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv22.itv: 707
SWDeviceGenericIO/XSWC2.OnItvB.itv22.day: Thu Sep 06 00:00:00 UTC 2018
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv22.itv: 707
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv22.day: 2018-09-06T00:00:00.000Z
2018-09-28 15:15:59.632] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv22, date: 2018-09-06T00:00:00.000Z
2018-09-28 15:15:59.633] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv23: SWDeviceGenericIO/XSWC2.OnItvB.itv23 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv23.itv: 708
SWDeviceGenericIO/XSWC2.OnItvB.itv23.day: Fri Sep 07 00:00:00 UTC 2018
2018-09-28 15:15:59.633] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv23.itv: 708
2018-09-28 15:15:59.633] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv23.day: 2018-09-07T00:00:00.000Z
2018-09-28 15:15:59.633] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv23, date: 2018-09-07T00:00:00.000Z
2018-09-28 15:15:59.633] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv24: SWDeviceGenericIO/XSWC2.OnItvB.itv24 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv24.itv: 708
SWDeviceGenericIO/XSWC2.OnItvB.itv24.day: Sat Sep 08 00:00:00 UTC 2018
2018-09-28 15:15:59.633] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv24.itv: 708
2018-09-28 15:15:59.639] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv24.day: 2018-09-08T00:00:00.000Z
2018-09-28 15:15:59.639] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv24, date: 2018-09-08T00:00:00.000Z
2018-09-28 15:15:59.639] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv25: SWDeviceGenericIO/XSWC2.OnItvB.itv25 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv25.itv: 708
SWDeviceGenericIO/XSWC2.OnItvB.itv25.day: Sun Sep 09 00:00:00 UTC 2018
2018-09-28 15:15:59.639] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv25.itv: 708
2018-09-28 15:15:59.639] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv25.day: 2018-09-09T00:00:00.000Z
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv25, date: 2018-09-09T00:00:00.000Z
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv26: SWDeviceGenericIO/XSWC2.OnItvB.itv26 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv26.itv: 708
SWDeviceGenericIO/XSWC2.OnItvB.itv26.day: Mon Sep 10 00:00:00 UTC 2018
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv26.itv: 708
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv26.day: 2018-09-10T00:00:00.000Z
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv26, date: 2018-09-10T00:00:00.000Z
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv27: SWDeviceGenericIO/XSWC2.OnItvB.itv27 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv27.itv: 709
SWDeviceGenericIO/XSWC2.OnItvB.itv27.day: Tue Sep 11 00:00:00 UTC 2018
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv27.itv: 709
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv27.day: 2018-09-11T00:00:00.000Z
2018-09-28 15:15:59.640] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv27, date: 2018-09-11T00:00:00.000Z
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv28: SWDeviceGenericIO/XSWC2.OnItvB.itv28 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv28.itv: 768
SWDeviceGenericIO/XSWC2.OnItvB.itv28.day: Wed Sep 12 00:00:00 UTC 2018
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv28.itv: 768
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv28.day: 2018-09-12T00:00:00.000Z
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv28, date: 2018-09-12T00:00:00.000Z
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv29: SWDeviceGenericIO/XSWC2.OnItvB.itv29 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv29.itv: 1010
SWDeviceGenericIO/XSWC2.OnItvB.itv29.day: Thu Sep 13 00:00:00 UTC 2018
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv29.itv: 1010
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv29.day: 2018-09-13T00:00:00.000Z
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv29, date: 2018-09-13T00:00:00.000Z
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv30: SWDeviceGenericIO/XSWC2.OnItvB.itv30 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv30.itv: 709
SWDeviceGenericIO/XSWC2.OnItvB.itv30.day: Fri Sep 14 00:00:00 UTC 2018
2018-09-28 15:15:59.641] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv30.itv: 709
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv30.day: 2018-09-14T00:00:00.000Z
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv30, date: 2018-09-14T00:00:00.000Z
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv31: SWDeviceGenericIO/XSWC2.OnItvB.itv31 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv31.itv: 710
SWDeviceGenericIO/XSWC2.OnItvB.itv31.day: Sat Sep 15 00:00:00 UTC 2018
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv31.itv: 710
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv31.day: 2018-09-15T00:00:00.000Z
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv31, date: 2018-09-15T00:00:00.000Z
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv32: SWDeviceGenericIO/XSWC2.OnItvB.itv32 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv32.itv: 710
SWDeviceGenericIO/XSWC2.OnItvB.itv32.day: Sun Sep 16 00:00:00 UTC 2018
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv32.itv: 710
2018-09-28 15:15:59.642] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv32.day: 2018-09-16T00:00:00.000Z
2018-09-28 15:15:59.643] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv32, date: 2018-09-16T00:00:00.000Z
2018-09-28 15:15:59.643] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv33: SWDeviceGenericIO/XSWC2.OnItvB.itv33 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv33.itv: 711
SWDeviceGenericIO/XSWC2.OnItvB.itv33.day: Mon Sep 17 00:00:00 UTC 2018
2018-09-28 15:15:59.643] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv33.itv: 711
2018-09-28 15:15:59.643] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv33.day: 2018-09-17T00:00:00.000Z
2018-09-28 15:15:59.649] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv33, date: 2018-09-17T00:00:00.000Z
2018-09-28 15:15:59.649] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv34: SWDeviceGenericIO/XSWC2.OnItvB.itv34 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv34.itv: 711
SWDeviceGenericIO/XSWC2.OnItvB.itv34.day: Tue Sep 18 00:00:00 UTC 2018
2018-09-28 15:15:59.649] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv34.itv: 711
2018-09-28 15:15:59.649] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv34.day: 2018-09-18T00:00:00.000Z
2018-09-28 15:15:59.649] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv34, date: 2018-09-18T00:00:00.000Z
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv35: SWDeviceGenericIO/XSWC2.OnItvB.itv35 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv35.itv: 711
SWDeviceGenericIO/XSWC2.OnItvB.itv35.day: Wed Sep 19 00:00:00 UTC 2018
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv35.itv: 711
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv35.day: 2018-09-19T00:00:00.000Z
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv35, date: 2018-09-19T00:00:00.000Z
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv36: SWDeviceGenericIO/XSWC2.OnItvB.itv36 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv36.itv: 711
SWDeviceGenericIO/XSWC2.OnItvB.itv36.day: Thu Sep 20 00:00:00 UTC 2018
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv36.itv: 711
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv36.day: 2018-09-20T00:00:00.000Z
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv36, date: 2018-09-20T00:00:00.000Z
2018-09-28 15:15:59.650] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv37: SWDeviceGenericIO/XSWC2.OnItvB.itv37 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv37.itv: 839
SWDeviceGenericIO/XSWC2.OnItvB.itv37.day: Fri Sep 21 00:00:00 UTC 2018
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv37.itv: 839
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv37.day: 2018-09-21T00:00:00.000Z
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv37, date: 2018-09-21T00:00:00.000Z
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv38: SWDeviceGenericIO/XSWC2.OnItvB.itv38 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv38.itv: 712
SWDeviceGenericIO/XSWC2.OnItvB.itv38.day: Sat Sep 22 00:00:00 UTC 2018
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv38.itv: 712
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv38.day: 2018-09-22T00:00:00.000Z
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv38, date: 2018-09-22T00:00:00.000Z
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv39: SWDeviceGenericIO/XSWC2.OnItvB.itv39 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv39.itv: 713
SWDeviceGenericIO/XSWC2.OnItvB.itv39.day: Sun Sep 23 00:00:00 UTC 2018
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv39.itv: 713
2018-09-28 15:15:59.651] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv39.day: 2018-09-23T00:00:00.000Z
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv39, date: 2018-09-23T00:00:00.000Z
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv40: SWDeviceGenericIO/XSWC2.OnItvB.itv40 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv40.itv: 713
SWDeviceGenericIO/XSWC2.OnItvB.itv40.day: Mon Sep 24 00:00:00 UTC 2018
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv40.itv: 713
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv40.day: 2018-09-24T00:00:00.000Z
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv40, date: 2018-09-24T00:00:00.000Z
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv41: SWDeviceGenericIO/XSWC2.OnItvB.itv41 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv41.itv: 720
SWDeviceGenericIO/XSWC2.OnItvB.itv41.day: Tue Sep 25 00:00:00 UTC 2018
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv41.itv: 720
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv41.day: 2018-09-25T00:00:00.000Z
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv41, date: 2018-09-25T00:00:00.000Z
2018-09-28 15:15:59.652] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv42: SWDeviceGenericIO/XSWC2.OnItvB.itv42 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv42.itv: 434
SWDeviceGenericIO/XSWC2.OnItvB.itv42.day: Wed Sep 26 00:00:00 UTC 2018
2018-09-28 15:15:59.653] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv42.itv: 434
2018-09-28 15:15:59.653] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv42.day: 2018-09-26T00:00:00.000Z
2018-09-28 15:15:59.653] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv42, date: 2018-09-26T00:00:00.000Z
2018-09-28 15:15:59.653] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv43: SWDeviceGenericIO/XSWC2.OnItvB.itv43 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv43.itv: 381
SWDeviceGenericIO/XSWC2.OnItvB.itv43.day: Thu Sep 27 00:00:00 UTC 2018
2018-09-28 15:15:59.659] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv43.itv: 381
2018-09-28 15:15:59.659] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv43.day: 2018-09-27T00:00:00.000Z
2018-09-28 15:15:59.659] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv43, date: 2018-09-27T00:00:00.000Z
2018-09-28 15:15:59.659] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv44: SWDeviceGenericIO/XSWC2.OnItvB.itv44 [ST]
SWDeviceGenericIO/XSWC2.OnItvB.itv44.itv: 43
SWDeviceGenericIO/XSWC2.OnItvB.itv44.day: Fri Sep 28 00:00:00 UTC 2018
2018-09-28 15:15:59.659] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv44.itv: 43
2018-09-28 15:15:59.659] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv44.day: 2018-09-28T00:00:00.000Z
2018-09-28 15:15:59.659] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 2, include entry for itv44, date: 2018-09-28T00:00:00.000Z
2018-09-28 15:15:59.660] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.OnItvB
2018-09-28 15:15:59.674] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv17: SWDeviceGenericIO/XSWC3.OnItvB.itv17 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv17.itv: 696
SWDeviceGenericIO/XSWC3.OnItvB.itv17.day: Tue Jul 31 00:00:00 UTC 2018
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv17.itv: 696
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv17.day: 2018-07-31T00:00:00.000Z
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv17, date: 2018-07-31T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv18: SWDeviceGenericIO/XSWC3.OnItvB.itv18 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv18.itv: 696
SWDeviceGenericIO/XSWC3.OnItvB.itv18.day: Wed Aug 01 00:00:00 UTC 2018
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv18.itv: 696
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv18.day: 2018-08-01T00:00:00.000Z
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv18, date: 2018-08-01T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv19: SWDeviceGenericIO/XSWC3.OnItvB.itv19 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv19.itv: 697
SWDeviceGenericIO/XSWC3.OnItvB.itv19.day: Thu Aug 02 00:00:00 UTC 2018
2018-09-28 15:15:59.675] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv19.itv: 697
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv19.day: 2018-08-02T00:00:00.000Z
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv19, date: 2018-08-02T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv20: SWDeviceGenericIO/XSWC3.OnItvB.itv20 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv20.itv: 697
SWDeviceGenericIO/XSWC3.OnItvB.itv20.day: Fri Aug 03 00:00:00 UTC 2018
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv20.itv: 697
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv20.day: 2018-08-03T00:00:00.000Z
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv20, date: 2018-08-03T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv21: SWDeviceGenericIO/XSWC3.OnItvB.itv21 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv21.itv: 698
SWDeviceGenericIO/XSWC3.OnItvB.itv21.day: Sat Aug 04 00:00:00 UTC 2018
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv21.itv: 698
2018-09-28 15:15:59.676] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv21.day: 2018-08-04T00:00:00.000Z
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv21, date: 2018-08-04T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv22: SWDeviceGenericIO/XSWC3.OnItvB.itv22 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv22.itv: 698
SWDeviceGenericIO/XSWC3.OnItvB.itv22.day: Sun Aug 05 00:00:00 UTC 2018
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv22.itv: 698
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv22.day: 2018-08-05T00:00:00.000Z
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv22, date: 2018-08-05T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv23: SWDeviceGenericIO/XSWC3.OnItvB.itv23 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv23.itv: 698
SWDeviceGenericIO/XSWC3.OnItvB.itv23.day: Mon Aug 06 00:00:00 UTC 2018
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv23.itv: 698
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv23.day: 2018-08-06T00:00:00.000Z
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv23, date: 2018-08-06T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.677] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv24: SWDeviceGenericIO/XSWC3.OnItvB.itv24 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv24.itv: 698
SWDeviceGenericIO/XSWC3.OnItvB.itv24.day: Tue Aug 07 00:00:00 UTC 2018
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv24.itv: 698
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv24.day: 2018-08-07T00:00:00.000Z
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv24, date: 2018-08-07T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv25: SWDeviceGenericIO/XSWC3.OnItvB.itv25 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv25.itv: 699
SWDeviceGenericIO/XSWC3.OnItvB.itv25.day: Wed Aug 08 00:00:00 UTC 2018
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv25.itv: 699
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv25.day: 2018-08-08T00:00:00.000Z
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv25, date: 2018-08-08T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv26: SWDeviceGenericIO/XSWC3.OnItvB.itv26 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv26.itv: 739
SWDeviceGenericIO/XSWC3.OnItvB.itv26.day: Thu Aug 09 00:00:00 UTC 2018
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv26.itv: 739
2018-09-28 15:15:59.678] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv26.day: 2018-08-09T00:00:00.000Z
2018-09-28 15:15:59.684] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv26, date: 2018-08-09T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.684] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv27: SWDeviceGenericIO/XSWC3.OnItvB.itv27 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv27.itv: 699
SWDeviceGenericIO/XSWC3.OnItvB.itv27.day: Fri Aug 10 00:00:00 UTC 2018
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv27.itv: 699
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv27.day: 2018-08-10T00:00:00.000Z
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv27, date: 2018-08-10T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv28: SWDeviceGenericIO/XSWC3.OnItvB.itv28 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv28.itv: 699
SWDeviceGenericIO/XSWC3.OnItvB.itv28.day: Sat Aug 11 00:00:00 UTC 2018
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv28.itv: 699
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv28.day: 2018-08-11T00:00:00.000Z
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv28, date: 2018-08-11T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv29: SWDeviceGenericIO/XSWC3.OnItvB.itv29 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv29.itv: 700
SWDeviceGenericIO/XSWC3.OnItvB.itv29.day: Sun Aug 12 00:00:00 UTC 2018
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv29.itv: 700
2018-09-28 15:15:59.685] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv29.day: 2018-08-12T00:00:00.000Z
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv29, date: 2018-08-12T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv30: SWDeviceGenericIO/XSWC3.OnItvB.itv30 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv30.itv: 700
SWDeviceGenericIO/XSWC3.OnItvB.itv30.day: Mon Aug 13 00:00:00 UTC 2018
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv30.itv: 700
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv30.day: 2018-08-13T00:00:00.000Z
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv30, date: 2018-08-13T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv31: SWDeviceGenericIO/XSWC3.OnItvB.itv31 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv31.itv: 700
SWDeviceGenericIO/XSWC3.OnItvB.itv31.day: Tue Aug 14 00:00:00 UTC 2018
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv31.itv: 700
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv31.day: 2018-08-14T00:00:00.000Z
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv31, date: 2018-08-14T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.686] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv32: SWDeviceGenericIO/XSWC3.OnItvB.itv32 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv32.itv: 701
SWDeviceGenericIO/XSWC3.OnItvB.itv32.day: Wed Aug 15 00:00:00 UTC 2018
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv32.itv: 701
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv32.day: 2018-08-15T00:00:00.000Z
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv32, date: 2018-08-15T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv33: SWDeviceGenericIO/XSWC3.OnItvB.itv33 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv33.itv: 700
SWDeviceGenericIO/XSWC3.OnItvB.itv33.day: Thu Aug 16 00:00:00 UTC 2018
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv33.itv: 700
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv33.day: 2018-08-16T00:00:00.000Z
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv33, date: 2018-08-16T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv34: SWDeviceGenericIO/XSWC3.OnItvB.itv34 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv34.itv: 700
SWDeviceGenericIO/XSWC3.OnItvB.itv34.day: Fri Aug 17 00:00:00 UTC 2018
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv34.itv: 700
2018-09-28 15:15:59.687] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv34.day: 2018-08-17T00:00:00.000Z
2018-09-28 15:15:59.688] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv34, date: 2018-08-17T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.688] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv35: SWDeviceGenericIO/XSWC3.OnItvB.itv35 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv35.itv: 701
SWDeviceGenericIO/XSWC3.OnItvB.itv35.day: Sat Aug 18 00:00:00 UTC 2018
2018-09-28 15:15:59.688] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv35.itv: 701
2018-09-28 15:15:59.688] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv35.day: 2018-08-18T00:00:00.000Z
2018-09-28 15:15:59.688] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv35, date: 2018-08-18T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.688] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv36: SWDeviceGenericIO/XSWC3.OnItvB.itv36 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv36.itv: 701
SWDeviceGenericIO/XSWC3.OnItvB.itv36.day: Sun Aug 19 00:00:00 UTC 2018
2018-09-28 15:15:59.688] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv36.itv: 701
2018-09-28 15:15:59.688] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv36.day: 2018-08-19T00:00:00.000Z
2018-09-28 15:15:59.694] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv36, date: 2018-08-19T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.694] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv37: SWDeviceGenericIO/XSWC3.OnItvB.itv37 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv37.itv: 701
SWDeviceGenericIO/XSWC3.OnItvB.itv37.day: Mon Aug 20 00:00:00 UTC 2018
2018-09-28 15:15:59.694] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv37.itv: 701
2018-09-28 15:15:59.694] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv37.day: 2018-08-20T00:00:00.000Z
2018-09-28 15:15:59.694] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv37, date: 2018-08-20T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv38: SWDeviceGenericIO/XSWC3.OnItvB.itv38 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv38.itv: 702
SWDeviceGenericIO/XSWC3.OnItvB.itv38.day: Tue Aug 21 00:00:00 UTC 2018
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv38.itv: 702
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv38.day: 2018-08-21T00:00:00.000Z
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv38, date: 2018-08-21T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv39: SWDeviceGenericIO/XSWC3.OnItvB.itv39 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv39.itv: 702
SWDeviceGenericIO/XSWC3.OnItvB.itv39.day: Wed Aug 22 00:00:00 UTC 2018
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv39.itv: 702
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv39.day: 2018-08-22T00:00:00.000Z
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv39, date: 2018-08-22T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv40: SWDeviceGenericIO/XSWC3.OnItvB.itv40 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv40.itv: 703
SWDeviceGenericIO/XSWC3.OnItvB.itv40.day: Thu Aug 23 00:00:00 UTC 2018
2018-09-28 15:15:59.695] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv40.itv: 703
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv40.day: 2018-08-23T00:00:00.000Z
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv40, date: 2018-08-23T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv41: SWDeviceGenericIO/XSWC3.OnItvB.itv41 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv41.itv: 703
SWDeviceGenericIO/XSWC3.OnItvB.itv41.day: Fri Aug 24 00:00:00 UTC 2018
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv41.itv: 703
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv41.day: 2018-08-24T00:00:00.000Z
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv41, date: 2018-08-24T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv42: SWDeviceGenericIO/XSWC3.OnItvB.itv42 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv42.itv: 703
SWDeviceGenericIO/XSWC3.OnItvB.itv42.day: Sat Aug 25 00:00:00 UTC 2018
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv42.itv: 703
2018-09-28 15:15:59.696] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv42.day: 2018-08-25T00:00:00.000Z
2018-09-28 15:15:59.697] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv42, date: 2018-08-25T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv43: SWDeviceGenericIO/XSWC3.OnItvB.itv43 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv43.itv: 704
SWDeviceGenericIO/XSWC3.OnItvB.itv43.day: Sun Aug 26 00:00:00 UTC 2018
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv43.itv: 704
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv43.day: 2018-08-26T00:00:00.000Z
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv43, date: 2018-08-26T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv44: SWDeviceGenericIO/XSWC3.OnItvB.itv44 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv44.itv: 702
SWDeviceGenericIO/XSWC3.OnItvB.itv44.day: Mon Aug 27 00:00:00 UTC 2018
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv44.itv: 702
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv44.day: 2018-08-27T00:00:00.000Z
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv44, date: 2018-08-27T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv45: SWDeviceGenericIO/XSWC3.OnItvB.itv45 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv45.itv: 704
SWDeviceGenericIO/XSWC3.OnItvB.itv45.day: Tue Aug 28 00:00:00 UTC 2018
2018-09-28 15:15:59.698] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv45.itv: 704
2018-09-28 15:15:59.699] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv45.day: 2018-08-28T00:00:00.000Z
2018-09-28 15:15:59.699] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv45, date: 2018-08-28T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.699] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv46: SWDeviceGenericIO/XSWC3.OnItvB.itv46 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv46.itv: 704
SWDeviceGenericIO/XSWC3.OnItvB.itv46.day: Wed Aug 29 00:00:00 UTC 2018
2018-09-28 15:15:59.704] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv46.itv: 704
2018-09-28 15:15:59.704] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv46.day: 2018-08-29T00:00:00.000Z
2018-09-28 15:15:59.704] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv46, date: 2018-08-29T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.704] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv47: SWDeviceGenericIO/XSWC3.OnItvB.itv47 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv47.itv: 705
SWDeviceGenericIO/XSWC3.OnItvB.itv47.day: Thu Aug 30 00:00:00 UTC 2018
2018-09-28 15:15:59.704] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv47.itv: 705
2018-09-28 15:15:59.704] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv47.day: 2018-08-30T00:00:00.000Z
2018-09-28 15:15:59.704] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv47, date: 2018-08-30T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv48: SWDeviceGenericIO/XSWC3.OnItvB.itv48 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv48.itv: 705
SWDeviceGenericIO/XSWC3.OnItvB.itv48.day: Fri Aug 31 00:00:00 UTC 2018
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv48.itv: 705
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv48.day: 2018-08-31T00:00:00.000Z
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:183 - device: KAI-0000000053, determining power usage history for relay 3, skip entry for itv48, date: 2018-08-31T00:00:00.000Z is before start time: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv49: SWDeviceGenericIO/XSWC3.OnItvB.itv49 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv49.itv: 706
SWDeviceGenericIO/XSWC3.OnItvB.itv49.day: Sat Sep 01 00:00:00 UTC 2018
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv49.itv: 706
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv49.day: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv49, date: 2018-09-01T00:00:00.000Z
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv50: SWDeviceGenericIO/XSWC3.OnItvB.itv50 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv50.itv: 706
SWDeviceGenericIO/XSWC3.OnItvB.itv50.day: Sun Sep 02 00:00:00 UTC 2018
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv50.itv: 706
2018-09-28 15:15:59.705] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv50.day: 2018-09-02T00:00:00.000Z
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv50, date: 2018-09-02T00:00:00.000Z
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv51: SWDeviceGenericIO/XSWC3.OnItvB.itv51 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv51.itv: 706
SWDeviceGenericIO/XSWC3.OnItvB.itv51.day: Mon Sep 03 00:00:00 UTC 2018
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv51.itv: 706
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv51.day: 2018-09-03T00:00:00.000Z
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv51, date: 2018-09-03T00:00:00.000Z
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv52: SWDeviceGenericIO/XSWC3.OnItvB.itv52 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv52.itv: 706
SWDeviceGenericIO/XSWC3.OnItvB.itv52.day: Tue Sep 04 00:00:00 UTC 2018
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv52.itv: 706
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv52.day: 2018-09-04T00:00:00.000Z
2018-09-28 15:15:59.706] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv52, date: 2018-09-04T00:00:00.000Z
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv53: SWDeviceGenericIO/XSWC3.OnItvB.itv53 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv53.itv: 707
SWDeviceGenericIO/XSWC3.OnItvB.itv53.day: Wed Sep 05 00:00:00 UTC 2018
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv53.itv: 707
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv53.day: 2018-09-05T00:00:00.000Z
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv53, date: 2018-09-05T00:00:00.000Z
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv54: SWDeviceGenericIO/XSWC3.OnItvB.itv54 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv54.itv: 707
SWDeviceGenericIO/XSWC3.OnItvB.itv54.day: Thu Sep 06 00:00:00 UTC 2018
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv54.itv: 707
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv54.day: 2018-09-06T00:00:00.000Z
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv54, date: 2018-09-06T00:00:00.000Z
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv55: SWDeviceGenericIO/XSWC3.OnItvB.itv55 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv55.itv: 708
SWDeviceGenericIO/XSWC3.OnItvB.itv55.day: Fri Sep 07 00:00:00 UTC 2018
2018-09-28 15:15:59.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv55.itv: 708
2018-09-28 15:15:59.708] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv55.day: 2018-09-07T00:00:00.000Z
2018-09-28 15:15:59.708] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv55, date: 2018-09-07T00:00:00.000Z
2018-09-28 15:15:59.713] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv56: SWDeviceGenericIO/XSWC3.OnItvB.itv56 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv56.itv: 708
SWDeviceGenericIO/XSWC3.OnItvB.itv56.day: Sat Sep 08 00:00:00 UTC 2018
2018-09-28 15:15:59.714] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv56.itv: 708
2018-09-28 15:15:59.714] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv56.day: 2018-09-08T00:00:00.000Z
2018-09-28 15:15:59.714] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv56, date: 2018-09-08T00:00:00.000Z
2018-09-28 15:15:59.714] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv57: SWDeviceGenericIO/XSWC3.OnItvB.itv57 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv57.itv: 708
SWDeviceGenericIO/XSWC3.OnItvB.itv57.day: Sun Sep 09 00:00:00 UTC 2018
2018-09-28 15:15:59.714] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv57.itv: 708
2018-09-28 15:15:59.714] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv57.day: 2018-09-09T00:00:00.000Z
2018-09-28 15:15:59.714] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv57, date: 2018-09-09T00:00:00.000Z
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv58: SWDeviceGenericIO/XSWC3.OnItvB.itv58 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv58.itv: 708
SWDeviceGenericIO/XSWC3.OnItvB.itv58.day: Mon Sep 10 00:00:00 UTC 2018
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv58.itv: 708
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv58.day: 2018-09-10T00:00:00.000Z
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv58, date: 2018-09-10T00:00:00.000Z
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv59: SWDeviceGenericIO/XSWC3.OnItvB.itv59 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv59.itv: 709
SWDeviceGenericIO/XSWC3.OnItvB.itv59.day: Tue Sep 11 00:00:00 UTC 2018
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv59.itv: 709
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv59.day: 2018-09-11T00:00:00.000Z
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv59, date: 2018-09-11T00:00:00.000Z
2018-09-28 15:15:59.715] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv60: SWDeviceGenericIO/XSWC3.OnItvB.itv60 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv60.itv: 768
SWDeviceGenericIO/XSWC3.OnItvB.itv60.day: Wed Sep 12 00:00:00 UTC 2018
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv60.itv: 768
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv60.day: 2018-09-12T00:00:00.000Z
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv60, date: 2018-09-12T00:00:00.000Z
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv1: SWDeviceGenericIO/XSWC3.OnItvB.itv1 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv1.itv: 1010
SWDeviceGenericIO/XSWC3.OnItvB.itv1.day: Thu Sep 13 00:00:00 UTC 2018
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv1.itv: 1010
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv1.day: 2018-09-13T00:00:00.000Z
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv1, date: 2018-09-13T00:00:00.000Z
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv2: SWDeviceGenericIO/XSWC3.OnItvB.itv2 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv2.itv: 709
SWDeviceGenericIO/XSWC3.OnItvB.itv2.day: Fri Sep 14 00:00:00 UTC 2018
2018-09-28 15:15:59.716] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv2.itv: 709
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv2.day: 2018-09-14T00:00:00.000Z
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv2, date: 2018-09-14T00:00:00.000Z
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv3: SWDeviceGenericIO/XSWC3.OnItvB.itv3 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv3.itv: 710
SWDeviceGenericIO/XSWC3.OnItvB.itv3.day: Sat Sep 15 00:00:00 UTC 2018
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv3.itv: 710
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv3.day: 2018-09-15T00:00:00.000Z
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv3, date: 2018-09-15T00:00:00.000Z
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv4: SWDeviceGenericIO/XSWC3.OnItvB.itv4 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv4.itv: 710
SWDeviceGenericIO/XSWC3.OnItvB.itv4.day: Sun Sep 16 00:00:00 UTC 2018
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv4.itv: 710
2018-09-28 15:15:59.717] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv4.day: 2018-09-16T00:00:00.000Z
2018-09-28 15:15:59.723] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv4, date: 2018-09-16T00:00:00.000Z
2018-09-28 15:15:59.723] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv5: SWDeviceGenericIO/XSWC3.OnItvB.itv5 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv5.itv: 711
SWDeviceGenericIO/XSWC3.OnItvB.itv5.day: Mon Sep 17 00:00:00 UTC 2018
2018-09-28 15:15:59.723] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv5.itv: 711
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv5.day: 2018-09-17T00:00:00.000Z
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv5, date: 2018-09-17T00:00:00.000Z
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv6: SWDeviceGenericIO/XSWC3.OnItvB.itv6 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv6.itv: 711
SWDeviceGenericIO/XSWC3.OnItvB.itv6.day: Tue Sep 18 00:00:00 UTC 2018
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv6.itv: 711
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv6.day: 2018-09-18T00:00:00.000Z
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv6, date: 2018-09-18T00:00:00.000Z
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv7: SWDeviceGenericIO/XSWC3.OnItvB.itv7 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv7.itv: 711
SWDeviceGenericIO/XSWC3.OnItvB.itv7.day: Wed Sep 19 00:00:00 UTC 2018
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv7.itv: 711
2018-09-28 15:15:59.724] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv7.day: 2018-09-19T00:00:00.000Z
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv7, date: 2018-09-19T00:00:00.000Z
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv8: SWDeviceGenericIO/XSWC3.OnItvB.itv8 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv8.itv: 711
SWDeviceGenericIO/XSWC3.OnItvB.itv8.day: Thu Sep 20 00:00:00 UTC 2018
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv8.itv: 711
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv8.day: 2018-09-20T00:00:00.000Z
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv8, date: 2018-09-20T00:00:00.000Z
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv9: SWDeviceGenericIO/XSWC3.OnItvB.itv9 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv9.itv: 839
SWDeviceGenericIO/XSWC3.OnItvB.itv9.day: Fri Sep 21 00:00:00 UTC 2018
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv9.itv: 839
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv9.day: 2018-09-21T00:00:00.000Z
2018-09-28 15:15:59.725] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv9, date: 2018-09-21T00:00:00.000Z
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv10: SWDeviceGenericIO/XSWC3.OnItvB.itv10 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv10.itv: 712
SWDeviceGenericIO/XSWC3.OnItvB.itv10.day: Sat Sep 22 00:00:00 UTC 2018
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv10.itv: 712
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv10.day: 2018-09-22T00:00:00.000Z
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv10, date: 2018-09-22T00:00:00.000Z
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv11: SWDeviceGenericIO/XSWC3.OnItvB.itv11 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv11.itv: 713
SWDeviceGenericIO/XSWC3.OnItvB.itv11.day: Sun Sep 23 00:00:00 UTC 2018
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv11.itv: 713
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv11.day: 2018-09-23T00:00:00.000Z
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv11, date: 2018-09-23T00:00:00.000Z
2018-09-28 15:15:59.726] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv12: SWDeviceGenericIO/XSWC3.OnItvB.itv12 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv12.itv: 713
SWDeviceGenericIO/XSWC3.OnItvB.itv12.day: Mon Sep 24 00:00:00 UTC 2018
2018-09-28 15:15:59.727] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv12.itv: 713
2018-09-28 15:15:59.727] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv12.day: 2018-09-24T00:00:00.000Z
2018-09-28 15:15:59.727] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv12, date: 2018-09-24T00:00:00.000Z
2018-09-28 15:15:59.727] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv13: SWDeviceGenericIO/XSWC3.OnItvB.itv13 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv13.itv: 720
SWDeviceGenericIO/XSWC3.OnItvB.itv13.day: Tue Sep 25 00:00:00 UTC 2018
2018-09-28 15:15:59.727] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv13.itv: 720
2018-09-28 15:15:59.727] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv13.day: 2018-09-25T00:00:00.000Z
2018-09-28 15:15:59.733] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv13, date: 2018-09-25T00:00:00.000Z
2018-09-28 15:15:59.733] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv14: SWDeviceGenericIO/XSWC3.OnItvB.itv14 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv14.itv: 847
SWDeviceGenericIO/XSWC3.OnItvB.itv14.day: Wed Sep 26 00:00:00 UTC 2018
2018-09-28 15:15:59.733] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv14.itv: 847
2018-09-28 15:15:59.733] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv14.day: 2018-09-26T00:00:00.000Z
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv14, date: 2018-09-26T00:00:00.000Z
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv15: SWDeviceGenericIO/XSWC3.OnItvB.itv15 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv15.itv: 714
SWDeviceGenericIO/XSWC3.OnItvB.itv15.day: Thu Sep 27 00:00:00 UTC 2018
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv15.itv: 714
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv15.day: 2018-09-27T00:00:00.000Z
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv15, date: 2018-09-27T00:00:00.000Z
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:124 - device: KAI-0000000053, itv16: SWDeviceGenericIO/XSWC3.OnItvB.itv16 [ST]
SWDeviceGenericIO/XSWC3.OnItvB.itv16.itv: 317
SWDeviceGenericIO/XSWC3.OnItvB.itv16.day: Fri Sep 28 00:00:00 UTC 2018
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:128 - device: KAI-0000000053, itv16.itv: 317
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@getPowerUsageHistoryDataFromRelay:137 - device: KAI-0000000053, itv16.day: 2018-09-28T00:00:00.000Z
2018-09-28 15:15:59.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.c.Iec61850PowerUsageHistoryCommand@timePeriodContainsDateTime:194 - device: KAI-0000000053, TimePeriod (2018-09-01T00:00:00.000Z - 2018-09-30T00:00:00.000Z), determining power usage history for relay 3, include entry for itv16, date: 2018-09-28T00:00:00.000Z
2018-09-28 15:15:59.735] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-28 15:15:59.735] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.p.PublicLightingGetPowerUsageHistoryRequestMessageProcessor@handleDeviceResponse:84 - Override for handleDeviceResponse() by PublicLightingGetPowerUsageHistoryRequestMessageProcessor
2018-09-28 15:15:59.736] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: GET_POWER_USAGE_HISTORY with message priority: 4
2018-09-28 15:15:59.754] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-13] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: GET_POWER_USAGE_HISTORY, Start time: 2018-09-28T15:15:59.419Z, end time: 2018-09-28T15:15:59.754Z, total time in milliseconds: 335
2018-09-28 15:15:59.757] [osgp-tst-03] [Thread-200] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:366 - associationClosed() for device: KAI-0000000053, IOException: Connection disconnected by client
2018-09-28 15:15:59.757] [osgp-tst-03] [Thread-200] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:371 - No event notifications received from device: KAI-0000000053
2018-09-28 15:15:59.984] [osgp-tst-03] [protocolLogItemRequestsMessageListenerContainer-2] INFO o.o.l.i.j.ProtocolLogItemRequestMessageListener@onMessage:38 - Received protocol log item request message off type [IEC61850_LOG_ITEM]
2018-09-28 15:16:00.015] [osgp-tst-03] [DefaultMessageListenerContainer-1] INFO o.o.c.i.j.p.ProtocolResponseMessageListener@onMessage:35 - Received protocol response message with correlationUid [LianderNetManagement|||KAI-0000000053|||20180928151558848] and type [GET_POWER_USAGE_HISTORY]
2018-09-28 15:16:00.037] [osgp-tst-03] [DefaultMessageListenerContainer-1] INFO o.o.c.a.s.DeviceResponseMessageService@processMessage:61 - Processing protocol response message with correlation uid [LianderNetManagement|||KAI-0000000053|||20180928151558848]
2018-09-28 15:16:00.037] [osgp-tst-03] [DefaultMessageListenerContainer-1] INFO o.o.c.a.s.DeviceResponseMessageService@processMessage:68 - Handling protocol response message.
2018-09-28 15:16:00.037] [osgp-tst-03] [DefaultMessageListenerContainer-1] INFO o.o.c.a.s.DeviceResponseMessageService@handleProtocolResponseMessage:187 - Sending domain response message for message of type GET_POWER_USAGE_HISTORY for device KAI-0000000053 with correlationUid LianderNetManagement|||KAI-0000000053|||20180928151558848.
2018-09-28 15:16:00.125] [osgp-tst-03] [domainPublicLightingIncomingOsgpCoreResponsesMessageListenerContainer-2] INFO o.o.a.d.p.i.j.c.OsgpCoreResponseMessageListener@onMessage:41 - Received message of type: GET_POWER_USAGE_HISTORY
2018-09-28 15:16:00.142] [osgp-tst-03] [domainPublicLightingIncomingOsgpCoreResponsesMessageListenerContainer-2] INFO o.o.a.d.p.i.j.c.m.PublicLightingPowerUsageHistoryResponseMessageProcessor@processMessage:87 - Calling application service function to handle response: GET_POWER_USAGE_HISTORY
2018-09-28 15:16:00.142] [osgp-tst-03] [domainPublicLightingIncomingOsgpCoreResponsesMessageListenerContainer-2] INFO o.o.a.d.p.a.s.DeviceMonitoringService@handleGetPowerUsageHistoryResponse:83 - handleResponse called for device: KAI-0000000053 for organisation: LianderNetManagement for messageType: GET_POWER_USAGE_HISTORY
```
