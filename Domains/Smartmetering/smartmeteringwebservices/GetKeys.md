
## GetKeys request

### Description
GetKeys is a request to retrieve keys of a device. Multiple keys can be requested in one request. The keys in the response will be encrypted with the configured public key of the calling application.

The following key types are allowed:
- E_METER_MASTER_KEY,
- E_METER_AUTHENTICATION_KEY,
- E_METER_ENCRYPTION_KEY_UNICAST,
- E_METER_ENCRYPTION_KEY_BROADCAST,
- G_METER_MASTER_KEY,
- G_METER_ENCRYPTION_KEY,
- G_METER_FIRMWARE_UPDATE_AUTHENTICATION_KEY,
- G_METER_OPTICAL_PORT_KEY

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)
