## SetSchedule messages

### Description

Request which commands a device to set a light or tariff schedule.

Response which returns the result of the request.

### IEC61850 Fields

The table shows the fields for XSWC1 (relay 1). The device has 4 relays (XSWC1...XSWC4).

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|**DESCRIPTION**|
|---|---|---|---|---|
|XSWC1.Sche|CF|sche1.enable|BOOLEAN|Flag indicating the schedule entry is enabled.|
|XSWC1.Sche|CF|sche1.day|INT32|Day in yyyymmdd format or defined by DAY enum.|
|XSWC1.Sche|CF|sche1.tOn|INT32|Timestamp in hhmm format when relay should switch on or -1 if not used.|
|XSWC1.Sche|CF|sche1.tOnT|INT8|Schedule entry type, 0 = fixed time, 1 = light sensor, 2 = astronomical time.|
|XSWC1.Sche|CF|sche1.tOff|INT32|Timestamp in hhmm format when relay should switch off or -1 if not used.|
|XSWC1.Sche|CF|sche1.tOffT|INT8|Schedule entry type, 0 = fixed time, 1 = light sensor, 2 = astronomical time.|
|XSWC1.Sche|CF|sche1.minOnPer|INT16U|Minimun burning time for this relay.|
|XSWC1.Sche|CF|sche1.minOffPer|INT16U|Not used.|
|XSWC1.Sche|CF|sche1.srBefWd|INT16U|Window for light sensor trigger, minutes before astronomical time.|
|XSWC1.Sche|CF|sche1.srAftWd|INT16U|Window for light sensor trigger, minutes after astronomical time.|
|XSWC1.Sche|CF|sche1.igBefWd|INT16U|Not used.|
|XSWC1.Sche|CF|sche1.igAftWd|INT16U|Not used.|

Although the device supports setting 64 schedule entries (sche1...sche64) for 4 relays (XSWC1...XSWC4), the actual number of schedule entries is limited by OSGP to 50.

```
enum DAY {
  0 Every day of the week;
  -1 Every weekday: Monday, Tuesday, Wednesday, Thursday, Friday;
  -2 Every weekend day: Saturday, Sunday;
  1 Monday;
  2 Tuesday;
  3 Wednesday;
  4 Thursday;
  5 Friday;
  6 Saturday;
  7 Sunday;
}
```

### Examples

#### Example 1: Light schedule based on light measurement

Description:
This schedule combines a 'morning/evening light' with an 'all night light'. Relay 1 and 2 will be switched on using a light measurement trigger. Relay 2 will be switched off at 23:00 using an absolute time. Relay 2 will be switched on at 07:00, but only when no light measurement trigger has been received yet. Relay 1 and 2 will be switched off using a light measurement trigger.

Screenshot of this schedule in an OSGP client application:

![screenshot of schedule](./relay-1-and-2-schedule.jpg)

SOAP Request Message for Platform web service:

