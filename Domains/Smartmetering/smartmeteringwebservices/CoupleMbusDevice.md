## CoupleMbusDevice request

### Description
CoupleMbusDevice is a request to couple a gateway and a m-bus device. The request needs the following parameters:
- DeviceIdentification
- MbusDeviceIdentification

All requests have similar response behaviour which is described in [ResponseMessages](ResponseMessages.md)

[GetCoupleMbusDeviceResponse](GetCoupleMbusDeviceResponse.md) returns if the result is successful from the request. The response request contains the DeviceIdentification and CorrelationUid which is received from the CoupleMbusDevice request.

### References

XSD: [sm-installation.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-installation.xsd)

WSDL: [SmartMeteringInstallation.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringInstallation.wsdl)
