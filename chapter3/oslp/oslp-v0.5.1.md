## Contract

Contract for [v0.5.1](./v0.5.1/oslp.proto.v0.5.1.md)

### Messages

These message below are part of OSLP v0.5.1.

- **[RegisterDeviceRequest](./v0.5.1/RegisterDevice.md)** (from device to platform) is a request that notifies the platform a device which wants to register. During the registration the sequence number is reset to a random value, the platform is notified if the device has a light schedule, the type of the device, the device identification, and the device communicates its IP address to the platform.
- **[RegisterDeviceResponse](./v0.5.1/RegisterDevice.md)** (from platform to device) is a response which holds the time of the platform so the device can synchronize the time, contains location information for the device like GPS coordinates and Day Light Saving time information. The device will sent ConfirmRegisterDeviceRequest after receiving the RegisterDeviceResponse.
- **[StartSelfTestRequest](./v0.5.1/StartSelfTest.md)** (from platform to device) is a request that notifies the device to switch all relays on.
- **[StartSelfTestResponse](./v0.5.1/StartSelfTest.md)** (from device to platform) is a response which confirms the StartSelfTestRequest has been executed or rejects the StartSelfTestRequest.
- **[StopSelfTestRequest](./v0.5.1/StopSelfTest.md)** (from platform to device) is a request that notifies the device to switch all relays off.
- **[StopSelfTestResponse](./v0.5.1/StopSelfTest.md)** (from device to platform) is a response which confirms the StopSelfTestResponse has been executed or rejects the StopSelfTestResponse.
- **[UpdateFirmwareRequest](./v0.5.1/UpdateFirmware.md)** (from platform to device) is a request which notifies the device to download a new firmware version from a server using a URL.
- **[UpdateFirmwareResponse](./v0.5.1/UpdateFirmware.md)** (from device to platform) is a response which confirms the UpdateFirmwareRequest has been executed or rejects the UpdateFirmwareRequest. Please note there are several events which are sent from the device to the platform to inform the platform when the firmware has been downloaded and whether or not the firmware was successfully activated.
- **[SetLightRequest](./v0.5.1/SetLight.md)** (from platform to device) is a request that notifies the device to switch on or off one ore several light relays, optionally with a dim-value per relay.
- **[SetLightResponse](./v0.5.1/SetLight.md)** (from device to platform) is a response which confirms the SetLightRequest has been executed or rejected.
- **[GetStatusRequest](./v0.5.1/GetStatus.md)** (from platform to device) is a request that requires the device to send the status of all relays, current network link and preferred network link, the type of configuration (PSLD vs SSLD), and the event notification mask which has been set.
- **[GetStatusResponse](./v0.5.1/GetStatus.md)** (from device to platform) is a response which confirms the GetStatusRequest has been executed and returns the current status for all of the relays and other information or rejects the GetStatusRequest.
- **[ResumeScheduleRequest](./v0.5.1/ResumeSchedule.md)** (from platform to device) is a request that notifies the device to continue the current schedule after the current schedule was interrupted (for example by switching by hand using SetLightRequest). This request can operate on a single relay or on all relays and the resuming of the schedule can be immediate or at the next schedule-entry.
- **[ResumeScheduleResponse](./v0.5.1/ResumeSchedule.md)** (from device to platform) is a response which confirms the ResumeScheduleRequest has been executed or rejected.
- **[SetEventNotificationsRequest](./v0.5.1/SetEventNotifications.md)** (from platform to device) is a request that sets the event notification mask.
- **[SetEventNotificationsResponse](./v0.5.1/SetEventNotifications.md)** (from device to platform) is a response which confirms the SetEventNotifications request has been executed or rejected.
- **[EventNotificationRequest](./v0.5.1/EventNotification.md)** (from device to platform) is a request that pushes an event notification from a device to the platform.
- **[EventNotificationResponse](./v0.5.1/EventNotification.md)** (from platform to device) is a response which confirms the EventNotificationRequest has been executed or rejected.
- **[GetFirmwareVersionRequest](./v0.5.1/GetFirmwareVersion.md)** (from platform to device) is a request that requests the device to sent its current firmware version.
- **[GetFirmwareVersionResponse](./v0.5.1/GetFirmwareVersion.md)** (from device to platform) is a response that sends the current firmware version to the platform.
- **[SetScheduleRequest](./v0.5.1/SetSchedule.md)** (from platform to device) is a request that sends a light or tariff schedule to the device.
- **[SetScheduleResponse](./v0.5.1/SetSchedule.md)** (from device to platform) is a response which confirms the SetScheduleRequest has been executed or rejected.
- **[SetConfigurationRequest](./v0.5.1/SetConfiguration.md)** (from platform to device) is a request that sends configuration settings to the device.
- **[SetConfigurationResponse](./v0.5.1/SetConfiguration.md)** (from device to platform) is a response which confirms the SetConfigurationRequest has been executed or rejected.
- **[GetPowerUsageHistoryRequest](./v0.5.1/GetPowerUsageHistory.md)** (from platform to device) is a request that requests the device to send the content of its power usage registers.
- **[GetPowerUsageHistoryResponse](./v0.5.1/GetPowerUsageHistory.md)** (from device to platform) is a response which confirms the GetPowerUsageHistoryRequest has been executed or rejected and contains the power usage data.
- **[GetActualPowerUsageRequest](./v0.5.1/GetActualPowerUsage.md)** (from platform to device) is a request that requests the device to send the content of its power usage registers.
- **[GetActualPowerUsageResponse](./v0.5.1/GetActualPowerUsage.md)** (from device to platform) is a response which confirms the GetActualPowerUsageRequest has been executed or rejected and contains the power usage data.
- **[SetRebootRequest](./v0.5.1/SetReboot.md)** (from platform to device) is a request that notifies the device to reboot immediately.
- **[SetRebootResponse](./v0.5.1/SetReboot.md)** (from device to platform) is a response which confirms the SetRebootRequest has been executed or rejected.
- **[SetTransitionRequest](./v0.5.1/SetTransition.md)** (from platform to device) is a request that notifies the device to switch its light relays according to light measurement schedule-entries.
- **[SetTransitionResponse](./v0.5.1/SetTransition.md)** (from device to platform) is a response which confirms the SetTransitionRequest has been executed or rejected.
- **[GetConfigurationRequest](./v0.5.1/GetConfiguration.md)** (from platform to device) is a request that requests the device to send its current configuration settings.
- **[GetConfigurationResponse](./v0.5.1/GetConfiguration.md)** (from device to platform) is a response which confirms the GetConfigurationRequest has been executed or rejected.
- **[ConfirmRegisterDeviceRequest](./v0.5.1/ConfirmRegisterDevice.md)** (from device to platform) is a request that notifies the platform that a device wants to perform the second step of the registration process.
- **[ConfirmRegisterDeviceResponse](./v0.5.1/ConfirmRegisterDevice.md)** (from platform to device) is a response which confirms the ConfirmRegisterDeviceRequest has been executed or rejected.
