## ResponseMessages

The response of a request should always contain a DeviceIdentification and CorrelationUid which is used in the response request. 
Assertions validate if  there is a 'SOAP Response' received, if the response is 'Schema Compliance' with the WSDL and if there has been a 'not SOAP Fault'. 
The last one occurs when a faultcode is returned. Possible faults are connection timed-out, SmartMeter could not be found, TCP-IP connection error or Correlationuid is unknown. 
The faults can be among others a FunctionalFault or TechnicalFault. The format of these faults is described in the [common.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/common.xsd).
