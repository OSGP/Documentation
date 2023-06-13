<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# RegisterDevice

## Description

The device registration is a 2 step process. First RegisterDeviceRequest and RegisterDeviceResponse are exchanged between device and platform. Second [ConfirmRegisterDeviceRequest and ConfirmRegisterDeviceResponse messages](confirmregisterdevice.md) are exchanged.

Request that notifies the platform a device which wants to register. During the registration the sequence number is reset to a random value the platform is notified if the device has a light schedule, the type of the device, the device identification, and the device communicates its IP address to the platform. Also a random number is determined by the device and this 'randomDevice' should be present in the response form the platform.

Response which holds the time of the platform so the device can synchronize the time, contains location information for the device like GPS coordinates and Daylight Saving Time information. The device will sent ConfirmRegisterDeviceRequest after receiving the RegisterDeviceResponse. Also a random number is determined by the platform and this 'randomPlatform' should be present in the next request 'ConfirmRegisterDeviceRequest' by the device.

## Message definitions

```javascript
message RegisterDeviceRequest {
    required string deviceIdentification = 1; // [(nanopb).max_size = 41];
    required bytes ipAddress = 2; // [(nanopb).max_size = 4];
    required DeviceType deviceType = 3;
    required bool hasSchedule = 4;
    required uint32 randomDevice = 5; // 16 bits
}

message RegisterDeviceResponse {
    required Status status = 1;
    required string currentTime = 2; // [(nanopb).max_size = 15];// - format YYYYMMDDhhmmss UTC
    required uint32 randomDevice = 3;
    required uint32 randomPlatform = 4;
    optional LocationInfo locationInfo = 5; // Location information of device
}
```

## Datatypes

```javascript
enum DeviceType {
    PSLD = 0;
    SSLD = 1;
}

enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}

message LocationInfo {
    optional sint32 timeOffset = 1; // correction in minutes with respect to UTC
    optional sint32 latitude = 2; // divide by 1000000 to get float value
    optional sint32 longitude = 3; // divide by 1000000 to get float value
}
```

## Example

OSLP RegisterDeviceRequest sent from 'device-01' to platform:

```javascript
registerDeviceRequest {
  deviceIdentification: "device-01"
  ipAddress: "#\000\000\001"
  deviceType: SSLD
  hasSchedule: false
  randomDevice: 13246
}
```

OSLP RegisterDeviceResponse sent from platform to 'device-01':

```javascript
registerDeviceResponse {
  status: OK
  currentTime: "20160106135210"
  randomDevice: 13246
  randomPlatform: 44765
  locationInfo {
    timeOffset: 60
    latitude: 50889228
    longitude: 5974140
  }
}
```

