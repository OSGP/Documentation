# GetProfileGenericDataResponse

## Description

GetProfileGenericDataResponse is a request to return the Generic profile buffer data as requested by a [GetProfileGenericData](getprofilegenericdata.md) request. It contains the DeviceIdentification and CorrelationUid which is received from the [GetProfileGenericData](getprofilegenericdata.md) request.

The response to the GetProfileGenericDataResponse request contains the logical name of the requested Generic profile as LogicalName according to the ObisCodeValues as specified in [common.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/common.xsd).

The definitions of the capture objects from the buffer that are included in the response are listed as CaptureObject according to the CaptureObject in [common.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/common.xsd).

The actual data from the buffer is included in the ProfileEntries, where each ProfileEntry has a list of values that match the capture objects from the response.

## References

XSD: [sm-monitoring.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-monitoring/sm-monitoring.xsd)

WSDL: [SmartMeteringMonitoring.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringMonitoring.wsdl)

