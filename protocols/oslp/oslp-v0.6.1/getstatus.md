<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# GetStatus

## Description

Request that requires the device to send the status of all relays, current network link and preferred network link, the type of configuration \(PSLD vs SSLD\), and the event notification mask which has been set. Further, many optional values can be set by the device, like serial number, MAC address, memory sizes, current firmware version, current IP address, etc.

Response which confirms the GetStatusRequest has been executed and returns the current status for all of the relays and other information or rejects the GetStatusRequest.

## Message definitions

```javascript
message GetStatusRequest {
    optional bool present = 1 [default = true];
}

message GetStatusResponse {
    required Status status = 1;
    repeated LightValue value = 2; // [(nanopb).max_count = 6];
    required LinkType preferredLinktype = 3;
    required LinkType actualLinktype = 4;
    required LightType lightType = 5;
    required uint32 eventNotificationMask = 6;         // Bitmask for max 32 events, using NotificationBit for bit positions.
    optional uint32 numberOfOutputs = 7;               // Hardware - The number of outputs of this device.
    optional uint32 dcOutputVoltageMaximum = 8;        // Hardware - DC output voltage MAXimum (in mV).
    optional uint32 dcOutputVoltageCurrent = 9;        // Hardware - DC output current voltage (in mV).
    optional uint32 maximumOutputPowerOnDcOutput = 10; // Hardware - Maximum output power on DC output (mW). 
    optional bytes serialNumber = 11; // [(nanopb).max_size = 18]; // Hardware - Serial number of this device.
    optional bytes macAddress = 12; // [(nanopb).max_size = 6]; // Hardware - MAC-address of this device.
    optional string hardwareId = 13; // [(nanopb).min_size = 10, (nanopd).max_size = 25] ; // Hardware - The hardware ID of this device.
    optional uint32 internalFlashMemSize = 14;         // Hardware - The internal flash memory size.
    optional uint32 externalFlashMemSize = 15;         // Hardware - The external flash memory size.
    optional uint32 lastInternalTestResultCode = 16;   // Hardware - The last internal test result code.
    optional uint32 startupCounter = 17;               // Hardware - The startup counter.
    optional string bootLoaderVersion = 18;            // Software - The boot loader version.
    optional string firmwareVersion = 19;              // Software - The firmware version.
    optional bytes currentConfigurationBackUsed = 20; // [(nanopb).max_size = 6]; // Software - The current configuration bank in use.
    optional string name = 21;                         // Device - The name of this device.
    optional string currentTime = 22;                  // Device - Not UTC, the time used in timing operations (adjusted "offset" + summer timing). YYYYMMDDhhmmss format.
    optional string currentIp = 23;                    // Device - The current IP address of this device.
}
```

## Datatypes

```javascript
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}

message LightValue {
    optional bytes index = 1; // [(nanopb).max_size = 1]; // index number of connected light (DALI), none means all connected ligts.
    required bool on = 2;
    optional bytes dimValue = 3; // [(nanopb).max_size = 1]; // 1 - 100 %
}

enum LinkType {
    LINK_NOT_SET = 0;
    GPRS = 1;
    CDMA = 2;
    ETHERNET = 3;
}

enum LightType {
    LT_NOT_SET = 0;
    RELAY = 1;
    ONE_TO_TEN_VOLT = 2;
    ONE_TO_TEN_VOLT_REVERSE = 3;
    DALI = 4;
}
```

## Example

Soap requests and responses sent to and from platform:

