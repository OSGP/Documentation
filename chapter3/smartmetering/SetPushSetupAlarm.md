## SetPushSetupAlarm request

### Description
SetPushSetupAlarm is a request to push a received alarm notification from a device to OSGP and to store it in the OSGP event table from the database. The request needs the DeviceIdentification, Host URL and port.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSetPushSetupAlarmResponse](GetSetPushSetupAlarmResponse.md) returns the result from setting a SetPushSetupAlarm. The response request contains the DeviceIdentification and CorrelationUid which is received from the SetPushSetupAlarm request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

