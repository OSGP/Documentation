### OSLP protobuf file, v0.5.1

```json
// import "nanopb.proto";

package oslp;

option java_package = "com.alliander.osgp.oslp";

message Message {
    optional RegisterDeviceRequest registerDeviceRequest = 1;
    optional RegisterDeviceResponse registerDeviceResponse = 2;
    optional StartSelfTestRequest startSelfTestRequest = 3;
    optional StartSelfTestResponse startSelfTestResponse = 4;
    optional StopSelfTestRequest stopSelfTestRequest = 5;
    optional StopSelfTestResponse stopSelfTestResponse = 6;
    optional UpdateFirmwareRequest updateFirmwareRequest = 7;
    optional UpdateFirmwareResponse updateFirmwareResponse = 8;
    optional SetLightRequest setLightRequest = 9;
    optional SetLightResponse setLightResponse = 10;
    optional GetStatusRequest getStatusRequest = 11;
    optional GetStatusResponse getStatusResponse = 12;
    optional ResumeScheduleRequest resumeScheduleRequest = 13;
    optional ResumeScheduleResponse resumeScheduleResponse = 14;
    optional SetEventNotificationsRequest setEventNotificationsRequest = 15;
    optional SetEventNotificationsResponse setEventNotificationsResponse = 16;
    optional EventNotificationRequest eventNotificationRequest = 17;
    optional EventNotificationResponse eventNotificationResponse = 18;
    optional GetFirmwareVersionRequest getFirmwareVersionRequest = 19;
    optional GetFirmwareVersionResponse getFirmwareVersionResponse = 20;
    optional SetScheduleRequest setScheduleRequest = 21;
    optional SetScheduleResponse setScheduleResponse = 22;
    optional SetConfigurationRequest setConfigurationRequest = 25;
    optional SetConfigurationResponse setConfigurationResponse = 26;
    optional GetPowerUsageHistoryRequest getPowerUsageHistoryRequest = 27;
    optional GetPowerUsageHistoryResponse getPowerUsageHistoryResponse = 28;
    optional GetActualPowerUsageRequest getActualPowerUsageRequest = 29;
    optional GetActualPowerUsageResponse getActualPowerUsageResponse = 30;
    optional SetRebootRequest setRebootRequest = 31;
    optional SetRebootResponse setRebootResponse = 32;
    optional SetTransitionRequest setTransitionRequest = 33;
    optional SetTransitionResponse setTransitionResponse = 34;
    optional GetConfigurationRequest getConfigurationRequest = 35;
    optional GetConfigurationResponse getConfigurationResponse = 36;
    optional ConfirmRegisterDeviceRequest confirmRegisterDeviceRequest = 37;
    optional ConfirmRegisterDeviceResponse confirmRegisterDeviceResponse =  38;
}

// ========= Device Installation
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

message StartSelfTestRequest {
    optional bool present = 1 [default = true];
}

message StartSelfTestResponse {
    required Status status = 1;
}

message StopSelfTestRequest {
    optional bool present = 1 [default = true];
}

message StopSelfTestResponse {
    required Status status = 1;
    required bytes selfTestResult = 2; // [(nanopb).max_size = 1];
}

// ========= Firmware Management
message GetFirmwareVersionRequest {
    optional bool present = 1 [default = true];
}

message GetFirmwareVersionResponse {
    required string firmwareVersion = 1; // [(nanopb).max_size = 7]; // RXX
}

message UpdateFirmwareRequest {
    required string firmwareDomain = 1; // [(nanopb).max_size = 100]; // Servername
    required string firmwareUrl = 2; // [(nanopb).max_size = 255]; // /firmware/PSLD/RXX
}

message UpdateFirmwareResponse {
    required Status status = 1;
}

// ========= Ad-Hoc & Status
message SetLightRequest {
    repeated LightValue values = 1; // [(nanopb).max_count = 6];
}

message SetLightResponse {
    required Status status = 1;
}

message GetStatusRequest {
    optional bool present = 1 [default = true];
}

message GetStatusResponse {
    required Status status = 1;
    repeated LightValue value = 2; // [(nanopb).max_count = 6];
    required LinkType preferredLinktype = 3;
    required LinkType actualLinktype = 4;
    required LightType lightType = 5;
    required uint32 eventNotificationMask = 6; // Bitmask for max 32 events, using NotificationBit for bit positions.
}

message ResumeScheduleRequest {
    optional bytes index = 1; // [(nanopb).max_size = 1]; // index number of connected light (DALI), none means all connected ligts.
    required bool immediate = 2; // [default = false]; // Resume at next schedule item or direct
}

message ResumeScheduleResponse {
    required Status status = 1;
}

message SetRebootRequest {
    optional bool present = 1 [default = true];
}

message SetRebootResponse {
    required Status status = 1;
}

message SetTransitionRequest {
    required TransitionType transitionType = 1; // Night-Day or Day-Night transition
    optional string time = 2; // [(nanopb).max_size = 7]; // - format hhmmss UTC
}

message SetTransitionResponse {
    required Status status = 1;
}

message SetEventNotificationsRequest {
    required uint32 NotificationMask = 1; // Bitmask for max 32 events, using NotificationBit for bit positions.
}

message SetEventNotificationsResponse {
    required Status status = 1;
}

message EventNotificationRequest {
    repeated EventNotification notifications = 1; // [(nanopb).max_count = 6];
}

message EventNotificationResponse {
    required Status status = 1;
}

// ========= Scheduling
message SetScheduleRequest {
    repeated Schedule schedules = 1; // [(nanopb).max_count = 50];
    optional PageInfo pageInfo = 2;
    required RelayType scheduleType = 3; // RT_NOT_SET is NOT supported!
}

message SetScheduleResponse {
    required Status status = 1;
}

// ========= Configuration
message SetConfigurationRequest {
    optional LightType lightType = 1;
    optional DaliConfiguration daliConfiguration = 2; // contains specific configuration for DALI controllers
    optional RelayConfiguration relayConfiguration = 3; // contains specific configuration for Relay
    optional uint32 shortTermHistoryIntervalMinutes = 4; 
    optional LinkType preferredLinkType = 5;
    optional MeterType meterType = 6;
    optional uint32 longTermHistoryInterval = 7; 
    optional LongTermIntervalType longTermHistoryIntervalType = 8; 
}

message SetConfigurationResponse {
    required Status status = 1;
}

message GetConfigurationRequest {
    optional bool present = 1 [default = true];
}

message GetConfigurationResponse {
    required Status status = 1;
    optional LightType lightType = 2;
    optional DaliConfiguration daliConfiguration = 3; // contains specific configuration for DALI controllers
    optional RelayConfiguration relayConfiguration = 4; // contains specific configuration for Relay
    optional uint32 shortTermHistoryIntervalMinutes = 5; 
    optional LinkType preferredLinkType = 6;
    optional MeterType meterType = 7;
    optional uint32 longTermHistoryInterval = 8; 
    optional LongTermIntervalType longTermHistoryIntervalType = 9; 
}

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

// ========= Monitoring
message GetPowerUsageHistoryRequest {
    required TimePeriod timePeriod = 1;
    optional uint32 page = 2;
    required HistoryTermType termType = 3;
}

message GetPowerUsageHistoryResponse {
    required Status status = 1;
    repeated PowerUsageData powerUsageData = 2; // [(nanopb).max_count = 20]; 
    optional PageInfo pageInfo = 3;
}

message GetActualPowerUsageRequest {
    optional bool present = 1 [default = true];
}

message GetActualPowerUsageResponse {
    required Status status = 1;
    required PowerUsageData powerUsageData = 2;
}

// ========= Types
message LocationInfo {
    optional sint32 timeOffset = 1; // correction in minutes with respect to UTC
    optional sint32 latitude = 2; // divide by 1000000 to get float value
    optional sint32 longitude = 3; // divide by 1000000 to get float value
}

message LightValue {
    optional bytes index = 1; // [(nanopb).max_size = 1]; // index number of connected light (DALI), none means all connected ligts.
    required bool on = 2;
    optional bytes dimValue = 3; // [(nanopb).max_size = 1]; // 1 - 100 %
}

message EventNotification {
    required Event event = 1;
    optional bytes index = 2; // [(nanopb).max_size=1];
    optional string description = 3; // [(nanopb).max_size = 81];
}

message Schedule {
    required Weekday weekday = 1;
    optional string startDay = 2; // [(nanopb).max_size = 9]; //- format YYYYMMDD UTC, indicates the range of a schedule entry, from startDay
    optional string endDay = 3; // [(nanopb).max_size = 9]; // - format YYYYMMDD UTC, including endDay
    required ActionTime actionTime = 4;
    optional string time = 5; // [(nanopb).max_size = 7]; // - format hhmmss localtime set when actionTime = ABSOLUTETIME
    optional Window window = 6; // window to wait for light sensor trigger
    repeated LightValue value = 7; // [(nanopb).max_count = 6];
    optional TriggerType triggerType = 8; // React to setTransition or switch astronomical
}

message Window {
    required uint32 minutesBefore = 1; // minutes before sunset / sunrise
    required uint32 minutesAfter = 2; // minutes after sunset / sunrise
}

message DaliConfiguration {
    optional bytes numberOfLights = 1; // [(nanopb).max_size = 1]; // number of lights connected to DALI controller
    repeated IndexAddressMap addressMap = 2; // [(nanopb).max_count = 4];
}

message RelayConfiguration {
    repeated IndexAddressMap addressMap = 1; // [(nanopb).max_count = 6];
}

message IndexAddressMap {
    required bytes index = 1; // [(nanopb).max_size = 1]; // external index, for example 1
    required bytes address = 2; // [(nanopb).max_size = 1]; // internal address, for example 2
    required RelayType relayType = 3;
}

message PageInfo {
    required uint32 currentPage = 1; // Pages start from 1
    required uint32 pageSize = 2;
    required uint32 totalPages = 3;
}

message TimePeriod {
    required string startTime = 1; // [(nanopb).max_size = 15];     // - format YYYYMMDDhhmmss UTC
    required string endTime = 2; // [(nanopb).max_size = 15];   // - format YYYYMMDDhhmmss UTC
}

message PowerUsageData {
    required string recordTime = 1; // [(nanopb).max_size = 15];    // Record time - format YYYYMMDDhhmmss UTC
    required MeterType meterType = 2;                               // Meter type (P1, Pulse, Aux)
    required uint64 totalConsumedEnergy = 3;                        // Electricity delivered to client (Tariff I + Tarrif II) in 0,001 kWh
    required uint32 actualConsumedPower = 4;                        // Actual Electricity power delivered in W
    optional PsldData psldData = 5;
    optional SsldData ssldData = 6;
}

message PsldData {
    required uint32 totalLightingHours = 1;     // Total lighting hours
}

message SsldData {
    required uint32 actualCurrent1 = 1;             // Instantaneous current L1 in mA
    required uint32 actualCurrent2 = 2;             // Instantaneous current L2 in mA
    required uint32 actualCurrent3 = 3;             // Instantaneous current L3 in mA
    required uint32 actualPower1 = 4;               // Instantaneous active power L1 in W
    required uint32 actualPower2 = 5;               // Instantaneous active power L2 in W
    required uint32 actualPower3 = 6;               // Instantaneous active power L3 in W
    required uint32 averagePowerFactor1 = 7;        // Power factor L1 (in 1/2^32) in steps of 0.1, 10 equals a power factor of 1
    required uint32 averagePowerFactor2 = 8;        // Power factor L2 (in 1/2^32) in steps of 0.1, 10 equals a power factor of 1
    required uint32 averagePowerFactor3 = 9;        // Power factor L3 (in 1/2^32) in steps of 0.1, 10 equals a power factor of 1
    repeated RelayData relayData = 10;   // [(nanopb).max_count = 4]; // Measurement data per relay 
}

message RelayData {
    required bytes index = 1; // [(nanopb).max_size = 1]; // external index, for example 1
    required uint32 totalLightingMinutes = 2;       // Total lighting minutes for lighting relay
}

// ========= Enumerations

// ========= Event Notification
enum NotificationBit {
    DIAG_EVENTS = 1;
    HARDWARE_FAILURE = 2;
    LIGHT_EVENTS = 4; // For example LightValue changes
    TARIFF_EVENTS = 8; // For example Tariff changes
    MONITOR_EVENTS = 16; // For example monitor buffer is almost full
    FIRMWARE_EVENTS = 32; // For example firmware activation
    COMM_EVENTS = 64; // For example alternative channel
    SECURITY_EVENTS = 128; // For example out of sequence
}


//Events must map to their notification bit:
//EG: 0000-0999 =1
//    1000-1999 =2
//    2000-2999 =4
//    3000-3999 =8
//    4000-4999 =16
//    5000-5999 =32
//    6000-6999 =64
//    7000-7999 =128
// OR to check  2^((event num)/1000)=notification bit

enum Event {
    // 0 - 999 Diagnostics
    DIAG_EVENTS_GENERAL = 0; 

    // 1000 - 1999 Hardware Failures
    HARDWARE_FAILURE_RELAY = 1000; // Index indicates relay (not supported yet) 

    // 2000 - 2999 Light Events
    LIGHT_EVENTS_LIGHT_ON = 2000; // Index indicates light
    LIGHT_EVENTS_LIGHT_OFF = 2001; // Index indicates light
    LIGHT_FAILURE_DALI_COMMUNICATION = 2500; // DALI communication failure
    LIGHT_FAILURE_BALLAST = 2501; // Ballast failure detected (DALI only)
    LIGHT_FAILURE_TARIFF_SWITCH_ATTEMPT = 2502; // Attempt to switch an endpoint configured as tariff from OVL schedule or manual override (index indicates endpoint) 

    // 3000 - 3999 Tariff Events
    TARIFF_EVENTS_TARIFF_ON = 3000; // Tariff switched on
    TARIFF_EVENTS_TARIFF_OFF = 3001; // Tariff switched off
     
    // 4000 - 4999
    MONITOR_EVENTS_LONG_BUFFER_FULL = 4000; // Long term monitoring buffer overrun occurred
    MONITOR_FAILURE_P1_COMMUNICATION = 4500; // P1 meter could not be read
    MONITOR_SHORT_DETECTED = 4600;
    MONITOR_SHORT_RESOLVED = 4601;
    MONITOR_DOOR_OPENED = 4700;
    MONITOR_DOOR_CLOSED = 4701;
     
    // 5000 - 5999 Firmware Events
    FIRMWARE_EVENTS_ACTIVATING = 5000; // Start activating new firmware, after downloading
    FIRMWARE_EVENTS_DOWNLOAD_NOTFOUND = 5501; // Download of firmware failed, i.e. location incorrect
    FIRMWARE_EVENTS_DOWNLOAD_FAILED = 5502; // Download of firmware failed, image incorrect 

    // 6000 – 6999
    COMM_EVENTS_ALTERNATIVE_CHANNEL = 6000; // Alternative channel selected for communication (description contains selected channel GPRS/CDMA/Ethernet)
    COMM_EVENTS_RECOVERED_CHANNEL = 6001; // Communication has been recovered for this channel
    
    // 7000 - 7999
    SECURITY_EVENTS_OUT_OF_SEQUENCE = 7000; // Out of sequence occurred and sequence number is renegotiated
}

// ========= Enums
enum TriggerType {
    TT_NOT_SET = 0;
    LIGHT_TRIGGER = 1;
    ASTRONOMICAL = 2;
}

enum TransitionType {
    NIGHT_DAY = 0;
    DAY_NIGHT = 1;
}

enum Weekday {
    MONDAY = 1;
    TUESDAY = 2;
    WEDNESDAY = 3;
    THURSDAY = 4;
    FRIDAY = 5;
    SATURDAY = 6;
    SUNDAY = 7;
    WEEKDAY = 8;
    WEEKEND = 9;
    ABSOLUTEDAY = 10;
    ALL = 11;
}

enum ActionTime {
    ABSOLUTETIME = 1;
    SUNRISE = 2;
    SUNSET = 3;
}

enum DeviceType {
    PSLD = 0;
    SSLD = 1;
}

enum Status {
    OK = 0;
    FAILURE = 1; // general failure
    REJECTED = 2; // request received in wrong state
}

enum LightType {
    LT_NOT_SET = 0;
    RELAY = 1;
    ONE_TO_TEN_VOLT = 2;
    ONE_TO_TEN_VOLT_REVERSE = 3;
    DALI = 4;
}

enum RelayType {
    RT_NOT_SET = 0;
    LIGHT = 1;
    TARIFF = 2;
}

enum MeterType {
    MT_NOT_SET = 0;
    P1 = 1;
    PULSE = 2;
    AUX = 3;
}

enum LinkType {
    LINK_NOT_SET = 0;
    GPRS = 1;
    CDMA = 2;
    ETHERNET = 3;
}

enum LongTermIntervalType {
    LT_INT_NOT_SET = 0;
    DAYS = 1;
    MONTHS = 2;
}

enum HistoryTermType {
    Short = 0;
    Long = 1;
}
```
