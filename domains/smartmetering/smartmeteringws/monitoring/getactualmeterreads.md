# GetActualMeterReads

## Description

GetActualMeterReads is a request to retrieve the actual import and export meter reads from an E-meter. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetActualMeterReadsResponse](getactualmeterreadsresponse.md) returns the retrieved meter reads values, unit and log time from the GetActualMeterReads request. The response contains the DeviceIdentification and CorrelationUid which is received from the GetActualMeterReads request.

## References

XSD: [sm-monitoring.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-monitoring.xsd)

WSDL: [SmartMeteringMonitoring.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringMonitoring.wsdl)

