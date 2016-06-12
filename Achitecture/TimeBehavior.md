### 1.5.1 Time Behavior

Time behavior is mainly significant in the Flexovl application when a lot of devices have to be addressed in a short period of time over a wireless network. Both latency and limited bandwidth have to be taken in consideration while demanding the coordinated on and off switching of the lighting (We do not want the Christmas tree effect after all).

- Time synchronization: devices periodically register with the platform and receive a time.
- Protocol: because of the limited bandwidth an efficient protocol "protobuf" was selected.

**Points of interest:**

- Light metering messages
- When the SSLD's are disabled the PSLDs cannot be addressed

Because of these points of interest we use message queueing combined with a retry mechanism of delayed delivery.

The platform and devices use UTC time. The OSLP protocol between platform and devices uses UTC time as well.
