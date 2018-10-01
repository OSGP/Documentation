## EventNotification messages

### Description

Light sensor device can send buffered report containing the current state of the digital inputs. The buffered report will be sent on data change.
OSGP will interpret the buffered report and save event information contained in the reports.

IEC61850 protocol Adapter logging:
``` json
2018-10-01 16:11:34.057] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.n.r.Iec61850ClientLMDEventListener@newReport:45 - newReport for reportId: A, timeOfEntry: 2018-10-01T16:11:34.057Z, sqNum: null
2018-10-01 16:11:34.057] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.n.r.Iec61850ClientLMDEventListener@logReportDetails:160 - Report details for device LichtmeterOost
                     RptId:     A
                DataSetRef:     AA1TH01LD0/LLN0.StatNrmlA
                   ConfRev:     null
                   BufOvfl:     null
                   EntryId:     null
        InclusionBitString:     [false, true, false, false, true, true, false, false, false, false, false, false, false, false, true, false, false]
        MoreSegmentsFollow:     false
                     SqNum:     null
                  SubSqNum:     null
               TimeOfEntry:     null
                   DataSet:     AA1TH01LD0/LLN0.StatNrmlA
           DataSet members:     4
                    member:     AA1TH01LD0/SPGGIO1.Ind [ST]
AA1TH01LD0/SPGGIO1.Ind.stVal: false
AA1TH01LD0/SPGGIO1.Ind.q: 0x00 0x00
AA1TH01LD0/SPGGIO1.Ind.t: Thu Jan 01 00:00:00 UTC 1970
                    member:     AA1TH01LD0/SPGGIO2.Ind [ST]
AA1TH01LD0/SPGGIO2.Ind.stVal: true
AA1TH01LD0/SPGGIO2.Ind.q: 0x00 0x00
AA1TH01LD0/SPGGIO2.Ind.t: Thu Jan 01 00:00:00 UTC 1970
                    member:     AA1TH01LD0/SPGGIO3.Ind [ST]
AA1TH01LD0/SPGGIO3.Ind.stVal: false
AA1TH01LD0/SPGGIO3.Ind.q: 0x00 0x00
AA1TH01LD0/SPGGIO3.Ind.t: Thu Jan 01 00:00:00 UTC 1970
                    member:     AA1TH01LD0/SPGGIO4.Ind [ST]
AA1TH01LD0/SPGGIO4.Ind.stVal: false
AA1TH01LD0/SPGGIO4.Ind.q: 0x00 0x00
AA1TH01LD0/SPGGIO4.Ind.t: Thu Jan 01 00:00:00 UTC 1970


2018-10-01 16:11:34.057] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.n.r.Iec61850ClientLMDEventListener@processReportedDataForLightMeasurementDevices:87 - Trying to find light measurement devices...
2018-10-01 16:11:34.135] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.n.r.Iec61850ClientLMDEventListener@processReportedDataForLightMeasurementDevices:89 - Found 4 light measurement devices.
2018-10-01 16:11:34.135] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.n.r.Iec61850ClientLMDEventListener@processReportedDataForLightMeasurementDevices:101 - Returning 4 results.
2018-10-01 16:11:34.139] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.a.s.DeviceManagementService@addEventNotifications:109 - addEventNotifications called for device LichtmeterOost: [EventNotificationDto[deviceUid=LichtmeterOost, dateTime=2018-10-01T16:11:34.057Z, eventType=LIGHT_SENSOR_REPORTS_LIGHT, index=3, description=reportId: A, timeOfEntry: 2018-10-01T16:11:34.057Z, sqNum: null]]
2018-10-01 16:11:34.139] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.m.OsgpRequestMessageSender@send:34 - Sending request message to OSGP.
2018-10-01 16:11:34.145] [osgp-tst-03] [ActiveMQ Task-1] INFO o.a.a.t.failover.FailoverTransport@doReconnect:1055 - Successfully connected to tcp://localhost:61616
2018-10-01 16:11:34.198] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.a.s.DeviceManagementService@addEventNotifications:109 - addEventNotifications called for device LichtmeterLeeuwarden: [EventNotificationDto[deviceUid=LichtmeterLeeuwarden, dateTime=2018-10-01T16:11:34.057Z, eventType=LIGHT_SENSOR_REPORTS_LIGHT, index=4, description=reportId: A, timeOfEntry: 2018-10-01T16:11:34.057Z, sqNum: null]]
2018-10-01 16:11:34.199] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.m.OsgpRequestMessageSender@send:34 - Sending request message to OSGP.
2018-10-01 16:11:34.202] [osgp-tst-03] [ActiveMQ Task-1] INFO o.a.a.t.failover.FailoverTransport@doReconnect:1055 - Successfully connected to tcp://localhost:61616
2018-10-01 16:11:34.292] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.a.s.DeviceManagementService@addEventNotifications:109 - addEventNotifications called for device LichtmeterNoord: [EventNotificationDto[deviceUid=LichtmeterNoord, dateTime=2018-10-01T16:11:34.057Z, eventType=LIGHT_SENSOR_REPORTS_DARK, index=2, description=reportId: A, timeOfEntry: 2018-10-01T16:11:34.057Z, sqNum: null]]
2018-10-01 16:11:34.292] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.m.OsgpRequestMessageSender@send:34 - Sending request message to OSGP.
2018-10-01 16:11:34.356] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.a.s.DeviceManagementService@addEventNotifications:109 - addEventNotifications called for device LichtmeterWest: [EventNotificationDto[deviceUid=LichtmeterWest, dateTime=2018-10-01T16:11:34.057Z, eventType=LIGHT_SENSOR_REPORTS_LIGHT, index=1, description=reportId: A, timeOfEntry: 2018-10-01T16:11:34.057Z, sqNum: null]]
2018-10-01 16:11:34.356] [osgp-tst-03] [Thread-613] INFO o.o.a.p.i.i.m.OsgpRequestMessageSender@send:34 - Sending request message to OSGP.
```
