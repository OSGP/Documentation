## Contract

Contract for [v0.6.1](./v0.6.1/oslp.proto.v0.6.1.md)

### Messages

These messages below are part of OSLP v0.6.1 and are new or different from OSLP v0.5.1. Note that OSLP v0.6.1 is backwards compatible with OSLP v0.5.1. Therefore, v0.6.1 offers the same RegisterDeviceRequest as v0.5.1 for example. If a message is not listed here, please see the message description here [OSLP v5.1.0](./oslp-v0.5.1.md).

- **[GetStatusRequest](./v0.6.1/GetStatus.md)** (from platform to device) is a request that requires the device to send the status of all relays, current network link and preferred network link, the type of configuration (PSLD vs SSLD), and the event notification mask which has been set.
- **[GetStatusResponse](./v0.6.1/GetStatus.md)** (from device to platform) is a response which confirms the GetStatusRequest has been executed and returns the current status for all of the relays and other information or rejects the GetStatusRequest.
- **[SetScheduleRequest](./v0.6.1/SetSchedule.md)** (from platform to device) is a request that sends a light or tariff schedule to the device.
- **[SetScheduleResponse](./v0.6.1/SetSchedule.md)** (from device to platform) is a response which confirms the SetScheduleRequest has been executed or rejected.
- **[SetConfigurationRequest](./v0.6.1/SetConfiguration.md)** (from platform to device) is a request that sends configuration settings to the device.
- **[SetConfigurationResponse](./v0.6.1/SetConfiguration.md)** (from device to platform) is a response which confirms the SetConfigurationRequest has been executed or rejected.
- **[GetConfigurationRequest](./v0.6.1/GetConfiguration.md)** (from platform to device) is a request that requests the device to send its current configuration settings.
- **[GetConfigurationResponse](./v0.6.1/GetConfiguration.md)** (from device to platform) is a response which confirms the GetConfigurationRequest has been executed or rejected.
- **[UpdateDeviceSslCertificationRequest](./v0.6.1/UpdateDeviceSslCertificationRequest.md)** (from platform to device)
- **[UpdateDeviceSslCertificationResponse](./v0.6.1/UpdateDeviceSslCertificationResponse.md)** (from platform to device)
- **[SetDeviceVerificationKeyRequest](./v0.6.1/SetDeviceVerificationKeyRequest.md)** (from platform to device)
- **[SetDeviceVerificationKeyResponse](./v0.6.1/SetDeviceVerificationKeyResponse.md)** (from platform to device)
- **[SwitchFirmwareRequest](./v0.6.1/SwitchFirmwareRequest.md)** (from platform to device)
- **[SwitchFirmwareResponse](./v0.6.1/SwitchFirmwareResponse.md)** (from platform to device)
- **[SwitchConfigurationRequest](./v0.6.1/SwitchConfigurationRequest.md)** (from platform to device)
- **[SwitchConfigurationResponse](./v0.6.1/SwitchConfigurationResponse.md)** (from platform to device)
