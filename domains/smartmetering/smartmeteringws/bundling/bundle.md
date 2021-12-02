# Bundle

## Description

Bundle is a special request in which one or more single request\(s\) to a specific device can be bundled. All requests sent to this device make use of one communication channel, which may improve performance considerably.

[GetBundleResponse](getbundleresponse.md) returns the result of the actions of the bundle. The response contains the DeviceIdentification and CorrelationUid which is received from the Bundle request.

The Bundle request has an **Actions** tag. This contains a list of one or more single request\(s\). The response behavior is described in [ResponseMessages](../../responsemessages.md).

## Actions

Currently, the following actions are supported:

* FindEventsRequest see [FindEvents](../management/findevents.md)
* SetSpecialDaysRequest see [SetSpecialDays](../configuration/setspecialdays.md)
* ReadAlarmRegisterRequest see [ReadAlarmRegister](../monitoring/readalarmregister.md)
* GetActualMeterReadsRequest see [ReadAlarmRegister](../monitoring/readalarmregister.md)
* GetActualMeterReadsGasRequest see [GetActualMeterReadsGas](../monitoring/getactualmeterreadsgas.md)
* GetAdministrativeStatusRequest see [GetAdministrativeStatus](../configuration/getadministrativestatus.md)
* GetPeriodicMeterReadsRequest see [GetPeriodicMeterReads](../monitoring/getperiodicmeterreads.md)
* GetPeriodicMeterReadsGasRequest see [GetPeriodicMeterReadsGas](../monitoring/getperiodicmeterreadsgas.md)
* SetAdministrativeStatusRequest see [SetAdministrativeStatus](../configuration/setadministrativestatus.md)
* SetActivityCalendarRequest see [SetActivityCalendar](../configuration/setactivitycalendar.md)
* SetEncryptionKeyExchangeOnGMeterRequest see [SetEncryptionKeyExchangeOnGMeter](../configuration/setencryptionkeyexchangeongmeter.md)
* SetAlarmNotificationsRequest see [SetAlarmNotifications](../configuration/setalarmnotifications.md)
* SetConfigurationObjectRequest see [SetConfigurationObject](../configuration/setconfigurationobject.md)
* SetPushSetupAlarmRequest see [SetPushSetupAlarm](../configuration/setpushsetupalarm.md)
* SetPushSetupSmsRequest see [SetPushSetupSms](../configuration/setpushsetupsms.md)
* SynchronizeTimeRequest see [SynchronizeTime](../adhocmanagement/synchronizetime.md)
* GetConfigurationRequest
* GetFirmwareVersionRequest
* UpdateFirmwareRequest see [UpdateFirmware](../configuration/updatefirmware.md)
* GetSpecificConfigurationObjectRequest see [SpecificConfigurationObject](../adhocmanagement/specificconfigurationobject.md)
* SetKeysRequest
* GetAssociationLnObjectsRequest
* SetClockConfigurationRequest [SetClockConfiguration](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetClockConfiguration.md)
* GetProfileGenericDataRequest see [GetProfileGenericData](../monitoring/getprofilegenericdata.md)
* ConfigureDefinableLoadProfileRequest see [ConfigureDefinableLoadProfile](../configuration/configuredefinableloadprofile.md)
* SetMbusUserKeyByChannelRequest see [SetMbusUserKeyByChannel](../configuration/setmbususerkeybychannel.md)
* GetMBusEncryptionKeyStatusRequest see [GetMbusEncryptionKeyStatus](../configuration/getmbusencryptionkeystatus.md)

## References

XSD: [sm-bundle.xsd](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas/sm-bundle.xsd)

WSDL: [SmartMeteringBundle.wsdl](https://github.com/OSGP/open-smart-grid-platform/blob/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/SmartMeteringBundle.wsdl)

