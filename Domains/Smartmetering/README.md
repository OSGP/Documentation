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

- **[bypass retry](./smartmeteringwebservices/bypassretry.md)** operations can be given the flag 'bypass retry'. Which means that an operation will not be retried in case of an error.
- **[priority](./smartmeteringwebservices/priority.md)** operations can be given a priority from 0 to 9, default is 4. Higher values causes messages to be processed faster.
- **[scheduling](./smartmeteringwebservices/scheduling.md)** operations can be scheduled for a certain time.
- **[bundling](./smartmeteringwebservices/bundling.md)** operations can be combined in a [Bundle](./smartmeteringwebservices/Bundle.md).


### Messages

#### SmartMeteringAdHoc
- **[SynchronizeTime](./smartmeteringwebservices/SynchronizeTime.md)** is an operation to synchronize the date and time on a device. The date and time are retrieved from the server and sent to the device.
- **[GetSynchronizeTimeResponse](./smartmeteringwebservices/GetSynchronizeTimeResponse.md)** is an operation which returns the response from the [SynchronizeTime](./smartmeteringwebservices/SynchronizeTime.md) operation.
- **[RetrieveAllAttributeValues](./smartmeteringwebservices/RetrieveAllAttributeValues.md)** is an operation to obtain all the attributes of the whole tree of objects from an E-meter.
- **[GetRetrieveAllAttributeValuesResponse](./smartmeteringwebservices/GetRetrieveAllAttributeValuesResponse.md)** is an operation which returns the response from the [RetrieveAllAttributeValues](./smartmeteringwebservices/RetrieveAllAttributeValues.md) operation.
- **[GetSpecificAttributeValue](./smartmeteringwebservices/GetSpecificAttributeValue.md)** is an operation to obtain a specific attribute value from an ObisCode from an E-meter.
- **[GetSpecificAttributeValueResponse](./smartmeteringwebservices/GetSpecificAttributeValueResponse.md)** is an operation which returns the response from the [GetSpecificAttributeValue](./smartmeteringwebservices/GetSpecificAttributeValue.md) operation.
- **[GetAssociationLnObjects](./smartmeteringwebservices/GetAssociationLnObjects.md)** is an operation to get the associated ln objects.
- **[GetGetAssociationLnObjectsResponse](./smartmeteringwebservices/GetGetAssociationLnObjectsResponse.md)** is an operation which gets the response from the [GetAssociationLnObjects](./smartmeteringwebservices/GetAssociationLnObjects.md) operation.
- **[ScanMbusChannels](./smartmeteringwebservices/ScanMbusChannels.md)** is an operation to get the M-Bus attribute values for all four channels from an E-meter.
- **[ScanMbusChannelsResponse](./smartmeteringwebservices/ScanMbusChannelsResponse.md)** is an operation which returns the response from the [ScanMbusChannels](./smartmeteringwebservices/ScanMbusChannels.md) operation.

