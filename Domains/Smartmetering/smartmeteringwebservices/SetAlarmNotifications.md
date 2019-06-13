## SetAlarmNotifications request

### Description
SetAlarmNotifications is a request to set the types of alarm notifications that must be notified from the device when they occur.
The following notifications can be enabled or disabled:

CLOCK_INVALID, REPLACE_BATTERY, POWER_UP, PROGRAM_MEMORY_ERROR, RAM_ERROR, NV_MEMORY_ERROR, MEASUREMENT_SYSTEM_ERROR, WATCHDOG_ERROR, FRAUD_ATTEMPT, COMMUNICATION_ERROR_M_BUS_CHANNEL_1, COMMUNICATION_ERROR_M_BUS_CHANNEL_2, COMMUNICATION_ERROR_M_BUS_CHANNEL_3, COMMUNICATION_ERROR_M_BUS_CHANNEL_4, FRAUD_ATTEMPT_M_BUS_CHANNEL_1, FRAUD_ATTEMPT_M_BUS_CHANNEL_2, FRAUD_ATTEMPT_M_BUS_CHANNEL_3, FRAUD_ATTEMPT_M_BUS_CHANNEL_4, NEW_M_BUS_DEVICE_DISCOVERED_CHANNEL_1, NEW_M_BUS_DEVICE_DISCOVERED_CHANNEL_2, NEW_M_BUS_DEVICE_DISCOVERED_CHANNEL_3, NEW_M_BUS_DEVICE_DISCOVERED_CHANNEL_4

The request needs the DeviceIdentification, AlarmType and Enabled parameters.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSetAlarmNotificationsResponse](GetSetAlarmNotificationsResponse.md) returns the result from setting a SetAlarmNotifications. The response contains the DeviceIdentification and CorrelationUid which is received from the SetAlarmNotifications request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

