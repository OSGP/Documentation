## SmartMetering Documentation (Beta version)

This chapter describes the SmartMetering domain including the web services. Currently the web services of the beta version are described, since the web services have not yet officially been released.
Information on the DLMS device simulator can be found in the [DLMS protocol section](../Protocols/DLMS/Devicesimulator.md)

### Scope
The goal of this domain is to read and manage millions of smart meters. This includes smart meter installation, firmware updates, smart meter removal, read smart meter values, time synchronisation, etc.
Everything that is needed to professionally manage millions of smart meters is or can be included in this domain.

### Features

Currently, the following Smart Metering features are available within the open smart grid platform:

- Add smart meter to the platform, so the device is known and additional actions can be performed for the device
- Process shipment file, which adds several smart meters to the platform along with all needed information
- Synchronize time between smart meters and head-end system, in case the smart meter adjusts its time, some events will be logged
- Retrieve events from the smart meter, several event logs are available
- Retrieve periodic meter reads from the smart meter

### Generic functionality

- **[bypass retry](./smartmeteringwebservices/bypassretry.md)** requests can be given the flag 'bypass retry'. Which means that a request will not be retried in case of an error.
- **[priority](./smartmeteringwebservices/priority.md)** requests can be given a priority from 0 to 9, default is 4. Higher values causes messages to be processed faster.
- **[scheduling](./smartmeteringwebservices/scheduling.md)** requests can be scheduled for a certain time.
- **[bundling](./smartmeteringwebservices/bundling.md)** requests can be combined in a [Bundle](./smartmeteringwebservices/Bundle.md).


### Messages

#### SmartMeteringAdHoc
- **[SynchronizeTime](./smartmeteringwebservices/SynchronizeTime.md)** is a request to synchronize the date and time on a device. The date and time are retrieved from the server and sent to the device.
- **[GetSynchronizeTimeResponse](./smartmeteringwebservices/GetSynchronizeTimeResponse.md)** is a request which returns the response from the [SynchronizeTime](./smartmeteringwebservices/SynchronizeTime.md) request.
- **[RetrieveAllAttributeValues](./smartmeteringwebservices/RetrieveAllAttributeValues.md)** is a request to obtain all the attributes of the whole tree of objects from an E-meter.
- **[GetRetrieveAllAttributeValuesResponse](./smartmeteringwebservices/GetRetrieveAllAttributeValuesResponse.md)** is a request which returns the response from the [RetrieveAllAttributeValues](./smartmeteringwebservices/RetrieveAllAttributeValues.md) request.
- **[GetSpecificAttributeValue](./smartmeteringwebservices/GetSpecificAttributeValue.md)** is a request to obtain a specific attribute value from an ObisCode from an E-meter.
- **[GetSpecificAttributeValueResponse](./smartmeteringwebservices/GetSpecificAttributeValueResponse.md)** is a request which returns the response from the [GetSpecificAttributeValue](./smartmeteringwebservices/GetSpecificAttributeValue.md) request.
- **[GetAssociationLnObjects](./smartmeteringwebservices/GetAssociationLnObjects.md)** is a request to get the associated ln objects.
- **[GetGetAssociationLnObjectsResponse](./smartmeteringwebservices/GetGetAssociationLnObjectsResponse.md)** is a request which gets the response from the [GetAssociationLnObjects](./smartmeteringwebservices/GetAssociationLnObjects.md) request.
- **[ScanMbusChannels](./smartmeteringwebservices/ScanMbusChannels.md)** is a request to get the M-Bus attribute values for all four channels from an E-meter.
- **[ScanMbusChannelsResponse](./smartmeteringwebservices/ScanMbusChannelsResponse.md)** is a request which returns the response from the [ScanMbusChannels](./smartmeteringwebservices/ScanMbusChannels.md) request.

