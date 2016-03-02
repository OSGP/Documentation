	<wsdl:message name="GetDevicesHeader">
		<wsdl:part element="common:OrganisationIdentification" name="OrganisationIdentification" />
		<wsdl:part element="common:UserName" name="UserName" />
		<wsdl:part element="common:ApplicationName" name="ApplicationName" />
	</wsdl:message>
	<wsdl:message name="GetDevicesRequest">
		<wsdl:part element="smman:GetDevicesRequest" name="GetDevicesRequest">
		</wsdl:part>
	</wsdl:message>
	<wsdl:message name="GetDevicesResponse">
		<wsdl:part element="smman:GetDevicesResponse" name="GetDevicesResponse">
		</wsdl:part>
	</wsdl:message>
