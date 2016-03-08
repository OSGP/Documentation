## ActualMeterReads request

### Description
ActualMeterReads is a request to retrieve the actual import and export meter reads from an E-meter. The request needs the DeviceIdentification.

[GetActualMeterReadsResponse](GetActualMeterReadsResponse.md) returns the retrieved meter reads values, unit and logtime from the ActualMeterReads request. The response request contains the DeviceIdentification and CorrelationUid which is received from the ActualMeterReads request.

### References

XSD: [sm-monitoring.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-monitoring.xsd)

WSDL: [SmartMeteringMonitoring.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringMonitoring.wsdl)
