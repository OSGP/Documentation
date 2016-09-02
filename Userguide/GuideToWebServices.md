## Building an App for the OSGP Platform

All the features of the OSGP Platform are accessible by it's webservices, as defined in the WSDL files.
To access these services and commuinicate with devices through the platform, please keep in mind the following things. 

- A Soap request will have to be generated from the Application.
- In the WSDL, xsd files of the Platform the Requests and it's objects are defined.
- Fill in the right Parameters once you have an empty soap request for a certain function. The restrictions/requirements are defined in the WSDL files.
- The request should have a header where an ApplicationName, UserName and OrganisationId are defined. At the moment User and App name are not required for the Platform (Besides Audability). The OrganisationId, however, must match a known organisation within the Platform. This organisation must have the right authortities to make a certain request.
- Furthermore, the Request must be signed with a certificate from the Organisation with the OrganisationId in the header.
- The requests are made to Secure HTTP protocol (https).
- For Asynchronious requests, the Platform will respond with a correlationId after succesfully making the request. Use this correlationId in the matching Response-Request to obtain the response from the device.

To learn more about the Platform's webservices, please take a look at the [Domain Documentation](../Domains/README.md) or for hands-on experience with the Platform's webservices follow the [UserGuide](../Userguide/Installation/Setup-VM-Vagrant.md).
