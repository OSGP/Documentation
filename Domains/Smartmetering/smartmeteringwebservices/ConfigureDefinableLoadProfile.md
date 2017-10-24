## ConfigureDefinableLoadProfile request

### Description
ConfigureDefinableLoadProfile is a request to change the configuration of the definable load profile (COSEM object of interface class 'Profile generic' with logical name '0-1:94.31.6.255') of the device. The request needs the DeviceIdentification, and at least one of CaptureObjects and CapturePeriod.

The CaptureObjects element may be included in the request to specify one or more objects to be captured in the definable load profile, containing definitions as CaptureObject according to the CaptureObjectDefinition in [common.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/common.xsd).
The CaptureObjects should not include the clock definition ({8,0-0:1.0.0.255,2,0}) as this will always be included as first capture object. This matches the way [GetProfileGenericData](./GetProfileGenericData.md) works when retrieving the buffer of the definable load profile (where you must not specify the clock definition as selected value).

The CapturePeriod may be included to specify the automatic capturing period in seconds (a value of zero meaning no automatic capturing should be done).

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

The response contains the DeviceIdentification and CorrelationUid which is received from the ConfigureDefinableLoadProfile request. [GetConfigureDefinableLoadProfileResponse](GetConfigureDefinableLoadProfileResponse.md) returns if the result is successful from the ConfigureDefinableLoadProfile request.

### References

XSD: [sm-configuration.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-configuration.xsd)

WSDL: [SmartMeteringConfiguration.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringConfiguration.wsdl)
