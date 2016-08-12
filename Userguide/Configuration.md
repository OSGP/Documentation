## Configuration
We have prepared a full set of configuration (properties files, certificates, key store, ...) which is available in our [Config repository](https://github.com/OSGP/Config). This configuration can be used to setup a trial environment. In case someone wants to set up an environment.

## Add a device

### Platform uses _single device calls_.
In order to add a device to the platform, call the add device method in the device installation web service (for a specific domain) for each device.

### Implementation may differ for different device types
Each device type may require its own set of attributes, security settings, etc.
Each device type may have its own registration mechanism

### For each device additional actions may be required:
Setting configuration, authorizations, schedules, firmware updates, etc.
