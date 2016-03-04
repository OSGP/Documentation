## SendWakeupSms request

### Description
SendWakeupSms is a request to wake up the E-meter by an empty SMS when it is sleeping. When the device becomes awake, an active session is setup, an IP-address is created and stored in the database and communication will be possible.

The request is send with the DeviceIdentification number from the desired device. The platform sends an wakeup request to [Jasper Wireless](https://kpn.jasperwireless.com/provision/jsp/login.jsp) with the applicable ICC ID which is retrieved from the database, based on the DeviceIdentification . 

[GetSendWakeupSmsResponses](./GetSendWakeupSmsResponses) request returns the result from sending the wakeup request. The response request contains the DeviceIdentification and CorrelationUid which is received from the SynchronizeTime request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)
