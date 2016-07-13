# Example use-case for this domain
Up-to-date information on use-cases can be found on the [open smart grid platform website](http://www.opensmartgridplatform.org).

#### Smart Meter Head-end System

**Technical drivers**

- Replacement or addition to the current head-end system
- During the coming years, many smart meters will be placed in houses, companies and other properties, therefore grid operators need a scalable solution
- E(lectricity) Meters can host up to 4 other smart devices, Gas Meters for example
- DLMS/COSEM is used by many(if not all) Smart Meters

**Customer drivers**

- People will have more insight in their power consumption
- Meter values can be gathered by the grid operator, instead of relying on people reporting the meter values

**Implementation**

Features available within the platform so far:

- Add smart meter to the platform, so the device is known and additonal actions can be performed for the device
- Process shipment file, which adds several smart meters to the platform along with all needed information
- Synchronize time between smart meters and head-end system, incase the smart meter adjusts it's time, some events will be logged
- Retrieve events from the smart meter, several event logs are available
- Retrieve periodic meter reads from the smart meter
