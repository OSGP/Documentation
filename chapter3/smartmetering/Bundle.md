## Bundle request

### Description
Bundle is a special request in which one or more single request(s) to a specific device can be bundled. All request sent to this device make use of one communication channel, which may improve performance considerably.

The Bundle request has an **Actions** tag. This contains a list of one or more single request(s).
The response behavior is described in [ResponseMessages](./ResponseMessages.md).

### Actions

Currently, the following actions are supported:

* FindEventsQuery see [FindEvents](./FindEvents.md)
* SpecialDaysRequestData see [SetSpecialDays](./SetSpecialDays.md)
* ReadAlarmRegisterData see [ReadAlarmRegister](./ReadAlarmRegister.md)
* ActualMeterReadsData see [ReadAlarmRegister](./ReadAlarmRegister.md)
* ActualMeterReadsGasData see [ActualMeterReadsGas](./ActualMeterReadsGas.md)
* GetAdministrativeStatusData see [GetAdministrativeStatus](./GetAdministrativeStatus.md)
* PeriodicMeterReadsRequestData see [PeriodicMeterReads](./PeriodicMeterReads.md)
* PeriodicMeterReadsGasRequestData see [PeriodicMeterReadsGas](./PeriodicMeterReadsGas.md)
* SetAdministrativeStatusTypeData see [GetAdministrativeStatus](./GetAdministrativeStatus.md)
* ActivityCalendarDataType see [SetActivityCalendar](./SetActivityCalendar.md)
* SetEncryptionKeyExchangeOnGMeterRequestData see [SetEncryptionKeyExchangeOnGMeter](./SetEncryptionKeyExchangeOnGMeter.md)
* SetAlarmNotificationsRequestData see [SetAlarmNotifications](./SetAlarmNotifications.md)
* SetConfigurationObjectRequestData see [SetConfigurationObject](./SetConfigurationObject.md)
* SetPushSetupAlarmRequestData see [SetPushSetupAlarm](./SetPushSetupAlarm.md)
* SetPushSetupSmsRequestData see [GetSetPushSetupSmsResponse](./GetSetPushSetupSmsResponse.md)
* SynchronizeTimeRequestData see [SynchronizeTime](./SynchronizeTime.md)
* GetConfigurationRequestData
* GetFirmwareVersionRequestData
* SpecificConfigurationObjectRequestData see [SpecificConfigurationObject](./SpecificConfigurationObject.md)
* KeySet
* GetAssociationLnObjectsRequestData

### References

XSD: [sm-notification.xsd](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/schemas/sm-bundle.xsd)

WSDL: [SmartMeteringBundle.wsdl](https://github.com/OSGP/Platform/blob/development/osgp-adapter-ws-smartmetering/src/main/webapp/WEB-INF/wsdl/smartmetering/SmartMeteringBundle.wsdl)

