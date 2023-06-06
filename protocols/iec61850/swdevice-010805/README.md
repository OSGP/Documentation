<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# SWDevice-010805

Contract for [SWDevice-010805](swdevice-010805.icd.md) The contract specifies the messages which can be exchanged with an SSLD.

## Messages

The messages below are part of OSGP and implemented in the IEC61850 protocol adapter and supported by the SWDevice-010805 device firmware.

* [**RegisterDeviceRequest**](registerdevice.md) \(from device to platform\) is a request that notifies the platform a device wants to register. During the registration the device sends its identification \(serial number\), and the device communicates its IP address to the platform.
* [**RegisterDeviceResponse**](registerdevice.md) \(from platform to device\) is a response which informs the device that the registration was successful. The device will not register anymore, until the next power cycle or reboot.
* [**StartSelfTestRequest**](startselftest.md) \(from platform to device\) is a request which commands a device to switch all light relays on.
* [**StartSelfTestResponse**](startselftest.md) \(from device to platform\) is a response which returns the result of the StartSelfTestRequest.
* [**StopSelfTestRequest**](stopselftest.md) \(from platform to device\) is a request which commands a device to switch all light relays off.
* [**StopSelfTestResponse**](stopselftest.md) \(from device to platform\) is a response which returns the result of the StopSelfTestRequest.
* [**SetRebootRequest**](setreboot.md) \(from platform to device\) is a request which commands a device to reboot immediately.
* [**SetRebootResponse**](setreboot.md) \(from device to platform\) is a response which returns the result of the SetRebootRequest.
* [**SetLightRequest**](setlight.md) \(from platform to device\) is a request which commands a device to switch on or off one ore several light relays.
* [**SetLightResponse**](setlight.md) \(from device to platform\) is a response which returns the result of the SetLightRequest.
* [**SetTransitionRequest**](settransition.md) \(from platform to device\) is a request which commands a device to switch its light relays according to light measurement schedule-entries.
* [**SetTransitionResponse**](settransition.md) \(from device to platform\) is a response which returns the result of the SetTransitionRequest.
* [**SetEventNotificationsRequest**](seteventnotifications.md) \(from platform to device\) is a request which commands a device to set the event notification mask.
* [**SetEventNotificationsResponse**](seteventnotifications.md) \(from device to platform\) is a response which returns the result of the SetEventNotificationsRequest.
* [**GetStatusRequest**](getstatus.md) \(from platform to device\) is a request which queries a device for the current status of all its relays, the type of configuration \(RELAY for SSLD\), and the event notification mask set on the device.
* [**GetStatusResponse**](getstatus.md) \(from device to platform\) is a response which returns the result of the GetStatusRequest and, if 'result = OK', returns the current status for all of the relays and other information.
* [**GetFirmwareVersionRequest**](getfirmwareversion.md) \(from platform to device\) is a request which queries a device for its current firmware version.
* [**GetFirmwareVersionResponse**](getfirmwareversion.md) \(from device to platform\) is a response which returns the result of the GetFirmwareVersionRequest and, if 'result = OK', returns the current firmware version.
* [**UpdateFirmwareRequest**](updatefirmware.md) \(from platform to device\) is a request which commands a device to download a new firmware version from a server using a URL.
* [**UpdateFirmwareResponse**](updatefirmware.md) \(from device to platform\) is a response which returns the result of the UpdateFirmwareRequest, which indicates if the device will start the process to download and install a new firmware version. Please note there are several events which are sent from the device to the platform to inform the platform when the firmware has been downloaded and whether or not the firmware was successfully activated.
* [**GetConfigurationRequest**](getconfiguration.md) \(from platform to device\) is a request which queries a device for its current configuration settings.
* [**GetConfigurationResponse**](getconfiguration.md) \(from device to platform\) is a response which returns the result of the GetConfigurationRequest and, if 'result = OK', returns the configuration settings retrieved from the device.
* [**SetConfigurationRequest**](setconfiguration.md) \(from platform to device\) is a request which commands a device to update its configuration.
* [**SetConfigurationResponse**](setconfiguration.md) \(from device to platform\) is a response which returns the result of the SetConfigurationRequest.
* [**SetScheduleRequest**](setschedule.md) \(from platform to device\) is a request which commands a device to update its light or tariff schedule.
* [**SetScheduleResponse**](setschedule.md) \(from device to platform\) is a response which returns the result of the SetScheduleRequest.
* [**UpdateDeviceSslCertificationRequest**](updatedevicesslcertification.md) \(from platform to device\) is a request which commands a device to download a new certificate file from a server using a URL.
* [**UpdateDeviceSslCertificationResponse**](updatedevicesslcertification.md) \(from platform to device\) is a response which returns the result of the UpdateDeviceSslCertificationRequest, which indicates if the device will start the process to download and install a new certificate file. Please note there are several events which are sent from the device to the platform to inform the platform whether or not the certificate file was successfully downloaded and activated.
* [**EventNotificationRequest**](eventnotification.md) \(from device to platform\) is a request that pushes an event notification from a device to the platform.

The following messages are not supported in IEC61850 and will return an UNSUPPORTED\_DEVICE\_ACTION SOAP Fault when a request is sent:

* **ResumeScheduleRequest**
* **SwitchConfigurationRequest**
* **SwitchFirmwareRequest**
* **SetDeviceVerificationKeyRequest**

The following message from device to OSGP is also not supported:

* **ConfirmRegisterDeviceRequest**

