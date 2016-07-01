##4.2 This domain covers the use of the open smart grid platform for smart lighting.


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
| **TariffSwitching** |
| **TariffSwitchingAdHocManagement** |
| GetDevices |   |   |
| GetStatus | DeviceIdentification | Status |
| **TariffSwitchingScheduleManagement** |
| SetSchedule | DeviceIdentification, Schedules, Page | - |