## PeriodicMeterReads request

### Description
PeriodicMeterReads is a request to retrieve the periodic import and export meter reads from an E-meter. The periode can be DAILY, MONTHLY or INTERVAL. The request needs the DeviceIdentification.

[GetPeriodicMeterReadsResponse](GetPeriodicMeterReadsResponse.md) returns the retrieved meter reads values, unit and logtime from the PeriodicMeterReads request. The response request contains the DeviceIdentification and CorrelationUid which is received from the PeriodicMeterReads request.

### References

XSD: [sm-monitoring.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-monitoring.xsd)

WSDL: [SmartMeteringMonitoring.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringMonitoring.wsdl)
