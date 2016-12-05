## GetAdministrativeStatus request

### Description
GetAdministrativeStatus is a request to retrieve the current AdministrativeStatus setting from a device. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetGetAdministrativeStatusResponse](GetGetAdministrativeStatusResponse.md) returns if the setting GetAdministrativeStatus is enabled. The response contains the DeviceIdentification and CorrelationUid which is received from the GetAdministrativeStatus request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

