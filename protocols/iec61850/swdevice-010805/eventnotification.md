# EventNotification

## Description

Buffered report sent from device to platform containing information about 1 event. The devices keep up to 120 events in the cyclic buffer `CSLC.EvnBuf.evn1/env120`. The events are converted to buffered reports when OSGP triggers the device to do so by writing true to `CSLC.evn_rpn01[BR].RptEna`. When this happens, the device will send the buffered reports to OSGP. OSGP will save the information specified by the remark field, like the event type and the event time:

```text
evnType: 4 = TARIFF_EVENTS_TARIFF_ON
swNum: 1 = get external index for switch 1
trgType: 3 = fixed time trigger
swVal: true = ON
trgTime: 2018-10-01T05:00:00.000Z
```

Example buffered report:

```text
                     RptId:     evn_rpn
                DataSetRef:     SWDeviceGenericIO/LLN0.evn_rpn
                   ConfRev:     null
                   BufOvfl:     true
                   EntryId:     none: [0, 0, 1, 102, 45, -1, 87, -73]
                                (f-�W�)
        InclusionBitString:     [true]
        MoreSegmentsFollow:     false
                     SqNum:     0
                  SubSqNum:     null
               TimeOfEntry:     none: 1096606800823
                                (2018-10-01T05:00:00.823Z)
               ReasonCodes:
                                0x40    (DataChange)
                   DataSet:     SWDeviceGenericIO/LLN0.evn_rpn
           DataSet members:     1
                    member:     SWDeviceGenericIO/CSLC.EvnRpn [ST]
SWDeviceGenericIO/CSLC.EvnRpn.evnType: 4
SWDeviceGenericIO/CSLC.EvnRpn.swNum: 1
SWDeviceGenericIO/CSLC.EvnRpn.trgType: 3
SWDeviceGenericIO/CSLC.EvnRpn.swVal: true
SWDeviceGenericIO/CSLC.EvnRpn.trgTime: Mon Oct 01 05:00:00 UTC 2018
SWDeviceGenericIO/CSLC.EvnRpn.remark: remark
                                        evnType: 4 = TARIFF_EVENTS_TARIFF_ON
                                        swNum: 1 = get external index for switch 1
                                        trgType: 3 = fixed time trigger
                                        swVal: true = ON
                                        trgTime: 2018-10-01T05:00:00.000Z
                                        remark: remark
```

NOTE: After executing operations SetLightRequest, GetStatusRequest and SetTransitionRequest, OSGP will enable reporting on the device. Optionally, OSGP will enable reporting after DeviceRegistrationRequest \(default is false\).

## IEC61850 Fields

| **ATTRIBUTE** | **FC** | **SUB ATTRIBUTE** | **DATATYPE** | **DESCRIPTION** |
| :--- | :--- | :--- | :--- | :--- |
| CSLC.evn\_rpn01 | BR | RptEna | BOOLEAN | Flag which indicates to the device to send buffered reports. |

IEC61850 platform message of the data sent to the device:

```javascript
LogicalDevice: SWDeviceGenericIO
messageType: EnableBufferedReporting {
  CSLC.evn_rpn01[BR].RtpEna: true
}
```

IEC61850 protocol Adapter logging:

