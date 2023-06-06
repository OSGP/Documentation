<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# SetKeyOnGMeterRequest

## Description

SetKeyOnGMeter is a request to transfer and set an encryption key, firmware update authentication key or an optical port key on a G-meter via the E-meter. The request needs the DeviceIdentification from the G-meter and the key type (secrettype). If the device identification of the G-meter is not known, but the gateway device identification and M-Bus channel are known, use the [SetMbusUserKeyByChannel](setmbususerkeybychannel.md) request instead.
If the key type is the optical port key, the parameter to close the optical port can be set as well.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetSetKeyOnGMeterResponse](getsetkeyongmeterresponse.md) returns the result from setting a SetKeyOnGMeter. The response contains the DeviceIdentification and CorrelationUid which is received from the SetKeyOnGMeter request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

