## SetAdministrativeStatus request

### Description
SetAdministrativeStatusis a request to set the AdministrativeStatus on a device. The request needs the DeviceIdentification and Enabled parameter.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSetAdministrativeStatusResponse](GetGetAdministrativeStatusResponse.md) returns if the setting SetAdministrativeStatus is enabled. The response request contains the DeviceIdentification and CorrelationUid which is received from the SetAdministrativeStatus request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)


