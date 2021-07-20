# FlexOVL\_540\_171101\_2

Contract for [FlexOVL\_540\_171101\_2](flexovl_540_171101_2_out.icd.md) The contract specifies the messages which can be exchanged with a LMD.

## Messages

The messages below are part of OSGP and implemented in the IEC61850 protocol adapter and supported by the FlexOVL\_540\_171101\_2 device firmware.

* [**GetStatusRequest**](getstatus.md) \(from platform to device\) is a request which queries a device for the current status of all its digital inputs.
* [**GetStatusResponse**](getstatus.md) \(from device to platform\) is a response which returns the result of the GetStatusRequest and, if 'result = OK', returns the current status for all of the digital inputs.
* [**EventNotificationRequest**](eventnotification.md) \(from device to platform\) is a request that pushes an event notification from a device to the platform.

No other message types are supported by this device.