``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/publiclighting/schedulemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetScheduleRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>

         <ns1:Schedules>
            <ns1:WeekDay>ALL</ns1:WeekDay>
            <ns1:ActionTime>SUNRISE</ns1:ActionTime>
            <ns1:TriggerWindow>
               <ns1:minutesBefore>15</ns1:minutesBefore>
               <ns1:minutesAfter>15</ns1:minutesAfter>
            </ns1:TriggerWindow>
            <ns1:LightValue>
               <ns1:Index>0</ns1:Index>
               <ns1:On>false</ns1:On>
            </ns1:LightValue>
            <ns1:TriggerType>LIGHT_TRIGGER</ns1:TriggerType>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ALL</ns1:WeekDay>
            <ns1:ActionTime>SUNSET</ns1:ActionTime>
            <ns1:TriggerWindow>
               <ns1:minutesBefore>15</ns1:minutesBefore>
               <ns1:minutesAfter>15</ns1:minutesAfter>
            </ns1:TriggerWindow>
            <ns1:LightValue>
               <ns1:Index>0</ns1:Index>
               <ns1:On>true</ns1:On>
            </ns1:LightValue>
            <ns1:TriggerType>LIGHT_TRIGGER</ns1:TriggerType>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ALL</ns1:WeekDay>
            <ns1:ActionTime>ABSOLUTETIME</ns1:ActionTime>
            <ns1:Time>23:00:00</ns1:Time>
            <ns1:TriggerWindow>
               <ns1:minutesBefore>30</ns1:minutesBefore>
               <ns1:minutesAfter>30</ns1:minutesAfter>
            </ns1:TriggerWindow>
            <ns1:LightValue>
               <ns1:Index>2</ns1:Index>
               <ns1:On>false</ns1:On>
            </ns1:LightValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ALL</ns1:WeekDay>
            <ns1:ActionTime>ABSOLUTETIME</ns1:ActionTime>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TriggerWindow>
               <ns1:minutesBefore>150</ns1:minutesBefore>
               <ns1:minutesAfter>45</ns1:minutesAfter>
            </ns1:TriggerWindow>
            <ns1:LightValue>
               <ns1:Index>2</ns1:Index>
               <ns1:On>true</ns1:On>
            </ns1:LightValue>
         </ns1:Schedules>

      </ns1:SetScheduleRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetScheduleAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/schedulemanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180926110014351</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetScheduleAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/publiclighting/schedulemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetScheduleAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180926110014351</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetScheduleAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetScheduleResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/schedulemanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetScheduleResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of data written to the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: SetSchedule {
  XSWC2.Sche[CF].sche1.enable: true
  XSWC2.Sche[CF].sche1.tOn: -1
  XSWC2.Sche[CF].sche1.tOnT: -1
  XSWC2.Sche[CF].sche1.tOff: 0
  XSWC2.Sche[CF].sche1.tOffT: 1
  XSWC2.Sche[CF].sche1.srBefWd: 15
  XSWC2.Sche[CF].sche1.srAftWd: 15

  XSWC2.Sche[CF].sche2.enable: true
  XSWC2.Sche[CF].sche2.tOn: 0
  XSWC2.Sche[CF].sche2.tOnT: 1
  XSWC2.Sche[CF].sche2.tOff: -1
  XSWC2.Sche[CF].sche2.tOffT: -1
  XSWC2.Sche[CF].sche2.srBefWd: 15
  XSWC2.Sche[CF].sche2.srAftWd: 15

  XSWC2.Sche[CF].sche3.enable: true
  XSWC2.Sche[CF].sche3.tOn: -1
  XSWC2.Sche[CF].sche3.tOnT: -1
  XSWC2.Sche[CF].sche3.tOff: 2300
  XSWC2.Sche[CF].sche3.tOffT: 0
  XSWC2.Sche[CF].sche3.srBefWd: 30
  XSWC2.Sche[CF].sche3.srAftWd: 30

  XSWC2.Sche[CF].sche4.enable: true
  XSWC2.Sche[CF].sche4.tOn: 700
  XSWC2.Sche[CF].sche4.tOnT: 0
  XSWC2.Sche[CF].sche4.tOff: -1
  XSWC2.Sche[CF].sche4.tOffT: -1
  XSWC2.Sche[CF].sche4.srBefWd: 150
  XSWC2.Sche[CF].sche4.srAftWd: 45

  XSWC3.Sche[CF].sche1.enable: true
  XSWC3.Sche[CF].sche1.tOn: -1
  XSWC3.Sche[CF].sche1.tOnT: -1
  XSWC3.Sche[CF].sche1.tOff: 0
  XSWC3.Sche[CF].sche1.tOffT: 1
  XSWC3.Sche[CF].sche1.srBefWd: 15
  XSWC3.Sche[CF].sche1.srAftWd: 15

  XSWC3.Sche[CF].sche2.tOn: 0
  XSWC3.Sche[CF].sche2.tOnT: 1
  XSWC3.Sche[CF].sche2.tOff: -1
  XSWC3.Sche[CF].sche2.tOffT: -1
  XSWC3.Sche[CF].sche2.srBefWd: 15
  XSWC3.Sche[CF].sche2.srAftWd: 15
  XSWC3.Sche[CF].sche2.enable: true

  XSWC3.Sche[CF].sche3.enable: false
  XSWC3.Sche[CF].sche4.enable: false
}
```

IEC61850 protocol adapter logging:
```
2018-09-26 11:12:39.470] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: SET_LIGHT_SCHEDULE with message priority: 4
2018-09-26 11:12:39.471] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: SET_LIGHT_SCHEDULE for domain: PUBLIC_LIGHTING 1.0
2018-09-26 11:12:39.471] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-09-26 11:12:39.471] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-09-26 11:12:39.475] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-09-26 11:12:39.480] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-09-26 11:12:39.531] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-26 11:12:39.531] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-09-26 11:12:39.707] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018
-09-26T11:12:39.471Z, end time: 2018-09-26T11:12:39.707Z, total time in milliseconds: 236
2018-09-26 11:12:39.710] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.Sche
2018-09-26 11:12:39.730] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 1 for relay 2 is enabled: true
2018-09-26 11:12:39.730] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 1 of 64 for relay 2 before setting new LIGHT schedule
2018-09-26 11:12:39.756] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 2 for relay 2 is enabled: true
2018-09-26 11:12:39.756] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 2 of 64 for relay 2 before setting new LIGHT schedule
2018-09-26 11:12:39.782] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 3 for relay 2 is enabled: true
2018-09-26 11:12:39.782] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 3 of 64 for relay 2 before setting new LIGHT schedule
2018-09-26 11:12:39.806] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 4 for relay 2 is enabled: true
2018-09-26 11:12:39.806] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 4 of 64 for relay 2 before setting new LIGHT schedule
2018-09-26 11:12:39.832] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 5 for relay 2 is enabled: false
...
2018-09-26 11:12:39.842] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 64 for relay 2 is enabled: false
2018-09-26 11:12:39.842] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.Sche
2018-09-26 11:12:40.046] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 1 for relay 3 is enabled: true
2018-09-26 11:12:40.046] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 1 of 64 for relay 3 before setting new LIGHT schedule
2018-09-26 11:12:40.083] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 2 for relay 3 is enabled: true
2018-09-26 11:12:40.084] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 2 of 64 for relay 3 before setting new LIGHT schedule
2018-09-26 11:12:40.488] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 3 for relay 3 is enabled: false
...
2018-09-26 11:12:40.499] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 64 for relay 3 is enabled: false
2018-09-26 11:12:40.499] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.CfSt
2018-09-26 11:12:40.589] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850Commands@enableOperationOfRelay:56 - masterControl.enbOper is true, switching of relay 2 is enabled
2018-09-26 11:12:40.589] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.Sche
2018-09-26 11:12:42.881] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write light schedule entry 1 for relay 2
2018-09-26 11:12:43.256] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write light schedule entry 2 for relay 2
2018-09-26 11:12:44.734] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write light schedule entry 3 for relay 2
2018-09-26 11:12:44.886] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write light schedule entry 4 for relay 2
2018-09-26 11:12:44.974] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.CfSt
2018-09-26 11:12:44.989] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850Commands@enableOperationOfRelay:56 - masterControl.enbOper is true, switching of relay 3 is enabled
2018-09-26 11:12:44.989] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.Sche
2018-09-26 11:12:45.008] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write light schedule entry 1 for relay 3
2018-09-26 11:12:45.034] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write light schedule entry 2 for relay 3
2018-09-26 11:12:45.059] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-26 11:12:45.059] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
2018-09-26 11:12:45.060] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: SET_LIGHT_SCHEDULE with message priority: 4
2018-09-26 11:12:45.060] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: SET_LIGHT_SCHEDULE, Start time: 2018-09-26T11:12:39.471Z, end time: 2018-09-26T11:12:45.060Z, total time in milliseconds: 5589
```



#### Example 2: Tariff Schedule

Description for this schedule:

This schedule defines the tariff switching moments. For most weekdays of the year the tariff is high from 7 'o clock in the morning until 11 'o clock in the evening. During the night and weekend, the tariff is low. However for certain days, like Christmas Day, the tariff has to be low as well (Christmas Day may be a weekday).

SOAP Request Message for Platform web service:

``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/tariffswitching/schedulemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetScheduleRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
         <ns1:Schedules>
            <ns1:WeekDay>WEEKDAY</ns1:WeekDay>
            <ns1:StartDay>2018-01-01</ns1:StartDay>
            <ns1:EndDay>2019-02-01</ns1:EndDay>
            <ns1:Time>23:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>WEEKDAY</ns1:WeekDay>
            <ns1:StartDay>2018-01-01</ns1:StartDay>
            <ns1:EndDay>2019-02-01</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>1</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ABSOLUTEDAY</ns1:WeekDay>
            <ns1:StartDay>2018-01-01</ns1:StartDay>
            <ns1:EndDay>2018-01-01</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ABSOLUTEDAY</ns1:WeekDay>
            <ns1:StartDay>2018-04-02</ns1:StartDay>
            <ns1:EndDay>2018-04-02</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ABSOLUTEDAY</ns1:WeekDay>
            <ns1:StartDay>2018-04-27</ns1:StartDay>
            <ns1:EndDay>2018-04-27</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ABSOLUTEDAY</ns1:WeekDay>
            <ns1:StartDay>2018-05-10</ns1:StartDay>
            <ns1:EndDay>2018-05-10</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ABSOLUTEDAY</ns1:WeekDay>
            <ns1:StartDay>2018-05-21</ns1:StartDay>
            <ns1:EndDay>2018-05-21</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ABSOLUTEDAY</ns1:WeekDay>
            <ns1:StartDay>2018-12-25</ns1:StartDay>
            <ns1:EndDay>2018-12-25</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ABSOLUTEDAY</ns1:WeekDay>
            <ns1:StartDay>2018-12-26</ns1:StartDay>
            <ns1:EndDay>2018-12-26</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

         <ns1:Schedules>
            <ns1:WeekDay>ABSOLUTEDAY</ns1:WeekDay>
            <ns1:StartDay>2019-01-01</ns1:StartDay>
            <ns1:EndDay>2019-01-01</ns1:EndDay>
            <ns1:Time>07:00:00</ns1:Time>
            <ns1:TariffValue>
               <ns1:Index>1</ns1:Index>
               <ns1:High>0</ns1:High>
            </ns1:TariffValue>
         </ns1:Schedules>

      </ns1:SetScheduleRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

SOAP Response Message:

``` xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetScheduleAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/tariffswitching/schedulemanagement/2014/10"
           xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180926150922041</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetScheduleAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

