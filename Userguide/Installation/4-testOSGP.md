
### Setting Up SoapUI
Start SoapUI by typing the following command in a terminal:
```shell
/home/dev/Tools/SoapUI-5.2.1/bin/soapui.sh
```

Go to File -> Preferences -> SSL Settings, and browse for the KeyStore to `/home/dev/Sources/Config/certificates/osgp-ca/certs/test-org.pfx` and fill out the password (the password is 1234)
![alt text](./installation-script-screenshots/85.png)

Go to WSDL Settings and check 'Generate Example Values in New Requests' and 'Generate Comments with Type Information in New Requests'
![alt text](./installation-script-screenshots/86.png)

Create a new SOAP Project and call it 'admin'
![alt text](./installation-script-screenshots/87.png)

Open the Project View by double-clicking on the 'admin' project. Go to 'WS-Security Configurations' and select the 'Keystores' Tab. Click on the '+' to add the `test-org.pfx` in `/home/dev/Sources/Config/certificates/osgp-ca/certs/`
Fill out the password (1234) and click Ok and close the Project View window.
![alt text](./installation-script-screenshots/87-1.png)

Right click the 'admin' project and choose 'Add WSDL'. Enter the following URL in the WSDL Location field:
```
https://localhost/osgp-adapter-ws-admin/wsdl/Admin/DeviceManagement.wsdl
```
Make sure the box 'Create sample requests for all operators' is checked, and click OK.
![alt text](./installation-script-screenshots/88.png)

Create another new SOAP Project and call it 'public-lighting'
![alt text](./installation-script-screenshots/88-1.png)

Open the Project View by double-clicking on the 'public-lighting' project. Go to 'WS-Security Configurations' and select the 'Keystores' Tab. Click on the '+' to add the `test-org.pfx` in `/home/dev/Sources/Config/certificates/osgp-ca/certs/`
Fill out the password (1234) and click Ok and close the Project View window.
![alt text](./installation-script-screenshots/88-2.png)

Right click the 'public-lighting' project and choose 'Add WSDL'. Enter the following URL in the WSDL Location field:
```
https://localhost/osgp-adapter-ws-publiclighting/wsdl/PublicLighting/PublicLightingAdHocManagement.wsdl
```
Make sure the box 'Create sample requests for all operators' is checked, and click OK.
![alt text](./installation-script-screenshots/88-3.png)

