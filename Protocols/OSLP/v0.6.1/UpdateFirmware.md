## UpdateFirmware messages

### Description

Request for a device to download and install new firmware. The request contains a URL defining the location of the new firmware image. The device should download the firmware from that location.

Response communicates status.

### Message definitions

``` json
message UpdateFirmwareRequest {
    required string firmwareDomain = 1; // [(nanopb).max_size = 100]; // Servername
    required string firmwareUrl = 2; // [(nanopb).max_size = 255]; // /firmware/PSLD/RXX
}

message UpdateFirmwareResponse {
    required Status status = 1;
}
```

### Data types

``` json
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:fir="http://www.opensmartgridplatform.org/schemas/firmwaremanagement/2014/10">
   <soapenv:Header>
	   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
	   <com:UserName>liander gebruiker</com:UserName>
	   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>   
      <fir1:UpdateFirmwareRequest xmlns:fir1="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
         <!--type: Identification-->
         <fir1:DeviceIdentification>device-01</fir1:DeviceIdentification>
         <!--anonymous type-->
         <fir1:FirmwareIdentification>SSLD-V17</fir1:FirmwareIdentification>		 
      </fir1:UpdateFirmwareRequest>	  
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>   
      <ns2:UpdateFirmwareAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>		 
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160104145959438</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>			
         </ns2:AsyncResponse>		 
      </ns2:UpdateFirmwareAsyncResponse>	  
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:fir="http://www.opensmartgridplatform.org/schemas/firmwaremanagement">
   <soapenv:Header>
   <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
   <com:UserName>liander gebruiker</com:UserName>
   <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <fir1:UpdateFirmwareAsyncRequest xmlns:fir1="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
         <fir1:AsyncRequest>
            <!--type: CorrelationUid-->
            <com:CorrelationUid>LianderNetManagement|||device-01|||20160104145959438</com:CorrelationUid>
            <!--type: Identification-->
            <com:DeviceId>device-01</com:DeviceId>
         </fir1:AsyncRequest>
      </fir1:UpdateFirmwareAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:UpdateFirmwareResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:UpdateFirmwareResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP UpdateFirmwareRequest sent to 'device-01' to update firmware:
``` json
updateFirmwareRequest {
  firmwareDomain: "flexovltest.cloudapp.net"
  firmwareUrl: "/firmware/SSLD/SSLD-V17.hex"
}
```

OSLP UpdateFirmwareResponse sent to the platform:
``` json
updateFirmwareResponse {
  status: OK
}
```