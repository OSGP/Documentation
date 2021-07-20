# SetConfiguration

## Description

Request which commands a device to update its configuration.

Response which returns the result of the request.

## IEC61850 Fields

| **ATTRIBUTE** | **FC** | **SUB ATTRIBUTE** | **DATATYPE** | **DESCRIPTION** |
| :--- | :--- | :--- | :--- | :--- |
| XSWC1.SwType | CO | Oper.ctlVal | INT8 | Switch type for relay 1, tariff = 0, light = 1. |
| XSWC2.SwType | CO | Oper.ctlVal | INT8 | Switch type for relay 2, tariff = 0, light = 1. |
| XSWC3.SwType | CO | Oper.ctlVal | INT8 | Switch type for relay 3, tariff = 0, light = 1. |
| XSWC4.SwType | CO | Oper.ctlVal | INT8 | Switch type for relay 4, tariff = 0, light = 1. |
| CSLC.SWCf | CF | LT | VisString64 | Light type, always set to "RELAY". |
| CSLC.SWCf | CF | adSetOft | INT16 | Offset in minutes with respect to astronomical sunset. |
| CSLC.SWCf | CF | adRiseOft | INT16 | Offset in minutes with respect to astronomical sunrise. |
| CSLC.Reg | CF | svrAddr | VisString64 | OSGP server address for device registration. |
| CSLC.Reg | CF | svrPort | INT32 | OSGP server port for device registration. |
| CSLC.Clock | CF | dstBegT | VisString255 | Daylight savings time begin time. |
| CSLC.Clock | CF | dstEndT | VisString255 | Daylight savings time end time. |
| CSLC.Clock | CF | enbDst | BOOLEAN | Flag indicating whether daylight savings time is enabled. |
| CSLC.Clock | CF | enbNtpC | BOOLEAN | Flag indicating whether NTP client is enabled. |
| CSLC.Clock | CF | ntpSvrA | VisString255 | NTP server address. |
| CSLC.Clock | CF | syncPer | INT16U | Time sync period in minutes. |
| CSLC.IPCf | CF | enbDHCP | BOOLEAN | Flag indicating whether DHCP client is enabled. |
| CSLC.IPCf | CF | ipAddr | VisString32 | Fixed IP address when DHCP is disabled. |
| CSLC.IPCf | CF | netmask | VisString32 | Netmask when DHCP is disabled. |
| CSLC.IPCf | CF | gateway | VisString32 | Gateway when DHCP is disabled. |

## Example

Soap requests and responses sent to and from platform:

