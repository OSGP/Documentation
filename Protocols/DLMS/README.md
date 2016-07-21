##DLMS/COSEM
The open smart grid platform supports DLMS/COSEM ([IEC 62056](https://en.wikipedia.org/wiki/IEC_62056)]. DLMS/COSEM is a popular protocol to read smart meters. DLMS/COSEM is the defacto standard in Europe.

The open smart grid platform DLMS/COSEM implementation was initial based on SMR5 and DSMR [v4](http://www.netbeheernederland.nl/themas/hotspot/hotspot-documenten/?dossierid=11010056&title=Slimme%20meter&onderdeel=Documenten).
Other types of meters/profiles can be added to the platform. The open smart grid platform implementation supports HLS3/4/5.

## Protocol security
* Public/private keypair(s)
* Multiple encryption levels inside protocol (DSMR requires highest encryption level)
* Full encryption of communication

###Used library
The [OpenMUC jDLMS library from Fraunhofer](https://www.openmuc.org/dlms-cosem/) is used to implement the protocol.
Please note that jDLMS is licensed under the GPLv3.

###DLMS device simulator
DLMS [device simulator](Protocols/DLMS/Devicesimulator.md)
