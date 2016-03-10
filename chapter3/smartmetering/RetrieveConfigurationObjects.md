## RetrieveConfigurationObjects request

### Description
RetrieveConfigurationObjects is a request to get the entire configuration objects tree and values from an E-meter. Because this is a big operation for a device, it can take up to 30 minutes to retrieve all the response information.
The request is send with the DeviceIdentification number from the desired device.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetRetrieveConfigurationObjectsResponse](GetRetrieveConfigurationObjectsResponse.md) returns the result values from getting the configuration objects. The response request contains the DeviceIdentification and CorrelationUid which is received from the RetrieveConfigurationObjects request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

