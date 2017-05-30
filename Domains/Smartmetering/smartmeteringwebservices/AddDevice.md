## AddDevice request

### Description
AddDevice is a request to add a device to the OSGP database. The request needs the following parameters:
- DeviceIdentification
- Device_type
- Communication_method
- Communication_provider
- ICC_id
- DSMR_version
- Supplier
- HLS3_active
- HLS4_active
- HLS5_active
- Master_key
- Global_encryption_unicast_key
- Authentication_key 
- Delivery_date

All requests have similar response behaviour which is described in [ResponseMessages](ResponseMessages.md)

[GetAddDeviceResponse](GetAddDeviceResponse.md) returns if the result is successful from the request. The response contains the DeviceIdentification and CorrelationUid which is received from the AddDevice request.

### References

XSD: [sm-installation.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-installation.xsd)

WSDL: [SmartMeteringInstallation.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringInstallation.wsdl)
