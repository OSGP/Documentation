<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# OSLP v0.6.1

Contract for [v0.6.1](oslp.proto.v0.6.1.md) The contract specifies the messages which can be exchanged with an SSLD.

## Messages

These messages below are part of OSLP v0.6.1. Note that OSLP v0.6.1 is backwards compatible with OSLP v0.5.1. Therefore, v0.6.1 offers the same RegisterDeviceRequest as v0.5.1 for example.

* [**RegisterDeviceRequest**](registerdevice.md) \(from device to platform\) is a request that notifies the platform a device which wants to register. During the registration the sequence number is reset to a random value, the platform is notified if the device has a light schedule, the type of the device, the device identification, and the device communicates its IP address to the platform.
* [**RegisterDeviceResponse**](registerdevice.md) \(from platform to device\) is a response which holds the time of the platform so the device can synchronize the time, contains location information for the device like GPS coordinates and Day Light Saving time information. The device will sent ConfirmRegisterDeviceRequest after receiving the RegisterDeviceResponse.
* [**ConfirmRegisterDeviceRequest**](confirmregisterdevice.md) \(from device to platform\) is a request that notifies the platform that a device wants to perform the second step of the registration process.
* [**ConfirmRegisterDeviceResponse**](confirmregisterdevice.md) \(from platform to device\) is a response which confirms the ConfirmRegisterDeviceRequest has been executed or rejected.
* [**StartSelfTestRequest**](startselftest.md) \(from platform to device\) is a request that notifies the device to switch all relays on.
* [**StartSelfTestResponse**](startselftest.md) \(from device to platform\) is a response which confirms the StartSelfTestRequest has been executed or rejected.
* [**StopSelfTestRequest**](stopselftest.md) \(from platform to device\) is a request that notifies the device to switch all relays off.
* [**StopSelfTestResponse**](stopselftest.md) \(from device to platform\) is a response which confirms the StopSelfTestRequest has been executed or rejected.
* [**UpdateFirmwareRequest**](updatefirmware.md) \(from platform to device\) is a request which notifies the device to download a new firmware version from a server using a URL.
* [**UpdateFirmwareResponse**](updatefirmware.md) \(from device to platform\) is a response which confirms the UpdateFirmwareRequest has been executed or rejects the UpdateFirmwareRequest. Please note there are several events which are sent from the device to the platform to inform the platform when the firmware has been downloaded and whether or not the firmware was successfully activated.
* [**SetLightRequest**](setlight.md) \(from platform to device\) is a request that notifies the device to switch on or off one ore several light relays, optionally with a dim-value per relay.
* [**SetLightResponse**](setlight.md) \(from device to platform\) is a response which confirms the SetLightRequest has been executed or rejected.
* [**GetStatusRequest**](getstatus.md) \(from platform to device\) is a request that requires the device to send the status of all relays, current network link and preferred network link, the type of configuration \(PSLD vs SSLD\), and the event notification mask which has been set.
* [**GetStatusResponse**](getstatus.md) \(from device to platform\) is a response which confirms the GetStatusRequest has been executed and returns the current status for all of the relays and other information or rejects the GetStatusRequest.
* [**ResumeScheduleRequest**](resumeschedule.md) \(from platform to device\) is a request that notifies the device to continue the current schedule after the current schedule was interrupted \(for example by switching by hand using SetLightRequest\). This request can operate on a single relay or on all relays and the resuming of the schedule can be immediate or at the next schedule-entry.
* [**ResumeScheduleResponse**](resumeschedule.md) \(from device to platform\) is a response which confirms the ResumeScheduleRequest has been executed or rejected.
* [**SetEventNotificationsRequest**](seteventnotifications.md) \(from platform to device\) is a request that sets the event notification mask.
* [**SetEventNotificationsResponse**](seteventnotifications.md) \(from device to platform\) is a response which confirms the SetEventNotifications request has been executed or rejected.
* [**EventNotificationRequest**](eventnotification.md) \(from device to platform\) is a request that pushes an event notification from a device to the platform.
* [**EventNotificationResponse**](eventnotification.md) \(from platform to device\) is a response which confirms the EventNotificationRequest has been executed or rejected.
* [**GetFirmwareVersionRequest**](getfirmwareversion.md) \(from platform to device\) is a request that requests the device to sent its current firmware version.
* [**GetFirmwareVersionResponse**](getfirmwareversion.md) \(from device to platform\) is a response that sends the current firmware version to the platform.
* [**SetScheduleRequest**](setschedule.md) \(from platform to device\) is a request that sends a light or tariff schedule to the device.
* [**SetScheduleResponse**](setschedule.md) \(from device to platform\) is a response which confirms the SetScheduleRequest has been executed or rejected.
* [**SetConfigurationRequest**](setconfiguration.md) \(from platform to device\) is a request that sends configuration settings to the device.
* [**SetConfigurationResponse**](setconfiguration.md) \(from device to platform\) is a response which confirms the SetConfigurationRequest has been executed or rejected.
* [**GetConfigurationRequest**](getconfiguration.md) \(from platform to device\) is a request that requests the device to send its current configuration settings.
* [**GetConfigurationResponse**](getconfiguration.md) \(from device to platform\) is a response which confirms the GetConfigurationRequest has been executed or rejected.
* [**SetRebootRequest**](setreboot.md) \(from platform to device\) is a request that notifies the device to reboot immediately.
* [**SetRebootResponse**](setreboot.md) \(from device to platform\) is a response which confirms the SetRebootRequest has been executed or rejected.
* [**SetTransitionRequest**](settransition.md) \(from platform to device\) is a request that notifies the device to switch its light relays according to light measurement schedule-entries.
* [**SetTransitionResponse**](settransition.md) \(from device to platform\) is a response which confirms the SetTransitionRequest has been executed or rejected.
* [**UpdateDeviceSslCertification**](updatedevicesslcertification.md) \(from platform to device\) is a request which commands a device to download a new certificate file from a server using a URL.
* [**UpdateDeviceSslCertification**](updatedevicesslcertification.md) \(from platform to device\) is a response which returns the result of the UpdateFirmwareRequest. Please note there are several events which are sent from the device to the platform to inform the platform whether or not the certificate file was successfully downloaded and activated.
* [**SetDeviceVerificationKeyRequest**](setdeviceverificationkey.md) \(from platform to device\) is a request which sends a new OSGP public key to the device.
* [**SetDeviceVerificationKeyResponse**](setdeviceverificationkey.md) \(from platform to device\) is a response which returns the result of the SetDeviceVerificationKeyRequest.
* [**SwitchFirmwareRequest**](switchfirmware.md) \(from platform to device\) is a request which commands the device to switch to the other firmware bank.
* [**SwitchFirmwareResponse**](switchfirmware.md) \(from platform to device\) is a response which returns the result of the SwitchFirmwareRequest.
* [**SwitchConfigurationRequest**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Protocols/OSLP/v0.6.1/SwitchConfigurationRequest.md) \(from platform to device\) is a request which commands the device to switch to the other configuration bank.
* [**SwitchConfigurationResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Protocols/OSLP/v0.6.1/SwitchConfigurationResponse.md) \(from platform to device\) is a response which returns the result of the SwitchConfigurationRequest.

