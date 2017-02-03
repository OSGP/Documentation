## SynchronizeTime request

### Description
SynchronizeTime request synchronizes the date and time on a device. The date and time are retrieved from the server and sent to the device with CLASS_ID 8, OBIS_CODE 0.0.1.0.0.255 and ATTRIBUTE_ID 2. The request is sent with the DeviceIdentification number from the desired device. The request should contain a Deviation of local time to UTC in minutes (from the range of -720 to 720 inclusive) and a value Dst indicating whether daylight savings is active.
For example in Central European Summer Time, DST is active and times are UTC/GMT +2 hours. For devices in a region where CEST applies, during the summer time the value for deviation should be "-120" (120 minutes deducted from local time gives GMT/UTC time) and dst should be "true".

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSynchronizeTimeResponse](./GetSynchronizeTimeResponse.md) returns the result from synchronizing date and time. The response contains the DeviceIdentification and CorrelationUid which is received from the SynchronizeTime request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringAdhoc.wsdl)

