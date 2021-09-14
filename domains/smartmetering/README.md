# SmartMetering

This chapter describes the SmartMetering domain including the web services. Currently the web services of the beta version are described, since the web services have not yet officially been released. Information on the DLMS device simulator can be found in the [DLMS protocol section](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Protocols/DLMS/Devicesimulator.md)

## Scope

The goal of this domain is to read and manage millions of smart meters. This includes smart meter installation, firmware updates, smart meter removal, read smart meter values, time synchronisation, etc. Everything that is needed to professionally manage millions of smart meters is or can be included in this domain.

## Features

Currently, the following Smart Metering features are available within the open smart grid platform:

* Add smart meter to the platform, so the device is known and additional actions can be performed for the device
* Process shipment file, which adds several smart meters to the platform along with all needed information
* Synchronize time between smart meters and head-end system, in case the smart meter adjusts its time, some events will be logged
* Retrieve events from the smart meter, several event logs are available
* Retrieve periodic meter reads from the smart meter

## Generic functionality

* [**bypass retry**](smartmeteringws/bypassretry.md) operations can be given the flag 'bypass retry'. Which means that an operation will not be retried in case of an error.
* [**priority**](smartmeteringws/priority.md) operations can be given a priority from 0 to 9, default is 4. Higher values causes messages to be processed faster.
* [**scheduling**](smartmeteringws/scheduling.md) operations can be scheduled for a certain time.
* [**bundling**](smartmeteringws/bundling/) operations can be combined in a [Bundle](smartmeteringws/bundling/bundle.md).

## Messages

### SmartMeteringAdHoc

* [**SynchronizeTime**](smartmeteringws/adhocmanagement/synchronizetime.md) is an operation to synchronize the date and time on a device. The date and time are retrieved from the server and sent to the device.
* [**GetSynchronizeTimeResponse**](smartmeteringws/adhocmanagement/getsynchronizetimeresponse.md) is an operation which returns the response from the [SynchronizeTime](smartmeteringws/adhocmanagement/synchronizetime.md) operation.
* [**RetrieveAllAttributeValues**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/RetrieveAllAttributeValues.md) is an operation to obtain all the attributes of the whole tree of objects from an E-meter.
* [**GetRetrieveAllAttributeValuesResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetRetrieveAllAttributeValuesResponse.md) is an operation which returns the response from the [RetrieveAllAttributeValues](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/RetrieveAllAttributeValues.md) operation.
* [**GetSpecificAttributeValue**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetSpecificAttributeValue.md) is an operation to obtain a specific attribute value from an ObisCode from an E-meter.
* [**GetSpecificAttributeValueResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetSpecificAttributeValueResponse.md) is an operation which returns the response from the [GetSpecificAttributeValue](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetSpecificAttributeValue.md) operation.
* [**GetAssociationLnObjects**](smartmeteringws/adhocmanagement/getassociationlnobjects.md) is an operation to get the associated ln objects.
* [**GetGetAssociationLnObjectsResponse**](smartmeteringws/adhocmanagement/getgetassociationlnobjectsresponse.md) is an operation which gets the response from the [GetAssociationLnObjects](smartmeteringws/adhocmanagement/getassociationlnobjects.md) operation.
* [**ScanMbusChannels**](smartmeteringws/configuration/scanmbuschannels.md) is an operation to get the M-Bus Short ID attribute values for all four channels from an E-meter.
* [**ScanMbusChannelsResponse**](smartmeteringws/configuration/scanmbuschannelsresponse.md) is an operation which returns the response from the [ScanMbusChannels](smartmeteringws/configuration/scanmbuschannels.md) operation.

### SmartMeteringConfiguration

