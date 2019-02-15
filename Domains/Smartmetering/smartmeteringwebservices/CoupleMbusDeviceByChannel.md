## CoupleMbusDeviceByChannel request

### Description
CoupleMbusDeviceByChannel is a request to couple a gateway and a m-bus device on a specific channel. This request should only be used for coupling after a NEW_MBUS_DEVICE_DISCOVERED alarm. If it is used with a channel where no mbus device is registered yet, it will throw an error. 

This operation does not write any information to the gateway device, it just collects the data that is already in that register and return this in a [CoupleMbusDeviceByChannelResponse](GetCoupleMbusDeviceByChannelResponse.md) so the database can be updated accordingly. 

The request needs the following parameters:
- DeviceIdentification of the gateway device
- CoupleMbusDeviceByChannelRequestData containing the channel number

All requests have similar response behaviour which is described in [ResponseMessages](ResponseMessages.md)

[GetCoupleMbusDeviceByChannelResponse](GetCoupleMbusDeviceByChannelResponse.md) can be used to collect the result of the CoupleMbusDeviceByChannel request. This request contains the DeviceIdentification and CorrelationUid which is returned after performing a CoupleMbusDeviceByChannel request.

### References

XSD: [sm-installation.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-installation.xsd)

WSDL: [SmartMeteringInstallation.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringInstallation.wsdl)
