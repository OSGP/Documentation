## The open smart grid platform core and admin functions for device management.

### Core

The Core component routes messages from domain adapter components to protocol adapter components and vice versa. Furthermore, it offers read-only database access for protocol adapter components.



Common webservices

| **Operation** | **Request** | **Response** |
| --- | --- | --- |
| **DeviceInstallation.wsdl** |
| AddDevice | DeviceIdentification | - |
| FindDevicesWhichHaveNoOwner | - | Devices |
| FindRecentDevices | - | Devices |
| StartDeviceTest | DeviceIdentification | - |
| StopDeviceTest | DeviceIdentification | - |
| UpdateDevice | DeviceIdentification | - |
| GetStatus | DeviceIdentification | Status |
| **DeviceManagement.wsdl** |
| ChangeOrganisation | Organisation | - |
| CreateOrganisation | Organisation | - |
| FindAllOrganisations | - | Organisations |
| FindDeviceAuthorisations | DeviceIdentification | DeviceAuthorisations |
| FindDevices | PageSize, Page | Devices, Page |
| FindEvents | DeviceIdentification, From, Until, PageSize, Page | Events, Page |
| FindMessageLogs | DeviceIdentification, Page | MessageLogPage |
| RemoveDevice | DeviceIdentification | - |
| RemoveOrganisation | Organisation |   |
| SetEventNotifications | DeviceIdentification, EventNotifications | - |
| SetOwner | DeviceIdentification, OrganisationIdentification | - |
| UpdateDeviceAuthorisations | DeviceAuthorisations | - |
| ActivateOrganisation | Organisation | - |
| **FirmwareManagement.wsdl** |
| GetFirmwareVersion | DeviceIdentification | FirmwareVersion |
| UpdateFirmware | DeviceIdentification, FirmwareIdentification | - |
| **ConfigurationManagement.wsdl** |
| GetConfiguration | DeviceIdentification | Configuration |
| SetConfiguration | DeviceIdentification, Configuration | - |
| **ScheduleManagement.wsdl** |
| SetSchedule | DeviceIdentification, Schedules, Page | - |
| SetTariffSchedule | DeviceIdentification, Schedules, Page | - |
| **AdHocManagement.wsdl** |
| SetReboot | DeviceIdentification | - |

* [Core WSDL's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-core/src/main/webapp/WEB-INF/wsdl/common)
* [Core XSD schema's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-core/src/main/webapp/WEB-INF/wsdl/common/schemas)


### Admin
* [Admin WSDL's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-admin/src/main/webapp/WEB-INF/wsdl/admin)
* [Admin XSD schema's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-admin/src/main/webapp/WEB-INF/wsdl/admin/schemas)
