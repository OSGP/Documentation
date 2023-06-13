<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# SetReboot

## Description

Request which commands a device to reboot immediately. After the reboot, the device will switch its relays according to its schedule. Any ad hoc changes to relays will be lost.

Response which returns the result of the request.

## IEC61850 Fields

| **ATTRIBUTE** | **FC** | **SUB ATTRIBUTE** | **DATATYPE** | **DESCRIPTION** |
| :--- | :--- | :--- | :--- | :--- |
| CSLC.RbOper | ST | Oper.ctlVal | BOOLEAN | Flag which, if set to true, will trigger a reboot. |

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope
    xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetRebootRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
      </ns1:SetRebootRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetRebootAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/adhocmanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925104202472</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetRebootAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetRebootAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925104202472</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetRebootAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetRebootResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/adhocmanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetRebootResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>>
```

IEC61850 platform message of the data set on the device:

```javascript
LogicalDevice: SWDeviceGenericIO
messageType: Reboot {
  CSLC.RbOper[ST].Oper.ctlVal: true
}
```

IEC61850 protocol adapter logging:

```text
2018-09-25 10:44:06.142] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.RbOper
2018-09-25 10:44:06.160] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850RebootCommand@apply:41 - device: KAI-0000000053, rebootOperationNode: SWDeviceGenericIO/CSLC.RbOper [CO]
SWDeviceGenericIO/CSLC.RbOper.Oper [CO]
SWDeviceGenericIO/CSLC.RbOper.Oper.ctlVal: false
SWDeviceGenericIO/CSLC.RbOper.Oper.origin [CO]
SWDeviceGenericIO/CSLC.RbOper.Oper.origin.orCat: 0
SWDeviceGenericIO/CSLC.RbOper.Oper.origin.orIdent: []
SWDeviceGenericIO/CSLC.RbOper.Oper.ctlNum: 0
SWDeviceGenericIO/CSLC.RbOper.Oper.T: Thu Jan 01 00:00:00 UTC 1970
SWDeviceGenericIO/CSLC.RbOper.Oper.Test: false
SWDeviceGenericIO/CSLC.RbOper.Oper.Check: 0x0
2018-09-25 10:44:06.176] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850RebootCommand@apply:47 - device: KAI-0000000053, oper: SWDeviceGenericIO/CSLC.RbOper.Oper [CO]
SWDeviceGenericIO/CSLC.RbOper.Oper.ctlVal: false
SWDeviceGenericIO/CSLC.RbOper.Oper.origin [CO]
SWDeviceGenericIO/CSLC.RbOper.Oper.origin.orCat: 0
SWDeviceGenericIO/CSLC.RbOper.Oper.origin.orIdent: []
SWDeviceGenericIO/CSLC.RbOper.Oper.ctlNum: 0
SWDeviceGenericIO/CSLC.RbOper.Oper.T: Thu Jan 01 00:00:00 UTC 1970
SWDeviceGenericIO/CSLC.RbOper.Oper.Test: false
SWDeviceGenericIO/CSLC.RbOper.Oper.Check: 0x0
2018-09-25 10:44:06.176] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850RebootCommand@apply:50 - device: KAI-0000000053, ctlVal: SWDeviceGenericIO/CSLC.RbOper.Oper.ctlVal: false
2018-09-25 10:44:06.176] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850RebootCommand@apply:53 - device: KAI-0000000053, set ctlVal to true in order to reboot the device
2018-09-25 10:44:06.192] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-25 10:44:06.193] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
```

