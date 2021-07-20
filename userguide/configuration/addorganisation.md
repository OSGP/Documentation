# Add a new organisation

## Adding an Organisation to the platform

This chapter describes how to add a new Organisation to the platform. This includes creating a certificate for the new organisation.

## Creating an Organisation

In SoapUi go to DeviceManagement under the Admin project. Click on request 1 under CreateOrganisation. Fill in the parameters like the example request below. Make sure to sign the request with the test-org.pfx and to use the test-org organisation in the request header.

This request creates a new organisation called "my-org":

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/admin/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>APPLICATION_NAME</ns:ApplicationName>
      <ns:UserName>USER_NAME</ns:UserName>
      <ns:OrganisationIdentification>test-org</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:CreateOrganisationRequest>
         <ns1:Organisation>
            <!--type: Identification-->
            <ns1:OrganisationIdentification>my-org</ns1:OrganisationIdentification>
            <!--type: string-->
            <ns1:Name>my-org</ns1:Name>
            <!--type: string-->
            <ns1:Prefix>MYO</ns1:Prefix>
            <!--type: PlatformFunctionGroup - enumeration: [ADMIN,USER]-->
            <ns1:FunctionGroup>ADMIN</ns1:FunctionGroup>
            <!--type: boolean-->
            <ns1:Enabled>true</ns1:Enabled>
            <!--1 or more repetitions:-->
            <!--type: PlatformDomain - enumeration: [COMMON,PUBLIC_LIGHTING,TARIFF_SWITCHING]-->
            <ns1:Domains>COMMON</ns1:Domains>
            <ns1:Domains>PUBLIC_LIGHTING</ns1:Domains>
         </ns1:Organisation>
      </ns1:CreateOrganisationRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

## Authorise the new Organisation for the device

To use this new organisation to control the SSLD\_000-00-01 device, the authorisations need to be updated. To do that the UpdateDeviceAuthorisations request will be used, it can be found under DeviceManagement in the admin project.

Fill in the parameters like shown below. The functionGroup will be set to AdHoc to authorise the 'my-org' organisation for the AdHoc functions.

Make sure to use the test-org as OrganisationIdentification in the request header, and to sign the request with the test-org.pfx.

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/admin/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>AAPLICATION_NAME</ns:ApplicationName>
      <ns:UserName>USER_NAME</ns:UserName>
      <ns:OrganisationIdentification>test-org</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:UpdateDeviceAuthorisationsRequest>
         <!--1 or more repetitions:-->
         <ns1:DeviceAuthorisations>
            <!--type: Identification-->
            <ns1:deviceIdentification>SSLD_000-00-01</ns1:deviceIdentification>
            <!--type: Identification-->
            <ns1:organisationIdentification>my-org</ns1:organisationIdentification>
            <!--type: DeviceFunctionGroup - enumeration: [OWNER,INSTALLATION,AD_HOC,MANAGEMENT,FIRMWARE,SCHEDULING,TARIFF_SCHEDULING,CONFIGURATION,MONITORING]-->
            <ns1:functionGroup>AD_HOC</ns1:functionGroup>
            <!--Optional:-->
            <!--type: boolean-->
         </ns1:DeviceAuthorisations>
      </ns1:UpdateDeviceAuthorisationsRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

### Creating a certificate for the new organisation

Now that the 'my-org' organisation is authorised to use the SSLD\_000-00-01 device, it is time to create a certificate for the my-org organisation. This certificate will be used to sign the requests.

Open a terminal and navigate to `/home/dev/Sources/OSGP/Config/certificates/`

A script has been created to create the certificates, execute it by running the following command in the terminal:

```text
./create_client_cert.sh my-org 1234 1234
```

You should receive similar output as shown in the screenshot below.

![alt text](../../.gitbook/assets/01%20%281%29.png)

Now that the certificate has been created, restart the tomcat server.

## Signing a request with the new certificate

When the tomcat server is up and running again, go to SoapUi and add the new certificate to the public-lighting project: double-click on the project, go to the WS-Security Configurations tab and select the keystores tab. Click the '+' button and browse to the my-org.pfx certificate which can be found in `/home/dev/Sources/OSGP/Config/certificates/osgp-ca/certs/`

![alt text](../../.gitbook/assets/02%20%281%29.png)

Now double-click on 'Request 1' in SetLight in PublicLightingAdHocManagement in the public-lighting project. Set the SSL Keystore to 'my-org.pfx' in the request properties so the request gets signed with the new certificate. Change the request parameters as shown in the example below:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.opensmartgridplatform.org/schemas/common/2014/10" xmlns:ns1="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>APPLICATION_NAME</ns:ApplicationName>
      <ns:UserName>USER_NAME</ns:UserName>
      <ns:OrganisationIdentification>my-org</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetLightRequest>
         <!--type: Identification-->
         <ns1:DeviceIdentification>SSLD_000-00-01</ns1:DeviceIdentification>
         <!--1 to 6 repetitions:-->
         <ns1:LightValue>
            <!--Optional:-->
            <!--anonymous type-->
            <ns1:Index>0</ns1:Index>
            <!--type: boolean-->
            <ns1:On>true</ns1:On>
            <!--Optional:-->
            <!--anonymous type-->
            <ns1:DimValue>50</ns1:DimValue>
         </ns1:LightValue>
      </ns1:SetLightRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

Note the OrganisationIdentification is now set to 'my-org'. Send the new request, you should receive the following response:

```markup
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ns2:SetLightAsyncResponse xmlns:ns2="http://www.opensmartgridplatform.org/schemas/publiclighting/adhocmanagement/2014/10" xmlns:ns3="http://www.opensmartgridplatform.org/schemas/common/2014/10">
         <ns2:AsyncResponse>
            <ns3:CorrelationUid>my-org|||SSLD_000-00-01|||20160805150420802</ns3:CorrelationUid>
            <ns3:DeviceId>SSLD_000-00-01</ns3:DeviceId>
         </ns2:AsyncResponse>
      </ns2:SetLightAsyncResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Check the device-simulator to see if the dimValue of the SSLD\_000-00-01 changed to 50.

You now have successfully created a new organisation, along with a certificate to sign the requests, and changed the device authorisations of the device to accept commands from the new organisation.

