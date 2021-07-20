# GetActualMeterReadsGas

## Description

GetActualMeterReadsGas is a request to retrieve the actual import and export meter reads from a G-meter. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetActualMeterReadsGasResponse](getactualmeterreadsgasresponse.md) returns the retrieved meter reads values, unit and log time from the GetActualMeterReadsGas request. The response contains the DeviceIdentification and CorrelationUid which is received from the GetActualMeterReadsGas request.

## References

XSD: [sm-monitoring.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-monitoring.xsd)

WSDL: [SmartMeteringMonitoring.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringMonitoring.wsdl)