#### SmartMeteringConfiguration
- **[SetSpecialDays](./smartmeteringwebservices/SetSpecialDays.md)** is an operation to set a dayId profile and its tariffs for a specific date on a device.
- **[GetSetSpecialDaysResponse](./smartmeteringwebservices/GetSetSpecialDaysResponse.md)** is an operation which returns the response from the [SetSpecialDays](./smartmeteringwebservices/SetSpecialDays.md) operation.
- **[SetConfigurationObject](./smartmeteringwebservices/SetConfigurationObject.md)** is an operation to set ConfigurationObject settings on a device to specify behaviour and connection options.
- **[GetSetConfigurationObjectResponse](./smartmeteringwebservices/GetSetConfigurationObjectResponse.md)** is an operation which returns the response from the [SetConfigurationObject](./smartmeteringwebservices/SetConfigurationObject.md) operation.
- **[GetConfigurationObject](./smartmeteringwebservices/GetConfigurationObject.md)** is an operation to retrieve a ConfigurationObject from a device.
- **[GetConfigurationObjectResponse](./smartmeteringwebservices/GetConfigurationObjectResponse.md)** is an operation which returns the response, a ConfigurationObject, from the [GetConfigurationObject](./smartmeteringwebservices/GetConfigurationObject.md) operation.
- **[SetPushSetupAlarm](./smartmeteringwebservices/SetPushSetupAlarm.md)** is an operation that pushes received alarm messages to OSGP.
- **[GetSetPushSetupAlarmResponse](./smartmeteringwebservices/GetSetPushSetupAlarmResponse.md)** is an operation which returns the response from the [SetPushSetupAlarm](./smartmeteringwebservices/SetPushSetupAlarm.md) operation.
- **[SetPushSetupSms](./smartmeteringwebservices/SetPushSetupSms.md)** is an operation to set an endpoint in a device which tells the device where to connect to when it is waked up.
- **[GetSetPushSetupSmsResponse](./smartmeteringwebservices/GetSetPushSetupSmsResponse.md)** is an operation which returns the response from the [SetPushSetupSms](./smartmeteringwebservices/SetPushSetupSms.md) operation.
- **[SetAlarmNotifications](./smartmeteringwebservices/SetAlarmNotifications.md)** is an operation to set the types of alarm notifications that must be notified from the device when they occur.
- **[GetSetAlarmNotificationsResponse](./smartmeteringwebservices/GetSetAlarmNotificationsResponse.md)** is an operation which returns the response from the [SetAlarmNotifications](./smartmeteringwebservices/SetAlarmNotifications.md) operation.
- **[SetEncryptionKeyExchangeOnGMeter](./smartmeteringwebservices/SetEncryptionKeyExchangeOnGMeter.md)** is an operation to transfer and set a G-meter key on a device.
- **[GetSetEncryptionKeyExchangeOnGMeterResponse](./smartmeteringwebservices/GetSetEncryptionKeyExchangeOnGMeterResponse.md)** is an operation which returns the response from the [SetEncryptionKeyExchangeOnGMeter](./smartmeteringwebservices/SetEncryptionKeyExchangeOnGMeter.md) operation.
- **[SetMbusUserKeyByChannel](./smartmeteringwebservices/SetMbusUserKeyByChannel.md)** is an operation to set the M-Bus encryption key on an M-Bus device by using the E-meter device identification and channel from the G-meter.
- **[SetMbusUserKeyByChannelResponse](./smartmeteringwebservices/SetMbusUserKeyByChannelResponse.md)** is an operation which returns the response from the [SetMbusUserKeyByChannel](./smartmeteringwebservices/SetMbusUserKeyByChannel.md) operation.
- **[GetMbusEncryptionKeyStatus](./smartmeteringwebservices/GetMbusEncryptionKeyStatus.md)** is an operation to retrieve the encryption key status for a M-Bus device.
- **[GetGetMbusEncryptionKeyStatusResponse](./smartmeteringwebservices/GetGetMbusEncryptionKeyStatusResponse.md)** is an operation which returns the response from the [GetMbusEncryptionKeyStatus](./smartmeteringwebservices/GetMbusEncryptionKeyStatus.md) operation.
- **[GetMbusEncryptionKeyStatusByChannel](./smartmeteringwebservices/GetMbusEncryptionKeyStatusByChannel.md)** is an operation to get the M-Bus encryption key status from an M-Bus device by using the E-meter device identification and channel from the G-meter.
- **[GetMbusEncryptionKeyStatusByChannelResponse](./smartmeteringwebservices/GetMbusEncryptionKeyStatusByChannelResponse.md)** is an operation which returns the response from the [GetMbusEncryptionKeyStatusByChannel](./smartmeteringwebservices/GetMbusEncryptionKeyStatusByChannel.md) operation.
- **[SetActivityCalendar](./smartmeteringwebservices/SetActivityCalendar.md)** is an operation to set several parameters on an E-meter such as tariffs per day in a week profile.
- **[GetSetActivityCalendarResponse](./smartmeteringwebservices/GetSetActivityCalendarResponse.md)** is an operation which returns the response from the [SetActivityCalendar](./smartmeteringwebservices/SetActivityCalendar.md) operation.
- **[GetAdministrativeStatus](./smartmeteringwebservices/GetAdministrativeStatus.md)** is an operation to retrieve the current AdministrativeStatus setting.
- **[GetGetAdministrativeStatusResponse](./smartmeteringwebservices/GetGetAdministrativeStatusResponse.md)** is an operation which returns the response from the [GetAdministrativeStatus](./smartmeteringwebservices/GetAdministrativeStatus.md) operation.
- **[SetAdministrativeStatus](./smartmeteringwebservices/SetAdministrativeStatus.md)** is an operation to set the AdministrativeStatus.
- **[GetSetAdministrativeStatusResponse](./smartmeteringwebservices/GetSetAdministrativeStatusResponse.md)** is an operation which returns the response from the [SetAdministrativeStatus](./smartmeteringwebservices/SetAdministrativeStatus.md) operation.
- **[GetFirmwareVersion](./smartmeteringwebservices/GetFirmwareVersion.md)** is an operation to retrieve the firmware version(s).
- **[GetGetFirmwareVersionResponse](./smartmeteringwebservices/GetGetFirmwareVersionResponse.md)** is an operation which returns the response from the [GetFirmwareVersionoperation](./smartmeteringwebservices/GetFirmwareVersion.md).
- **[ReplaceKeys](./smartmeteringwebservices/ReplaceKeys.md)** is an operation to change the keys on a E-meter.
- **[GetReplaceKeysResponse](./smartmeteringwebservices/GetReplaceKeysResponse.md)** is an operation which returns the response from the [ReplaceKeys](./smartmeteringwebservices/ReplaceKeys.md) operation.
- **[UpdateFirmware](./smartmeteringwebservices/UpdateFirmware.md)** is an operation to update the firmware module(s) on a device.
- **[GetUpdateFirmwareResponse](./smartmeteringwebservices/GetUpdateFirmwareResponse.md)** is an operation which returns the response from the [UpdateFirmware](./smartmeteringwebservices/UpdateFirmware.md) operation.
- **[GenerateAndReplaceKeys](./smartmeteringwebservices/GenerateAndReplaceKeys.md)** is an operation to generate and set the encryption and authentication key on a device.
- **[GenerateAndReplaceKeysResponse](./smartmeteringwebservices/GenerateAndReplaceKeysResponse.md)** is an operation which returns the response from the [GenerateAndReplaceKeys](./smartmeteringwebservices/GenerateAndReplaceKeys.md) operation.
- **[SetClockConfiguration](./smartmeteringwebservices/SetClockConfiguration.md)** is an operation to set the clock configuration on a device.
- **[GetSetClockConfigurationResponse](./smartmeteringwebservices/GetSetClockConfigurationResponse.md)** is an operation which returns the response from the [SetClockConfiguration](./smartmeteringwebservices/SetClockConfiguration.md) operation.
- **[ConfigureDefinableLoadProfile](./smartmeteringwebservices/ConfigureDefinableLoadProfile.md)** is an operation to configure the load profile on a device.
- **[GetConfigureDefinableLoadProfileResponse](./smartmeteringwebservices/GetConfigureDefinableLoadProfileResponse.md)** is an operation which returns the response from the [ConfigureDefinableLoadProfile](./smartmeteringwebservices/ConfigureDefinableLoadProfile.md) operation.

