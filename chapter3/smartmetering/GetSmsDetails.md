## GetSmsDetails

### Description
GetSmsDetails is a request to receive information about the sent SMS and its delivery status from [SendWakeupSms](./SendWakeupSms.md), it needs the messageID which is obtained by the [GetSendWakeupSmsResponse](./GetSendWakeupSmsResponse) request and DeviceIdentification number.

All requests have similar response behaviour which is described in [ResponseMessages](./ResponseMessages.md).

[GetGetSmsDetailsResponse](,.GetGetSmsDetailsResponse.md) request returns the result from sending the GetSmsDetails request. The response request contains the DeviceIdentification and CorrelationUid which is received from the GetSmsDetails request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)
