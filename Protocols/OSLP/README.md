## 5.3 OSLP Documentation


### 5.3.1 The Open Street Light Protocol

The OSLP is a lightweight message based protocol. OSLP uses [Google Protocol Buffers](https://developers.google.com/protocol-buffers/?hl=en). It is defined as a contract/interface. The interface defines datatypes and messages which use those datatypes.

### 5.3.2 OSLP v0.5.1

The protobuf contract for [OSLP v0.5.1](./oslp/v0.5.1/oslp.proto.v0.5.1.md).
For v0.5.1 port number 12121 is used.

### 5.3.3 OSLP v0.6.0

The protobuf contract for [OSLP v0.6.0](./oslp/v0.5.1/oslp.proto.v0.6.0.md).
For v0.6.0 port number 12122 is used.

### 5.3.4 OSLP Envelope

The requests and responses are sent using an OSLP envelope. This structure contains the following fields: securityKey, sequenceNumber, deviceId and payloadMessage. The first 3 field are byte arrays, the payloadMessage is a protobuf type which is serializable.

``` java
class OslpEnvelope {
    /**
     * Length of the security hash.
     * Length for ECDSA is 71 or 72 or 73 bytes.
     * Length for RSA is 128 bytes.
     */
    public static final int SECURITY_KEY_LENGTH = 128;

    /**
     * Length of the sequence number.
     */
    public static final int SEQUENCE_NUMBER_LENGTH = 2;

    /**
     * Length of the manufacturer id.
     */
    public static final int MANUFACTURER_ID_LENGTH = 2;

    /**
     * Length of the device id.
     */
    public static final int DEVICE_ID_LENGTH = 10;

    /**
     * Length of the length.
     */
    public static final int LENGTH_INDICATOR_LENGTH = 2;

    /**
     * Buffer for security key bytes.
     */
    public byte[] securityKey = new byte[SECURITY_KEY_LENGTH];

    /**
     * Buffer for sequence number bytes.
     */
    public byte[] sequenceNumber = new byte[SEQUENCE_NUMBER_LENGTH];

    /**
     * Buffer for deviceid bytes.
     */
    public byte[] deviceId = new byte[DEVICE_ID_LENGTH + MANUFACTURER_ID_LENGTH];

    /**
     * Buffer for OSLP payload.
     */
    public Message payloadMessage;
}
```
