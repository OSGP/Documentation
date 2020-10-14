## GetConfiguration messages

### Description

Request which queries a device for its current configuration.

Response which returns the result of the request and, if 'result = OK', contains the configuration of the device.

### IEC61850 Fields

|**ATTRIBUTE**|**FC**|**SUB ATTRIBUTE**|**DATATYPE**|**DESCRIPTION**|
|---|---|---|---|---|
|XSWC1.SwType|ST|stVal|INT8|Switch type for relay 1, tariff = 0, light = 1.|
|XSWC2.SwType|ST|stVal|INT8|Switch type for relay 2, tariff = 0, light = 1.|
|XSWC3.SwType|ST|stVal|INT8|Switch type for relay 3, tariff = 0, light = 1.|
|CSLC.SWCf|CF|LT|VisString64|Device light type, always set to RELAY.|
|CSLC.SWCf|CF|adSetOft|INT16|Offset in minutes with respect to astronomical sunset.|
|CSLC.SWCf|CF|adRiseOft|INT16|Offset in minutes with respect to astronomical sunrise.|
|CSLC.Reg|CF|svrAddr|VisString64|OSGP server address for device registration.|
|CSLC.Reg|CF|svrPort|INT32|OSGP server port for device registration.|
|CSLC.Clock|CF|dstBegT|VisString255|Daylight savings time begin time.|
|CSLC.Clock|CF|dstEndT|VisString255|Daylight savings time end time.|
|CSLC.Clock|CF|enbDst|BOOLEAN|Flag indicating whether daylight savings time is enabled.|
|CSLC.Clock|CF|enbNtpC|BOOLEAN|Flag inidicating whether NTP client is enabled.|
|CSLC.Clock|CF|ntpSvrA|VisString255|NTP server address.|
|CSLC.Clock|CF|syncPer|INT16U|Time sync period.|
|CSLC.IPCf|CF|enbDHCP|BOOLEAN|Flag indicating whether DHCP client is enabled.|
|CSLC.IPCf|CF|ipAddr|VisString32|Fixed IP address when DHCP is disabled.|
|CSLC.IPCf|CF|netmask|VisString32|Netmask when DHCP is disabled.|
|CSLC.IPCf|CF|gateway|VisString32|Gateway when DHCP is disabled.|

### Example

