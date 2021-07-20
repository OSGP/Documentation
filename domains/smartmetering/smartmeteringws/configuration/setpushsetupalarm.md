# SetPushSetupAlarm

## Description

SetPushSetupAlarm is a request to define the destination of the TCP message that is optionally sent by the device. The request needs the DeviceIdentification, Host URL and port.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetSetPushSetupAlarmResponse](getsetpushsetupalarmresponse.md) returns the result from setting a SetPushSetupAlarm. The response contains the DeviceIdentification and CorrelationUid which is received from the SetPushSetupAlarm request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

