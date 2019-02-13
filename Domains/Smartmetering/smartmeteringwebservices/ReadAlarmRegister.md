## ReadAlarmRegister request

### Description
ReadAlarmRegister is a request to retrieve the query alarm register. A notification will be sent and the query will be stored in the database. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetReadAlarmRegisterResponse](GetReadAlarmRegisterResponse.md) returns the alarm notifications from the ReadAlarmRegister request. The response contains the DeviceIdentification and CorrelationUid which is received from the ReadAlarmRegister request.

### References

XSD: [sm-monitoring.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-monitoring.xsd)

WSDL: [SmartMeteringMonitoring.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringMonitoring.wsdl)