Soap requests and responses sent to and from platform:
``` xml
<soapenv:Envelope
      xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
      xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
      xmlns:ns1="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:GetConfigurationRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
      </ns1:GetConfigurationRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetConfigurationAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925073838432</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetConfigurationAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope
    xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10"
    xmlns:ns1="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>SoapUI</ns:ApplicationName>
      <ns:UserName>Sander</ns:UserName>
      <ns:OrganisationIdentification>LianderNetManagement</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:GetConfigurationAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925073838432</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:GetConfigurationAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:GetConfigurationResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
         <ns2:Configuration>
            <ns2:LightType>RELAY</ns2:LightType>
            <ns2:RelayConfiguration>
               <ns2:RelayMap>
                  <ns2:Index>1</ns2:Index>
                  <ns2:Address>1</ns2:Address>
                  <ns2:RelayType>TARIFF</ns2:RelayType>
                  <ns2:alias/>
               </ns2:RelayMap>
               <ns2:RelayMap>
                  <ns2:Index>2</ns2:Index>
                  <ns2:Address>2</ns2:Address>
                  <ns2:RelayType>LIGHT</ns2:RelayType>
                  <ns2:alias/>
               </ns2:RelayMap>
               <ns2:RelayMap>
                  <ns2:Index>3</ns2:Index>
                  <ns2:Address>3</ns2:Address>
                  <ns2:RelayType>LIGHT</ns2:RelayType>
                  <ns2:alias/>
               </ns2:RelayMap>
            </ns2:RelayConfiguration>
            <ns2:PreferredLinkType>ETHERNET</ns2:PreferredLinkType>
            <ns2:TimeSyncFrequency>1440</ns2:TimeSyncFrequency>
            <ns2:DeviceFixedIp>
               <ns2:IpAddress>192.168.0.110</ns2:IpAddress>
               <ns2:NetMask>255.255.0.0</ns2:NetMask>
               <ns2:GateWay>192.168.0.1</ns2:GateWay>
            </ns2:DeviceFixedIp>
            <ns2:DhcpEnabled>true</ns2:DhcpEnabled>
            <ns2:OsgpIpAddress>168.63.97.65</ns2:OsgpIpAddress>
            <ns2:OsgpPortNumber>50003</ns2:OsgpPortNumber>
            <ns2:NtpHost>0.nl.pool.ntp.org</ns2:NtpHost>
            <ns2:NtpEnabled>true</ns2:NtpEnabled>
            <ns2:NtpSyncInterval>1440</ns2:NtpSyncInterval>
            <ns2:AutomaticSummerTimingEnabled>true</ns2:AutomaticSummerTimingEnabled>
            <ns2:AstroGateSunRiseOffset>0</ns2:AstroGateSunRiseOffset>
            <ns2:AstroGateSunSetOffset>0</ns2:AstroGateSunSetOffset>
            <ns2:SummerTimeDetails>2019-03-30T23:00:00.000Z</ns2:SummerTimeDetails>
            <ns2:WinterTimeDetails>2018-10-27T22:00:00.000Z</ns2:WinterTimeDetails>
         </ns2:Configuration>
      </ns2:GetConfigurationResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Platform message of the data read from the device:
``` json
LogicalDevice: SWDeviceGenericIO
messageType: GetConfiguration {
  XSWC1.SwType[ST].stVal: 0
  XSWC2.SwType[ST].stVal: 1
  XSWC3.SwType[ST].stVal: 1
  CSLC.SWCf[CF].LT: RELAY
  CSLC.SWCf[CF].adSetOft: 0
  CSLC.SWCf[CF].adRiseOft: 0
  CSLC.Reg[CF].svrPort: 50003
  CSLC.Reg[CF].svrAddr: 168.63.97.65
  CSLC.Clock[CF].dstBegT: M3.5.0
  CSLC.Clock[CF].dstEndT: M10.5.0
  CSLC.Clock[CF].enbDst: true
  CSLC.Clock[CF].enbNtpC: true
  CSLC.Clock[CF].ntpSvrA: 0.nl.pool.ntp.org
  CSLC.Clock[CF].syncPer: 1440
  CSLC.IPCf[CF].enbDHCP: true
  CSLC.IPCf[CF].ipAddr: 192.168.0.110
  CSLC.IPCf[CF].netmask: 255.255.0.0
  CSLC.IPCf[CF].gateway: 192.168.0.1
}
```

IEC61850 protocol adapter logging:
```
2018-09-25 07:38:39.006] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.SwType
2018-09-25 07:38:39.058] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.SwType
2018-09-25 07:38:39.074] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.SwType
2018-09-25 07:38:39.091] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetConfigurationCommand@apply:90 - Reading the software configuration values
2018-09-25 07:38:39.091] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.SWCf
2018-09-25 07:38:39.108] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, LT has value RELAY
2018-09-25 07:38:39.110] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetConfigurationCommand@apply:126 - Reading the registration configuration values
2018-09-25 07:38:39.110] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Reg
2018-09-25 07:38:39.129] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, svrAddr has value 168.63.97.65
2018-09-25 07:38:39.129] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetConfigurationCommand@apply:144 - Reading the IP configuration values
2018-09-25 07:38:39.130] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.IPCf
2018-09-25 07:38:39.146] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, ipAddr has value 192.168.0.110
2018-09-25 07:38:39.146] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, netmask has value 255.255.0.0
2018-09-25 07:38:39.146] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, gateway has value 192.168.0.1
2018-09-25 07:38:39.147] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850GetConfigurationCommand@apply:175 - Reading the clock configuration values
2018-09-25 07:38:39.147] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Clock
2018-09-25 07:38:39.163] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, dstBegT has value M3.5.0
2018-09-25 07:38:39.163] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, dstEndT has value M10.5.0
2018-09-25 07:38:39.163] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@getString:88 - Device: KAI-0000000053, ntpSvrA has value 0.nl.pool.ntp.org
```
