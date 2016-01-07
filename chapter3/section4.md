## 3.4 OSLP Documentation


### 3.4.1 The Open Street Light Protocol

The OSLP is a lightweight message based protocol. OSLP uses [Google Protocol Buffers](https://developers.google.com/protocol-buffers/?hl=en). It is defined as a contract/interface. The interface defines datatypes and messages which use those datatypes.
See this contract for [v0.5.1](https://github.com/OSGP/Protocol-Adapter-OSLP/blob/master/oslp/src/main/protobuf/oslp.proto)

### 3.4.2 Messages

- **[RegisterDeviceRequest](./oslp/v0.5.1/RegisterDevice.md)** (from device to platform) is a request that notifies the platform a device which wants to register. During the registration the sequence number is reset to a random value the platform is notified if the device has a light schedule, the type of the device, the device identification, and the device communicates it's IP address to the platform.
- **[RegisterDeviceResponse](./oslp/v0.5.1/RegisterDevice.md)** (from platform to device) is a response which holds the time of the platform so the device can synchronize the time, contains location information for the device like GPS coordinates and Day Light Saving time information. The device will sent ConfirmRegisterDeviceRequest after receiving the RegisterDeviceResponse.
- **[StartSelfTestRequest](./oslp/v0.5.1/StartSelfTest.md)** (from platform to device) is a request that notifies the device to switch all relays on.
- **[StartSelfTestResponse](./oslp/v0.5.1/StartSelfTest.md)** (from device to platform) is a response which confirms the StartSelfTestRequest has been executed or rejects the StartSelfTestRequest.
- **[StopSelfTestRequest](./oslp/v0.5.1/StopSelfTest.md)** (from platform to device) is a request that notifies the device to switch all relays off.
- **[StopSelfTestResponse](./oslp/v0.5.1/StopSelfTest.md)** (from device to platform) is a response which confirms the StopSelfTestResponse has been executed or rejects the StopSelfTestResponse.
- **[UpdateFirmwareRequest](./oslp/v0.5.1/UpdateFirmware.md)** (from platform to device) is a request which notifies the device to download a new firmware version from a server using a URL.
- **[UpdateFirmwareResponse](./oslp/v0.5.1/UpdateFirmware.md)** (from device to platform) is a response which confirms the UpdateFirmwareRequest has been executed or rejects the UpdateFirmwareRequest. Please note there are several events which are sent from the device to the platform to inform the platform when the firmware has been downloaded and whether or not the firmware was successfully activated.
- **[SetLightRequest](./oslp/v0.5.1/SetLight.md)** (from platform to device) is a request that notifies the device to switch on or off one ore several light relays, optionally with a dim-value per relay.
- **[SetLightResponse](./oslp/v0.5.1/SetLight.md)** (from device to platform) is a response which confirms the SetLightRequest has been executed or rejected.
- **[GetStatusRequest](./oslp/v0.5.1/GetStatus.md)** (from platform to device) is a request that requires the device to send the status of all relays, current network link and preferred network link, the type of configuration (PSLD vs SSLD), and the event notification mask which has been set.
- **[GetStatusResponse](./oslp/v0.5.1/GetStatus.md)** (from device to platform) is a response which confirms the GetStatusRequest has been executed and returns the current status for all of the relays and other information or rejects the GetStatusRequest.
- **[ResumeScheduleRequest](./oslp/v0.5.1/ResumeSchedule.md)** (from platform to device) is a request that notifies the device to continue the current schedule after the current schedule was interrupted (for example by switching by hand using SetLightRequest). This request can operate on a single relay or on all relays and the resuming of the schedule can be immediate or at the next schedule-entry.
- **[ResumeScheduleResponse](./oslp/v0.5.1/ResumeSchedule.md)** (from device to platform) is a response which confirms the ResumeScheduleRequest has been executed or rejected.
- **[SetEventNotificationsRequest](./oslp/v0.5.1/SetEventNotifications.md)** (from platform to device) is a request that sets the event notification mask.
- **[SetEventNotificationsResponse](./oslp/v0.5.1/SetEventNotifications.md)** (from device to platform) is a response which confirms the SetEventNotifications request has been executed or rejected.
- **[EventNotificationRequest](./oslp/v0.5.1/EventNotification.md)** (from device to platform) is a request that pushes an event notification from a device to the platform.
- **[EventNotificationResponse](./oslp/v0.5.1/EventNotification.md)** (from platform to device) is a response which confirms the EventNotificationRequest has been executed or rejected.
- **[GetFirmwareVersionRequest](./oslp/v0.5.1/GetFirmwareVersion.md)** (from platform to device) is a request that requests the device to sent it's current firmware version.
- **[GetFirmwareVersionResponse](./oslp/v0.5.1/GetFirmwareVersion.md)** (from device to platform) is a response that sends the current firmware version to the platform.
- **[SetScheduleRequest](./oslp/v0.5.1/SetSchedule.md)** (from platform to device) is a request that sends a light or tariff schedule to the device.
- **[SetScheduleResponse](./oslp/v0.5.1/SetSchedule.md)** (from device to platform) is a response which confirms the SetScheduleRequest has been executed or rejected.
- **[SetConfigurationRequest](./oslp/v0.5.1/SetConfiguration.md)** (from platform to device) is a request that sends configuration settings to the device.
- **[SetConfigurationResponse](./oslp/v0.5.1/SetConfiguration.md)** (from device to platform) is a response which confirms the SetConfigurationRequest has been executed or rejected.
- **[GetPowerUsageHistoryRequest](./oslp/v0.5.1/GetPowerUsageHistory.md)** (from platform to device) is a request that requests the device to send the content of it's power usage registers.
- **[GetPowerUsageHistoryResponse](./oslp/v0.5.1/GetPowerUsageHistory.md)** (from device to platform) is a response which confirms the GetPowerUsageHistoryRequest has been executed or rejected and contains the power usage data.
- **[GetActualPowerUsageRequest](./oslp/v0.5.1/GetActualPowerUsage.md)** (from platform to device) is a request that requests the device to send the content of it's power usage registers.
- **[GetActualPowerUsageResponse](./oslp/v0.5.1/GetActualPowerUsage.md)** (from device to platform) is a response which confirms the GetActualPowerUsageRequest has been executed or rejected and contains the power usage data.
- **[SetRebootRequest](./oslp/v0.5.1/SetReboot.md)** (from platform to device) is a request that notifies the device to reboot immediately.
- **[SetRebootResponse](./oslp/v0.5.1/SetReboot.md)** (from device to platform) is a response which confirms the SetRebootRequest has been executed or rejected.
- **[SetTransitionRequest](./oslp/v0.5.1/SetTransition.md)** (from platform to device) is a request that notifies the device to switch it's light relays according to light measurement schedule-entries.
- **[SetTransitionResponse](./oslp/v0.5.1/SetTransition.md)** (from device to platform) is a response which confirms the SetTransitionRequest has been executed or rejected.
- **[GetConfigurationRequest](./oslp/v0.5.1/GetConfiguration.md)** (from platform to device) is a request that requests the device to send it's current configuration settings.
- **[GetConfigurationResponse](./oslp/v0.5.1/GetConfiguration.md)** (from device to platform) is a response which confirms the GetConfigurationRequest has been executed or rejected.
- **[ConfirmRegisterDeviceRequest](./oslp/v0.5.1/ConfirmRegisterDevice.md)** (from device to platform) is a request that notifies the platform that a device wants to perform the second step of the registration process.
- **[ConfirmRegisterDeviceResponse](./oslp/v0.5.1/ConfirmRegisterDevice.md)** (from platform to device) is a response which confirms the ConfirmRegisterDeviceRequest has been executed or rejected.

### 3.4.3 OSLP Envelope

The requests and responses are sent using an OSLP envelope. This structure contains the following fields: securityKey, sequenceNumber, deviceId and payloadMessage. The first 3 field are byte arrays, the payloadMessage is a protobuf type which is serializable.

``` java
class OslpEnvelope {
    /**
     * Length of the security hash.
	 * Length for ECDSA is 71 or 72 or 73 bytes.
     * Length for RSA is 128 bytes.
     */
    public static final int SECURITY_KEY_LENGTH = 128;

    /**
     * Length of the sequence number.
     */
    public static final int SEQUENCE_NUMBER_LENGTH = 2;

    /**
     * Length of the manufacturer id.
     */
    public static final int MANUFACTURER_ID_LENGTH = 2;

    /**
     * Length of the device id.
     */
    public static final int DEVICE_ID_LENGTH = 10;

    /**
     * Length of the length.
     */
    public static final int LENGTH_INDICATOR_LENGTH = 2;

    /**
     * Buffer for security key bytes.
     */
    public byte[] securityKey = new byte[SECURITY_KEY_LENGTH];

    /**
     * Buffer for sequence number bytes.
     */
    public byte[] sequenceNumber = new byte[SEQUENCE_NUMBER_LENGTH];

    /**
     * Buffer for deviceid bytes.
     */
    public byte[] deviceId = new byte[DEVICE_ID_LENGTH + MANUFACTURER_ID_LENGTH];

    /**
     * Buffer for OSLP payload.
     */
    public Message payloadMessage;
}
```
