<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# SendNotification

## Description

SendNotification is a request from the platform to let Webapps know there is a result ready to retrieve. In this way, there is no need for constant polling between Webapps and the platform. The request needs the DeviceIdentification.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

## References

XSD: [sm-notification.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-notification.xsd)

WSDL: [SmartMeteringNotification.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringNotification.wsdl)