* [**SetSpecialDays**](smartmeteringws/configuration/setspecialdays.md) is an operation to set a dayId profile and its tariffs for a specific date on a device.
* [**GetSetSpecialDaysResponse**](smartmeteringws/configuration/getsetspecialdaysresponse.md) is an operation which returns the response from the [SetSpecialDays](smartmeteringws/configuration/setspecialdays.md) operation.
* [**SetConfigurationObject**](smartmeteringws/configuration/setconfigurationobject.md) is an operation to set ConfigurationObject settings on a device to specify behaviour and connection options.
* [**GetSetConfigurationObjectResponse**](smartmeteringws/configuration/getsetconfigurationobjectresponse.md) is an operation which returns the response from the [SetConfigurationObject](smartmeteringws/configuration/setconfigurationobject.md) operation.
* [**GetConfigurationObject**](smartmeteringws/configuration/getconfigurationobject.md) is an operation to retrieve a ConfigurationObject from a device.
* [**GetConfigurationObjectResponse**](smartmeteringws/configuration/getconfigurationobjectresponse.md) is an operation which returns the response, a ConfigurationObject, from the [GetConfigurationObject](smartmeteringws/configuration/getconfigurationobject.md) operation.
* [**SetPushSetupAlarm**](smartmeteringws/configuration/setpushsetupalarm.md) is an operation that pushes received alarm messages to OSGP.
* [**GetSetPushSetupAlarmResponse**](smartmeteringws/configuration/getsetpushsetupalarmresponse.md) is an operation which returns the response from the [SetPushSetupAlarm](smartmeteringws/configuration/setpushsetupalarm.md) operation.
* [**SetPushSetupSms**](smartmeteringws/configuration/setpushsetupsms.md) is an operation to set an endpoint in a device which tells the device where to connect to when it is waked up.
* [**GetSetPushSetupSmsResponse**](smartmeteringws/configuration/getsetpushsetupsmsresponse.md) is an operation which returns the response from the [SetPushSetupSms](smartmeteringws/configuration/setpushsetupsms.md) operation.
* [**SetAlarmNotifications**](smartmeteringws/configuration/setalarmnotifications.md) is an operation to set the types of alarm notifications that must be notified from the device when they occur.
* [**GetSetAlarmNotificationsResponse**](smartmeteringws/configuration/getsetalarmnotificationsresponse.md) is an operation which returns the response from the [SetAlarmNotifications](smartmeteringws/configuration/setalarmnotifications.md) operation.
* [**SetEncryptionKeyExchangeOnGMeter**](smartmeteringws/configuration/setencryptionkeyexchangeongmeter.md) is an operation to transfer and set a G-meter key on a device.
* [**GetSetEncryptionKeyExchangeOnGMeterResponse**](smartmeteringws/configuration/getsetencryptionkeyexchangeongmeterresponse.md) is an operation which returns the response from the [SetEncryptionKeyExchangeOnGMeter](smartmeteringws/configuration/setencryptionkeyexchangeongmeter.md) operation.
* [**SetMbusUserKeyByChannel**](smartmeteringws/configuration/setmbususerkeybychannel.md) is an operation to set the M-Bus encryption key on an M-Bus device by using the E-meter device identification and channel from the G-meter.
* [**SetMbusUserKeyByChannelResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetMbusUserKeyByChannelResponse.md) is an operation which returns the response from the [SetMbusUserKeyByChannel](smartmeteringws/configuration/setmbususerkeybychannel.md) operation.
* [**GetMbusEncryptionKeyStatus**](smartmeteringws/configuration/getmbusencryptionkeystatus.md) is an operation to retrieve the encryption key status for a M-Bus device.
* [**GetGetMbusEncryptionKeyStatusResponse**](smartmeteringws/configuration/getgetmbusencryptionkeystatusresponse.md) is an operation which returns the response from the [GetMbusEncryptionKeyStatus](smartmeteringws/configuration/getmbusencryptionkeystatus.md) operation.
* [**GetMbusEncryptionKeyStatusByChannel**](smartmeteringws/configuration/getmbusencryptionkeystatusbychannel.md) is an operation to get the M-Bus encryption key status from an M-Bus device by using the E-meter device identification and channel from the G-meter.
* [**GetMbusEncryptionKeyStatusByChannelResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetMbusEncryptionKeyStatusByChannelResponse.md) is an operation which returns the response from the [GetMbusEncryptionKeyStatusByChannel](smartmeteringws/configuration/getmbusencryptionkeystatusbychannel.md) operation.
* [**SetActivityCalendar**](smartmeteringws/configuration/setactivitycalendar.md) is an operation to set several parameters on an E-meter such as tariffs per day in a week profile.
* [**GetSetActivityCalendarResponse**](smartmeteringws/configuration/getsetactivitycalendarresponse.md) is an operation which returns the response from the [SetActivityCalendar](smartmeteringws/configuration/setactivitycalendar.md) operation.
* [**GetAdministrativeStatus**](smartmeteringws/configuration/getadministrativestatus.md) is an operation to retrieve the current AdministrativeStatus setting.
* [**GetGetAdministrativeStatusResponse**](smartmeteringws/configuration/getgetadministrativestatusresponse.md) is an operation which returns the response from the [GetAdministrativeStatus](smartmeteringws/configuration/getadministrativestatus.md) operation.
* [**SetAdministrativeStatus**](smartmeteringws/configuration/setadministrativestatus.md) is an operation to set the AdministrativeStatus.
* [**GetSetAdministrativeStatusResponse**](smartmeteringws/configuration/getsetadministrativestatusresponse.md) is an operation which returns the response from the [SetAdministrativeStatus](smartmeteringws/configuration/setadministrativestatus.md) operation.
* [**GetFirmwareVersion**](smartmeteringws/configuration/getfirmwareversion.md) is an operation to retrieve the firmware version\(s\).
* [**GetGetFirmwareVersionResponse**](smartmeteringws/configuration/getgetfirmwareversionresponse.md) is an operation which returns the response from the [GetFirmwareVersionoperation](smartmeteringws/configuration/getfirmwareversion.md).
* [**ReplaceKeys**](smartmeteringws/configuration/replacekeys.md) is an operation to change the keys on a E-meter.
* [**GetReplaceKeysResponse**](smartmeteringws/configuration/getreplacekeysresponse.md) is an operation which returns the response from the [ReplaceKeys](smartmeteringws/configuration/replacekeys.md) operation.
* [**UpdateFirmware**](smartmeteringws/configuration/updatefirmware.md) is an operation to update the firmware module\(s\) on a device.
* [**GetUpdateFirmwareResponse**](smartmeteringws/configuration/getupdatefirmwareresponse.md) is an operation which returns the response from the [UpdateFirmware](smartmeteringws/configuration/updatefirmware.md) operation.
* [**GenerateAndReplaceKeys**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GenerateAndReplaceKeys.md) is an operation to generate and set the encryption and authentication key on a device.
* [**GenerateAndReplaceKeysResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GenerateAndReplaceKeysResponse.md) is an operation which returns the response from the [GenerateAndReplaceKeys](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GenerateAndReplaceKeys.md) operation.
* [**SetClockConfiguration**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetClockConfiguration.md) is an operation to set the clock configuration on a device.
* [**GetSetClockConfigurationResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetSetClockConfigurationResponse.md) is an operation which returns the response from the [SetClockConfiguration](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetClockConfiguration.md) operation.
* [**ConfigureDefinableLoadProfile**](smartmeteringws/configuration/configuredefinableloadprofile.md) is an operation to configure the load profile on a device.
* [**GetConfigureDefinableLoadProfileResponse**](smartmeteringws/configuration/getconfiguredefinableloadprofileresponse.md) is an operation which returns the response from the [ConfigureDefinableLoadProfile](smartmeteringws/configuration/configuredefinableloadprofile.md) operation.

