<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# ReplaceKeys

## Description

ReplaceKeys is a request to change the keys on an E-meter. The request needs the DeviceIdentification, an AuthenticationKey and an EncryptionKey.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetReplaceKeysResponse](getreplacekeysresponse.md) returns if the result is successful from the ReplaceKeys request. The response contains the DeviceIdentification and CorrelationUid which is received from the ReplaceKeys request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