#### SmartMeteringConfiguration
- **[SetSpecialDays](./smartmeteringwebservices/SetSpecialDays.md)** is a request to set a dayId profile and its tariffs for a specific date on a device.
- **[GetSetSpecialDaysResponse](./smartmeteringwebservices/GetSetSpecialDaysResponse.md)** is a request which returns the response from the [SetSpecialDays](./smartmeteringwebservices/SetSpecialDays.md) request.
- **[SetConfigurationObject](./smartmeteringwebservices/SetConfigurationObject.md)** is a request to set ConfigurationObject settings on a device to specify behaviour and connection options.
- **[GetSetConfigurationObjectResponse](./smartmeteringwebservices/GetSetConfigurationObjectResponse.md)** is a request which returns the response from the [SetConfigurationObject](./smartmeteringwebservices/SetConfigurationObject.md) request.
- **[GetConfigurationObject](./smartmeteringwebservices/GetConfigurationObject.md)** is a request to retrieve a ConfigurationObject from a device.
- **[GetConfigurationObjectResponse](./smartmeteringwebservices/GetConfigurationObjectResponse.md)** is a request which returns the response, a ConfigurationObject, from the [GetConfigurationObject](./smartmeteringwebservices/GetConfigurationObject.md) request.
- **[SetPushSetupAlarm](./smartmeteringwebservices/SetPushSetupAlarm.md)** is a request that pushes received alarm messages to OSGP.
- **[GetSetPushSetupAlarmResponse](./smartmeteringwebservices/GetSetPushSetupAlarmResponse.md)** is a request which returns the response from the [SetPushSetupAlarm](./smartmeteringwebservices/SetPushSetupAlarm.md) request.
- **[SetPushSetupSms](./smartmeteringwebservices/SetPushSetupSms.md)** is a request to set an endpoint in a device which tells the device where to connect to when it is waked up.
- **[GetSetPushSetupSmsResponse](./smartmeteringwebservices/GetSetPushSetupSmsResponse.md)** is a request which returns the response from the [SetPushSetupSms](./smartmeteringwebservices/SetPushSetupSms.md) request.
- **[SetAlarmNotifications](./smartmeteringwebservices/SetAlarmNotifications.md)** is a request to set the types of alarm notifications that must be notified from the device when they occur.
- **[GetSetAlarmNotificationsResponse](./smartmeteringwebservices/GetSetAlarmNotificationsResponse.md)** is a request which returns the response from the [SetAlarmNotifications](./smartmeteringwebservices/SetAlarmNotifications.md) request.
- **[SetEncryptionKeyExchangeOnGMeter](./smartmeteringwebservices/SetEncryptionKeyExchangeOnGMeter.md)** is a request to transfer and set a G-meter key on a device.
- **[GetSetEncryptionKeyExchangeOnGMeterResponse](./smartmeteringwebservices/GetSetEncryptionKeyExchangeOnGMeterResponse.md)** is a request which returns the response from the [SetEncryptionKeyExchangeOnGMeter](./smartmeteringwebservices/SetEncryptionKeyExchangeOnGMeter.md) request.
- **[GetMbusEncryptionKeyStatus](./smartmeteringwebservices/GetMbusEncryptionKeyStatus.md)** is a request to retrieve the encryption key status for a M-Bus device.
- **[GetGetMbusEncryptionKeyStatusResponse](./smartmeteringwebservices/GetGetMbusEncryptionKeyStatusResponse.md)** is a request which returns the response from the [GetMbusEncryptionKeyStatus](./smartmeteringwebservices/GetMbusEncryptionKeyStatus.md) request.
- **[SetActivityCalendar](./smartmeteringwebservices/SetActivityCalendar.md)** is a request to set several parameters on an E-meter such as tariffs per day in a week profile.
- **[GetSetActivityCalendarResponse](./smartmeteringwebservices/GetSetActivityCalendarResponse.md)** is a request which returns the response from the [SetActivityCalendar](./smartmeteringwebservices/SetActivityCalendar.md) request.
- **[GetAdministrativeStatus](./smartmeteringwebservices/GetAdministrativeStatus.md)** is a request to retrieve the current AdministrativeStatus setting.
- **[GetGetAdministrativeStatusResponse](./smartmeteringwebservices/GetGetAdministrativeStatusResponse.md)** is a request which returns the response from the [GetAdministrativeStatus](./smartmeteringwebservices/GetAdministrativeStatus.md) request.
- **[SetAdministrativeStatus](./smartmeteringwebservices/SetAdministrativeStatus.md)** is a request to set the AdministrativeStatus.
- **[GetSetAdministrativeStatusResponse](./smartmeteringwebservices/GetSetAdministrativeStatusResponse.md)** is a request which returns the response from the [SetAdministrativeStatus](./smartmeteringwebservices/SetAdministrativeStatus.md) request.
- **[GetFirmwareVersion](./smartmeteringwebservices/GetFirmwareVersion.md)** is a request to retrieve the firmware version(s).
- **[GetGetFirmwareVersionResponse](./smartmeteringwebservices/GetGetFirmwareVersionResponse.md)** is a request which returns the response from the [GetFirmwareVersionRequest](./smartmeteringwebservices/GetFirmwareVersion.md).
- **[ReplaceKeys](./smartmeteringwebservices/ReplaceKeys.md)** is a request to change the keys on a E-meter.
- **[GetReplaceKeysResponse](./smartmeteringwebservices/GetReplaceKeysResponse.md)** is a request which returns the response from the [ReplaceKeys](./smartmeteringwebservices/ReplaceKeys.md) request.
- **[GetMbusEncryptionKeyStatusByChannel](./smartmeteringwebservices/GetMbusEncryptionKeyStatusByChannel.md)** is a request to get the M-Bus encryption key status from an M-Bus device by using the E-meter device identification and channel from the G-meter.
- **[GetMbusEncryptionKeyStatusByChannelResponse](./smartmeteringwebservices/GetMbusEncryptionKeyStatusByChannelResponse.md)** is a request which returns the response from the [GetMbusEncryptionKeyStatusByChannel](./smartmeteringwebservices/GetMbusEncryptionKeyStatusByChannel.md) request.
- **[SetMbusUserKeyByChannel](./smartmeteringwebservices/SetMbusUserKeyByChannel.md)** is a request to set the M-Bus encryption key on an M-Bus device by using the E-meter device identification and channel from the G-meter.
- **[SetMbusUserKeyByChannelResponse](./smartmeteringwebservices/SetMbusUserKeyByChannelResponse.md)** is a request which returns the response from the [SetMbusUserKeyByChannel](./smartmeteringwebservices/SetMbusUserKeyByChannel.md) request.
- **[UpdateFirmware](./smartmeteringwebservices/UpdateFirmware.md)** is a request to update the firmware module(s) on a device.
- **[GetUpdateFirmwareResponse](./smartmeteringwebservices/GetUpdateFirmwareResponse.md)** is a request which returns the response from the [UpdateFirmware](./smartmeteringwebservices/UpdateFirmware.md) request.
- **[GenerateAndReplaceKeys](./smartmeteringwebservices/GenerateAndReplaceKeys.md)** is a request to generate and set the encryption and authentication key on a device.
- **[GenerateAndReplaceKeysResponse](./smartmeteringwebservices/GenerateAndReplaceKeysResponse.md)** is a request which returns the response from the [GenerateAndReplaceKeys](./smartmeteringwebservices/GenerateAndReplaceKeys.md) request.
- **[SetClockConfiguration](./smartmeteringwebservices/SetClockConfiguration.md)** is a request to set the clock configuration on a device.
- **[GetSetClockConfigurationResponse](./smartmeteringwebservices/GetSetClockConfigurationResponse.md)** is a request which returns the response from the [SetClockConfiguration](./smartmeteringwebservices/SetClockConfiguration.md) request.
- **[ConfigureDefinableLoadProfile](./smartmeteringwebservices/ConfigureDefinableLoadProfile.md)** is a request to configure the load profile on a device.
- **[GetConfigureDefinableLoadProfileResponse](./smartmeteringwebservices/GetConfigureDefinableLoadProfileResponse.md)** is a request which returns the response from the [ConfigureDefinableLoadProfile](./smartmeteringwebservices/ConfigureDefinableLoadProfile.md) request.

