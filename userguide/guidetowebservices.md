<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Web Services

All the features of the open smart grid platform are accessible by it's webservices, as defined in the WSDL files. To use these services to communicate with devices through the platform, please keep in mind the following things.

* A Soap request will have to be generated from your Application.
* In the WSDL and xsd files of the Platform the Requests and it's objects are defined.
* Fill in the parameters once you have an empty soap request for a certain function. The restrictions/requirements are defined in the WSDL files.
* The request should have a header where an ApplicationName, UserName and OrganisationId are defined. At the moment User and App name are not used in the Platform \(Except for audability and logging\). The OrganisationId, however, must match a known organisation within the Platform. This organisation must have the right authortities to make a certain request.
* Furthermore, the Request must be signed with a certificate from the Organization with the OrganisationId in the header.
* The requests use the Secure HTTP protocol \(https\).
* For Asynchronious requests, the Platform will respond with a correlationId after succesfully making the request. Use this correlationId in the matching Response-Request to obtain the response from the device.

To learn more about the open smart grid platform's webservices, please take a look at the [Domain Documentation](../domains) or for hands-on experience with the Platform's webservices follow the [UserGuide](installationguide/installation/setup-vm-vagrant.md).

## Rest

It is not possible to communicate with the Platform directly using REST webservices. As mentioned above, the open smart grid platform uses SOAP \(For reasons defined [here](../architecture/platform-components-description.md)\). If you want to use REST for your front end, you can write an Integration Layer that serves as a Soap Client and exposes the Soap calls through Rest web services that you can access from your front end.

## Flows

When using the SOAP Web service, there are 2 flows that can occur:

* some calls are synchronous: a response is returned immediately;
* other calls are a-synchronous: an initial response contains a correlation id, which can be used to obtain the actual response.

