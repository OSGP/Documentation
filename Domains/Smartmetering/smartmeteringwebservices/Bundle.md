## Bundle request

### Description
Bundle is a special request in which one or more single request(s) to a specific device can be bundled. All requests sent to this device make use of one communication channel, which may improve performance considerably.

[GetBundleResponse](GetBundleResponse.md) returns the result of the actions of the bundle. The response contains the DeviceIdentification and CorrelationUid which is received from the Bundle request.

The Bundle request has an **Actions** tag. This contains a list of one or more single request(s).
The response behavior is described in [ResponseMessages](./ResponseMessages.md).

### Actions

Currently, the following actions are supported:

* FindEventsRequest see [FindEvents](./FindEvents.md)
* SetSpecialDaysRequest see [SetSpecialDays](./SetSpecialDays.md)
* ReadAlarmRegisterRequest see [ReadAlarmRegister](./ReadAlarmRegister.md)
* GetActualMeterReadsRequest see [ReadAlarmRegister](./ReadAlarmRegister.md)
* GetActualMeterReadsGasRequest see [GetActualMeterReadsGas](./GetActualMeterReadsGas.md)
* GetAdministrativeStatusRequest see [GetAdministrativeStatus](./GetAdministrativeStatus.md)
* GetPeriodicMeterReadsRequest see [GetPeriodicMeterReads](./GetPeriodicMeterReads.md)
* GetPeriodicMeterReadsGasRequest see [GetPeriodicMeterReadsGas](./GetPeriodicMeterReadsGas.md)
* SetAdministrativeStatusRequest see [SetAdministrativeStatus](./SetAdministrativeStatus.md)
* SetActivityCalendarRequest see [SetActivityCalendar](./SetActivityCalendar.md)
* SetEncryptionKeyExchangeOnGMeterRequest see [SetEncryptionKeyExchangeOnGMeter](./SetEncryptionKeyExchangeOnGMeter.md)
* SetAlarmNotificationsRequest see [SetAlarmNotifications](./SetAlarmNotifications.md)
* SetConfigurationObjectRequest see [SetConfigurationObject](./SetConfigurationObject.md)
* SetPushSetupAlarmRequest see [SetPushSetupAlarm](./SetPushSetupAlarm.md)
* SetPushSetupSmsRequest see [SetPushSetupSms](./SetPushSetupSms.md)
* SynchronizeTimeRequest see [SynchronizeTime](./SynchronizeTime.md)
* GetConfigurationRequest
* GetFirmwareVersionRequest
* GetSpecificConfigurationObjectRequest see [SpecificConfigurationObject](./SpecificConfigurationObject.md)
* SetKeysRequest
* GetAssociationLnObjectsRequest
* SetClockConfigurationRequest [SetClockConfiguration](./SetClockConfiguration.md)
* GetProfileGenericDataRequest see [GetProfileGenericData](./GetProfileGenericData.md)
* ConfigureDefinableLoadProfileRequest see [ConfigureDefinableLoadProfile](./ConfigureDefinableLoadProfile.md)
* SetMbusUserKeyByChannelRequest see [SetMbusUserKeyByChannel](./SetMbusUserKeyByChannel.md)
* GetMBusEncryptionKeyStatusRequest see [GetMbusEncryptionKeyStatus](./GetMbusEncryptionKeyStatus.md)

### References

XSD: [sm-bundle.xsd](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/schemas/sm-bundle.xsd)

WSDL: [SmartMeteringBundle.wsdl](https://github.com/OSGP/Shared/blob/development/osgp-ws-smartmetering/src/main/resources/SmartMeteringBundle.wsdl)

