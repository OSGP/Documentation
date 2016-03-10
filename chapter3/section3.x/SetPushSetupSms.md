## SetPushSetupSms request

### Description
SetPushSetupSms is a request to set an endpoint in a device which tells the device where to connect to when it is waked up.
The request needs the DeviceIdentification, host URL and port.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSetPushSetupSmsResponse](GetSetPushSetupSmsResponse.md) returns the result from setting a SetPushSetupSms. The response request contains the DeviceIdentification and CorrelationUid which is received from the SetPushSetupSms request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

