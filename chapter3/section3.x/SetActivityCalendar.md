## SetActivityCalendar request

### Description
SetActivityCalendar is a request to set tarrifs on an E-meter according a SeasonProfile and WeekProfile. In a WeekProfile, seven dayprofiles can be filled in with a starttime and dayId which contains the tariff. 

The request needs the DeviceIdentification, CalendarName, ActivatePassiveCalendarTime, SeasonProfileName, SeasonStart, WeekProfileName, DayId and StartTime.

[GetSetActivityCalendarResponse](GetSetActivityCalendarResponse.md) returns the result from setting a SetActivityCalendar. The response request contains the DeviceIdentification and CorrelationUid which is received from the SetActivityCalendar request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

