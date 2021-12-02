# FindMessageLogs

## Description

FindMessageLogs is a request to retrieve logged messages for a device. The request needs the DeviceIdentification and a Page number to return.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetFindMessageLogsResponse](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetFindMessageLogsResponse.md) returns if the result is successful from the request. The response contains the DeviceIdentification and CorrelationUid which is received from the FindMessageLogs request.

**Note: This functionality also exists in the admin device management service. It was duplicated here to be implemented asynchronously, as there is no support for asynchronous requests triggering a notification service in the admin project. As soon as asynchronous requests and notifications are implemented throughout the OSGP platform, this method should be removed in favour of the admin implementation.**

## References

XSD: [sm-management.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-management.xsd)

WSDL: [SmartMeteringManagement.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringManagement.wsdl)

