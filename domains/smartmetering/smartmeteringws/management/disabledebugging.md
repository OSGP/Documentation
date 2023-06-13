<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# DisableDebugging

## Description

Disable debugging for a device. Communication with the device will be logged and made available through [FindMessageLogs](findmessagelogs.md),

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetDisableDebuggingResponse](getdisabledebuggingresponse.md) returns the result status. The response contains the DeviceIdentification and CorrelationUid which is received from the GetDisableDebuggingRequest request.

## References

XSD: [sm-management.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-management.xsd)

WSDL: [SmartMeteringManagement.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringManagement.wsdl)

