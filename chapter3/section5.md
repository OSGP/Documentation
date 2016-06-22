## 3.5 SmartMetering Documentation (Beta version)

This chapter describes the SmartMetering webservices (3.5.1 & 3.5.2) and the DLMS device simulator (3.5.3). Currently the webservices of the beta version are described, since the webservices have not yet offically been released.

### 3.5.1 Generic functionality

- **[priority](./smartmetering/priority.md)** requests can be given a priority from 0 to 9, default is 4. Higher values causes messages to be processed faster.
- **[scheduling](./smartmetering/scheduling.md)** requests can be scheduled for a certain time.
- **[bundeling](./smartmetering/bundeling.md)** requests can be combined in a [Bundle](./smartmetering/Bundle.md).


### 3.5.2 Messages

#### SmartMeteringAdHoc
- **[SynchronizeTime](./smartmetering/SynchronizeTime.md)** is a request to synchronize the date and time on a device. The date and time are retrieved from the server and sent to the device.
- **[GetSynchronizeTimeResponse](./smartmetering/GetSynchronizeTimeResponse.md)** is a request which returns the response from the [SynchronizeTime](./smartmetering/SynchronizeTime.md) request.
- **[RetrieveConfigurationObjects](./smartmetering/RetrieveConfigurationObjects.md)** is a request to obtain the entire tree and list of objects from an E-meter. 
- **[GetRetrieveConfigurationObjectsResponse](./smartmetering/GetRetrieveConfigurationObjectsResponse.md)** is a request which returns the response from the [RetrieveConfigurationObjects](./smartmetering/RetrieveConfigurationObjects.md) request.
- **[GetSpecificConfigurationObject](./smartmetering/GetSpecificConfigurationObject.md)** is a request to obtain a specific object from an E-meter. 
- **[GetSpecificConfigurationObjectResponse](./smartmetering/GetSpecificConfigurationObjectResponse.md)** is a request which returns the response from the [GetSpecificConfigurationObject](./smartmetering/GetSpecificConfigurationObject.md) request.

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
- **[GetFirmwareVersionRequest](./smartmetering/GetFirmwareVersionRequest.md)** is a request to retrieve the firmwareversion(s).
- **[GetFirmwareVersionAsyncRequest](./smartmetering/GetFirmwareVersionAsyncRequest.md)** is a request which returns the response from the [GetFirmwareVersionRequest](./smartmetering/GetFirmwareVersionRequest.md).
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

#### SmartMeteringBundle
- **[Bundle](./smartmetering/Bundle.md)**  is a special request in which one or more single request(s) to a specific device can be bundled. 
  All request sent to this device make use of one communication channel, which may improve performance considerably.

### 3.5.3 DLMS device simulator

The library that is used to connect to DLMS devices contains functionality to build a simulator for a device. The library offers the following core functionality.

- zero or more servers can be started on a host (different ports)
- zero or more logical devices can be registered with a server (different device id)
- zero or more annotated objects can be registered with a logical device
- these objects define available dlms classes, ObisCodes, attributeIds and methods for the device and can contain any logic
- authentication and encryption are supported

If you want to simulate a certain device you will prepare annotated classes and register instances of these with a logical device. Because you create plain Java you can make use of all functionality Java offers, for example databases. To try and make the simulation more realistic you may build in connection timeouts etc.

#### Usage

For each combination of a cosem class and obiscode you create a java class that you annotate with @CosemClass(id = ..., obis = "x.x.x.x.x.255")

In these java classes you can add fields of type DataObject that you annotate with @CosemAttribute(id = ..., type = Type.x)

Also you can create getXXX and setXXX methods to intercept getting and setting data on a logical device. XXX will be the name of the corresponding field starting with a capital letter.

For example:

```
@CosemClass(id = 3, obis = "1.0.1.8.0.255")
public class ImportValue {

    @CosemAttribute(id = 2, type = Type.DOUBLE_LONG_UNSIGNED)
    private DataObject d1 = DataObject.newUInteger32Data(10001);

    @CosemAttribute(id = 3, type = Type.STRUCTURE)
    private DataObject d2 = DataObject.newStructureData(DataObject.newInteger8Data((byte) -2),
            DataObject.newInteger8Data((byte) 30));
            
    public void setD1(DataObject newData) throws IllegalAttributeAccessException {
      // ....
    }
    public DataObject getD1() throws IllegalAttributeAccessException {
      return d1;
    }
}
```

The value of the field will be the response to get(AttributeAddress...) that is fired from osgp CommandExecutors. NOTE that these values can also be set! For example using the ClientConsole.

You can also annotate methods with or without a DataObject return value and with or without a DataObject parameter: @CosemMethod(id = ..., consumes = Type.x)

For example:

```
    @CosemMethod(id = 1)
    public void hello() throws IllegalMethodAccessException {
        System.out.println("Has been called");
        return;
    }

    @CosemMethod(id = 2, consumes = Type.OCTET_STRING)
    public DataObject hello2(DataObject datO) throws IllegalMethodAccessException {
        throw new IllegalMethodAccessException(MethodResultCode.OTHER_REASON);
    }

```
Such a method will be called when osgp fires ClientConnection.action, the DataObject that may be returned will become available in osgp on the MethodResult object.

####Per command design
The way to implement request/response for a command in the simulator is as follows.
- create a separate package per command
- create a java class for each combination of classid and obiscode
- in this class implement the attribute id's and the methods that will be requested as explained above
