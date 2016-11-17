## EnableDebugging request

### Description
Enable debugging for a device. Communication with the device will be logged and made available through [FindMessageLogs](./FindMessageLogs.md),

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetEnableDebuggingResponse](./GetEnableDebuggingResponse.md) returns the result status. The response request contains the DeviceIdentification and CorrelationUid which is received from the SynchronizeTime request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)