SOAP Request message for response:

``` xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/tariffswitching/schedulemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetScheduleAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180926150922041</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetScheduleAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

SOAP Response message:
``` xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetScheduleResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/tariffswitching/schedulemanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetScheduleResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message for data written to device:

``` json
LogicalDevice: SWDeviceGenericIO
messageType: SetSchedule {
  XSWC1.Sche[CF].sche1.enable: true
  XSWC1.Sche[CF].sche1.day: -1
  XSWC1.Sche[CF].sche1.tOn: 2300
  XSWC1.Sche[CF].sche1.tOnT: 0
  XSWC1.Sche[CF].sche1.tOff: -1
  XSWC1.Sche[CF].sche1.tOffT: -1
  XSWC1.Sche[CF].sche2.enable: true
  XSWC1.Sche[CF].sche2.day: -1
  XSWC1.Sche[CF].sche2.tOn: -1
  XSWC1.Sche[CF].sche2.tOnT: -1
  XSWC1.Sche[CF].sche2.tOff: 700
  XSWC1.Sche[CF].sche2.tOffT: 0
  XSWC1.Sche[CF].sche3.enable: true
  XSWC1.Sche[CF].sche3.day: 20180101
  XSWC1.Sche[CF].sche4.enable: true
  XSWC1.Sche[CF].sche4.day: 20180402
  XSWC1.Sche[CF].sche5.enable: true
  XSWC1.Sche[CF].sche5.day: 20180427
  XSWC1.Sche[CF].sche6.enable: true
  XSWC1.Sche[CF].sche6.day: 20180510
  XSWC1.Sche[CF].sche7.enable: true
  XSWC1.Sche[CF].sche7.day: 20180521
  XSWC1.Sche[CF].sche8.enable: true
  XSWC1.Sche[CF].sche8.day: 20181225
  XSWC1.Sche[CF].sche9.enable: true
  XSWC1.Sche[CF].sche9.day: 20181226
  XSWC1.Sche[CF].sche10.enable: true
  XSWC1.Sche[CF].sche10.day: 20190101
}
```