### SmartMeteringInstallation

* [**AddDevice**](smartmeteringws/installation/adddevice.md) is an operation to add a device to the OSGP database.
* [**GetAddDeviceResponse**](smartmeteringws/installation/getadddeviceresponse.md) is an operation which returns the response from the [AddDevice](smartmeteringws/installation/adddevice.md) operation.
* [**CoupleMbusDevice**](smartmeteringws/installation/couplembusdevice.md) is an operation to couple a M-Bus device to a gateway.
* [**GetCoupleMbusDeviceResponse**](smartmeteringws/installation/getcouplembusdeviceresponse.md) is an operation which returns the response from the [CoupleMbusDevice](smartmeteringws/installation/couplembusdevice.md) operation.
* [**CoupleMbusDeviceByChannel**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/CoupleMbusDeviceByChannel.md) is an operation to couple a M-Bus device to a gateway.
* [**GetCoupleMbusDeviceByChannelResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetCoupleMbusDeviceByChannelResponse.md) is an operation which returns the response from the [CoupleMbusDeviceByChannel](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/CoupleMbusDeviceByChannel.md) operation.
* [**DeCoupleMbusDevice**](smartmeteringws/installation/decouplembusdevice.md) is an operation to decouple an M-Bus device from a gateway.
* [**GetDeCoupleMbusDeviceResponse**](smartmeteringws/installation/getdecouplembusdeviceresponse.md) is an operation which returns the response from the [DeCoupleMbusDevice](smartmeteringws/installation/decouplembusdevice.md) operation.

