## SmartMetering Documentation (Beta version)

This chapter describes the SmartMetering domain including the webservices. Currently the webservices of the beta version are described, since the webservices have not yet officially been released.
Information on the DLMS device simulator can be found in the [DLMS protocol section](../Protocols/DLMS/Devicesimulator.md)

### Scope
The goal of this domain is to read and manage millions of smart smart meters. This includes smart meter installation, firmware updates, smart meter removal, read smart meter values, time synchronisation, etc.
Everything that is needed to professional manage millions of smart meters is or can be included in this domain.

### Features

Smart metering features available within on the open smart grid platform so far:

- Add smart meter to the platform, so the device is known and additional actions can be performed for the device
- Process shipment file, which adds several smart meters to the platform along with all needed information
- Synchronize time between smart meters and head-end system, in case the smart meter adjusts it's time, some events will be logged
- Retrieve events from the smart meter, several event logs are available
- Retrieve periodic meter reads from the smart meter

### Generic functionality

- **[priority](./smartmeteringwebservices/priority.md)** requests can be given a priority from 0 to 9, default is 4. Higher values causes messages to be processed faster.
- **[scheduling](./smartmeteringwebservices/scheduling.md)** requests can be scheduled for a certain time.
- **[bundeling](./smartmeteringwebservices/bundeling.md)** requests can be combined in a [Bundle](./smartmeteringwebservices/Bundle.md).


### Messages

#### SmartMeteringAdHoc
- **[SynchronizeTime](./smartmeteringwebservices/SynchronizeTime.md)** is a request to synchronize the date and time on a device. The date and time are retrieved from the server and sent to the device.
- **[GetSynchronizeTimeResponse](./smartmeteringwebservices/GetSynchronizeTimeResponse.md)** is a request which returns the response from the [SynchronizeTime](./smartmeteringwebservices/SynchronizeTime.md) request.
- **[RetrieveAllAttributeValues](./smartmeteringwebservices/RetrieveAllAttributeValues.md)** is a request to obtain all the attributes of the whole tree of objects from an E-meter. 
- **[GetRetrieveAllAttributeValuesResponse](./smartmeteringwebservices/GetRetrieveAllAttributeValuesResponse.md)** is a request which returns the response from the [RetrieveAllAttributeValues](./smartmeteringwebservices/RetrieveAllAttributeValues.md) request.
- **[GetSpecificAttributeValue](./smartmeteringwebservices/GetSpecificAttributeValue.md)** is a request to obtain a specific attribute value from an ObisCode from an E-meter. 
- **[GetSpecificAttributeValueResponse](./smartmeteringwebservices/GetSpecificAttributeValueResponse.md)** is a request which returns the response from the [GetSpecificAttributeValue](./smartmeteringwebservices/GetSpecificAttributeValue.md) request.
- **[GetAssociationLnObjects](./smartmeteringwebservices/GetAssociationLnObjects.md)** is a request to get the associated ln objects.
- **[GetGetAssociationLnObjectsResponse](./smartmeteringwebservices/GetGetAssociationLnObjectsResponse.md) ** is a request which gets the response from the [GetAssociationLnObjects](./smartmeteringwebservices/GetAssociationLnObjects.md) request.

