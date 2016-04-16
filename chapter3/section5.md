## 3.5 SmartMetering Documentation

### 3.5.1 Messages

#### SmartMeteringAdHoc
- **[SynchronizeTime](./smartmetering/SynchronizeTime.md)** is a request to synchronize the date and time on a device. The date and time are retrieved from the server and sent to the device.
- **[GetSynchronizeTimeResponse](./smartmetering/GetSynchronizeTimeResponse.md)** is a request which returns the response from the [SynchronizeTime](./smartmetering/SynchronizeTime.md) request.
- **[RetrieveConfigurationObjects](./smartmetering/RetrieveConfigurationObjects.md)** is a request to obtain the entire tree and list of objects from an E-meter. 
- **[GetRetrieveConfigurationObjectsResponse](./smartmetering/GetRetrieveConfigurationObjectsResponse.md)** is a request which returns the response from the [RetrieveConfigurationObjects](./smartmetering/RetrieveConfigurationObjects.md) request.

#### SmartMeteringConfiguration
- **[SetSpecialDays](./smartmetering/SetSpecialDays.md)** is a request to set a dayId profile and its tariffs for a specific date on a device.
- **[GetSetSpecialDaysResponse](./smartmetering/GetSetSpecialDaysResponse.md)** is a request which returns the response from the [SetSpecialDays](./smartmetering/SetSpecialDays.md) request.
- **[SetConfigurationObject](./smartmetering/SetConfigurationObject.md)** is a request to set ConfigurationObject settings on a device to specify behaviour and connection options. 
- **[GetSetConfigurationObjectResponse](./smartmetering/GetSetConfigurationObjectResponse.md)** is a request which returns the response from the [SetConfigurationObject](./smartmetering/SetConfigurationObject.md) request.
- **[SetPushSetupAlarm](./smartmetering/SetPushSetupAlarm.md)** is a request that pushes received alarm messages to OSGP.
- **[GetSetPushSetupAlarmResponse](./smartmetering/GetSetPushSetupAlarmResponse.md)** is a request which returns the response from the [SetPushSetupAlarm](./smartmetering/SetPushSetupAlarm.md) request.
- **[SetPushSetupSms](./smartmetering/SetPushSetupSms.md)** is a request to set an endpoint in a device which tells the device where to connect to when it is waked up.
- **[GetSetPushSetupSmsResponse](./smartmetering/GetSetPushSetupSmsResponse.md)** is a request which returns the response from the [SetPushSetupSms](./smartmetering/SetPushSetupSms.md) request.
- **[SetAlarmNotifications](./smartmetering/SetAlarmNotifications.md)** is a request to set the types of alarmnotifications that must be notified from the device when they occur.
- **[GetSetAlarmNotificationsResponse](./smartmetering/GetSetAlarmNotificationsResponse.md)** is a request which returns the response from the [SetAlarmNotifications](./smartmetering/SetAlarmNotifications.md) request.
- **[SetEncryptionKeyExchangeOnGMeter](./smartmetering/SetEncryptionKeyExchangeOnGMeter.md)** is a request to transfer and set a G-meter key on a device.
- **[GetSetEncryptionKeyExchangeOnGMeterResponse](./smartmetering/GetSetEncryptionKeyExchangeOnGMeterResponse.md)** is a request which returns the response from the [SetEncryptionKeyExchangeOnGMeter](./smartmetering/SetEncryptionKeyExchangeOnGMeter.md) request.
- **[SetActivityCalendar](./smartmetering/SetActivityCalendar.md)** is a request to set several parameters on an E-meter such as tariffs per day in a weekprofile.
- **[GetSetActivityCalendarResponse](./smartmetering/GetSetActivityCalendarResponse.md)** is a request which returns the response from the [SetActivityCalendar](./smartmetering/SetActivityCalendar.md) request.
- **[GetAdministrativeStatus](./smartmetering/GetAdministrativeStatus.md)** is a request to retrieve the current AdministrativeStatus setting.
- **[GetGetAdministrativeStatusResponse](./smartmetering/GetGetAdministrativeStatusResponse.md)** is a request which returns the response from the [GetAdministrativeStatus](./smartmetering/GetAdministrativeStatus.md) request.
- **[SetAdministrativeStatus](./smartmetering/SetAdministrativeStatus.md)** is a request to set the AdministrativeStatus.
- **[GetSetAdministrativeStatusResponse](./smartmetering/GetSetAdministrativeStatusResponse.md)** is a request which returns the response from the [SetAdministrativeStatus](./smartmetering/SetAdministrativeStatus.md) request.
- **[ReplaceKeys](./smartmetering/ReplaceKeys.md)** is a request to change the keys on a E-meter.
- **[GetReplaceKeysResponse](./smartmetering/GetReplaceKeysResponse.md)** is a request which returns the response from the [ReplaceKeys](./smartmetering/ReplaceKeys.md) request.

