## GetFirmwareVersion request

### Description
GetFirmwareVersion is a request to retrieve the firmware version(s) of a device. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetGetFirmwareVersionResponse](GetGetFirmwareVersionResponse.md) returns the version(s). The response contains the DeviceIdentification and CorrelationUid which is received from the GetFirmwareVersion request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

