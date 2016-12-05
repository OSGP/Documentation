## FindEvents request

### Description
FindEvents is a request to retrieve periodic events logging from a device. 
The request needs the DeviceIdentification, EventLogCategory, From and Until DateTime.
The EventlogCategories consist off:
- STANDARD_EVENT_LOG
- FRAUD_DETECTION_LOG
- COMMUNICATION_SESSION
- M_BUS_EVENT_LOG

DSMR Chapter 4.2.1 describes the several events and their description.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetFindEventsResponse](GetFindEventsResponse.md) returns if the result is successful from the request. The response contains the DeviceIdentification and CorrelationUid which is received from the FindEvents request.

### References

XSD: [sm-management.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-management.xsd)

WSDL: [SmartMeteringManagement.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringManagement.wsdl)
