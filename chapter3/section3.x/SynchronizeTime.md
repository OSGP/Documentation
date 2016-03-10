## SynchronizeTime request

### Description
SynchronizeTime request synchronizes the date and time on a device. The date and time are retrieved from the server and sent to the device with CLASS_ID 8, OBIS_CODE 0.0.1.0.0.255 and ATTRIBUTE_ID 2. The request is send with the DeviceIdentification number from the desired device.

The response for the SynchronizeTime request should always contain an DeviceIdentification and CorrelationUid. Assertions validate if  there is a 'SOAP Response' received, if the response is 'Schema Compliance' with the WSDL and if there has been a 'not SOAP Fault'. The last one occurs when an faultcode is returned. Possible faults are connection timed-out, SmartMeter could not be found, TCP-IP connection error or Correlationuid is unknown. 
The faults can be among others a FunctionalFault or TechnicalFault. The format of these faults is described in the [common.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/common.xsd).

[GetSynchronizeTimeResponse](./GetSynchronizeTimeResponse.md) returns the result from synchronizing date and time. The response request contains the DeviceIdentification and CorrelationUid which is received from the SynchronizeTime request.

### References

XSD: [sm-adhoc.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-adhoc.xsd)

WSDL: [SmartMeteringAdhoc.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringAdhoc.wsdl)

