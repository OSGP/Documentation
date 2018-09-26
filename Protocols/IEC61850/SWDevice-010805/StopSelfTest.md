## StopSelfTest messages

### Description

Request which commands the device to switch all light relays off and then queries the device for the status of the relays.

Response which returns the result of the request.

### IEC61850 Fields

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|
|---|---|---|---|
|XSWC2.Pos|CO|Oper.ctlVal|BOOLEAN|
|XSWC3.Pos|CO|Oper.ctlVal|BOOLEAN|

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:StopDeviceTestRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
      </ns1:StopDeviceTestRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:StopDeviceTestAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925142825021</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:StopDeviceTestAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:StopDeviceTestAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925142825021</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:StopDeviceTestAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:StopDeviceTestResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:StopDeviceTestResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

IEC61850 platform message of the data written to the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: StopSelfTest {
  XSWC2.Pos[CO].Oper.ctlVal: false
  XSWC3.Pos[CO].Oper.ctlVal: false
}
```

IEC61850 platform message of the data read from the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: GetStatus {
  XSWC2.Pos[ST]: false
  CSLC.SWCf[CF]: RELAY
  XSWC3.Pos[ST]: false
  XSWC1.Pos[ST]: false
  CSLC.EvnBuf[CF]: 1FFFFFF
}
```

IEC61850 protocol adapter logging:
```
2018-09-25 14:30:28.448] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: STOP_SELF_TEST with message priority: 4
2018-09-25 14:30:28.448] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: STOP_SELF_TEST for domain: CORE 1.0
2018-09-25 14:30:28.448] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 2
2018-09-25 14:30:28.448] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using
 response time-out: 10000
2018-09-25 14:30:28.451] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053:
 {0=0, 1=1, 2=2, 3=3}
2018-09-25 14:30:28.452] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-09-25 14:30:28.496] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-25 14:30:28.497] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-serve
r-model/SWDevice-010805.icd
2018-09-25 14:30:28.559] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-09-25T14:30:28
.448Z, end time: 2018-09-25T14:30:28.559Z, total time in milliseconds: 111
2018-09-25 14:30:28.561] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:339 - Turning all lights relays off
2018-09-25 14:30:28.561] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@createListOfInternalIndicesToSwitch:220 - creating list of internal indices using device output settings
2018-09-25 14:30:28.561] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetLightCommand@apply:66 - Trying to switch light relay with internal index: 2 on: false for device: KAI-0000000053
2018-09-25 14:30:28.561] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.CfSt
2018-09-25 14:30:28.577] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850Commands@enableOperationOfRelay:56 - masterControl.enbOper is true, switching of relay 2 is enabled
2018-09-25 14:30:28.577] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.Pos
2018-09-25 14:30:28.592] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetLightCommand@switchLightRelay:108 - Switching relay 2 off
2018-09-25 14:30:28.608] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetLightCommand@apply:66 - Trying to switch light relay with internal index: 3 on: false for device: KAI-0000000053
2018-09-25 14:30:28.608] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.CfSt
2018-09-25 14:30:28.684] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850Commands@enableOperationOfRelay:56 - masterControl.enbOper is true, switching of relay 3 is enabled
2018-09-25 14:30:28.684] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.Pos
2018-09-25 14:30:28.908] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetLightCommand@switchLightRelay:108 - Switching relay 3 off
2018-09-25 14:30:28.924] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-25 14:30:28.925] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@selfTestSleep:391 - Waiting 5000 milliseconds before getting the device status
2018-09-25 14:30:33.925] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.Pos
2018-09-25 14:30:36.862] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 1 => off
2018-09-25 14:30:36.863] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.Pos
2018-09-25 14:30:37.550] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 2 => off
2018-09-25 14:30:37.550] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.Pos
2018-09-25 14:30:37.663] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 3 => off
2018-09-25 14:30:37.663] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.EvnBuf
2018-09-25 14:30:38.469] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, enbEvnType has value 1FFFFFF
2018-09-25 14:30:38.469] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:74 - Got EvnBuf.enbEvnType filter 1FFFFFF
2018-09-25 14:30:38.469] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.SWCf
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, LT has value RELAY
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:354 - Fetching and checking the devicestatus
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): false for lightValue.getIndex(): 1 and lightValueDto.getIndex(): 2
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): false for lightValue.getIndex(): 1 and lightValueDto.getIndex(): 3
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): true for lightValue.getIndex(): 2 and lightValueDto.getIndex(): 2
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): false for lightValue.getIndex(): 2 and lightValueDto.getIndex(): 3
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): false for lightValue.getIndex(): 3 and lightValueDto.getIndex(): 2
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): true for lightValue.getIndex(): 3 and lightValueDto.getIndex(): 3
2018-09-25 14:30:38.485] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:372 - All lights relays are off, returning OK
2018-09-25 14:30:38.486] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
2018-09-25 14:30:38.486] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: STOP_SELF_TEST with message priority: 4
```
