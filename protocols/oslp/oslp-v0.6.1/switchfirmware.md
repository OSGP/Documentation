<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# SwitchFirmware

## Description

Request to switch from the current firmware version to the other firmware version, indicated by the argument newFirmwareVersion.

## Message definitions

```javascript
message SwitchFirmwareRequest {
    required string newFirmwareVersion = 1; // [(nanopb).max_size = 6]; // The version of the firmware which should be installed. 
}

message SwitchFirmwareResponse {
    required Status status = 1; // FIRMWARE_EVENTS_ACTIVATING Event will be sent, after the firmware change has completed.
}
```

## Datatypes

```javascript
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SwitchFirmwareRequest>
         <!--type: Identification-->
         <ns1:DeviceIdentification>device-01</ns1:DeviceIdentification>
         <!--type: string-->
         <ns1:Version>W0311g</ns1:Version>
      </ns1:SwitchFirmwareRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SwitchFirmwareAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160313211917467</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SwitchFirmwareAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SwitchFirmwareAsyncRequest>
         <ns1:AsyncRequest>
            <!--type: CorrelationUid-->
            <ns:CorrelationUid>LianderNetManagement|||device-01|||20160313211917467</ns:CorrelationUid>
            <!--type: Identification-->
            <ns:DeviceId>device-01</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SwitchFirmwareAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SwitchFirmwareResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SwitchFirmwareResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP messages:

```javascript
switchFirmwareRequest {
  newFirmwareVersion: "W0311g"
}

switchFirmwareResponse {
  status: OK
}
```

