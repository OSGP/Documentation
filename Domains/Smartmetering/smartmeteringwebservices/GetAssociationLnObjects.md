## GetAssociationLnObjects request

### Description
GetAssociationLnObjects is a request to get the Association LN object tree from an E-meter. The request is sent with the DeviceIdentification number from the desired device.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetGetAssociationLnObjectsResponse](GetGetAssociationLnObjectsResponse.md) returns the result values from getting the Association LN object. The response contains the DeviceIdentification and CorrelationUid which is received from the GetAssociationLnObjects request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)

