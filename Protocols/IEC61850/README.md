## IEC61850
The open smart grid platform support IEC61850. IEC61850 is a popular protocol in the field of "smart grids". IEC 61850 started as an standard for substation automation but has expanded into other domains such as EV and solar panels. Currently, the IEC61850 protocol is used within the Public Lighting, Microgrids and Distribution Automation domains.
[IEC 61850 on Wikipedia](https://en.wikipedia.org/wiki/IEC_61850)

## Protocol security
* No security options exist in this IEC61850 version 1 and 2
* Use through a secured tunnelling protocol like TLS (with client certificates) or VPN 
IEC Security guidelines can be found in IEC 62351.

### Specific communication service mapping (SCSM) 
The open smart grid platform implementation supports:
* IEC 61850-8-1: Mappings to MMS (ISO/IEC9506-1 and ISO/IEC 9506-2)

### Used library
The [OpenMUC IEC61850 library from Fraunhofer](https://www.openmuc.org/iec-61850/) is used to implement the protocol.

## Supported Devices
This devices are currently supported by the Open Smart Grid Platform.
* Wago 750-881 RTU
* ABB 540CID11 RTU
* Kaifa AS101 load control box
