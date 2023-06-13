<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# SetAlarmNotifications

## Description

SetAlarmNotifications is a request to set the types of alarm notifications that must be notified from the device when they occur. The following notifications can be enabled or disabled:

CLOCK\_INVALID, REPLACE\_BATTERY, POWER\_UP, PROGRAM\_MEMORY\_ERROR, RAM\_ERROR, NV\_MEMORY\_ERROR, MEASUREMENT\_SYSTEM\_ERROR, WATCHDOG\_ERROR, FRAUD\_ATTEMPT, COMMUNICATION\_ERROR\_M\_BUS\_CHANNEL\_1, COMMUNICATION\_ERROR\_M\_BUS\_CHANNEL\_2, COMMUNICATION\_ERROR\_M\_BUS\_CHANNEL\_3, COMMUNICATION\_ERROR\_M\_BUS\_CHANNEL\_4, FRAUD\_ATTEMPT\_M\_BUS\_CHANNEL\_1, FRAUD\_ATTEMPT\_M\_BUS\_CHANNEL\_2, FRAUD\_ATTEMPT\_M\_BUS\_CHANNEL\_3, FRAUD\_ATTEMPT\_M\_BUS\_CHANNEL\_4, NEW\_M\_BUS\_DEVICE\_DISCOVERED\_CHANNEL\_1, NEW\_M\_BUS\_DEVICE\_DISCOVERED\_CHANNEL\_2, NEW\_M\_BUS\_DEVICE\_DISCOVERED\_CHANNEL\_3, NEW\_M\_BUS\_DEVICE\_DISCOVERED\_CHANNEL\_4

The request needs the DeviceIdentification, AlarmType and Enabled parameters.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetSetAlarmNotificationsResponse](getsetalarmnotificationsresponse.md) returns the result from setting a SetAlarmNotifications. The response contains the DeviceIdentification and CorrelationUid which is received from the SetAlarmNotifications request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

