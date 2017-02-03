## GetSpecificAttributeValue request

### Description
GetSpecificAttributeValue is a request to get a specific attribute value from an ObisCode from an E-meter.

The request is sent with the DeviceIdentification number from the desired device and dlms specific values that point to the object: 
- a ClassId
- an ObisCode 
- and an AttributeId

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSpecificAttributeValueResponse](GetSpecificAttributeValueResponse.md) returns the result values as text (String) from getting the configuration object. The response contains the DeviceIdentification and CorrelationUid which is received from the GetSpecificAttributeValue request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringAdhoc.wsdl)

