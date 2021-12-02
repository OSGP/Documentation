# SetAdministrativeStatus

## Description

SetAdministrativeStatusis a request to set the AdministrativeStatus on a device. The request needs the DeviceIdentification and Enabled parameter.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetSetAdministrativeStatusResponse](getsetadministrativestatusresponse.md) returns if the setting SetAdministrativeStatus is enabled. The response contains the DeviceIdentification and CorrelationUid which is received from the SetAdministrativeStatus request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

