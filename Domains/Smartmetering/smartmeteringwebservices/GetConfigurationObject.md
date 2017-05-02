## GetConfigurationObject request

### Description
GetConfigurationObject is a request to retrieve a ConfigurationObject from a device. The configuration object in the electricity meter with the OBIS code 0-1:94.31.3.255 is used to access the GPRS_operation_mode setting and following flags:
- discover_on_open_cover
- discover_on_power_on
- dynamic_mbus_address
- P0_enable
- HLS_3_on_P3_enable
- HLS_4_on_P3_enable
- HLS_5_on_P3_enable
- HLS_3_on_P0_enable
- HLS_4_on_P0_enable
- HLS_5_on_P0_enable

See DSMR document chapter 8.3 for detailed description. The request needs the DeviceIdentification.

All requests have similar response behavior which is described in [ResponseMessages](./ResponseMessages.md).

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