#### SmartMeteringInstallation
- **[AddDevice](./smartmeteringwebservices/AddDevice.md)** is an operation to add a device to the OSGP database.
- **[GetAddDeviceResponse](./smartmeteringwebservices/GetAddDeviceResponse.md)** is an operation which returns the response from the [AddDevice](./smartmeteringwebservices/AddDevice.md) operation.
- **[CoupleMbusDevice](./smartmeteringwebservices/CoupleMbusDevice.md)** is an operation to couple a M-Bus device to a gateway.
- **[GetCoupleMbusDeviceResponse](./smartmeteringwebservices/GetCoupleMbusDeviceResponse.md)** is an operation which returns the response from the [CoupleMbusDevice](./smartmeteringwebservices/CoupleMbusDevice.md) operation.
- **[CoupleMbusDeviceByChannel](./smartmeteringwebservices/CoupleMbusDeviceByChannel.md)** is an operation to couple a M-Bus device to a gateway.
- **[GetCoupleMbusDeviceByChannelResponse](./smartmeteringwebservices/GetCoupleMbusDeviceByChannelResponse.md)** is an operation which returns the response from the [CoupleMbusDeviceByChannel](./smartmeteringwebservices/CoupleMbusDeviceByChannel.md) operation.
- **[DeCoupleMbusDevice](./smartmeteringwebservices/DeCoupleMbusDevice.md)** is an operation to decouple an M-Bus device from a gateway.
- **[GetDeCoupleMbusDeviceResponse](./smartmeteringwebservices/GetDeCoupleMbusDeviceResponse.md)** is an operation which returns the response from the [DeCoupleMbusDevice](./smartmeteringwebservices/DeCoupleMbusDevice.md) operation.

