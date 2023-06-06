<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# GetKeys

## Description

GetKeys is a request to retrieve keys of a device. Multiple keys can be requested in one request. The keys in the response will be encrypted with the configured public key of the calling application.

The following key types are allowed:

* E\_METER\_MASTER\_KEY,
* E\_METER\_AUTHENTICATION\_KEY,
* E\_METER\_ENCRYPTION\_KEY\_UNICAST,
* E\_METER\_ENCRYPTION\_KEY\_BROADCAST,
* G\_METER\_MASTER\_KEY,
* G\_METER\_ENCRYPTION\_KEY,
* G\_METER\_FIRMWARE\_UPDATE\_AUTHENTICATION\_KEY,
* G\_METER\_OPTICAL\_PORT\_KEY

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