#### SmartMeteringConfiguration
- **[SetSpecialDays](./smartmeteringwebservices/SetSpecialDays.md)** is a request to set a dayId profile and its tariffs for a specific date on a device.
- **[GetSetSpecialDaysResponse](./smartmeteringwebservices/GetSetSpecialDaysResponse.md)** is a request which returns the response from the [SetSpecialDays](./smartmeteringwebservices/SetSpecialDays.md) request.
- **[SetConfigurationObject](./smartmeteringwebservices/SetConfigurationObject.md)** is a request to set ConfigurationObject settings on a device to specify behaviour and connection options. 
- **[GetSetConfigurationObjectResponse](./smartmeteringwebservices/GetSetConfigurationObjectResponse.md)** is a request which returns the response from the [SetConfigurationObject](./smartmeteringwebservices/SetConfigurationObject.md) request.
- **[SetPushSetupAlarm](./smartmeteringwebservices/SetPushSetupAlarm.md)** is a request that pushes received alarm messages to OSGP.
- **[GetSetPushSetupAlarmResponse](./smartmeteringwebservices/GetSetPushSetupAlarmResponse.md)** is a request which returns the response from the [SetPushSetupAlarm](./smartmeteringwebservices/SetPushSetupAlarm.md) request.
- **[SetPushSetupSms](./smartmeteringwebservices/SetPushSetupSms.md)** is a request to set an endpoint in a device which tells the device where to connect to when it is waked up.
- **[GetSetPushSetupSmsResponse](./smartmeteringwebservices/GetSetPushSetupSmsResponse.md)** is a request which returns the response from the [SetPushSetupSms](./smartmeteringwebservices/SetPushSetupSms.md) request.
- **[SetAlarmNotifications](./smartmeteringwebservices/SetAlarmNotifications.md)** is a request to set the types of alarmnotifications that must be notified from the device when they occur.
- **[GetSetAlarmNotificationsResponse](./smartmeteringwebservices/GetSetAlarmNotificationsResponse.md)** is a request which returns the response from the [SetAlarmNotifications](./smartmeteringwebservices/SetAlarmNotifications.md) request.
- **[SetEncryptionKeyExchangeOnGMeter](./smartmeteringwebservices/SetEncryptionKeyExchangeOnGMeter.md)** is a request to transfer and set a G-meter key on a device.
- **[GetSetEncryptionKeyExchangeOnGMeterResponse](./smartmeteringwebservices/GetSetEncryptionKeyExchangeOnGMeterResponse.md)** is a request which returns the response from the [SetEncryptionKeyExchangeOnGMeter](./smartmeteringwebservices/SetEncryptionKeyExchangeOnGMeter.md) request.
- **[SetActivityCalendar](./smartmeteringwebservices/SetActivityCalendar.md)** is a request to set several parameters on an E-meter such as tariffs per day in a weekprofile.
- **[GetSetActivityCalendarResponse](./smartmeteringwebservices/GetSetActivityCalendarResponse.md)** is a request which returns the response from the [SetActivityCalendar](./smartmeteringwebservices/SetActivityCalendar.md) request.
- **[GetAdministrativeStatus](./smartmeteringwebservices/GetAdministrativeStatus.md)** is a request to retrieve the current AdministrativeStatus setting.
- **[GetGetAdministrativeStatusResponse](./smartmeteringwebservices/GetGetAdministrativeStatusResponse.md)** is a request which returns the response from the [GetAdministrativeStatus](./smartmeteringwebservices/GetAdministrativeStatus.md) request.
- **[SetAdministrativeStatus](./smartmeteringwebservices/SetAdministrativeStatus.md)** is a request to set the AdministrativeStatus.
- **[GetSetAdministrativeStatusResponse](./smartmeteringwebservices/GetSetAdministrativeStatusResponse.md)** is a request which returns the response from the [SetAdministrativeStatus](./smartmeteringwebservices/SetAdministrativeStatus.md) request.
- **[GetFirmwareVersion](./smartmeteringwebservices/GetFirmwareVersion.md)** is a request to retrieve the firmwareversion(s).
- **[GetGetFirmwareVersionResponse](./smartmeteringwebservices/GetGetFirmwareVersionResponse.md)** is a request which returns the response from the [GetFirmwareVersionRequest](./smartmeteringwebservices/GetFirmwareVersion.md).
- **[ReplaceKeys](./smartmeteringwebservices/ReplaceKeys.md)** is a request to change the keys on a E-meter.
- **[GetReplaceKeysResponse](./smartmeteringwebservices/GetReplaceKeysResponse.md)** is a request which returns the response from the [ReplaceKeys](./smartmeteringwebservices/ReplaceKeys.md) request.

