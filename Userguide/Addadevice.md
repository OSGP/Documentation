## Add a device

### Platform uses _single device calls_.
In order to add a device to the platform, call the add device method in the device installation web service (for a specific domain) for each device.

### Implementation may differ for different device types
Each device type may require its own set of attributes, security settings, etc.
Each device type may have its own registration mechanism.

- To add a DLMS Device to the Platform, take a look at the documentation of the Soap call [AddDevice](../Domains/Smartmetering/smartmeteringwebservices/AddDevice.md) as defined in the [SmartMeteringInstallation.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringInstallation.wsdl).

- To add an OSLP Device to the Platform, the Soap call defined in [DeviceInstallation](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-core/src/main/webapp/WEB-INF/wsdl/common/DeviceInstallation.wsdl) can be used, or the [UpdateKey Request](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-admin/src/main/webapp/WEB-INF/wsdl/admin/DeviceManagement.wsdl).

Please take a look at the [Test OSGP Chapter](./Installation/testOSGP.md) in the installation manual for a detailed guide of how to add a OSLP device to the platform.

### Additional Device actions
In the [Domain Chapter](../Domains/README.md) of the documentation more information of the Web Service calls can be found for Adding devices, setting configuration, authorizations, schedules, firmware updates, etc.