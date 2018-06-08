## AddDevice request

### Description
AddDevice is a request to add a device to the OSGP database. For the list of parameters, see the .xsd file (link below). 

All requests have similar response behaviour which is described in [ResponseMessages](ResponseMessages.md)

[GetAddDeviceResponse](GetAddDeviceResponse.md) returns if the result is successful from the request. The response contains the DeviceIdentification and CorrelationUid which is received from the AddDevice request.

### References

XSD: [sm-installation.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-installation.xsd)

WSDL: [SmartMeteringInstallation.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringInstallation.wsdl)

### Example scenario

```
  Scenario: Add a new device
    When receiving a smartmetering add device request
      | DeviceIdentification  | TEST1024000000001 |
      | DeviceType            | SMART_METER_E  |
      | CommunicationMethod   | GPRS  |
      | CommunicationProvider | KPN   |
      | ICC_id                | 1234  |
      | DSMR_version          | 4.2.2 |
      | Supplier              | Kaifa |
      | HLS3_active           | false |
      | HLS4_active           | false |
      | HLS5_active           | true  |
      | Master_key            | m_key |
      | Authentication_key    | a_key |
      | Encryption_key        | e_key |
    Then the get add device response should be returned
      | DeviceIdentification  | TEST1024000000001 |
      | Result                | OK                |
    And the dlms device with identification "TEST1024000000001" exists
    And a request to the device can be performed after activation
    And the stored keys are not equal to the received keys
```    

### Example XML Message

``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:ns1="http://www.alliander.com/schemas/osgp/smartmetering/sm-installation/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>AutomaticTest</ns:ApplicationName>
      <ns:UserName>SoapUI</ns:UserName>
      <ns:OrganisationIdentification>test-org</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:AddDeviceRequest>
         <ns1:Device>
            <!--Optional:-->
            <ns1:Device_Identification>TEST1024000000001</ns1:Device_Identification>
            <!--Optional:-->
            <ns1:Device_type>SMART_METER_E</ns1:Device_type>
            <!--Optional:-->
            <ns1:Communication_method>GPRS</ns1:Communication_method>
            <!--Optional:-->
            <ns1:Communication_provider>KPN</ns1:Communication_provider>
            <!--Optional:-->
            <ns1:ICC_id>icc_id</ns1:ICC_id>
            <!--Optional:-->
            <ns1:DSMR_version>4.2.2</ns1:DSMR_version>
            <!--Optional:-->
            <ns1:Supplier>Kaifa</ns1:Supplier>
            <!--Optional:-->
            <ns1:HLS3_active>false</ns1:HLS3_active>
            <!--Optional:-->
            <ns1:HLS4_active>false</ns1:HLS4_active>
            <!--Optional:-->
            <ns1:HLS5_active>true</ns1:HLS5_active>
            <!--Optional:-->
            <ns1:Master_key>m_key</ns1:Master_key>
            <!--Optional:-->
            <ns1:Global_encryption_unicast_key>e_key</ns1:Global_encryption_unicast_key>
            <!--Optional:-->
            <ns1:Authentication_key>a_key</ns1:Authentication_key>
            <ns1:Delivery_date>2017-05-17 06:16:57.07</ns1:Delivery_date>
         </ns1:Device>
      </ns1:AddDeviceRequest>
   </soapenv:Body>
</soapenv:Envelope>
```
