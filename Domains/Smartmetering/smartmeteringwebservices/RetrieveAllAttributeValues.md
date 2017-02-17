## RetrieveAllAttributeValues request

### Description
RetrieveAllAttributeValues is a request to get the all attribute values of all the objects in the device tree and values from an E-meter. Because this is a big operation for a device, it can take up to 30 minutes to retrieve all the response information.
The request is send with the DeviceIdentification number from the desired device.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetRetrieveAllAttributeValuesResponse](GetRetrieveAllAttributeValuesResponse.md) returns the result values from getting all the attribute values. The response request contains the DeviceIdentification and CorrelationUid which is received from the RetrieveAllAttributeValues request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)

