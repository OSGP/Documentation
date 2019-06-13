## SetDeviceCommunicationSettings request

### Description
SetDeviceCommunicationSettings is a request to set the OSGP device communication settings for a specific device. The request needs the DeviceIdentification, ChallengeLength, WithListSupported, SelectiveAccessSupported, IpAddressIsStatic, UseSn and UseHdlc.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

The returned response for the SetDeviceCommunicationSettings request is as specified in [SetDeviceCommunicationSettingsResponse](SetDeviceCommunicationSettingsResponse.md).


### References

XSD: [sm-management.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-management.xsd)

WSDL: [SmartMeteringManagement.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringManagement.wsdl)