#### SmartMeteringManagement
- **[FindEvents](./smartmeteringwebservices/FindEvents.md)** is an operation to retrieve events logging from a device.
- **[GetFindEventsResponse](./smartmeteringwebservices/GetFindEventsResponse.md)** is an operation which returns the response from the [FindEvents](./smartmeteringwebservices/FindEvents.md) operation.
- **[GetDevices](./smartmeteringwebservices/GetDevices.md)** is an operation to retrieve the last known relay statuses for a group of devices.
- **[EnableDebugging](./smartmeteringwebservices/EnableDebugging.md)** is an operation to enable debug logging for a device.
- **[GetEnableDebuggingResponse](./smartmeteringwebservices/GetEnableDebuggingResponse.md)** is an operation which returns the response from the [EnableDebugging](./smartmeteringwebservices/EnableDebugging.md) operation.
- **[DisableDebugging](./smartmeteringwebservices/DisableDebugging.md)** is an operation to disable debug logging for a device.
- **[GetDisableDebuggingResponse](./smartmeteringwebservices/GetDisableDebuggingResponse.md)** is an operation which returns the response from the [DisableDebugging](./smartmeteringwebservices/DisableDebugging.md) operation.
- **[FindMessageLogs](./smartmeteringwebservices/FindMessageLogs.md)** is an operation to read the debug logging from a device.
- **[GetFindMessageLogsResponse](./smartmeteringwebservices/GetFindMessageLogsResponse.md)** is an operation which returns the response from the [FindMessageLogs](./smartmeteringwebservices/FindMessageLogs.md) operation.
- **[SetDeviceCommunicationSettings](./smartmeteringwebservices/SetDeviceCommunicationSettings.md)** is an operation to set the OSGP device communication settings for a specific device.
- **[SetDeviceCommunicationSettingsResponse](./smartmeteringwebservices/SetDeviceCommunicationSettingsResponse.md)** is an operation which returns the response from the [SetDeviceCommunicationSettings](./smartmeteringwebservices/SetDeviceCommunicationSettings.md) operation.
- **[SetDeviceLifecycleStatusByChannel](./smartmeteringwebservices/SetDeviceLifecycleStatusByChannel.md)** is an operation to set the lifecycle status from a device.
- **[SetDeviceLifecycleStatusByChannelResponse](./smartmeteringwebservices/SetDeviceLifecycleStatusByChannelResponse.md)** is an operation which returns the response from the [SetDeviceLifecycleStatusByChannel](./smartmeteringwebservices/SetDeviceLifecycleStatusByChannel.md) operation.

