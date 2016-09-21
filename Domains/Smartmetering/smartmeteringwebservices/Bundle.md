## Bundle request

### Description
Bundle is a special request in which one or more single request(s) to a specific device can be bundled. All request sent to this device make use of one communication channel, which may improve performance considerably.

[GetBundleResponse](GetBundleResponse.md) returns the result of the actions of the bundle. The response request contains the DeviceIdentification and CorrelationUid which is received from the Bundle request.

The Bundle request has an **Actions** tag. This contains a list of one or more single request(s).
The response behavior is described in [ResponseMessages](./ResponseMessages.md).

### Actions

Currently, the following actions are supported:

* FindEventsRequest see [FindEvents](./FindEvents.md)
* SetSpecialDaysRequest see [SetSpecialDays](./SetSpecialDays.md)
* ReadAlarmRegisterRequest see [ReadAlarmRegister](./ReadAlarmRegister.md)
* GetActualMeterReadsRequest see [ReadAlarmRegister](./ReadAlarmRegister.md)
* GetActualMeterReadsGasRequest see [ActualMeterReadsGas](./ActualMeterReadsGas.md)
* GetAdministrativeStatusRequest see [GetAdministrativeStatus](./SetAdministrativeStatus.md)
* GetPeriodicMeterReadsRequest see [PeriodicMeterReads](./PeriodicMeterReads.md)
* GetPeriodicMeterReadsGasRequest see [PeriodicMeterReadsGas](./PeriodicMeterReadsGas.md)
* SetAdministrativeStatusRequest see [GetAdministrativeStatus](./GetAdministrativeStatus.md)
* SetActivityCalendarRequest see [SetActivityCalendar](./SetActivityCalendar.md)
* SetEncryptionKeyExchangeOnGMeterRequest see [SetEncryptionKeyExchangeOnGMeter](./SetEncryptionKeyExchangeOnGMeter.md)
* SetAlarmNotificationsRequest see [SetAlarmNotifications](./SetAlarmNotifications.md)
* SetConfigurationObjectRequest see [SetConfigurationObject](./SetConfigurationObject.md)
* SetPushSetupAlarmRequest see [SetPushSetupAlarm](./SetPushSetupAlarm.md)
* SetPushSetupSmsRequest see [GetSetPushSetupSmsResponse](./GetSetPushSetupSmsResponse.md)
* SynchronizeTimeRequest see [SynchronizeTime](./SynchronizeTime.md)
* GetConfigurationRequest
* GetFirmwareVersionRequest
* GetSpecificConfigurationObjectRequest see [SpecificConfigurationObject](./SpecificConfigurationObject.md)
* SetKeysRequest
* GetAssociationLnObjectsRequest

### References

XSD: [sm-notification.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-bundle.xsd)

WSDL: [SmartMeteringBundle.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringBundle.wsdl)

