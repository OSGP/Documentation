<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# DeCoupleMbusDevice

## Description

DeCoupleMbusDevice is a request to decouple an Mbus device \(such as a gas meter\) from a device to the OSGP database. The request needs the following parameters:

* DeviceIdentification
* MbusDeviceIdentification

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md)

[GetDeCoupleMbusDeviceResponse](getdecouplembusdeviceresponse.md) returns if the result is successful from the request. The response contains the DeviceIdentification and CorrelationUid which is received from the DeCoupleMbusDevice request.

## References

XSD: [sm-installation.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-installation.xsd)

WSDL: [SmartMeteringInstallation.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringInstallation.wsdl)