#### SmartMeteringInstallation
- **[AddDevice](./smartmeteringwebservices/AddDevice.md)** is a request to add a device to the OSGP database.
- **[GetAddDeviceResponse](./smartmeteringwebservices/GetAddDeviceResponse.md)** is a request which returns the response from the [AddDevice](./smartmeteringwebservices/AddDevice.md) request.
- **[CoupleMbusDevice](./smartmeteringwebservices/CoupleMbusDevice.md)** is a request to couple a M-Bus device to a gateway.
- **[GetCoupleMbusDeviceResponse](./smartmeteringwebservices/GetCoupleMbusDeviceResponse.md)** is a request which returns the response from the [CoupleMbusDevice](./smartmeteringwebservices/CoupleMbusDevice.md) request.
- **[DeCoupleMbusDevice](./smartmeteringwebservices/DeCoupleMbusDevice.md)** is a request to decouple an M-Bus device from a gateway.
- **[GetDeCoupleMbusDeviceResponse](./smartmeteringwebservices/GetDeCoupleMbusDeviceResponse.md)** is a request which returns the response from the [DeCoupleMbusDevice](./smartmeteringwebservices/DeCoupleMbusDevice.md) request.
- **[CoupleMbusDeviceByChannel](./smartmeteringwebservices/CoupleMbusDeviceByChannel.md)** is a request to couple a M-Bus device to a gateway.
- **[GetCoupleMbusDeviceByChannelResponse](./smartmeteringwebservices/GetCoupleMbusDeviceByChannelResponse.md)** is a request which returns the response from the [CoupleMbusDeviceByChannel](./smartmeteringwebservices/CoupleMbusDeviceByChannel.md) request.

