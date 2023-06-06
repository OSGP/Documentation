<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# Distribution automation

The Open Smart Grid Platform can also be used in the monitoring of a variety of components in substations; RTUs, switches, transformers, etc. Often, an RTU or Remote Terminal Unit is used as a central information hub in a substation. The RTU is connected to one or more sensors or devices that can measure any kind of information. Usually, the focus is on measuring power quality values, temperature and other 'health' variables, but any kind of measurable data can be read through OSGP.

## Scope

The goal of this domain is to control and monitor substations; the current focus is on health status information and power quality data, but this may be extended in the future.

## Features

Currently, the following features are available within the Open Smart Grid Platform using the IEC 61850 protocol;

### Get PQ Values

Get PQ Values retrieves the actual, current PQ values from a device. Examples of PQ values are Current, Voltage, Reactive Power, Active Power, etc. These examples merely serve as an indication of what is possible; OSGP does not impose any restriction on the number or content of variables that can be read. The outline of what should be measured is configured on the device and in the application that reads the data.

### Get Health Status

Retrieves the current health status of a device. This is useful in a monitoring application.

### Get Device Model

Retrieves the device model or metadata of a device. This includes the variables that can be measured, the information structure of the device, etc.

### Notifications

When either report data or the result for a request is available, a notification is sent to a client, after which the client will be able to obtain the data or result by sending an 'async' message. A notification message always contains the correlation ID of the original request; the client can retrieve the result using this correlation ID.

## Messages

* **GetPQValues** is a request to retrieve PQ values from a device.
* **GetPQValuesAsync** is a request to retrieve the result of the GetPQValues request or to retrieve report data pushed by the device.
* **GetHealthStatus** is a request to retrieve the health status of a device.
* **GetHealthStatusAsync** is a request to retrieve the result of a GetHealthStatus request.
* **GetDeviceModel** is a request to retrieve the device model from a device
* **GetDeviceModelAsync** is a request to retrieve the result of a GetDeviceModel request.

## WSDLs

* [WSDL's and schema's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-distributionautomation/src/main/resources)

