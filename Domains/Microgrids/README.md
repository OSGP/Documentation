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
In order to determine whether all report data are received, the response of a GetDataAsync message will (in case of a report) contain report metadata consisting of a report id, sequence number and time of entry.

### Messages

- **GetData** is an asynchronous request to retrieve measurement and profile data from a device.
- **GetDataAsync** is a request to retrieve the result of the GetData request or to retrieve report data pushed by the device.
- **SetData** is an asynchronous request to set setpoints and profiles on a device.
- **SetDataAsync** is a request to retrieve the result of the SetData request.

### WSDLs

* [WSDL's and schema's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-microgrids/src/main/webapp/WEB-INF/wsdl/microgrids)
