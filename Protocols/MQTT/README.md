## MQTT Documentation

## MQ Telemetry Transport Protocol

MQTT is a lightweight publish/subscribe messaging protocol designed for constrained devices and networks. 

## Dependencies

The MQTT Protocol Adapter uses the HiveMQ MQTT client `com.hivemq:hivemq-mqtt-client` which supports MQTT 3. 
The MQTT Protocol Simulator also uses HiveMQ, as well as the Moquette MQTT broker `io.moquette:moquette-broker`.
The reason for using Moquette is that there is no Maven dependency for the HiveMQ broker component.

## Simulator

The simulator runs an MQTT broker and a client which repeatedly publishes messages as specified in its `mqtt_simulator_spec.json` file.

Example:

```
{
  "brokerHost": "0.0.0.0",
  "brokerPort": 8883,
  "startupPauseMillis": 5000,
  "messages": [
    {

      "topic" : "TST-01/measurement",
      "payload": "TST-01; 220.1; 220.2; 220.3; 5.1; 5.2; 5.3; 7.1; 7.2; 7.3;",
      "pauseMillis": 30000
    },
    {

      "topic" : "TST-01/congestion",
      "payload": "TST-01; 5.1; 5.2; 5.3; 7.1; 7.2; 7.3;",
      "pauseMillis": 30000
    }
  ]
}
```

The spec file above will pause for 5 seconds and then start publishing a measurement and congestion message with intervals of 30 seconds.
The message payload is assumed to be a String and not validated or parsed in any way. 

The protocol adapter will establish a connection with the simulator and subscribe to the default topics `+/measurement,+/congestion`. 
This means `measurement` and `congestion` messages from any device (`+`).
 
A configurable default QoS value is used (See `com.hivemq.client.mqtt.datatypes.MqttQos` for the values).

If not yet present, an MqttDevice is saved in the database of the protocol adapter with the values used. 
If the MqttDevice is updated in the database, the updated values will be used for subsequent communication.
There is not yet any means to update this data, other than manual updating in the database.