#### SmartMeteringInstallation
- **[AddDevice](./smartmeteringwebservices/AddDevice.md)** is a request to add a device to the OSGP database.
- **[GetAddDeviceResponse](./smartmeteringwebservices/GetAddDeviceResponse.md)** is a request which returns the response from the [AddDevice](./smartmeteringwebservices/AddDevice.md) request.
- **[CoupleMbusDevice](./smartmeteringwebservices/CoupleMbusDevice.md)** is a request to couple a M-Bus device to a gateway.
- **[GetCoupleMbusDeviceResponse](./smartmeteringwebservices/GetCoupleMbusDeviceResponse.md)** is a request which returns the response from the [CoupleMbusDevice](./smartmeteringwebservices/CoupleMbusDevice.md) request.
- **[DeCoupleMbusDevice](./smartmeteringwebservices/DeCoupleMbusDevice.md)** is a request to decouple an M-Bus device from a gateway.
- **[GetDeCoupleMbusDeviceResponse](./smartmeteringwebservices/GetDeCoupleMbusDeviceResponse.md)** is a request which returns the response from the [DeCoupleMbusDevice](./smartmeteringwebservices/DeCoupleMbusDevice.md) request.

#### SmartMeteringManagement
- **[FindEvents](./smartmeteringwebservices/FindEvents.md)** is a request to retrieve events logging from a device.
- **[GetFindEventsResponse](./smartmeteringwebservices/GetFindEventsResponse.md)** is a request which returns the response from the [FindEvents](./smartmeteringwebservices/FindEvents.md) request.
- **[GetDevices](./smartmeteringwebservices/GetDevices.md)** is a request to retrieve the last known relay statuses for a group of devices.

#### SmartMeteringMonitoring
- **[GetActualMeterReads](./smartmeteringwebservices/GetActualMeterReads.md)** is a request to retrieve the actual meter reads from an E-meter.
- **[GetActualMeterReadsResponse](./smartmeteringwebservices/GetActualMeterReadsResponse.md)** is a request which returns the response from the [ActualMeterReads](./smartmeteringwebservices/GetActualMeterReads.md) request.
- **[GetActualMeterReadsGas](./smartmeteringwebservices/GetActualMeterReadsGas.md)** is a request to retrieve the actual meter reads from a G-meter.
- **[GetActualMeterReadsGasResponse](./smartmeteringwebservices/GetActualMeterReadsGasResponse.md)** is a request which returns the response from the [ActualMeterReadsGas](./smartmeteringwebservices/ActualMeterReadsGas.md) request.
- **[GetPeriodicMeterReads](./smartmeteringwebservices/GetPeriodicMeterReads.md)** is a request to retrieve the periodic meter reads from an E-meter.
- **[GetPeriodicMeterReadsResponse](./smartmeteringwebservices/GetPeriodicMeterReadsResponse.md)** is a request which returns the response from the [PeriodicMeterReads](./smartmeteringwebservices/GetPeriodicMeterReads.md) request.
- **[GetPeriodicMeterReadsGas](./smartmeteringwebservices/GetPeriodicMeterReadsGas.md)** is a request to retrieve the periodic meter reads from a G-meter.
- **[GetPeriodicMeterReadsGasResponse](./smartmeteringwebservices/GetPeriodicMeterReadsGasResponse.md)** is a request which returns the response from the [PeriodicMeterReadsGas](./smartmeteringwebservices/GetPeriodicMeterReadsGas.md) request.
- **[ReadAlarmRegister](./smartmeteringwebservices/ReadAlarmRegister.md)** is a request to read the alarm register from a device.
- **[GetReadAlarmRegisterResponse](./smartmeteringwebservices/GetReadAlarmRegisterResponse.md)** is a request which returns the response from the [ReadAlarmRegister](./smartmeteringwebservices/ReadAlarmRegister.md) request.
- **[RetrievePushNotificationAlarm](./smartmeteringwebservices/RetrievePushNotificationAlarm.md)** is a request to push retrieved alarm notifications to OSGP.

#### SmartMeteringNotification
- **[SendNotification](./smartmeteringwebservices/SendNotification.md)** is a request to let Webapps know there is a result ready to retrieve from the platform.

#### SmartMeteringBundle
- **[Bundle](./smartmeteringwebservices/Bundle.md)**  is a special request in which one or more single request(s) to a specific device can be bundled.
- **[GetBundleResponse](./smartmeteringwebservices/Bundle.md)** is a request which gets the response from the [Bundle](./smartmeteringwebservices/Bundle.md) request.

All request sent to this device make use of one communication channel, which may improve performance considerably.

### WSDL's
* [SmartMetering WSDL's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering)
* [PublicLighting XSD schema's](https://github.com/OSGP/Platform/tree/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas)
