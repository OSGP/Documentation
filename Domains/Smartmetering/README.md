## 4.5 SmartMetering Documentation (Beta version)

This chapter describes the SmartMetering webservices (3.5.1 & 3.5.2) and the DLMS device simulator (3.5.3). Currently the webservices of the beta version are described, since the webservices have not yet offically been released.

### 4.5.1 Generic functionality

- **[priority](./smartmeteringwebservices/priority.md)** requests can be given a priority from 0 to 9, default is 4. Higher values causes messages to be processed faster.
- **[scheduling](./smartmeteringwebservices/scheduling.md)** requests can be scheduled for a certain time.
- **[bundeling](./smartmeteringwebservices/bundeling.md)** requests can be combined in a [Bundle](./smartmeteringwebservices/Bundle.md).


### 4.5.2 Messages

#### SmartMeteringAdHoc
- **[SynchronizeTime](./smartmeteringwebservices/SynchronizeTime.md)** is a request to synchronize the date and time on a device. The date and time are retrieved from the server and sent to the device.
- **[GetSynchronizeTimeResponse](./smartmeteringwebservices/GetSynchronizeTimeResponse.md)** is a request which returns the response from the [SynchronizeTime](./smartmeteringwebservices/SynchronizeTime.md) request.
- **[RetrieveConfigurationObjects](./smartmeteringwebservices/RetrieveConfigurationObjects.md)** is a request to obtain the entire tree and list of objects from an E-meter. 
- **[GetRetrieveConfigurationObjectsResponse](./smartmeteringwebservices/GetRetrieveConfigurationObjectsResponse.md)** is a request which returns the response from the [RetrieveConfigurationObjects](./smartmeteringwebservices/RetrieveConfigurationObjects.md) request.
- **[GetSpecificConfigurationObject](./smartmeteringwebservices/GetSpecificConfigurationObject.md)** is a request to obtain a specific object from an E-meter. 
- **[GetSpecificConfigurationObjectResponse](./smartmeteringwebservices/GetSpecificConfigurationObjectResponse.md)** is a request which returns the response from the [GetSpecificConfigurationObject](./smartmeteringwebservices/GetSpecificConfigurationObject.md) request.

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
- **[GetFirmwareVersionRequest](./smartmeteringwebservices/GetFirmwareVersionRequest.md)** is a request to retrieve the firmwareversion(s).
- **[GetFirmwareVersionAsyncRequest](./smartmeteringwebservices/GetFirmwareVersionAsyncRequest.md)** is a request which returns the response from the [GetFirmwareVersionRequest](./smartmeteringwebservices/GetFirmwareVersionRequest.md).
- **[ReplaceKeys](./smartmeteringwebservices/ReplaceKeys.md)** is a request to change the keys on a E-meter.
- **[GetReplaceKeysResponse](./smartmeteringwebservices/GetReplaceKeysResponse.md)** is a request which returns the response from the [ReplaceKeys](./smartmeteringwebservices/ReplaceKeys.md) request.

#### SmartMeteringInstallation
- **[AddDevice](./smartmeteringwebservices/AddDevice.md)** is a request to add a device to the OSGP database.
- **[GetAddDeviceResponse](./smartmeteringwebservices/GetAddDeviceResponse.md)** is a request which returns the response from the [AddDevice](./smartmeteringwebservices/AddDevice.md) request.

#### SmartMeteringManagement
- **[FindEvents](./smartmeteringwebservices/FindEvents.md)** is a request to retrieve events logging from a device.
- **[GetFindEventsResponse](./smartmeteringwebservices/GetFindEventsResponse.md)** is a request which returns the response from the [FindEvents](./smartmeteringwebservices/FindEvents.md) request.
- **[GetDevices](./smartmeteringwebservices/GetDevices.md)** is a request to retrieve the last known relay statuses for a group of devices.

#### SmartMeteringMonitoring
- **[ActualMeterReads](./smartmeteringwebservices/ActualMeterReads.md)** is a request to retrieve the actual meter reads from an E-meter.
- **[GetActualMeterReadsResponse](./smartmeteringwebservices/GetActualMeterReadsResponse.md)** is a request which returns the response from the [ActualMeterReads](./smartmeteringwebservices/ActualMeterReads.md) request.
- **[ActualMeterReadsGas](./smartmeteringwebservices/ActualMeterReadsGas.md)** is a request to retrieve the actual meter reads from a G-meter.
- **[GetActualMeterReadsGasResponse](./smartmeteringwebservices/GetActualMeterReadsGasResponse.md)** is a request which returns the response from the [ActualMeterReadsGas](./smartmeteringwebservices/ActualMeterReadsGas.md) request.
- **[PeriodicMeterReads](./smartmeteringwebservices/PeriodicMeterReads.md)** is a request to retrieve the periodic meter reads from an E-meter.
- **[GetPeriodicMeterReadsResponse](./smartmeteringwebservices/GetPeriodicMeterReadsResponse.md)** is a request which returns the response from the [PeriodicMeterReads](./smartmeteringwebservices/PeriodicMeterReads.md) request.
- **[PeriodicMeterReadsGas](./smartmeteringwebservices/PeriodicMeterReadsGas.md)** is a request to retrieve the periodic meter reads from a G-meter.
- **[GetPeriodicMeterReadsGasResponse](./smartmeteringwebservices/GetPeriodicMeterReadsGasResponse.md)** is a request which returns the response from the [PeriodicMeterReadsGas](./smartmeteringwebservices/PeriodicMeterReadsGas.md) request.
- **[ReadAlarmRegister](./smartmeteringwebservices/ReadAlarmRegister.md)** is a request to read the alarm register from a device.
- **[GetReadAlarmRegisterResponse](./smartmeteringwebservices/GetReadAlarmRegisterResponse.md)** is a request which returns the response from the [ReadAlarmRegister](./smartmeteringwebservices/ReadAlarmRegister.md) request.
- **[RetrievePushNotificationAlarm](./smartmeteringwebservices/RetrievePushNotificationAlarm.md)** is a request to push retrieved alarm notifications to OSGP.

#### SmartMeteringNotification
- **[SendNotification](./smartmeteringwebservices/SendNotification.md)** is a request to let Webapps know there is a result ready to retrieve from the platform.

#### SmartMeteringBundle
- **[Bundle](./smartmeteringwebservices/Bundle.md)**  is a special request in which one or more single request(s) to a specific device can be bundled. 
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
