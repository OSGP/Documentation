# UpdateDeviceSslCertification

## Description

Request to download a new SSL certificate from the certificate server. The device will be given the domain name and URL where the certificate is located.

## Message definitions

```javascript
message UpdateDeviceSslCertificationRequest {
    required string certificateDomain = 1; // [(nanopb).max_size = 100]; // The domain name of the certificate Server.
    required string certificateUrl = 2; // [(nanopb).max_size = 255];    // The relative path of the certificate.
}

message UpdateDeviceSslCertificationResponse {
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
      <ns1:UpdateDeviceSslCertificationRequest>
         <!--type: Identification-->
         <ns1:DeviceIdentification>device-01</ns1:DeviceIdentification>
         <ns1:Certification>
            <ns1:certificateDomain>cert-server</ns1:certificateDomain>
            <ns1:certificateUrl>/certs/new-cert.pem</ns1:certificateUrl>
         </ns1:Certification>
      </ns1:UpdateDeviceSslCertificationRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:UpdateDeviceSslCertificationAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160305115500062</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:UpdateDeviceSslCertificationAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Kevin</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:UpdateDeviceSslCertificationAsyncRequest>
         <ns1:AsyncRequest>
            <!--type: CorrelationUid-->
            <ns:CorrelationUid>LianderNetManagement|||device-01|||20160305115500062</ns:CorrelationUid>
            <!--type: Identification-->
            <ns:DeviceId>device-01</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:UpdateDeviceSslCertificationAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:UpdateDeviceSslCertificationResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/devicemanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:UpdateDeviceSslCertificationResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP messages:

```javascript
updateDeviceSslCertificationRequest {
  certificateDomain: "cert-server"
  certificateUrl: "/certs/new-cert.pem"
}

updateDeviceSslCertificationResponse {
  status: OK
}
```

