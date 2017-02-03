# Tariff switching
This covers the services for tariff switching domain using the open smart grid platform.

##Scope
This domain allows tariff switching. It allows a relay to switch when a tariff changes. 
This domain could be used to replace ripple control tariff signals.

### Webservices

| **Operation** | **Request** | **Response** |
| --- | --- | --- |
| **TariffSwitchingAdHocManagement** |
| GetDevices |   |   |
| GetStatus | DeviceIdentification | Status |
| **TariffSwitchingScheduleManagement** |
| SetSchedule | DeviceIdentification, Schedules, Page | - |


* [Tariff switching WSDL's](https://github.com/OSGP/Shared/tree/development/osgp-adapter-ws-tariffswitching/src/main/resources)
* [Tariff switching XSD schema's](https://github.com/OSGP/Shared/tree/development/osgp-adapter-ws-tariffswitching/src/main/resources/schemas)
