## DeCoupleMBusDevice request

### Description
DeCoupleMBusDevice is a request to decouple an MBus device (such as a gas meter) from a device to the OSGP database. The request needs the following parameters:
- DeviceIdentification
- MBusDeviceIdentification

All requests have similar response behaviour which is described in [ResponseMessages](ResponseMessages.md)

[GetDeCoupleMBusDeviceResponse](GetDeCoupleMBusDeviceResponse.md) returns if the result is successful from the  request. The response request contains the DeviceIdentification and CorrelationUid which is received from the DeCoupleMBusDevice request.

### References

XSD: [sm-installation.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/SmartMeteringInstallation.xsd)

WSDL: [SmartMeteringInstallation.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringInstallation.wsdl)
