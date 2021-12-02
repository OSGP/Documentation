# EnableDebugging

## Description

Enable debugging for a device. Communication with the device will be logged and made available through [FindMessageLogs](findmessagelogs.md),

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetEnableDebuggingResponse](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetEnableDebuggingResponse.md) returns the result status. The response contains the DeviceIdentification and CorrelationUid which is received from the GetEnableDebuggingRequest request.

## References

XSD: [sm-management.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-management.xsd)

WSDL: [SmartMeteringManagement.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringManagement.wsdl)