#### SmartMeteringMonitoring
- **[GetActualMeterReads](./smartmeteringwebservices/GetActualMeterReads.md)** is an operation to retrieve the actual meter reads from an E-meter.
- **[GetActualMeterReadsResponse](./smartmeteringwebservices/GetActualMeterReadsResponse.md)** is an operation which returns the response from the [ActualMeterReads](./smartmeteringwebservices/GetActualMeterReads.md) operation.
- **[GetActualMeterReadsGas](./smartmeteringwebservices/GetActualMeterReadsGas.md)** is an operation to retrieve the actual meter reads from a G-meter.
- **[GetActualMeterReadsGasResponse](./smartmeteringwebservices/GetActualMeterReadsGasResponse.md)** is an operation which returns the response from the [ActualMeterReadsGas](./smartmeteringwebservices/ActualMeterReadsGas.md) operation.
- **[GetPeriodicMeterReads](./smartmeteringwebservices/GetPeriodicMeterReads.md)** is an operation to retrieve the periodic meter reads from an E-meter.
- **[GetPeriodicMeterReadsResponse](./smartmeteringwebservices/GetPeriodicMeterReadsResponse.md)** is an operation which returns the response from the [PeriodicMeterReads](./smartmeteringwebservices/GetPeriodicMeterReads.md) operation.
- **[GetPeriodicMeterReadsGas](./smartmeteringwebservices/GetPeriodicMeterReadsGas.md)** is an operation to retrieve the periodic meter reads from a G-meter.
- **[GetPeriodicMeterReadsGasResponse](./smartmeteringwebservices/GetPeriodicMeterReadsGasResponse.md)** is an operation which returns the response from the [PeriodicMeterReadsGas](./smartmeteringwebservices/GetPeriodicMeterReadsGas.md) operation.
- **[GetProfileGenericData](./smartmeteringwebservices/GetProfileGenericData.md)** is an operation to retrieve any Profile Generic data from an E-meter.
- **[GetProfileGenericDataResponse](./smartmeteringwebservices/GetProfileGenericDataResponse.md)** is an operation which returns the response from the [ProfileGenericData](./smartmeteringwebservices/GetProfileGenericData.md) operation.
- **[ReadAlarmRegister](./smartmeteringwebservices/ReadAlarmRegister.md)** is an operation to read the alarm register from a device.
- **[GetReadAlarmRegisterResponse](./smartmeteringwebservices/GetReadAlarmRegisterResponse.md)** is an operation which returns the response from the [ReadAlarmRegister](./smartmeteringwebservices/ReadAlarmRegister.md) operation.
- **[RetrievePushNotificationAlarm](./smartmeteringwebservices/RetrievePushNotificationAlarm.md)** is an operation to push retrieved alarm notifications to OSGP.
- **[ClearAlarmRegister](./smartmeteringwebservices/ClearAlarmRegister.md)** is an operation to clear the Alarm register flags for pushed event notifications.
- **[ClearAlarmRegisterResponse](./smartmeteringwebservices/ClearAlarmRegisterResponse.md)** is an operation which returns the response from the [ClearAlarmRegister](./smartmeteringwebservices/ClearAlarmRegister.md) operation.

#### DeviceManagement
- **[SetDeviceLifecycleStatus](./smartmeteringwebservices/SetDeviceLifecycleStatus.md)** is an operation to set the device lifecycle status of a device.
- **[SetDeviceLifecycleStatusResponse](./smartmeteringwebservices/SetDeviceLifecycleStatusResponse.md)** is an operation which returns the response from the [SetDeviceLifecycleStatus](./smartmeteringwebservices/SetDeviceLifecycleStatus.md) operation.

#### SmartMeteringNotification
- **[SendNotification](./smartmeteringwebservices/SendNotification.md)** is an operation to let Webapps know there is a result ready to retrieve from the platform.

#### SmartMeteringBundle
- **[Bundle](./smartmeteringwebservices/Bundle.md)**  is a special operation in which one or more single operation(s) to a specific device can be bundled.
- **[GetBundleResponse](./smartmeteringwebservices/Bundle.md)** is an operation which gets the response from the [Bundle](./smartmeteringwebservices/Bundle.md) operation.

All operations sent to this device make use of one communication channel, which may improve performance considerably.

### WSDL's
* [SmartMetering WSDL's](https://github.com/OSGP/Shared/tree/development/osgp-ws-smartmetering/src/main/resources)
* [SmartMetering XSD schema's](https://github.com/OSGP/Shared/tree/development/osgp-ws-smartmetering/src/main/resources/schemas)
