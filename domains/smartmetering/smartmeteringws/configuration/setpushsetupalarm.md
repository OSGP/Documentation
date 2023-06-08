<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# SetPushSetupAlarm

## Description

SetPushSetupAlarm is a request to define the TCP message that is optionally sent by the device. The request consists of the DeviceIdentification and at least one of the following optional items:
- The destination: Host URL and port.
- The push object list, defining which information should be sent in the alarm.

If an item is not included in the message, the value in the meter will remain unchanged.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetSetPushSetupAlarmResponse](getsetpushsetupalarmresponse.md) returns the result from setting a SetPushSetupAlarm. The response contains the DeviceIdentification and CorrelationUid which is received from the SetPushSetupAlarm request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

