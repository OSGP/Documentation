<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# GetConfigurationObject

## Description

GetConfigurationObject is a request to retrieve a ConfigurationObject from a device. The configuration object in the electricity meter with the OBIS code 0-1:94.31.3.255 is used to access the GPRS\_operation\_mode setting and following flags:

* discover\_on\_open\_cover
* discover\_on\_power\_on
* dynamic\_mbus\_address
* P0\_enable
* HLS\_3\_on\_P3\_enable
* HLS\_4\_on\_P3\_enable
* HLS\_5\_on\_P3\_enable
* HLS\_3\_on\_P0\_enable
* HLS\_4\_on\_P0\_enable
* HLS\_5\_on\_P0\_enable

See DSMR document chapter 8.3 for detailed description. The request needs the DeviceIdentification.

All requests have similar response behavior which is described in [ResponseMessages](../../responsemessages.md).

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

