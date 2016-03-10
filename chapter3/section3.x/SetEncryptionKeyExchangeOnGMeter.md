## SetEncryptionKeyExchangeOnGMeter request

### Description
SetEncryptionKeyExchangeOnGMeter is a request to transfer and set a G-meter key on a G-meter via the E-meter. The request needs the DeviceIdentification from the G-meter.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetSetEncryptionKeyExchangeOnGMeterResponse](GetSetEncryptionKeyExchangeOnGMeterResponse.md) returns the result from setting a SetEncryptionKeyExchangeOnGMeter. The response request contains the DeviceIdentification and CorrelationUid which is received from the SetEncryptionKeyExchangeOnGMeter request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringConfiguration.wsdl)

