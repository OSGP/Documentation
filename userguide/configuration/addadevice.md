# Add a device

## Platform uses _single device calls_.

In order to add a device to the platform, call the add device method in the device installation web service \(for a specific domain\) for each device.

## Implementation may differ for different device types

Each device type may require its own set of attributes, security settings, etc. Each device type may have its own registration mechanism.

* To add a DLMS Device to the Platform, take a look at the documentation of the Soap call [AddDevice](../../domains/smartmetering/smartmeteringws/installation/adddevice.md) as defined in the [SmartMeteringInstallation.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringInstallation.wsdl).
* To add an OSLP Device to the Platform, the Soap call defined in [CoreDeviceInstallation](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-core/src/main/resources/CoreDeviceInstallation.wsdl) can be used, or the [UpdateKey Request](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-admin/src/main/resources/AdminDeviceManagement.wsdl).

Please take a look at the chapter [Testing the open smart grid platform](../installationguide/request/testosgp.md) in the installation manual for a detailed guide of how to add a OSLP device to the platform.

## Additional Device actions

In the [Domain Chapter](../../domains/) of the documentation more information of the Web Service calls can be found for Adding devices, setting configuration, authorizations, schedules, firmware updates, etc.

