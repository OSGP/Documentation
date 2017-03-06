## Microgrids documentation

A first experiment with Microgrids using the open smart grid platform.
The open smart grid platform act as an central component to monitor and control microgrids.

### Scope
The goal of this domain is to control and monitor microgrids.

### Features
Currently, the following features are available within the open smart grid platform:

#### Get Data
Get data is used to retrieve measurement and profile data from the device

#### Set Data
Set data is used to set setpoints and profiles on the device

#### Notifications
When either report data or the result for a request is available, a notification is sent to a client,
after which the client will be able to obtain the data or result by sending an 'async' message.

#### Reporting
When a device is connected it will periodically push measurement reports (and send trigger-based status reports) to OSGP. OSGP will inform the client via a notification, after which the data can be retrieved in a way similar to GetData (using the GetDataAsync message).
In order to determine whether all report data are received, the response of a GetDataAsync message will (in case of a report) contain report metadata consisting of a report id, sequence number and time of entry.(XSD is already updated with report metadata, returning the report metadata from OSGP is not yet implemented)

### Messages

- **GetData** is a request to retrieve measurement and profile data from a device.
- **GetDataAsync** is a request to retrieve the result of the GetData request or to retrieve report data pushed by the device.
- **SetData** is a request to set setpoints and profiles on a device.
- **SetDataAsync** is a request to retrieve the result of the SetData request.

### WSDLs

* [WSDL's and schema's](https://github.com/OSGP/Shared/tree/development/osgp-ws-microgrids/src/main/resources)

### Cucumber test
Functionality like **GetData** can now be tested, with the Cucumber framework, using the **protocol-simulator-iec61850**. This simulator can be started from the Cucumber tests, and is configured with its own properties file.

### Multiple Server names
By default the RTU device is configured with the servername: **WAGO61850Server**. This name also appears in the **icd** file, that is used by the RTU device. The name of this icd file, is configured in a properties file. Multiple server names are now supported, with the introduction of the new column: **server_name** in the **iec61850_device** table. If this value is null, 
the default servername (WAGO61850Server) is used, otherwise the servername from the database is used (eg 'WAGO123'). In that case another corresponding icd file, in which this servername is used, must be configured! 


