## SwitchConfiguration messages

### Description

Request to switch from the current (active) configuration set to the other configuration set, indicated by the configuration set index.

### Message definitions

```json
message SwitchConfigurationRequest {
    required bytes newConfigurationSet = 1; // [(nanopb).max_count = 1]; // The index of the configuration set (0,1).
}

message SwitchConfigurationResponse {
    required Status status = 1; // FIRMWARE_EVENTS_CONFIGURATION_CHANGED Event will be sent, after the Configuration change.
}
```

### Datatypes

``` json
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

### Example

Soap requests and responses sent to and from platform:
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SwitchConfigurationRequest>
         <!--type: Identification-->
         <ns1:DeviceIdentification>device-01</ns1:DeviceIdentification>
         <!--type: int, 0 or 1-->
         <ns1:ConfigurationBank>1</ns1:ConfigurationBank>
      </ns1:SwitchConfigurationRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SwitchConfigurationAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160313210830055</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SwitchConfigurationAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SwitchConfigurationAsyncRequest>
         <ns1:AsyncRequest>
            <!--type: CorrelationUid-->
            <ns:CorrelationUid>LianderNetManagement|||device-01|||20160313210830055</ns:CorrelationUid>
            <!--type: Identification-->
            <ns:DeviceId>device-01</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SwitchConfigurationAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SwitchConfigurationResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SwitchConfigurationResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP messages:
```json
switchConfigurationRequest {
  newConfigurationSet: "1"
}

switchConfigurationResponse {
  status: OK
}
```