```markup
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
      <ns1:SetConfigurationRequest>
         <ns1:DeviceIdentification>KAI-0000000053</ns1:DeviceIdentification>
         <ns1:Configuration>
            <ns1:LightType>RELAY</ns1:LightType>
            <ns1:RelayConfiguration>
               <ns1:RelayMap>
                  <ns1:Index>1</ns1:Index>
                  <ns1:Address>1</ns1:Address>
                  <ns1:RelayType>TARIFF</ns1:RelayType>
               </ns1:RelayMap>
               <ns1:RelayMap>
                  <ns1:Index>2</ns1:Index>
                  <ns1:Address>2</ns1:Address>
                  <ns1:RelayType>LIGHT</ns1:RelayType>
               </ns1:RelayMap>
               <ns1:RelayMap>
                  <ns1:Index>3</ns1:Index>
                  <ns1:Address>3</ns1:Address>
                  <ns1:RelayType>LIGHT</ns1:RelayType>
               </ns1:RelayMap>
            </ns1:RelayConfiguration>
            <ns1:PreferredLinkType>ETHERNET</ns1:PreferredLinkType>
            <ns1:TimeSyncFrequency>1440</ns1:TimeSyncFrequency>
            <ns1:DeviceFixedIp>
               <ns1:IpAddress>192.168.0.110</ns1:IpAddress>
               <ns1:NetMask>255.255.0.0</ns1:NetMask>
               <ns1:GateWay>192.168.0.1</ns1:GateWay>
            </ns1:DeviceFixedIp>
            <ns1:DhcpEnabled>true</ns1:DhcpEnabled>
            <ns1:OsgpIpAddress>168.63.97.65</ns1:OsgpIpAddress>
            <ns1:OsgpPortNumber>50003</ns1:OsgpPortNumber>
            <ns1:NtpHost>0.nl.pool.ntp.org</ns1:NtpHost>
            <ns1:NtpEnabled>true</ns1:NtpEnabled>
            <ns1:NtpSyncInterval>1440</ns1:NtpSyncInterval>
            <ns1:AutomaticSummerTimingEnabled>true</ns1:AutomaticSummerTimingEnabled>
            <ns1:AstroGateSunRiseOffset>0</ns1:AstroGateSunRiseOffset>
            <ns1:AstroGateSunSetOffset>0</ns1:AstroGateSunSetOffset>
            <ns1:SummerTimeDetails>2019-03-30T23:00:00.000Z</ns1:SummerTimeDetails>
            <ns1:WinterTimeDetails>2018-10-27T22:00:00.000Z</ns1:WinterTimeDetails>
         </ns1:Configuration>
      </ns1:SetConfigurationRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetConfigurationAsyncResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925135306803</ns3:CorrelationUid>
            <ns3:DeviceId>KAI-0000000053</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetConfigurationAsyncResponse>
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
      <ns1:SetConfigurationAsyncRequest>
         <ns1:AsyncRequest>
            <ns:CorrelationUid>LianderNetManagement|||KAI-0000000053|||20180925135306803</ns:CorrelationUid>
            <ns:DeviceId>KAI-0000000053</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetConfigurationAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetConfigurationResponse
          xmlns:ns2="http://www.opensmartgridplatform.org/schemas/configurationmanagement/2014/10"
          xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:SetConfigurationResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

IEC61850 platform message of the data sent to the device:

```javascript
LogicalDevice: SWDeviceGenericIO
messageType: SetConfiguration {
  CSLC.Reg[CF].svrPort: 50003
  CSLC.SWCf[CF].adSetOft: 0
  CSLC.Clock[CF].ntpSvrA: 0.nl.pool.ntp.org
  CSLC.SWCf[CF].LT: RELAY
  CSLC.Clock[CF].dstEndT: M10.5.6/22
  CSLC.IPCf[CF].enbDHCP: true
  XSWC2.SwType[CO].Oper.ctlVal: 1
  XSWC3.SwType[CO].Oper.ctlVal: 1
  CSLC.Clock[CF].enbDst: true
  XSWC1.SwType[CO].Oper.ctlVal: 0
  CSLC.Clock[CF].enbNtpC: true
  CSLC.IPCf[CF].netmask: 255.255.0.0
  CSLC.IPCf[CF].gateway: 192.168.0.1
  CSLC.IPCf[CF].ipAddr: 192.168.0.110
  CSLC.Reg[CF].svrAddr: 168.63.97.65
  CSLC.SWCf[CF].adRiseOft: 0
  CSLC.Clock[CF].syncPer: 1440
  CSLC.Clock[CF].dstBegT: M3.5.6/23
}
```

IEC61850 protocol adapter logging:

```text
2018-09-25 13:53:07.723] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC1.SwType
2018-09-25 13:53:07.756] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:70 - Updating Switch for internal index 1 to 0 (TARIFF)
2018-09-25 13:53:07.772] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC2.SwType
2018-09-25 13:53:07.801] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:70 - Updating Switch for internal index 2 to 1 (LIGHT)
2018-09-25 13:53:07.817] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/XSWC3.SwType
2018-09-25 13:53:08.002] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:70 - Updating Switch for internal index 3 to 1 (LIGHT)
2018-09-25 13:53:08.016] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Reg
2018-09-25 13:53:08.031] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:92 - Updating OspgIpAddress to 168.63.97.65
2018-09-25 13:53:08.031] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing 168.63.97.65 to svrAddr
2018-09-25 13:53:08.400] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:100 - Updating OsgpPortNumber to 50003
2018-09-25 13:53:08.444] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.SWCf
2018-09-25 13:53:08.761] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:120 - Updating AstroGateSunRiseOffset to 0
2018-09-25 13:53:08.916] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:130 - Updating AstroGateSunSetOffset to 0
2018-09-25 13:53:09.208] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:140 - Updating LightType to RELAY
2018-09-25 13:53:09.209] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing RELAY to LT
2018-09-25 13:53:10.728] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.Clock
2018-09-25 13:53:10.743] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:165 - Updating TimeSyncFrequency to 1440
2018-09-25 13:53:10.762] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:175 - Updating AutomaticSummerTimingEnabled to true
2018-09-25 13:53:10.781] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:202 - Updating DstBeginTime to M3.5.6/23 based on SummerTimeDetails 2019-03-30T23:00:00.000Z
2018-09-25 13:53:10.781] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing M3.5.6/23 to dstBegT
2018-09-25 13:53:10.800] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:213 - Updating DstEndTime to M10.5.6/22 based on WinterTimeDetails 2018-10-27T22:00:00.000Z
2018-09-25 13:53:10.800] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing M10.5.6/22 to dstEndT
2018-09-25 13:53:10.818] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:221 - Updating ntpEnabled to true
2018-09-25 13:53:10.836] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:230 - Updating ntpHost to 0.nl.pool.ntp.org
2018-09-25 13:53:10.836] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing 0.nl.pool.ntp.org to ntpSvrA
2018-09-25 13:53:10.855] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:239 - Updating ntpSyncInterval to 1440
2018-09-25 13:53:10.874] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.h.DeviceConnection@createObjectReference:94 - Device: KAI-0000000053, ObjectReference: SWDeviceGenericIO/CSLC.IPCf
2018-09-25 13:53:10.891] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:259 - Updating DhcpEnabled to true
2018-09-25 13:53:14.062] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:271 - Updating deviceFixedIpAddress to 192.168.0.110
2018-09-25 13:53:14.062] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing 192.168.0.110 to ipAddr
2018-09-25 13:53:14.082] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:277 - Updating deviceFixedIpNetmask to 255.255.0.0
2018-09-25 13:53:14.082] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing 255.255.0.0 to netmask
2018-09-25 13:53:14.101] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.s.c.Iec61850SetConfigurationCommand@apply:283 - Updating deviceFixIpGateway to 192.168.0.1
2018-09-25 13:53:14.101] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.i.n.helper.NodeContainer@writeString:99 - Device: KAI-0000000053, writing 192.168.0.1 to gateway
2018-09-25 13:53:14.119] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceMessageLoggingService@logMessage:52 - Sending iec61850LogItemRequestMessage for device: KAI-0000000053
2018-09-25 13:53:14.120] [osgp-tst-03] [iec61850RequestsMessageListenerContainer-11] INFO o.o.a.p.i.s.DeviceResponseService@handleDeviceMessageStatus:42 - OK device message status received: OK
```

