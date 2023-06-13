<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# ConfirmRegisterDevice

## Description

Request which contains the 2 random numbers from RegisterDeviceRequest and RegisterDeviceResponse. The numbers should match with the previous request and response and this is checked by the platform.

Response which contains the sequenceWindow which is the maximum allowed difference between sequence numbers for future messages. Further the response contains the 2 random numbers from the ConfirmRegisterDeviceRequest. The numbers should match with the previous request and response and this is checked by the device.

## Message definitions

```javascript
message ConfirmRegisterDeviceRequest {
    required uint32 randomDevice = 1;
    required uint32 randomPlatform = 2;
}

message ConfirmRegisterDeviceResponse {
    required Status status = 1;
    required uint32 randomDevice = 2;
    required uint32 randomPlatform = 3;
    required uint32 sequenceWindow = 4;
}
```

## Datatypes

```javascript
enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

## Example

OSLP ConfirmRegisterDeviceRequest sent from 'device-01' to platform:

```javascript
confirmRegisterDeviceRequest {
  randomDevice: 13246
  randomPlatform: 44765
}
```

OSLP ConfirmRegisterDeviceResponse sent from platform to 'device-01':

```javascript
confirmRegisterDeviceResponse {
  status: OK
  randomDevice: 13246
  randomPlatform: 44765
  sequenceWindow: 6
}
```

