## Contract

Contract for [SWDevice-010805](./SWDevice-010805/SWDevice-010805.icd.md)
Contrary to OSLP the contract between OSGP and IEC61850 devices does not exist of request/response messages, in stead the request messages received by OSGP will result in multiple read/write operations at the device. The response messages returned by OSGP will contain the result of these operations.

### Messages

The messages below are part of OSGP and implemented in the IEC61850 protocol adapter and supported by the SWDevice-010805 device firmware.

- **[StartSelfTestRequest](./SWDevice-010805/StartSelfTest.md)** is a request which commands a device to switch all light relays on.
- **[StartSelfTestResponse](./SWDevice-010805/StartSelfTest.md)** is a response which returns the result of the StartSelfTestRequest.

- **[StopSelfTestRequest](./SWDevice-010805/StopSelfTest.md)** is a request which commands a device to switch all light relays off.
- **[StopSelfTestResponse](./SWDevice-010805/StopSelfTest.md)** is a response which returns the result of the StopSelfTestRequest.

- **[SetRebootRequest](./SWDevice-010805/SetReboot.md)** is a request which commands a device to reboot immediately.
- **[SetRebootResponse](./SWDevice-010805/SetReboot.md)** is a response which returns the result of the SetRebootRequest.

- **[SetLightRequest](./SWDevice-010805/SetLight.md)** is a request which commands a device to switch on or off one ore several light relays.
- **[SetLightResponse](./SWDevice-010805/SetLight.md)** is a response which returns the result of the SetLightRequest.

- **[SetTransitionRequest](./SWDevice-010805/SetTransition.md)** is a request which commands a device to switch its light relays according to light measurement schedule-entries.
- **[SetTransitionResponse](./SWDevice-010805/SetTransition.md)** is a response which returns the result of the SetTransitionRequest.

- **[SetEventNotificationsRequest](./SWDevice-010805/SetEventNotifications.md)** is a request which commands a device to set the event notification mask.
- **[SetEventNotificationsResponse](./SWDevice-010805/SetEventNotifications.md)** is a response which returns the result of the SetEventNotificationsRequest.

- **[GetStatusRequest](./SWDevice-010805/GetStatus.md)** is a request which queries a device for the current status of all its relays, the type of configuration, and the event notification mask set on the device.
- **[GetStatusResponse](./SWDevice-010805/GetStatus.md)** (from device to platform) is a response which returns the result of the GetStatusRequest and, if 'result = OK', returns the current status for all of the relays and other information.

- **[GetFirmwareVersionRequest](./SWDevice-010805/GetFirmwareVersion.md)** is a request which queries a device for its current firmware version.
- **[GetFirmwareVersionResponse](./SWDevice-010805/GetFirmwareVersion.md)** is a response which returns the result of the GetFirmwareVersionRequest and, if 'result = OK', returns  the current firmware version.

- **[UpdateFirmwareRequest](./SWDevice-010805/UpdateFirmware.md)** is a request which commands a device to download a new firmware version from a server using a URL.
- **[UpdateFirmwareResponse](./SWDevice-010805/UpdateFirmware.md)** is a response which returns the result of the UpdateFirmwareRequest. Please note there are several events which are sent from the device to the platform to inform the platform when the firmware has been downloaded and whether or not the firmware was successfully activated.

- **[GetConfigurationRequest](./SWDevice-010805/GetConfiguration.md)** is a request which queries a device for its current configuration settings.
- **[GetConfigurationResponse](./SWDevice-010805/GetConfiguration.md)** is a response which returns the result of the GetConfigurationRequest and, if 'result = OK', returns the configuration settings retrieved from the device.

- **[SetConfigurationRequest](./SWDevice-010805/SetConfiguration.md)** is a request which commands a device to update its configuration.
- **[SetConfigurationResponse](./SWDevice-010805/SetConfiguration.md)** is a response which returns the result of the SetConfigurationRequest.

- **[SetScheduleRequest](./SWDevice-010805/SetSchedule.md)** is a request which commands a device to update its light or tariff schedule.
- **[SetScheduleResponse](./SWDevice-010805/SetSchedule.md)** is a response which returns the result of the SetScheduleRequest.

- **[SetConfigurationRequest](./SWDevice-010805/SetConfiguration.md)** is a request which commands a device to update its configuration settings.
- **[SetConfigurationResponse](./SWDevice-010805/SetConfiguration.md)** is a response which returns the result of the SetConfigurationRequest.

The following messages are not supported in IEC61850 and will return a UNSUPPORTED_DEVICE_ACTION SOAP Fault when a request is sent:
- **ResumeScheduleRequest**
- **SwitchConfigurationRequest**
  **SwitchFirmwareRequest**
  **UpdateDeviceSslCertificationRequest**
  **SetDeviceVerificationKeyRequest**

The following message from device to OSGP is also not supported:
  **ConfirmRegisterDeviceRequest**


TODO

- **[RegisterDeviceRequest](./v0.6.1/RegisterDevice.md)** (from device to platform) is a request that notifies the platform a device which wants to register. During the registration the sequence number is reset to a random value, the platform is notified if the device has a light schedule, the type of the device, the device identification, and the device communicates its IP address to the platform.
- **[RegisterDeviceResponse](./v0.6.1/RegisterDevice.md)** (from platform to device) is a response which holds the time of the platform so the device can synchronize the time, contains location information for the device like GPS coordinates and Day Light Saving time information. The device will sent ConfirmRegisterDeviceRequest after receiving the RegisterDeviceResponse.

- **[EventNotificationRequest](./v0.6.1/EventNotification.md)** (from device to platform) is a request that pushes an event notification from a device to the platform.
- **[EventNotificationResponse](./v0.6.1/EventNotification.md)** (from platform to device) is a response which confirms the EventNotificationRequest has been executed or rejected.

- **[GetPowerUsageHistoryRequest](./v0.6.1/GetPowerUsageHistory.md)** (from platform to device) is a request that requests the device to send the content of its power usage registers.
- **[GetPowerUsageHistoryResponse](./v0.6.1/GetPowerUsageHistory.md)** (from device to platform) is a response which confirms the GetPowerUsageHistoryRequest has been executed or rejected and contains the power usage data.
