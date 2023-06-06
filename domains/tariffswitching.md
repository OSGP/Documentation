<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# Tariff switching

This covers the services for tariff switching domain using the open smart grid platform.

## Scope

This domain allows tariff switching. It allows a relay to switch when a tariff changes. This domain could be used to replace ripple control tariff signals.

### Webservices

| **Operation** | **Request** | **Response** |
| :--- | :--- | :--- |
| **TariffSwitchingAdHocManagement.wsdl** |  |  |
| GetDevices |  |  |
| GetStatus | DeviceIdentification | Status |
| **TariffSwitchingScheduleManagement.wsdl** |  |  |
| SetSchedule | DeviceIdentification, Schedules, Page | - |

* [Tariff switching WSDL's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-tariffswitching/src/main/resources)
* [Tariff switching XSD schema's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-tariffswitching/src/main/resources/schemas)

## TARIFF \(normal\) vs. TARIFF\_REVERSED

When configuring a device via the platform to switch relays according to a tariff schedule, the device can be instructed to switch the tariff relay normally \("TARIFF"\) or reversed \("TARIFF\_REVERSED"\).

The devices themselves are unaware of the difference between TARIFF and TARIFF\_REVERSED. When sending a setScheduleRequest message for a tariff schedule to the platform, the tariff switching domain adapter checks if the device relay\(s\) are configured with TARIFF\_REVERSED. If so, the tariff switching domain adapter will invert the relay value for all tariff schedule entries before the tariff schedule is sent to the device.

When two devices have the same schedule, while one device is using TARIFF and the other TARIFF\_REVERSED, the state of their tariff relays will always be the opposite of each other.

### Communicated/Stored values

The values as shown in the table below will be returned, when getting the status from a device or from the platform.

| **Type** | **State** | **Relay powered** | **Returned by Device** | **Returned by Platform** |
| :--- | :--- | :--- | :--- | :--- |
| **TARIFF** | LOW | yes | on = true | High = false |
|  | HIGH | no | on = false | High = true |
| **TARIFF\_REVERSED** | LOW | no | on = false | High = false |
|  | HIGH | yes | on = true | High = true |

