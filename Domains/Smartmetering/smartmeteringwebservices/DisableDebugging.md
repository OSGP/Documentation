## DisableDebugging request

### Description
Disable debugging for a device. Communication with the device will be logged and made available through [FindMessageLogs](./FindMessageLogs.md),

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetDisableDebuggingResponse](./GetDisableDebuggingResponse.md) returns the result status. The response contains the DeviceIdentification and CorrelationUid which is received from the GetDisableDebuggingRequest request.

### References

XSD: [sm-management.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-management.xsd)

WSDL: [SmartMeteringManagement.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringManagement.wsdl)

