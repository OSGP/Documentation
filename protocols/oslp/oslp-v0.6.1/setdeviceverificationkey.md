<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# SetDeviceVerificationKey

## Description

Request to switch to a new Platform public key used for verifying OSLP envelopes by the device. The base-64 encoded version of the key will be sent to the device, which is equivalent to the content of a PEM file \(only the certificate chunk, not the headers\).

## Message definitions

```javascript
message SetDeviceVerificationKeyRequest {
    required bytes certificateChunk = 1; // [(nanopb).max_size = 138]; // Verification key / public key of the platform to check the validity of an incoming message.
}

message SetDeviceVerificationKeyResponse {
    required Status status = 1;
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
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetDeviceVerificationKeyRequest>
         <!--type: Identification-->
         <ns1:DeviceIdentification>device-01</ns1:DeviceIdentification>
         <!--type: VerificationKey-->
         <ns1:VerificationKey>MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEow7CWR7EiNDRt1XQ/h1UrLE24zY3BkA582mfiywZ2h8tPkwleCBfcyLeZvS0T4NGz+zzO5CZphlD1TQtjL/ZXg==</ns1:VerificationKey>
      </ns1:SetDeviceVerificationKeyRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetDeviceVerificationKeyAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160305122132785</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetDeviceVerificationKeyAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetDeviceVerificationKeyAsyncRequest>
         <ns1:AsyncRequest>
            <!--type: CorrelationUid-->
            <ns:CorrelationUid>LianderNetManagement|||device-01|||20160305122132785</ns:CorrelationUid>
            <!--type: Identification-->
            <ns:DeviceId>device-01</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetDeviceVerificationKeyAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetDeviceVerificationKeyResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetDeviceVerificationKeyResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP messages:

```javascript
setDeviceVerificationKeyRequest {
  certificateChunk: "MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEow7CWR7EiNDRt1XQ/h1UrLE24zY3BkA582mfiywZ2h8tPkwleCBfcyLeZvS0T4NGz+zzO5CZphlD1TQtjL/ZXg=="
}

setDeviceVerificationKeyResponse {
  status: OK
}
```

