# Admin

## The open smart grid platform core and admin functions for device management.

## Scope

This core and admin domain contains all generic web services that can be used in other domains. Most generic services relate to device management including powerful device authorization management

### Common webservices

| **Operation** | **Request** | **Response** |
| :--- | :--- | :--- |
| **CoreDeviceInstallation.wsdl** |  |  |
| AddDevice | DeviceIdentification | - |
| FindDevicesWhichHaveNoOwner | - | Devices |
| FindRecentDevices | - | Devices |
| StartDeviceTest | DeviceIdentification | - |
| StopDeviceTest | DeviceIdentification | - |
| UpdateDevice | DeviceIdentification | - |
| GetStatus | DeviceIdentification | Status |
| **AdminDeviceManagement.wsdl / CoreDeviceManagement.wsdl** |  |  |
| ChangeOrganisation | Organisation | - |
| CreateOrganisation | Organisation | - |
| FindAllOrganisations | - | Organisations |
| FindDeviceAuthorisations | DeviceIdentification | DeviceAuthorisations |
| FindDevices | PageSize, Page | Devices, Page |
| FindEvents | DeviceIdentification, From, Until, PageSize, Page | Events, Page |
| FindMessageLogs | DeviceIdentification, Page | MessageLogPage |
| RemoveDevice | DeviceIdentification | - |
| RemoveOrganisation | Organisation |  |
| SetEventNotifications | DeviceIdentification, EventNotifications | - |
| SetOwner | DeviceIdentification, OrganisationIdentification | - |
| UpdateDeviceAuthorisations | DeviceAuthorisations | - |
| ActivateOrganisation | Organisation | - |
| SetDeviceLifecycleStatus | DeviceIdentification, DeviceLifecycleStatus | - |
| **CoreFirmwareManagement.wsdl** |  |  |
| GetFirmwareVersion | DeviceIdentification | FirmwareVersion |
| UpdateFirmware | DeviceIdentification, FirmwareIdentification | - |
| **CoreConfigurationManagement.wsdl** |  |  |
| GetConfiguration | DeviceIdentification | Configuration |
| SetConfiguration | DeviceIdentification, Configuration | - |
| **CoreAdHocManagement.wsdl** |  |  |
| SetReboot | DeviceIdentification | - |

* [Core WSDL's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-core/src/main/resources)
* [Core XSD schema's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-core/src/main/resources/schemas)

### Admin webservices

* [Admin WSDL's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-admin/src/main/resources)
* [Admin XSD schema's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-admin/src/main/resources/schemas)

