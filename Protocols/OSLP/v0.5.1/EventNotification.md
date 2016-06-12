## EventNotification messages

### Description

Request sent from device to platform containing information about 1 to 6 events.

Response sent from platform to 'device-01' communicates status.

### Message definitions

``` json
message EventNotificationRequest {
    repeated EventNotification notifications = 1; // [(nanopb).max_count = 6];
}

message EventNotificationResponse {
    required Status status = 1;
}
```

### Datatypes

``` json
message EventNotification {
    required Event event = 1;
    optional bytes index = 2; // [(nanopb).max_size=1];
    optional string description = 3; // [(nanopb).max_size = 81];
}

enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}
```

### Example

OSLP request sent from 'device-01' to platform:
``` json
eventNotificationRequest {
  notifications {
    event: TARIFF_EVENTS_TARIFF_OFF
    index: "\003"
    description: "Tariff Off Example Event"
  }
}
```

OSLP response sent to 'device-01':
``` json
eventNotificationResponse {
  status: OK
}
```