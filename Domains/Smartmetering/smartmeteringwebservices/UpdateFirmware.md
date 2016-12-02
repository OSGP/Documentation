## UpdateFirmware request

### Description
UpdateFirmware is a request to install another firmware version(s) on a device. The request needs the DeviceIdentification, and the FirmwareIdentifier that was appointed to the firmware file when the firmware was added to the platform.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetUpdateFirmwareResponse](GetUpdateFirmwareResponse.md) returns the version(s). The response request contains the DeviceIdentification and CorrelationUid which is received from the UpdateFirmware request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