### SmartMeteringManagement

* [**ClearMBusStatusOnAllChannels**](smartmeteringws/management/clearmbusstatusonallchannels.md) is an operation to clear the M-Bus status on all channels, so G-meters are ready to raise new alarms.
* [**FindEvents**](smartmeteringws/management/findevents.md) is an operation to retrieve events logging from a device.
* [**GetFindEventsResponse**](smartmeteringws/management/getfindeventsresponse.md) is an operation which returns the response from the [FindEvents](smartmeteringws/management/findevents.md) operation.
* [**GetDevices**](smartmeteringws/management/getdevices.md) is an operation to retrieve the last known relay statuses for a group of devices.
* [**EnableDebugging**](smartmeteringws/management/enabledebugging.md) is an operation to enable debug logging for a device.
* [**GetEnableDebuggingResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetEnableDebuggingResponse.md) is an operation which returns the response from the [EnableDebugging](smartmeteringws/management/enabledebugging.md) operation.
* [**DisableDebugging**](smartmeteringws/management/disabledebugging.md) is an operation to disable debug logging for a device.
* [**GetDisableDebuggingResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetDisableDebuggingResponse.md) is an operation which returns the response from the [DisableDebugging](smartmeteringws/management/disabledebugging.md) operation.
* [**FindMessageLogs**](smartmeteringws/management/findmessagelogs.md) is an operation to read the debug logging from a device.
* [**GetFindMessageLogsResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/GetFindMessageLogsResponse.md) is an operation which returns the response from the [FindMessageLogs](smartmeteringws/management/findmessagelogs.md) operation.
* [**SetDeviceCommunicationSettings**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceCommunicationSettings.md) is an operation to set the OSGP device communication settings for a specific device.
* [**SetDeviceCommunicationSettingsResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceCommunicationSettingsResponse.md) is an operation which returns the response from the [SetDeviceCommunicationSettings](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceCommunicationSettings.md) operation.
* [**SetDeviceLifecycleStatus**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceLifecycleStatus.md) is an operation to set the lifecycle status from a device.
* [**SetDeviceLifecycleStatusResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceLifecycleStatusResponse.md) is an operation which returns the response from the [SetDeviceLifecycleStatus](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceLifecycleStatus.md) operation.
* [**SetDeviceLifecycleStatusByChannel**](smartmeteringws/management/setdevicelifecyclestatusbychannel.md) is an operation to set the lifecycle status from a device.
* [**SetDeviceLifecycleStatusByChannelResponse**](smartmeteringws/management/setdevicelifecyclestatusbychannelresponse.md) is an operation which returns the response from the [SetDeviceLifecycleStatusByChannel](smartmeteringws/management/setdevicelifecyclestatusbychannel.md) operation.

### SmartMeteringMonitoring

