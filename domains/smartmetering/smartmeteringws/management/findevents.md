# FindEvents

## Description

FindEvents is a request to retrieve periodic events logging from a device. The request needs the DeviceIdentification, EventLogCategory, From and Until DateTime. The EventlogCategories consist off:

* STANDARD\_EVENT\_LOG
* FRAUD\_DETECTION\_LOG
* COMMUNICATION\_SESSION
* M\_BUS\_EVENT\_LOG
* POWER\_QUALITY\_EVENT\_LOG
* AUXILIARY\_EVENT\_LOG

DSMR Chapter 4.2.1 and SMR chapter 4.2.1 describe the several events and their description.

All requests have similar response behaviour which is described in [ResponseMessages](../../responsemessages.md).

[GetFindEventsResponse](getfindeventsresponse.md) returns if the result is successful from the request. The response contains the DeviceIdentification and CorrelationUid which is received from the FindEvents request.

## References

XSD: [sm-management.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-management.xsd)

WSDL: [SmartMeteringManagement.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringManagement.wsdl)

