<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# GetAssociationLnObjects

## Description

GetAssociationLnObjects is a request to get the Association LN object tree from an E-meter. The request is sent with the DeviceIdentification number from the desired device.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetGetAssociationLnObjectsResponse](getgetassociationlnobjectsresponse.md) returns the result values from getting the Association LN object. The response contains the DeviceIdentification and CorrelationUid which is received from the GetAssociationLnObjects request.

## References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringAdhoc.wsdl)

