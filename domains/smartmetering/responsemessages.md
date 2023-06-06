<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# ResponseMessages

The response of a request should always contain a DeviceIdentification and CorrelationUid which is used in the response request. Assertions validate if there is a 'SOAP Response' received, if the response is 'Schema Compliant' with the WSDL and if there has been a 'not SOAP Fault'. The last one occurs when a fault code is returned. Possible faults are connection timed-out, SmartMeter could not be found, TCP-IP connection error or Correlationuid is unknown. The faults can be among others a FunctionalFault or TechnicalFault. Responses to a bundle request may include faults in the form of FaultResponseData, resembling the other faults. The format of these faults is described in the [common.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/common.xsd).