* [**GetActualMeterReads**](smartmeteringws/monitoring/getactualmeterreads.md) is an operation to retrieve the actual meter reads from an E-meter.
* [**GetActualMeterReadsResponse**](smartmeteringws/monitoring/getactualmeterreadsresponse.md) is an operation which returns the response from the [ActualMeterReads](smartmeteringws/monitoring/getactualmeterreads.md) operation.
* [**GetActualMeterReadsGas**](smartmeteringws/monitoring/getactualmeterreadsgas.md) is an operation to retrieve the actual meter reads from a G-meter.
* [**GetActualMeterReadsGasResponse**](smartmeteringws/monitoring/getactualmeterreadsgasresponse.md) is an operation which returns the response from the [ActualMeterReadsGas](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/ActualMeterReadsGas.md) operation.
* [**GetPeriodicMeterReads**](smartmeteringws/monitoring/getperiodicmeterreads.md) is an operation to retrieve the periodic meter reads from an E-meter.
* [**GetPeriodicMeterReadsResponse**](smartmeteringws/monitoring/getperiodicmeterreadsresponse.md) is an operation which returns the response from the [PeriodicMeterReads](smartmeteringws/monitoring/getperiodicmeterreads.md) operation.
* [**GetPeriodicMeterReadsGas**](smartmeteringws/monitoring/getperiodicmeterreadsgas.md) is an operation to retrieve the periodic meter reads from a G-meter.
* [**GetPeriodicMeterReadsGasResponse**](smartmeteringws/monitoring/getperiodicmeterreadsgasresponse.md) is an operation which returns the response from the [PeriodicMeterReadsGas](smartmeteringws/monitoring/getperiodicmeterreadsgas.md) operation.
* [**GetProfileGenericData**](smartmeteringws/monitoring/getprofilegenericdata.md) is an operation to retrieve any Profile Generic data from an E-meter.
* [**GetProfileGenericDataResponse**](smartmeteringws/monitoring/getprofilegenericdataresponse.md) is an operation which returns the response from the [ProfileGenericData](smartmeteringws/monitoring/getprofilegenericdata.md) operation.
* [**ReadAlarmRegister**](smartmeteringws/monitoring/readalarmregister.md) is an operation to read the alarm register from a device.
* [**GetReadAlarmRegisterResponse**](smartmeteringws/monitoring/getreadalarmregisterresponse.md) is an operation which returns the response from the [ReadAlarmRegister](smartmeteringws/monitoring/readalarmregister.md) operation.
* [**RetrievePushNotificationAlarm**](smartmeteringws/monitoring/retrievepushnotificationalarm.md) is an operation to push retrieved alarm notifications to OSGP.
* [**ClearAlarmRegister**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/ClearAlarmRegister.md) is an operation to clear the Alarm register flags for pushed event notifications.
* [**ClearAlarmRegisterResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/ClearAlarmRegisterResponse.md) is an operation which returns the response from the [ClearAlarmRegister](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/ClearAlarmRegister.md) operation.

### DeviceManagement

* [**SetDeviceLifecycleStatus**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceLifecycleStatus.md) is an operation to set the device lifecycle status of a device.
* [**SetDeviceLifecycleStatusResponse**](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceLifecycleStatusResponse.md) is an operation which returns the response from the [SetDeviceLifecycleStatus](https://github.com/OSGP/Documentation/tree/805a7da4c3cbf27ddb6aed765ebc7a7eab320933/Domains/Smartmetering/smartmeteringwebservices/SetDeviceLifecycleStatus.md) operation.

### SmartMeteringNotification

* [**SendNotification**](smartmeteringws/notifications/sendnotification.md) is an operation to let Webapps know there is a result ready to retrieve from the platform.

### SmartMeteringBundle

* [**Bundle**](smartmeteringws/bundling/bundle.md)  is a special operation in which one or more single operation\(s\) to a specific device can be bundled.
* [**GetBundleResponse**](smartmeteringws/bundling/bundle.md) is an operation which gets the response from the [Bundle](smartmeteringws/bundling/bundle.md) operation.

All operations sent to this device make use of one communication channel, which may improve performance considerably.

## WSDL's

* [SmartMetering WSDL's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-smartmetering/src/main/resources)
* [SmartMetering XSD schema's](https://github.com/OSGP/open-smart-grid-platform/tree/development/osgp/shared/osgp-ws-smartmetering/src/main/resources/schemas)