```javascript
2018-10-01 10:52:10.476] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: GET_LIGHT_STATUS with message priority: 4
2018-10-01 10:52:10.477] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: GET_LIGHT_STATUS for domain: PUBLIC_LIGHTING 1.0
2018-10-01 10:52:10.477] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-10-01 10:52:10.477] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-10-01 10:52:10.480] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-10-01 10:52:10.483] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 0 and max retry count: 0
2018-10-01 10:52:12.312] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-10-01 10:52:12.314] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-10-01 10:52:12.406] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-10-01T10:52:10.477Z, end time: 2018-10-01T10:52:12.406Z, total time in milliseconds: 1929
2018-10-01 10:52:12.414] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.Pos
2018-10-01 10:52:12.751] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 1 => on
2018-10-01 10:52:12.752] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.Pos
2018-10-01 10:52:13.106] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 2 => off
2018-10-01 10:52:13.106] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.Pos
2018-10-01 10:52:13.405] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:63 - Got status of relay 3 => off
2018-10-01 10:52:13.406] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.EvnBuf
2018-10-01 10:52:13.728] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, enbEvnType has value 1FFFFFF
2018-10-01 10:52:13.728] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.s.c.Iec61850GetStatusCommand@apply:74 - Got EvnBuf.enbEvnType filter 1FFFFFF
2018-10-01 10:52:13.729] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.SWCf
2018-10-01 10:52:14.058] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, LT has value RELAY
2018-10-01 10:52:14.058] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-10-01 10:52:14.058] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.m.p.PublicLightingGetStatusRequestMessageProcessor@handleDeviceResponse:69 - Override for handleDeviceResponse() by PublicLightingGetStatusRequestMessageProcessor
2018-10-01 10:52:14.058] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.m.SsldDeviceRequestMessageProcessor@handleGetStatusDeviceResponse:68 - Handling getStatusDeviceResponse for device: KAI-0000000053
2018-10-01 10:52:14.058] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: GET_LIGHT_STATUS with message priority: 4
2018-10-01 10:52:14.064] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/LLN0.evn_rpn01
2018-10-01 10:52:14.064] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@setSqNum:62 - First new SqNum for report listener for device: KAI-0000000053 is: 0
2018-10-01 10:52:14.509] [osgp-tst-04] [iec61850RequestsMessageListenerContainer-7] INFO o.o.a.p.i.i.n.s.c.Iec61850EnableReportingCommand@enableReportingOnDeviceWithoutUsingSequenceNumber:79 - Allowing device KAI-0000000053 to send reports containing events
2018-10-01 10:52:14.786] [osgp-tst-04] [Thread-327] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@newReport:92 - newReport for device: KAI-0000000053, reportId: evn_rpn, timeOfEntry: 2018-10-01T05:00:00.823Z, sqNum: 0
2018-10-01 10:52:14.795] [osgp-tst-04] [Thread-327] WARN o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@newReport:96 - Buffer Overflow reported for device: KAI-0000000053, reportId: evn_rpn, timeOfEntry: 2018-10-01T05:00:00.823Z, sqNum: 0 - entries within the buffer may have been lost.
2018-10-01 10:52:14.796] [osgp-tst-04] [Thread-327] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@logReportDetails:273 - Report details for device KAI-0000000053
                     RptId:     evn_rpn
                DataSetRef:     SWDeviceGenericIO/LLN0.evn_rpn
                   ConfRev:     null
                   BufOvfl:     true
                   EntryId:     none: [0, 0, 1, 102, 45, -1, 87, -73]
                                (f-�W�)
        InclusionBitString:     [true]
        MoreSegmentsFollow:     false
                     SqNum:     0
                  SubSqNum:     null
               TimeOfEntry:     none: 1096606800823
                                (2018-10-01T05:00:00.823Z)
               ReasonCodes:
                                0x40    (DataChange)
                   DataSet:     SWDeviceGenericIO/LLN0.evn_rpn
           DataSet members:     1
                    member:     SWDeviceGenericIO/CSLC.EvnRpn [ST]
SWDeviceGenericIO/CSLC.EvnRpn.evnType: 4
SWDeviceGenericIO/CSLC.EvnRpn.swNum: 1
SWDeviceGenericIO/CSLC.EvnRpn.trgType: 3
SWDeviceGenericIO/CSLC.EvnRpn.swVal: true
SWDeviceGenericIO/CSLC.EvnRpn.trgTime: Mon Oct 01 05:00:00 UTC 2018
SWDeviceGenericIO/CSLC.EvnRpn.remark: remark
                                        evnType: 4 = TARIFF_EVENTS_TARIFF_ON
                                        swNum: 1 = get external index for switch 1
                                        trgType: 3 = fixed time trigger
                                        swVal: true = ON
                                        trgTime: 2018-10-01T05:00:00.000Z
                                        remark: remark


2018-10-01 10:52:14.796] [osgp-tst-04] [Thread-327] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@newReport:117 - Handle member SWDeviceGenericIO/CSLC.EvnRpn for device: KAI-0000000053, reportId: evn_rpn, timeOfEntry: 2018-10-01T05:00:00.823Z, sqNum: 0
2018-10-01 10:52:14.798] [osgp-tst-04] [Thread-328] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@newReport:92 - newReport for device: KAI-0000000053, reportId: evn_rpn, timeOfEntry: 2018-10-01T05:51:01.157Z, sqNum: 1
2018-10-01 10:52:14.798] [osgp-tst-04] [Thread-328] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@logReportDetails:273 - Report details for device KAI-0000000053
                     RptId:     evn_rpn
                DataSetRef:     SWDeviceGenericIO/LLN0.evn_rpn
                   ConfRev:     null
                   BufOvfl:     false
                   EntryId:     none: [0, 0, 1, 102, 46, 46, 10, 37]
                                (f..
%)
        InclusionBitString:     [true]
        MoreSegmentsFollow:     false
                     SqNum:     1
                  SubSqNum:     null
               TimeOfEntry:     none: 1096609861157
                                (2018-10-01T05:51:01.157Z)
               ReasonCodes:
                                0x40    (DataChange)
                   DataSet:     SWDeviceGenericIO/LLN0.evn_rpn
           DataSet members:     1
                    member:     SWDeviceGenericIO/CSLC.EvnRpn [ST]
SWDeviceGenericIO/CSLC.EvnRpn.evnType: 3
SWDeviceGenericIO/CSLC.EvnRpn.swNum: 2
SWDeviceGenericIO/CSLC.EvnRpn.trgType: 1
SWDeviceGenericIO/CSLC.EvnRpn.swVal: false
SWDeviceGenericIO/CSLC.EvnRpn.trgTime: Mon Oct 01 05:51:01 UTC 2018
SWDeviceGenericIO/CSLC.EvnRpn.remark: remark
                                        evnType: 3 = LIGHT_EVENTS_LIGHT_OFF
                                        swNum: 2 = get external index for switch 2
                                        trgType: 1 = light trigger (sensor trigger)
                                        swVal: false = OFF
                                        trgTime: 2018-10-01T05:51:01.000Z
                                        remark: remark


2018-10-01 10:52:14.799] [osgp-tst-04] [Thread-328] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@newReport:117 - Handle member SWDeviceGenericIO/CSLC.EvnRpn for device: KAI-0000000053, reportId: evn_rpn, timeOfEntry: 2018-10-01T05:51:01.157Z, sqNum: 1
2018-10-01 10:52:19.510] [osgp-tst-04] [Timer-52] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/LLN0.evn_rpn01
2018-10-01 10:52:21.299] [osgp-tst-04] [Timer-52] INFO o.o.a.p.i.i.n.s.c.Iec61850ClearReportCommand@clearReportOnDevice:32 - Cleared event buffer for device: KAI-0000000053
2018-10-01 10:52:21.301] [osgp-tst-04] [Thread-329] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@associationClosed:366 - associationClosed() for device: KAI-0000000053, IOException: Connection disconnected by client
2018-10-01 10:52:21.301] [osgp-tst-04] [Timer-52] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: GET_LIGHT_STATUS, Start time: 2018-10-01T10:52:10.477Z, end time: 2018-10-01T10:52:21.301Z, total time in milliseconds: 10824
2018-10-01 10:52:21.303] [osgp-tst-04] [Thread-329] INFO o.o.a.p.i.a.s.DeviceManagementService@addEventNotifications:109 - addEventNotifications called for device KAI-0000000053: [EventNotificationDto[deviceUid=KAI-0000000053, dateTime=2018-10-01T05:00:00.000Z, eventType=TARIFF_EVENTS_TARIFF_ON, index=1, description=fixed time trigger], EventNotificationDto[deviceUid=KAI-0000000053, dateTime=2018-10-01T05:51:01.000Z, eventType=LIGHT_EVENTS_LIGHT_OFF, index=2, description=light trigger (sensor trigger)]]
2018-10-01 10:52:21.304] [osgp-tst-04] [Thread-329] INFO o.o.a.p.i.i.m.OsgpRequestMessageSender@send:34 - Sending request message to OSGP.
```