#### SmartMeteringInstallation
- **[AddDevice](./smartmetering/AddDevice.md)** is a request to add a device to the OSGP database.
- **[GetAddDeviceResponse](./smartmetering/GetAddDeviceResponse.md)** is a request which returns the response from the [AddDevice](./smartmetering/AddDevice.md) request.

#### SmartMeteringManagement
- **[FindEvents](./smartmetering/FindEvents.md)** is a request to retrieve events logging from a device.
- **[GetFindEventsResponse](./smartmetering/GetFindEventsResponse.md)** is a request which returns the response from the [FindEvents](./smartmetering/FindEvents.md) request.
- **[GetDevices](./smartmetering/GetDevices.md)** is a request to retrieve the last known relay statuses for a group of devices.

#### SmartMeteringMonitoring
- **[ActualMeterReads](./smartmetering/ActualMeterReads.md)** is a request to retrieve the actual meter reads from an E-meter.
- **[GetActualMeterReadsResponse](./smartmetering/GetActualMeterReadsResponse.md)** is a request which returns the response from the [ActualMeterReads](./smartmetering/ActualMeterReads.md) request.
- **[ActualMeterReadsGas](./smartmetering/ActualMeterReadsGas.md)** is a request to retrieve the actual meter reads from a G-meter.
- **[GetActualMeterReadsGasResponse](./smartmetering/GetActualMeterReadsGasResponse.md)** is a request which returns the response from the [ActualMeterReadsGas](./smartmetering/ActualMeterReadsGas.md) request.
- **[PeriodicMeterReads](./smartmetering/PeriodicMeterReads.md)** is a request to retrieve the periodic meter reads from an E-meter.
- **[GetPeriodicMeterReadsResponse](./smartmetering/GetPeriodicMeterReadsResponse.md)** is a request which returns the response from the [PeriodicMeterReads](./smartmetering/PeriodicMeterReads.md) request.
- **[PeriodicMeterReadsGas](./smartmetering/PeriodicMeterReadsGas.md)** is a request to retrieve the periodic meter reads from a G-meter.
- **[GetPeriodicMeterReadsGasResponse](./smartmetering/GetPeriodicMeterReadsGasResponse.md)** is a request which returns the response from the [PeriodicMeterReadsGas](./smartmetering/PeriodicMeterReadsGas.md) request.
- **[ReadAlarmRegister](./smartmetering/ReadAlarmRegister.md)** is a request to read the alarm register from a device.
- **[GetReadAlarmRegisterResponse](./smartmetering/GetReadAlarmRegisterResponse.md)** is a request which returns the response from the [ReadAlarmRegister](./smartmetering/ReadAlarmRegister.md) request.
- **[RetrievePushNotificationAlarm](./smartmetering/RetrievePushNotificationAlarm.md)** is a request to push retrieved alarm notifications to OSGP.

#### SmartMeteringNotification
- **[SendNotification](./smartmetering/SendNotification.md)** is a request to let Webapps know there is a result ready to retrieve from the platform.

