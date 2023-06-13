<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Smart lighting

## This domain covers the use of the open smart grid platform for smart lighting.

## Scope

The goal of this domain is to control, monitor and manage \(street\) lights at scale. It allows streetlight owners to control/manage the \(street\) lights in an more intelligent way compared to ripple control technology.

## Features

This domain consist of [Switching schedules](lightschedules.md), groups, light sensors, manual switching and monitoring of a typical public lighting use-case.

## PublicLighting webservices

| **Operation** | **Request** | **Response** |
| :--- | :--- | :--- |
| **PublicLightingAdHocManagement.wsdl** |  |  |
| SetTransition | DeviceIdentification, TransitionType, Time | - |
| FindAllDevices | Page | DevicePage |
| GetStatus | DeviceIdentification | LightValues, PreferredLinkType, ActualLinkType, LightType, EventNotifications |
| ResumeSchedule | DeviceIdentification, Index, IsImmediate | - |
| SetLight | DeviceIdentification, LightValue | - |
| **PublicLightingScheduleManagement.wsdl** |  |  |
| SetSchedule | DeviceIdentification, Schedules, Page | - |

* [PublicLighting WSDL's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-publiclighting/src/main/resources)
* [PublicLighting XSD schema's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-publiclighting/src/main/resources/schemas)

