## ActualMeterReadsGas request

### Description
ActualMeterReadsGas is a request to retrieve the actual import and export meter reads from a G-meter. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetActualMeterReadsGasResponse](GetActualMeterReadsGasResponse.md) returns the retrieved meter reads values, unit and logtime from the ActualMeterReadsGas request. The response request contains the DeviceIdentification and CorrelationUid which is received from the ActualMeterReadsGas request.

### References

XSD: [sm-monitoring.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-monitoring.xsd)

WSDL: [SmartMeteringMonitoring.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringMonitoring.wsdl)
