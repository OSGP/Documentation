## SetConfigurationObject request

### Description
SetConfigurationObject is a request to set ConfigurationObject settings on a device. The attributes with OBIS code 0-1:94.31.3.255 give access to set GPRS_operation_mode setting and following flags:
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

See DSMR document chapter 8.3 for detailed description. The request needs the DeviceIdentification, GprsOperationMode, ConfigurationFlagType and Enabled parameters.

[GetSetConfigurationObjectResponse](GetSetConfigurationObjectResponse.md) returns the result from setting a SetConfigurationObject. The response request contains the DeviceIdentification and CorrelationUid which is received from the SetConfigurationObject request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