#### SmartMeteringManagement
- **[FindEvents](./smartmeteringwebservices/FindEvents.md)** is a request to retrieve events logging from a device.
- **[GetFindEventsResponse](./smartmeteringwebservices/GetFindEventsResponse.md)** is a request which returns the response from the [FindEvents](./smartmeteringwebservices/FindEvents.md) request.
- **[GetDevices](./smartmeteringwebservices/GetDevices.md)** is a request to retrieve the last known relay statuses for a group of devices.
- **[EnableDebugging](./smartmeteringwebservices/EnableDebugging.md)** is a request to enable debug logging for a device.
- **[GetEnableDebuggingResponse](./smartmeteringwebservices/GetEnableDebuggingResponse.md)** is a request which returns the response from the [EnableDebugging](./smartmeteringwebservices/EnableDebugging.md) request.
- **[DisableDebugging](./smartmeteringwebservices/DisableDebugging.md)** is a request to disable debug logging for a device.
- **[GetDisableDebuggingResponse](./smartmeteringwebservices/GetDisableDebuggingResponse.md)** is a request which returns the response from the [DisableDebugging](./smartmeteringwebservices/DisableDebugging.md) request.
- **[FindMessageLogs](./smartmeteringwebservices/FindMessageLogs.md)** is a request to read the debug logging from a device.
- **[GetFindMessageLogsResponse](./smartmeteringwebservices/GetFindMessageLogsResponse.md)** is a request which returns the response from the [FindMessageLogs](./smartmeteringwebservices/FindMessageLogs.md) request.
- **[SetDeviceCommunicationSettings](./smartmeteringwebservices/SetDeviceCommunicationSettings.md)** is a request to set the OSGP device communication settings for a specific device.
- **[SetDeviceCommunicationSettingsResponse](./smartmeteringwebservices/SetDeviceCommunicationSettingsResponse.md)** is a request which returns the response from the [SetDeviceCommunicationSettings](./smartmeteringwebservices/SetDeviceCommunicationSettings.md) request.
- **[SetDeviceLifecycleStatusByChannel](./smartmeteringwebservices/SetDeviceLifecycleStatusByChannel.md)** is a request to set the lifecycle status from a device.
- **[SetDeviceLifecycleStatusByChannelResponse](./smartmeteringwebservices/SetDeviceLifecycleStatusByChannelResponse.md)** is a request which returns the response from the [SetDeviceLifecycleStatusByChannel](./smartmeteringwebservices/SetDeviceLifecycleStatusByChannel.md) request.

