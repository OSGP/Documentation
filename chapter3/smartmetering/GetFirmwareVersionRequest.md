## GetFirmwareVersionRequest request

### Description
GetFirmwareVersionRequest is a request to retrieve the firmware version(s) of a device. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetFirmwareVersionAsyncRequest](GetFirmwareVersionAsyncRequest.md) returns if the version(s). The response request contains the DeviceIdentification and CorrelationUid which is received from the GetFirmwareVersionRequest request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

