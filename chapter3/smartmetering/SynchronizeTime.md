## SynchronizeTime request

### Description
SynchronizeTime request synchronizes the date and time on a device. The date and time are retrieved from the server and sent to the device with CLASS_ID 8, OBIS_CODE 0.0.1.0.0.255 and ATTRIBUTE_ID 2. The request is send with the DeviceIdentification number from the desired device.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSynchronizeTimeResponse](./GetSynchronizeTimeResponse.md) returns the result from synchronizing date and time. The response request contains the DeviceIdentification and CorrelationUid which is received from the SynchronizeTime request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)