IEC61850 protocol adapter logging:
```
2018-09-26 15:09:22.380] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceRequestMessageListener@onMessage:61 - Received message of type: SET_TARIFF_SCHEDULE with message priority: 4
2018-09-26 15:09:22.381] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@printDomainInfo:53 - Calling DeviceService function: SET_TARIFF_SCHEDULE for domain: TARIFF_SWITCHING 1.0
2018-09-26 15:09:22.381] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.BaseMessageProcessor@getJmsXdeliveryCount:64 - jmsXdeliveryCount: 1
2018-09-26 15:09:22.381] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:115 - Trying to connect to deviceIdentification: KAI-0000000053 at IP address 84.30.69.148 using response time-out: 10000
2018-09-26 15:09:22.386] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.r.Iec61850ClientSSLDEventListener@buildExternalByInternalIndexMap:80 - Retrieved internal to external index map for device KAI-0000000053: {0=0, 1=1, 2=2, 3=3}
2018-09-26 15:09:22.393] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:97 - Attempting to connect to server: 84.30.69.148 on port: 102, max redelivery count: 3 and max retry count: 3
2018-09-26 15:09:22.439] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.Iec61850Client@connect:113 - Connected to device: KAI-0000000053
2018-09-26 15:09:22.439] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@readServerModelFromConfiguredIcdFile:316 - Reading ServerModel from SCL / ICD file: /etc/osp/kaifa-server-model/SWDevice-010805.icd
2018-09-26 15:09:22.496] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@connect:159 - Connected to device: KAI-0000000053, fetched server model. Start time: 2018-09-26T15:09:22.381Z, end time: 2018-09-26T15:09:22.496Z, total time in milliseconds: 115
2018-09-26 15:09:22.506] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.Sche
2018-09-26 15:09:22.527] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 1 for relay 1 is enabled: true
2018-09-26 15:09:22.527] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 1 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:22.552] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 2 for relay 1 is enabled: true
2018-09-26 15:09:22.552] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 2 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:22.575] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 3 for relay 1 is enabled: true
2018-09-26 15:09:22.575] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 3 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:22.600] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 4 for relay 1 is enabled: true
2018-09-26 15:09:22.600] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 4 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:22.623] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 5 for relay 1 is enabled: true
2018-09-26 15:09:22.624] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 5 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:22.649] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 6 for relay 1 is enabled: true
2018-09-26 15:09:22.649] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 6 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:22.746] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 7 for relay 1 is enabled: true
2018-09-26 15:09:22.747] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 7 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:22.896] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 8 for relay 1 is enabled: true
2018-09-26 15:09:22.896] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 8 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:22.929] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 9 for relay 1 is enabled: true
2018-09-26 15:09:22.929] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 9 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:23.137] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 10 for relay 1 is enabled: true
2018-09-26 15:09:23.137] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:451 - Disabling schedule entry 10 of 64 for relay 1 before setting new TARIFF schedule
2018-09-26 15:09:23.392] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 11 for relay 1 is enabled: false
2018-09-26 15:09:23.392] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 12 for relay 1 is enabled: false
...
2018-09-26 15:09:23.395] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 63 for relay 1 is enabled: false
2018-09-26 15:09:23.401] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@disableScheduleEntries:449 - Checking if schedule entry 64 for relay 1 is enabled: false
2018-09-26 15:09:23.402] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.CfSt
2018-09-26 15:09:23.514] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850Commands@enableOperationOfRelay:56 - masterControl.enbOper is true, switching of relay 1 is enabled
2018-09-26 15:09:23.515] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.Sche
2018-09-26 15:09:26.367] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 1 for relay 1
2018-09-26 15:09:26.528] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 2 for relay 1
2018-09-26 15:09:26.937] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 3 for relay 1
2018-09-26 15:09:27.833] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 4 for relay 1
2018-09-26 15:09:27.882] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 5 for relay 1
2018-09-26 15:09:27.932] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 6 for relay 1
2018-09-26 15:09:27.982] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 7 for relay 1
2018-09-26 15:09:28.235] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 8 for relay 1
2018-09-26 15:09:28.815] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 9 for relay 1
2018-09-26 15:09:31.566] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetScheduleCommand@apply:113 - Write tariff schedule entry 10 for relay 1
2018-09-26 15:09:31.867] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-26 15:09:31.868] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
2018-09-26 15:09:31.868] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.m.DeviceResponseMessageSender@sendMessage:111 - Sending protocol response message for device: KAI-0000000053 of message type: SET_TARIFF_SCHEDULE with message priority: 4
2018-09-26 15:09:31.868] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.Iec61850DeviceConnectionService@logDuration:355 - Device: KAI-0000000053, messageType: SET_TARIFF_SCHEDULE, Start time: 2018-09-26T15:09:22.381Z, end time: 2018-09-26T15:09:31.868Z, total time in milliseconds: 9487
```
