<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# ClearMBusStatusOnAllChannels

## Description

ClearMBusStatusOnAllChannels is a request to clear the M-Bus status on all channels, so G-meters are ready to raise new alarms.

E-meters before version 5.1 clear the status by themselves. 

The procedure to clear the M-Bus status is described in paragraph 5.8 Auxiliary event Handling in SMR5.1 (P3 Companion Standard)

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[ClearMBusStatusOnAllChannelsResponse](clearmbusstatusonallchannelsresponse.md) returns if the result is successful from the request. The response contains the DeviceIdentification and CorrelationUid which is received from the ClearMBusStatusOnAllChannels request.

## References

XSD: [sm-management.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-management.xsd)

WSDL: [SmartMeteringManagement.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringManagement.wsdl)

