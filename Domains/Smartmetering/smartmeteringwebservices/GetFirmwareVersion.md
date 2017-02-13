## GetFirmwareVersion request

### Description
GetFirmwareVersion is a request to retrieve the firmware version(s) of a device. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetGetFirmwareVersionResponse](GetGetFirmwareVersionResponse.md) returns the version(s). The response contains the DeviceIdentification and CorrelationUid which is received from the GetFirmwareVersion request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

