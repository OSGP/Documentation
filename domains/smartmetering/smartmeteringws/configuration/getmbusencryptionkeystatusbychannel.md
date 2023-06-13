<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# GetMbusEncryptionKeyStatusByChannel

## Description

GetMbusEncryptionKeyStatusByChannel is a request to retrieve the encryption key status of an M-Bus device from an E-meter. The request needs the DeviceIdentification of the gateway device and a channel.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

The returned response for the GetMbusEncryptionKeyStatusByChannel request is as specified in [GetMbusEncryptionKeyStatusByChannelResponse](getmbusencryptionkeystatusbychannelresponse.md).

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