```markup
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.opensmartgridplatform.org/schemas/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.opensmartgridplatform.org/schemas/common">SoapUI</ApplicationName>
      <UserName xmlns="http://www.opensmartgridplatform.org/schemas/common">Kevin</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetStatusRequest xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:DeviceIdentification>device-01</ns2:DeviceIdentification>
      </ns2:GetStatusRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:GetStatusAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106133844686</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:GetStatusAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header>
      <OrganisationIdentification xmlns="http://www.opensmartgridplatform.org/schemas/common">LianderNetManagement</OrganisationIdentification>
      <ApplicationName xmlns="http://www.opensmartgridplatform.org/schemas/common">SoapUI</ApplicationName>
      <UserName xmlns="http://www.opensmartgridplatform.org/schemas/common">Kevin</UserName>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns2:GetStatusAsyncRequest xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncRequest>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160106133844686</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncRequest>
      </ns2:GetStatusAsyncRequest>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns3:GetStatusResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/deviceinstallation/2014/10">
         <ns3:Result>OK</ns3:Result>
         <ns3:DeviceStatus>
            <ns3:LightValues>
               <ns3:Index>1</ns3:Index>
               <ns3:On>false</ns3:On>
            </ns3:LightValues>
            <ns3:LightValues>
               <ns3:Index>2</ns3:Index>
               <ns3:On>false</ns3:On>
            </ns3:LightValues>
            <ns3:TariffValues>
               <ns3:Index>3</ns3:Index>
               <ns3:High>true</ns3:High>
            </ns3:TariffValues>
            <ns3:PreferredLinkType>ETHERNET</ns3:PreferredLinkType>
            <ns3:ActualLinkType>ETHERNET</ns3:ActualLinkType>
            <ns3:LightType>RELAY</ns3:LightType>
            <ns3:EventNotifications>DIAG_EVENTS</ns3:EventNotifications>
            <ns3:EventNotifications>HARDWARE_FAILURE</ns3:EventNotifications>
            <ns3:EventNotifications>LIGHT_EVENTS</ns3:EventNotifications>
            <ns3:EventNotifications>TARIFF_EVENTS</ns3:EventNotifications>
            <ns3:EventNotifications>MONITOR_EVENTS</ns3:EventNotifications>
            <ns3:EventNotifications>FIRMWARE_EVENTS</ns3:EventNotifications>
            <ns3:EventNotifications>COMM_EVENTS</ns3:EventNotifications>
            <ns3:EventNotifications>SECURITY_EVENTS</ns3:EventNotifications>
            <ns3:NumberOfOutputs>4</ns3:NumberOfOutputs>
            <ns3:DcOutputVoltageMaximum>24000</ns3:DcOutputVoltageMaximum>
            <ns3:DcOutputVoltageCurrent>0</ns3:DcOutputVoltageCurrent>
            <ns3:MaximumOutputPowerOnDcOutput>15000</ns3:MaximumOutputPowerOnDcOutput>
            <ns3:MacAddress>D8-80-39-46-17-4E</ns3:MacAddress>
            <ns3:HardwareId>SB10</ns3:HardwareId>
            <ns3:InternalFlashMemSize>1048576</ns3:InternalFlashMemSize>
            <ns3:ExternalFlashMemSize>8388608</ns3:ExternalFlashMemSize>
            <ns3:LastInternalTestResultCode>0</ns3:LastInternalTestResultCode>
            <ns3:StartupCounter>2</ns3:StartupCounter>
            <ns3:BootLoaderVersion>v1.0</ns3:BootLoaderVersion>
            <ns3:FirmwareVersion>W0311g</ns3:FirmwareVersion>
            <ns3:CurrentConfigurationBackUsed>0</ns3:CurrentConfigurationBackUsed>
            <ns3:Name>device-01</ns3:Name>
            <ns3:CurrentTime>20160313141247</ns3:CurrentTime>
            <ns3:CurrentIp>192.168.178.16</ns3:CurrentIp>
         </ns3:DeviceStatus>
      </ns3:GetStatusResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP GetStatusRequest sent to 'device-01':

```javascript
getStatusRequest {
}
```

OSLP GetStatusResponse sent to platform:

```javascript
getStatusResponse {
  status: OK
  value {
    index: "\001"
    on: false
  }
  value {
    index: "\002"
    on: false
  }
  value {
    index: "\003"
    on: false
  }
  value {
    index: "\004"
    on: false
  }
  preferredLinktype: ETHERNET
  actualLinktype: ETHERNET
  lightType: RELAY
  eventNotificationMask: 255
  numberOfOutputs: 4
  dcOutputVoltageMaximum: 24000
  dcOutputVoltageCurrent: 0
  maximumOutputPowerOnDcOutput: 15000
  serialNumber: "123456789123456789"
  macAddress: "\330\2009F\027N"
  hardwareId: "SB10                      "
  internalFlashMemSize: 1048576
  externalFlashMemSize: 8388608
  lastInternalTestResultCode: 0
  startupCounter: 2
  bootLoaderVersion: "v1.0"
  firmwareVersion: "W0311g"
  currentConfigurationBackUsed: "\000"
  name: "device-01"
  currentTime: "20160313141247"
  currentIp: "192.168.178.16"
}
```