#### SmartMeteringMonitoring
- **[GetActualMeterReads](./smartmeteringwebservices/GetActualMeterReads.md)** is a request to retrieve the actual meter reads from an E-meter.
- **[GetActualMeterReadsResponse](./smartmeteringwebservices/GetActualMeterReadsResponse.md)** is a request which returns the response from the [ActualMeterReads](./smartmeteringwebservices/GetActualMeterReads.md) request.
- **[GetActualMeterReadsGas](./smartmeteringwebservices/GetActualMeterReadsGas.md)** is a request to retrieve the actual meter reads from a G-meter.
- **[GetActualMeterReadsGasResponse](./smartmeteringwebservices/GetActualMeterReadsGasResponse.md)** is a request which returns the response from the [ActualMeterReadsGas](./smartmeteringwebservices/ActualMeterReadsGas.md) request.
- **[GetPeriodicMeterReads](./smartmeteringwebservices/GetPeriodicMeterReads.md)** is a request to retrieve the periodic meter reads from an E-meter.
- **[GetPeriodicMeterReadsResponse](./smartmeteringwebservices/GetPeriodicMeterReadsResponse.md)** is a request which returns the response from the [PeriodicMeterReads](./smartmeteringwebservices/GetPeriodicMeterReads.md) request.
- **[GetPeriodicMeterReadsGas](./smartmeteringwebservices/GetPeriodicMeterReadsGas.md)** is a request to retrieve the periodic meter reads from a G-meter.
- **[GetPeriodicMeterReadsGasResponse](./smartmeteringwebservices/GetPeriodicMeterReadsGasResponse.md)** is a request which returns the response from the [PeriodicMeterReadsGas](./smartmeteringwebservices/GetPeriodicMeterReadsGas.md) request.
- **[GetProfileGenericData](./smartmeteringwebservices/GetProfileGenericData.md)** is a request to retrieve any Profile Generic data from an E-meter.
- **[GetProfileGenericDataResponse](./smartmeteringwebservices/GetProfileGenericDataResponse.md)** is a request which returns the response from the [ProfileGenericData](./smartmeteringwebservices/GetProfileGenericData.md) request.
- **[ReadAlarmRegister](./smartmeteringwebservices/ReadAlarmRegister.md)** is a request to read the alarm register from a device.
- **[GetReadAlarmRegisterResponse](./smartmeteringwebservices/GetReadAlarmRegisterResponse.md)** is a request which returns the response from the [ReadAlarmRegister](./smartmeteringwebservices/ReadAlarmRegister.md) request.
- **[RetrievePushNotificationAlarm](./smartmeteringwebservices/RetrievePushNotificationAlarm.md)** is a request to push retrieved alarm notifications to OSGP.
- **[ClearAlarmRegister](./smartmeteringwebservices/ClearAlarmRegister.md)** is a request to clear the Alarm register flags for pushed event notifications.
- **[ClearAlarmRegisterResponse](./smartmeteringwebservices/ClearAlarmRegisterResponse.md)** is a request which returns the response from the [ClearAlarmRegister](./smartmeteringwebservices/ClearAlarmRegister.md) request.

#### SmartMeteringNotification
- **[SendNotification](./smartmeteringwebservices/SendNotification.md)** is a request to let Webapps know there is a result ready to retrieve from the platform.

#### SmartMeteringBundle
- **[Bundle](./smartmeteringwebservices/Bundle.md)**  is a special request in which one or more single request(s) to a specific device can be bundled.
- **[GetBundleResponse](./smartmeteringwebservices/Bundle.md)** is a request which gets the response from the [Bundle](./smartmeteringwebservices/Bundle.md) request.

All request sent to this device make use of one communication channel, which may improve performance considerably.

### WSDL's
* [SmartMetering WSDL's](https://github.com/OSGP/Shared/tree/development/osgp-ws-smartmetering/src/main/resources)
* [SmartMetering XSD schema's](https://github.com/OSGP/Shared/tree/development/osgp-ws-smartmetering/src/main/resources/schemas)
