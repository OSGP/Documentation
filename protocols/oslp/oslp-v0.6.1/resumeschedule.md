<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# ResumeSchedule

## Description

Request that notifies the device to continue the current schedule after the current schedule was interrupted \(for example by switching by hand using SetLightRequest\). This request can operate on a single relay or on all relays and the resuming of the schedule can be immediate or at the next schedule-entry.

Response which confirms the ResumeScheduleRequest has been executed or rejects the ResumeScheduleRequest.

## Message definitions

```javascript
message ResumeScheduleRequest {
    optional bytes index = 1; // [(nanopb).max_size = 1]; // index number of connected light (DALI), none means all connected lights.
    required bool immediate = 2; // [default = false]; // Resume at next schedule item or direct
}

message ResumeScheduleResponse {
    required Status status = 1;
}
```

## Data types

```javascript
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

## Example

Soap requests and responses sent to and from platform:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/publiclighting/2014/10" xmlns:adh="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>liander gebruiker</com:UserName>
      <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <adh:ResumeScheduleRequest>
         <adh:DeviceIdentification>device-01</adh:DeviceIdentification>
         <!--Optional:-->
         <adh:Index>1</adh:Index>
         <adh:IsImmediate>1</adh:IsImmediate>
      </adh:ResumeScheduleRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:ResumeScheduleAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>LianderNetManagement|||device-01|||20160104152159539</ns3:CorrelationUid>
            <ns3:DeviceId>device-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:ResumeScheduleAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:com="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:adh="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <com:OrganisationIdentification>LianderNetManagement</com:OrganisationIdentification>
      <com:UserName>liander gebruiker</com:UserName>
      <com:ApplicationName>WEB_NET_MANAGEMENT</com:ApplicationName>
   </soapenv:Header>
   <soapenv:Body>
      <adh:ResumeScheduleAsyncRequest>
         <adh:AsyncRequest>
            <com:CorrelationUid>LianderNetManagement|||device-01|||20160104152159539</com:CorrelationUid>
            <com:DeviceId>device-01</com:DeviceId>
         </adh:AsyncRequest>
      </adh:ResumeScheduleAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:ResumeScheduleResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:Result>OK</ns2:Result>
      </ns2:ResumeScheduleResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

OSLP ResumeScheduleRequest sent to 'device-01':

```javascript
resumeScheduleRequest {
  index: "\001"
  immediate: true
}
```

OSLP ResumeScheduleResponse sent to platform:

```javascript
resumeScheduleResponse {
  status: OK
}
```

