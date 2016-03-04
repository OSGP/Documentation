## GetSendWakeupSmsResponse request

### Description
GetSendWakeupSmsResponse request returns the result from sending the wakeup request. The response request contains the DeviceIdentification and CorrelationUid which is received from the [SynchronizeTime](./SynchronizeTime.md) request. The response returns the messageID from the send SMS message which is needed to perform a [GetSmsDetails](./GetSmsDetails.md) request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)
