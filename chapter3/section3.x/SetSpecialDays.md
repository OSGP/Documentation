## SetSpecialDays request

### Description
SetSpecialDays is a request to set a dayId profile for a specific date on a device, other than the standard applicable dayId's. This can be usefull to change tariffs and tariff scheduling for specific days such as public holidays.
The request is send with the DeviceIdentification number from the desired device, date and dayId.

[GetSetSpecialDaysResponse](GetSetSpecialDaysResponse.md) returns the result from setting a Special Day. The response request contains the DeviceIdentification and CorrelationUid which is received from the SetSpecialDays request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

