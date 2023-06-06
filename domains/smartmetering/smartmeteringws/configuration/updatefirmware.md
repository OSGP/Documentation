<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# UpdateFirmware

## Description

UpdateFirmware is a request to install another firmware version\(s\) on a device. The request needs the DeviceIdentification and the firmware versions, that together with the device model \(as stored with the identified device\) uniquely determine the firmware file to be used.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetUpdateFirmwareResponse](getupdatefirmwareresponse.md) returns the version\(s\). The response contains the DeviceIdentification and CorrelationUid which is received from the UpdateFirmware request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

