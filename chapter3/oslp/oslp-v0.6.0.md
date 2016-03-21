## Contract

Contract for [v0.6.0](./v0.6.0/oslp.proto.v0.6.0.md)

### Messages

These messages below are part of OSLP v0.6.0 and are new or different from OSLP v0.5.1. Note that OSLP v0.6.0 is backwards compatible with OSLP v0.5.1. Therefore, v0.6.0 offers the same RegisterDeviceRequest as v0.5.1 for example. If a message is not listed here, please see the message description here [OSLP v5.1.0](./oslp-v0.5.1.md).

- **[GetStatusRequest](./oslp/v0.6.0/GetStatus.md)** (from platform to device) is a request that requires the device to send the status of all relays, current network link and preferred network link, the type of configuration (PSLD vs SSLD), and the event notification mask which has been set.
- **[GetStatusResponse](./oslp/v0.6.0/GetStatus.md)** (from device to platform) is a response which confirms the GetStatusRequest has been executed and returns the current status for all of the relays and other information or rejects the GetStatusRequest.
- **[SetScheduleRequest](./oslp/v0.6.0/SetSchedule.md)** (from platform to device) is a request that sends a light or tariff schedule to the device.
- **[SetScheduleResponse](./oslp/v0.6.0/SetSchedule.md)** (from device to platform) is a response which confirms the SetScheduleRequest has been executed or rejected.
- **[SetConfigurationRequest](./oslp/v0.6.0/SetConfiguration.md)** (from platform to device) is a request that sends configuration settings to the device.
- **[SetConfigurationResponse](./oslp/v0.6.0/SetConfiguration.md)** (from device to platform) is a response which confirms the SetConfigurationRequest has been executed or rejected.
- **[GetConfigurationRequest](./oslp/v0.6.0/GetConfiguration.md)** (from platform to device) is a request that requests the device to send its current configuration settings.
- **[GetConfigurationResponse](./oslp/v0.6.0/GetConfiguration.md)** (from device to platform) is a response which confirms the GetConfigurationRequest has been executed or rejected.
- **[UpdateDeviceSslCertificationRequest](./oslp/v0.6.0/UpdateDeviceSslCertificationRequest.md)** (from platform to device)
- **[UpdateDeviceSslCertificationResponse](./oslp/v0.6.0/UpdateDeviceSslCertificationResponse.md)** (from platform to device)
- **[SetDeviceVerificationKeyRequest](./oslp/v0.6.0/SetDeviceVerificationKeyRequest.md)** (from platform to device)
- **[SetDeviceVerificationKeyResponse](./oslp/v0.6.0/SetDeviceVerificationKeyResponse.md)** (from platform to device)
- **[SwitchFirmwareRequest](./oslp/v0.6.0/SwitchFirmwareRequest.md)** (from platform to device)
- **[SwitchFirmwareResponse](./oslp/v0.6.0/SwitchFirmwareResponse.md)** (from platform to device)
- **[SwitchConfigurationRequest](./oslp/v0.6.0/SwitchConfigurationRequest.md)** (from platform to device)
- **[SwitchConfigurationResponse](./oslp/v0.6.0/SwitchConfigurationResponse.md)** (from platform to device)