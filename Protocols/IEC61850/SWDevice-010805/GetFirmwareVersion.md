## GetFirmwareVersion messages

### Description

Request which queries the device for its current firmware version.

Response which returns the result of the request and, if 'result = OK' contains the firmware version.

### IEC61850 Fields

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|**DESCRIPTION**|
|---|---|---|---|---|
|SWDeviceGenericIO/CSLC.FuncFwDw|ST|curVer|VisString32|Current functional firmware version|
|SWDeviceGenericIO/CSLC.ScyFwDw|ST|curVer|VisString32|Current security firmware version|

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:fman="http://www.opensmartgridplatform.org/schemas/firmwaremanagement">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>Sander</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <fman:GetFirmwareVersionRequest xmlns:fman="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
         <!--type: Identification-->
         <fman:DeviceIdentification>KAI-0000000053</fman:DeviceIdentification>
      </fman:GetFirmwareVersionRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetFirmwareVersionAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180924135200412</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetFirmwareVersionAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:fman="http://www.opensmartgridplatform.org/schemas/firmwaremanagement">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>Sander</com:UserName>
      <com:ApplicationName>SoapUI</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <fman:GetFirmwareVersionAsyncRequest xmlns:fman="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10">
         <fman:AsyncRequest>
            <!--type: CorrelationUid-->
            <com:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180924135200412</com:CorrelationUid>
            <!--type: Identification-->
            <com:DeviceId>KAI-0000000053</com:DeviceId>
         </fman:AsyncRequest>
      </fman:GetFirmwareVersionAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetFirmwareVersionResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/firmwaremanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:FirmwareVersion>
            <ns2:FirmwareModuleType>FUNCTIONAL</ns2:FirmwareModuleType>
            <ns2:Version>01_21_01A</ns2:Version>
         </ns2:FirmwareVersion>
         <ns2:FirmwareVersion>
            <ns2:FirmwareModuleType>SECURITY</ns2:FirmwareModuleType>
            <ns2:Version>01_06_02A</ns2:Version>
         </ns2:FirmwareVersion>
      </ns2:GetFirmwareVersionResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of the data received from the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: GetFirmwareVersion {
  CSLC.FuncFwDw[ST].curVer: 01_21_01A
  CSLC.ScyFwDw[ST].curVer: 01_06_02A
}
```
