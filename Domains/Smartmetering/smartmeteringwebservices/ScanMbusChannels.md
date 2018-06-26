## ScanMbusChannels request

### Description
ScanMbusChannels is a request to read the M-Bus Short Equipment Identifier (Short ID) attributes (Identification number, Manufacturer identification, Version identification, and Device type identification) from all four channels on a Gateway device to determine if an M-Bus device is bound on a channel of the Gateway device.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

The returned response for the ScanMbusChannels request is as specified in [ScanMbusChannelsResponse](ScanMbusChannelsResponse.md).

### References

XSD: [sm-management.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringAdhoc.wsdl)