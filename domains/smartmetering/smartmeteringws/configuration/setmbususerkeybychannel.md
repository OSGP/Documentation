<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# SetMbusUserKeyByChannel

## Description

SetMbusUserKeyByChannel is a request to generate, transfer and set an M-Bus user key on an M-Bus device \(for instance a G-meter behind an E-meter\) via the DLMS gateway device. The request needs the DeviceIdentification from the gateway device and the channel for the M-Bus device. A use case for a request with the channel \(as only identification of the M-Bus device besides the identification of the gateway\) as input is to be able to respond to new M-Bus device discovered on channel x alarms \(x in 1..4\) from a gateway. If a new M-Bus User key is to be set on an M-Bus device with a known identification, this can be done with the [SetKeyOnGMeter](setkeyongmeter.md) request.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

The response contains the DeviceIdentification and CorrelationUid which is received from the SetMbusUserKeyByChannel request. [GetSetMbusUserKeyByChannelResponse](getsetmbususerkeybychannelresponse.md) returns the result from issuing a SetMbusUserKeyByChannel request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

