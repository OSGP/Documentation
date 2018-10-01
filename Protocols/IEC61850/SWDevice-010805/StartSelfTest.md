## StartSelfTest messages

### Description

Request which commands the device to switch all light relays on and then queries the device for the status of the relays.
Part of this request is also to retrieve the status of the relays after switching on.

Response returns the result of the request.

### IEC61850 Fields

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|**DESCRIPTION**|
|---|---|---|---|---|
|XSWC2.Pos|CO|Oper.ctlVal|BOOLEAN|Flag which, if set to true, immediately switches relay 2 on.|
|XSWC3.Pos|CO|Oper.ctlVal|BOOLEAN|Flag which, if set to true, immediately switches relay 3 on.|

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
      <ns1:StartDeviceTestRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
      </ns1:StartDeviceTestRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:StartDeviceTestAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925142331454</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:StartDeviceTestAsyncResponse>
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
      <ns1:StartDeviceTestAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925142331454</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:StartDeviceTestAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:StartDeviceTestResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:StartDeviceTestResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

IEC61850 platform message of the data written to the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: StartSelfTest {
  XSWC2.Pos[CO].Oper.ctlVal: true
  XSWC3.Pos[CO].Oper.ctlVal: true
}
```
IEC61850 platform message of the data read from the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: GetStatus {
  XSWC2.Pos[ST].stVal: true
  CSLC.SWCf[CF].LT: RELAY
  XSWC3.Pos[ST].stVal: true
  XSWC1.Pos[ST].stVal: false
  CSLC.EvnBuf[CF]enbEvnType: 1FFFFFF
}
```

IEC61850 protocol adapter logging:
```
2018-09-25 14:23:31.994] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: START_SELF_TEST with message priority: 4
2018-09-25 14:23:31.994] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: START_SELF_TEST for domain: CORE 1.0
2018-09-25 14:23:31.995] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-09-25 14:23:31.995] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-09-25 14:23:32.002] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-09-25 14:23:32.005] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-09-25 14:23:32.056] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-25 14:23:32.056] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-09-25 14:23:32.111] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-09-25T14:23:31.995Z, end time: 2018-09-25T14:23:32.111Z, total time in milliseconds: 116
2018-09-25 14:23:32.114] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:339 - Turning all lights relays on
2018-09-25 14:23:32.114] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@createListOfInternalIndicesToSwitch:220 - creating list of internal indices using device output settings
2018-09-25 14:23:32.114] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetLightCommand@apply:66 - Trying to switch light relay with internal index: 2 on: true for device: KAI-0000000053
2018-09-25 14:23:32.115] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.CfSt
2018-09-25 14:23:32.128] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850Commands@enableOperationOfRelay:56 - masterControl.enbOper is true, switching of relay 2 is enabled
2018-09-25 14:23:32.129] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.Pos
2018-09-25 14:23:32.144] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetLightCommand@switchLightRelay:108 - Switching relay 2 on
2018-09-25 14:23:32.162] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetLightCommand@apply:66 - Trying to switch light relay with internal index: 3 on: true for device: KAI-0000000053
2018-09-25 14:23:32.162] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.CfSt
2018-09-25 14:23:32.258] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850Commands@enableOperationOfRelay:56 - masterControl.enbOper is true, switching of relay 3 is enabled
2018-09-25 14:23:32.258] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.Pos
2018-09-25 14:23:32.480] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetLightCommand@switchLightRelay:108 - Switching relay 3 on
2018-09-25 14:23:32.523] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-25 14:23:32.523] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@selfTestSleep:391 - Waiting 5000 milliseconds before getting the device status
2018-09-25 14:23:37.524] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.Pos
2018-09-25 14:23:39.899] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 1 => off
2018-09-25 14:23:39.900] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.Pos
2018-09-25 14:23:40.148] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 2 => on
2018-09-25 14:23:40.148] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.Pos
2018-09-25 14:23:40.287] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 3 => on
2018-09-25 14:23:40.287] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.EvnBuf
2018-09-25 14:23:41.762] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, enbEvnType has value 1FFFFFF
2018-09-25 14:23:41.762] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:74 - Got EvnBuf.enbEvnType filter 1FFFFFF
2018-09-25 14:23:41.763] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.SWCf
2018-09-25 14:23:41.778] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, LT has value RELAY
2018-09-25 14:23:41.778] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-25 14:23:41.778] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:354 - Fetching and checking the devicestatus
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): false for lightValue.getIndex(): 1 and lightValueDto.getIndex(): 2
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): false for lightValue.getIndex(): 1 and lightValueDto.getIndex(): 3
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): true for lightValue.getIndex(): 2 and lightValueDto.getIndex(): 2
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): false for lightValue.getIndex(): 2 and lightValueDto.getIndex(): 3
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): false for lightValue.getIndex(): 3 and lightValueDto.getIndex(): 2
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:359 - relaysWithInternalIdToSwitch.getIndex().equals(lightValue.getIndex()): true for lightValue.getIndex(): 3 and lightValueDto.getIndex(): 3
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850SsldDeviceService@runSelfTest:372 - All lights relays are on, returning OK
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
2018-09-25 14:23:41.779] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: START_SELF_TEST with message priority: 4
2018-09-25 14:23:41.780] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: START_SELF_TEST, Start time: 2018-09-25T14:23:31.995Z, end time: 2018-09-25T14:23:41.780Z, total time in milliseconds: 9785
```
