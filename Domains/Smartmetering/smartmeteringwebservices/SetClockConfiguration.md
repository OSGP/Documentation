## SetClockConfiguration request

### Description
SetClockConfiguration is a request to change the configuration of the internal clock of the device. The request needs the DeviceIdentification, TimeZoneOffset, DaylightSavingsBegin, DaylightSavingsEnd, DaylightSavingsDeviation, DaylightSavingsEnabled.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

The response contains the DeviceIdentification and CorrelationUid which is received from the SetClockConfiguration request. [GetSetClockConfigurationResponse](GetSetClockConfigurationResponse.md) returns if the result is successful from the SetClockConfiguration request. 

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

