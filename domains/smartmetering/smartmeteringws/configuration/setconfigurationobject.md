# SetConfigurationObject

## Description

SetConfigurationObject is a request to set ConfigurationObject settings on a device. The attributes with OBIS code 0-1:94.31.3.255 give access to set GPRS\_operation\_mode setting and following flags:

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

See DSMR document chapter 8.3 for detailed description. The request needs the DeviceIdentification, GprsOperationMode, ConfigurationFlagType and Enabled parameters.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetSetConfigurationObjectResponse](getsetconfigurationobjectresponse.md) returns the result from setting a SetConfigurationObject. The response contains the DeviceIdentification and CorrelationUid which is received from the SetConfigurationObject request.

## References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

