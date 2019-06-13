## SetEncryptionKeyExchangeOnGMeter request

### Description
SetEncryptionKeyExchangeOnGMeter is a request to transfer and set a G-meter key on a G-meter via the E-meter. The request needs the DeviceIdentification from the G-meter.
If the device identification of the G-meter is not known, but the gateway device identification and M-Bus channel are known, use the [SetMbusUserKeyByChannel](./SetMbusUserKeyByChannel.md) request instead.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSetEncryptionKeyExchangeOnGMeterResponse](GetSetEncryptionKeyExchangeOnGMeterResponse.md) returns the result from setting a SetEncryptionKeyExchangeOnGMeter. The response contains the DeviceIdentification and CorrelationUid which is received from the SetEncryptionKeyExchangeOnGMeter request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)

