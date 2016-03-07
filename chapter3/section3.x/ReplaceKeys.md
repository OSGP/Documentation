## ReplaceKeys request

### Description
ReplaceKeys is a request to change the keys on an E-meter. The request needs the DeviceIdentification, an AuthenticationKey and an EncryptionKey.

[GetReplaceKeysResponse](GetReplaceKeysResponse.md) returns if the result is successful from the ReplaceKeys request. The response request contains the DeviceIdentification and CorrelationUid which is received from the ReplaceKeys request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

