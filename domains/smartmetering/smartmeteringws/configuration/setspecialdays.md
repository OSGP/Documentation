<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# SetSpecialDays

## Description

SetSpecialDays is a request to set a dayId profile for a specific date on a device, other than the standard applicable dayId's. This can be useful to change tariffs and tariff scheduling for specific days such as public holidays. The request is send with the DeviceIdentification number from the desired device, date and dayId.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetSetSpecialDaysResponse](getsetspecialdaysresponse.md) returns the result from setting a Special Day. The response contains the DeviceIdentification and CorrelationUid which is received from the SetSpecialDays request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

