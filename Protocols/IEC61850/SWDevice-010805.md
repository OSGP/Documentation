## Contract

Contract for [SWDevice-010805](./SWDevice-010805/SWDevice-010805-icd.md)
The contract specifies the messages which can be exchanged with an SSLD.

### Messages

The messages below are part of OSGP and implemented in the IEC61850 protocol adapter and supported by the SWDevice-010805 device firmware.

- **[RegisterDeviceRequest](./SWDevice-010805/RegisterDevice.md)** (from device to platform) is a request that notifies the platform a device wants to register. During the registration the device sends its identification (serial number), and the device communicates its IP address to the platform.
- **[RegisterDeviceResponse](./SWDevice-010805/RegisterDevice.md)** (from platform to device) is a response which informs the device that the registration was successful. The device will not register anymore, until the next power cycle or reboot.

- **[StartSelfTestRequest](./SWDevice-010805/StartSelfTest.md)** (from platform to device) is a request which commands a device to switch all light relays on.
- **[StartSelfTestResponse](./SWDevice-010805/StartSelfTest.md)** (from device to platform) is a response which returns the result of the StartSelfTestRequest.

- **[StopSelfTestRequest](./SWDevice-010805/StopSelfTest.md)** (from platform to device) is a request which commands a device to switch all light relays off.
- **[StopSelfTestResponse](./SWDevice-010805/StopSelfTest.md)** (from device to platform) is a response which returns the result of the StopSelfTestRequest.

- **[SetRebootRequest](./SWDevice-010805/SetReboot.md)** (from platform to device) is a request which commands a device to reboot immediately.
- **[SetRebootResponse](./SWDevice-010805/SetReboot.md)** (from device to platform) is a response which returns the result of the SetRebootRequest.

- **[SetLightRequest](./SWDevice-010805/SetLight.md)** (from platform to device) is a request which commands a device to switch on or off one ore several light relays.
- **[SetLightResponse](./SWDevice-010805/SetLight.md)** (from device to platform) is a response which returns the result of the SetLightRequest.

- **[SetTransitionRequest](./SWDevice-010805/SetTransition.md)** (from platform to device) is a request which commands a device to switch its light relays according to light measurement schedule-entries.
- **[SetTransitionResponse](./SWDevice-010805/SetTransition.md)** (from device to platform) is a response which returns the result of the SetTransitionRequest.

- **[SetEventNotificationsRequest](./SWDevice-010805/SetEventNotifications.md)** (from platform to device) is a request which commands a device to set the event notification mask.
- **[SetEventNotificationsResponse](./SWDevice-010805/SetEventNotifications.md)** (from device to platform) is a response which returns the result of the SetEventNotificationsRequest.

- **[GetStatusRequest](./SWDevice-010805/GetStatus.md)** (from platform to device) is a request which queries a device for the current status of all its relays, the type of configuration (RELAY for SSLD), and the event notification mask set on the device.
- **[GetStatusResponse](./SWDevice-010805/GetStatus.md)** (from device to platform) is a response which returns the result of the GetStatusRequest and, if 'result = OK', returns the current status for all of the relays and other information.

- **[GetFirmwareVersionRequest](./SWDevice-010805/GetFirmwareVersion.md)** (from platform to device) is a request which queries a device for its current firmware version.
- **[GetFirmwareVersionResponse](./SWDevice-010805/GetFirmwareVersion.md)** (from device to platform) is a response which returns the result of the GetFirmwareVersionRequest and, if 'result = OK', returns  the current firmware version.

- **[UpdateFirmwareRequest](./SWDevice-010805/UpdateFirmware.md)** (from platform to device) is a request which commands a device to download a new firmware version from a server using a URL.
- **[UpdateFirmwareResponse](./SWDevice-010805/UpdateFirmware.md)** (from device to platform) is a response which returns the result of the UpdateFirmwareRequest, which indicates if the device will start the process to download and install a new firmware version. Please note there are several events which are sent from the device to the platform to inform the platform when the firmware has been downloaded and whether or not the firmware was successfully activated.

- **[GetConfigurationRequest](./SWDevice-010805/GetConfiguration.md)** (from platform to device) is a request which queries a device for its current configuration settings.
- **[GetConfigurationResponse](./SWDevice-010805/GetConfiguration.md)** (from device to platform) is a response which returns the result of the GetConfigurationRequest and, if 'result = OK', returns the configuration settings retrieved from the device.

- **[SetConfigurationRequest](./SWDevice-010805/SetConfiguration.md)** (from platform to device) is a request which commands a device to update its configuration.
- **[SetConfigurationResponse](./SWDevice-010805/SetConfiguration.md)** (from device to platform) is a response which returns the result of the SetConfigurationRequest.

- **[SetScheduleRequest](./SWDevice-010805/SetSchedule.md)** (from platform to device) is a request which commands a device to update its light or tariff schedule.
- **[SetScheduleResponse](./SWDevice-010805/SetSchedule.md)** (from device to platform) is a response which returns the result of the SetScheduleRequest.

- **[GetPowerUsageHistoryRequest](./SWDevice-010805/GetPowerUsageHistory.md)** (from platform to device) is a request that requests the device to send the content of its power usage registers.
- **[GetPowerUsageHistoryResponse](./SWDevice-010805/GetPowerUsageHistory.md)** (from device to platform) is a response which confirms the GetPowerUsageHistoryRequest has been executed or rejected and contains the power usage data.

- **[UpdateDeviceSslCertificationRequest](./SWDevice-010805/UpdateDeviceSslCertification.md)** (from platform to device) is a request which commands a device to download a new certificate file from a server using a URL.
- **[UpdateDeviceSslCertificationResponse](./SWDevice-010805/UpdateDeviceSslCertification.md)** (from platform to device) is a response which returns the result of the UpdateDeviceSslCertificationRequest, which indicates if the device will start the process to download and install a new certificate file. Please note there are several events which are sent from the device to the platform to inform the platform whether or not the certificate file was successfully downloaded and activated.

- **[EventNotificationRequest](./SWDevice-010805/EventNotification.md)** (from device to platform) is a request that pushes an event notification from a device to the platform.

The following messages are not supported in IEC61850 and will return an UNSUPPORTED_DEVICE_ACTION SOAP Fault when a request is sent:
- **ResumeScheduleRequest**
- **SwitchConfigurationRequest**
- **SwitchFirmwareRequest**
- **SetDeviceVerificationKeyRequest**

The following message from device to OSGP is also not supported:
- **ConfirmRegisterDeviceRequest**
