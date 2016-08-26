## DeCoupleMbusDevice request

### Description
DeCoupleMbusDevice is a request to decouple an Mbus device (such as a gas meter) from a device to the OSGP database. The request needs the following parameters:
- DeviceIdentification
- MbusDeviceIdentification

All requests have similar response behaviour which is described in [ResponseMessages](ResponseMessages.md)

[GetDeCoupleMbusDeviceResponse](GetDeCoupleMbusDeviceResponse.md) returns if the result is successful from the  request. The response request contains the DeviceIdentification and CorrelationUid which is received from the DeCoupleMbusDevice request.

### References

XSD: [sm-installation.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-installation.xsd)

WSDL: [SmartMeteringInstallation.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringInstallation.wsdl)