### First SOAP Requests to Add a Device to OSGP
Before we can send our first request, we have to add the test-org.pfx as SSL Keystore: Go to the properties interface for the request (bottom left of the screen, after selecting 'Request 1' under UpdateKey in the 'admin' project'), and choose `test-org.pfx` from the drop-down box.
###Note
- This has to be done for each request!

![alt text](./installation-script-screenshots/89.png)

A SSLD needs to be added to the platform, together with a public key. The UpdateKey function of the admin webservice offers that functionality. Double click 'Request 1' under UpdateKey in the 'admin' project. Add the following request:
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:ns1="http://www.alliander.com/schemas/osgp/admin/devicemanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>APPLICATION_NAME</ns:ApplicationName>
      <ns:UserName>USER_NAME</ns:UserName>
      <ns:OrganisationIdentification>test-org</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:UpdateKeyRequest>
         <!--type: Identification-->
         <ns1:DeviceIdentification>SSLD_000-00-01</ns1:DeviceIdentification>
         <!--type: string-->
         <ns1:PublicKey>MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEFhUImXFJdqmputquVAc2CPdnn9Ju00M3m/Ice7wABNN+oAYKQbw/OceqvZmFF1+r4nO/vCm/f1JO5nEorE2jNQ==</ns1:PublicKey>
         <!--type: long-->
         <ns1:ProtocolInfoId>1</ns1:ProtocolInfoId>
      </ns1:UpdateKeyRequest>
   </soapenv:Body>
</soapenv:Envelope>
```
![alt text](./installation-script-screenshots/89-1.png)

Click the 'play' button to submit the request to the endpoint. You should receive similar response as shown in the screenshot below:
![alt text](./installation-script-screenshots/90.png)

After the SSLD has been added, let's see if the function FindAllDevices shows the SSLD. Continue with the FindAllDevices request from the public-lighting project.
Do not forget to set the SSL keystore in the Request Properties. Use the following parameters in the request:
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:ns1="http://www.alliander.com/schemas/osgp/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>APPLICATION_NAME</ns:ApplicationName>
      <ns:UserName>USER_NAME</ns:UserName>
      <ns:OrganisationIdentification>test-org</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:FindAllDevicesRequest>
         <!--type: int-->
         <ns1:Page>0</ns1:Page>
      </ns1:FindAllDevicesRequest>
   </soapenv:Body>
</soapenv:Envelope>
```
After the request has been submitted, the response should include the SSLD device with ID SSLD_000_00_01
![alt text](./installation-script-screenshots/91.png)

### Opening Device Simulator to Add a Device
In order to be able to use the SSLD-000-00-01 Device, the device needs to be simulated in the Device Simulator. To do this we have to create it.
In the Firefox Browser, open the Device Simulator by going to the following URL: 
```
https://localhost/web-device-simulator/devices
```
If you encounter a Untrusted Connection page, go to 'I Understand the Risks' -> Add Exception.. -> Confirm Security Exception
![alt text](./installation-script-screenshots/92.png)

Click Add Device
![alt text](./installation-script-screenshots/93.png)

Fill out the fields like this:
- Device Identification: SSLD_000-00-01
- IP Address: 127.0.0.1
- Device Type: SSLD
- Protocol: OSLP

Click Create Device
![alt text](./installation-script-screenshots/94.png)

You should return to the Devices screen and see the message "Device with identification SSLD_000-00-01 was created."
![alt text](./installation-script-screenshots/95.png)

### Registering a Device
Now click on the newly created device and click the 'Register Device' button. After a while the message "Device identification with identification SSLD_000-00-01 was registered at XXXXXXXX" appears.
![alt text](./installation-script-screenshots/96.png)

Then click the 'Confirm Registration' button. The message should read: "Device with identification SSLD_000-00-01 was confirmed to be registered."
![alt text](./installation-script-screenshots/97.png)

### Using 'SetLight' SOAP Request to Switch the Light On
Now that the Device is known in the platform, and simulated in the Device-Simulator, the device can be used. Let's switch on the Light.
Using SoapUI, click on Request 1 under SetLight at the public-lighting project. Set the following parameters in the request (And do not forget to set the Keystore in the request properties):

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:ns1="http://www.alliander.com/schemas/osgp/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>APPLICATION_NAME</ns:ApplicationName>
      <ns:UserName>USER_NAME</ns:UserName>
      <ns:OrganisationIdentification>test-org</ns:OrganisationIdentification>
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
            <ns1:DimValue>100</ns1:DimValue>
         </ns1:LightValue>
      </ns1:SetLightRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

Submit the request. Take note of the CorrelationUid in the response. We can send out a request later using that Id to ask the Platform if the request succeeded. 
![alt text](./installation-script-screenshots/98.png)

In the home screen of the OSLP device simulator, the lightbulb should light up for SSLD_000-00-01. Now we know the request succeeded. 
![alt text](./installation-script-screenshots/99.png)

Normally we don't have a device simulator to know if the SetLight request succeeded. But we can ask the platform by sending another request: GetSetLightResponse.
In SoapUi open Request 1 under 'GetSetLightResponse' in the 'public-lighting' project. Set the following parameters in the request (And the keystore in the request properties):
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.alliander.com/schemas/osgp/common/2014/10" xmlns:ns1="http://www.alliander.com/schemas/osgp/publiclighting/adhocmanagement/2014/10">
   <soapenv:Header>
      <ns:ApplicationName>APPLICATION_NAME</ns:ApplicationName>
      <ns:UserName>USER_NAME</ns:UserName>
      <ns:OrganisationIdentification>test-org</ns:OrganisationIdentification>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:SetLightAsyncRequest>
         <ns1:AsyncRequest>
            <!--type: CorrelationUid-->
            <ns:CorrelationUid>test-org|||SSLD_000-00-01|||20160721083641940</ns:CorrelationUid>
            <!--type: Identification-->
            <ns:DeviceId>SSLD_000-00-01</ns:DeviceId>
         </ns1:AsyncRequest>
      </ns1:SetLightAsyncRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

#### Note
- Do not forget to set the CorrelationUid to value in the response you received from the setLight request.

![alt text](./installation-script-screenshots/100.png)

