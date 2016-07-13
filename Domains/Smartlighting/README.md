## This domain covers the use of the open smart grid platform for smart lighting.


PublicLighting webservices

| **Operation** | **Request** | **Response** |
| --- | --- | --- |
| **DeviceMonitoring.wsdl** |
| GetActualPowerUsage | DeviceIdentification | PowerUsageData |
| GetPowerUsageHistory | DeviceIdentification, TimePeriod, HistoryTermType, Page | PowerUsageData, PageInfo |
| **PublicLightingAdHocManagement** |
| SetTransition | DeviceIdentification, TransitionType, Time | - |
| FindAllDevices | Page | DevicePage |
| GetStatus | DeviceIdentification | LightValues, PreferredLinkType, ActualLinkType, LightType, EventNotifications |
| ResumeSchedule | DeviceIdentification, Index, IsImmediate | - |
| SetLight | DeviceIdentification, LightValue | - |
| **PublicLightingScheduleManagement** |
| SetSchedule | DeviceIdentification, Schedules, Page | - |

* [PublicLighting WSDL's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-publiclighting/src/main/webapp/WEB-INF/wsdl/publiclighting)
* [PublicLighting XSD schema's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-publiclighting/src/main/webapp/WEB-INF/wsdl/publiclighting/schemas)