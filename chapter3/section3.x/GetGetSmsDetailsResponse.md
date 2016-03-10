## GetGetSmsDetailsResponse

### Description

GetGetSmsDetailsResponse request returns the result from sending the [GetSmsDetails](./GetSmsDetails.md) request. The response request contains the DeviceIdentification and CorrelationUid which is received from the GetSmsDetails request. The response returns the status, sms message attempt status and message type. With these information can be determined if the SMS message is delivered and acknowledged if it is successful received.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)
