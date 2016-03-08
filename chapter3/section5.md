## 3.5 SmartMetering Documentation


### 3.5.1 Integration tests

In this paragraph you will find an approach for developing integration tests. The tests are based on surefire, failsafe, spring-test and a package naming convention.

#### a. package naming convention
Just put your integration tests in a package with "integrationtests" somewhere in the name  
#### b. pom.xml
* dependencies:
```xml
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-test</artifactId>
            <version>4.2.0.RELEASE</version>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.postgresql</groupId>
            <artifactId>postgresql</artifactId>
            <version>9.4.1207.jre7</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
```
* property:
```xml
    <properties>
        <skipITs>true</skipITs>
    </properties>
```
* plugins:
```xml
            <plugin>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>2.19.1</version>
                <configuration>
                    <excludes>
                        <exclude>%regex[.*integrationtests.*class]</exclude>                        
                    </excludes>
                </configuration>
            </plugin>
            <plugin>
                <artifactId>maven-failsafe-plugin</artifactId>
                <version>2.19.1</version>
                <executions>
                    <execution>
                        <configuration>
                            <includes>
                                <include>%regex[.*integrationtests.*class]</include>                            
                            </includes>
                        </configuration>
                        <goals>
                            <goal>integration-test</goal>
                        </goals>
                    </execution>
                </executions> 
            </plugin>
```

#### c. example test
```
/**
 * This integration test requires A running up to date postgres db that can be
 * accessed using user and password from test.properties and an up and running
 * E-meter with device id E0004001515495114 and the ip address in this test.
 * Tests under the integrationtests package will only be run with
 * "-DskipITs=false"
 *
 */
@RunWith(SpringJUnit4ClassRunner.class)
@TestPropertySource("classpath:/test.properties")
@ContextConfiguration(classes = { ApplicationContext.class })
public class ScalerUnitTest {

    @Autowired
    private TestScalerUnitCommandExecutor commandExecutor;

    @Autowired
    private DlmsConnectionFactory dlmsConnectionFactory;

    @Autowired
    private DomainHelperService domainHelperService;

    @Test
    public void testGetScalerUnit() throws Exception {
        final DlmsDeviceMessageMetadata dlmsDeviceMessageMetadata = new DlmsDeviceMessageMetadata();
        dlmsDeviceMessageMetadata.setDeviceIdentification("E0004001515495114");
        dlmsDeviceMessageMetadata.setIpAddress("89.200.96.223");

        final LnClientConnection connection = this.dlmsConnectionFactory.getConnection(this.domainHelperService
                .findDlmsDevice(dlmsDeviceMessageMetadata));

        final ScalerUnitTestResponse execute = this.commandExecutor.execute(connection, new TestChannelQuery());

        Assert.assertEquals(DlmsUnit.WH, execute.getScalerUnit().getDlmsUnit());

    }

}
```
#### d. running
mvn -DskipITs=false verify

### 3.5.2 Webservices

#### SmartMeteringAdHoc
- **[SynchronizeTime](./section3.x/SynchronizeTime.md)** is a request to synchronize the date and time on a device. The date and time are retrieved from the server and sent to the device.
- **[GetSynchronizeTimeResponse](./section3.x/GetSynchronizeTimeResponse.md)** is a request which returns the response from the [SynchronizeTime](./section3.x/SynchronizeTime.md) request.
- **[SendWakeupSms](./section3.x/SendWakeupSms.md)** is a request to wake up the E-meter by SMS when it is sleeping. When the device becomes awake, communication is possible.
- **[GetSendWakeupSmsResponse](./section3.x/GetSendWakeupSmsResponse.md)** is a request which returns the response from the [SendWakeupSms](./section3.x/SendWakeupSms.md) and the messageID from the SMS message.
- **[GetSmsDetails](./section3.x/GetSmsDetails.md)** is a request to receive information about the sent SMS and its delivery status from [SendWakeupSms](./section3.x/SendWakeupSms.md), it needs the messageID which is obtained by the [GetSendWakeupSmsResponses](./section3.x/GetSendWakeupSmsResponses.md) request.
- **[GetGetSmsDetailsResponse](./section3.x/GetGetSmsDetailsResponse.md)** is a request with the response from the [GetSmsDetails](./section3.x/GetSmsDetails.md) request.
- **[RetrieveConfigurationObjects](./section3.x/RetrieveConfigurationObjects.md)** is a request to obtain the entire tree and list of objects from an E-meter. 
- **[GetRetrieveConfigurationObjectsResponse](./section3.x/GetRetrieveConfigurationObjectsResponse.md)** is a request which returns the response from the [RetrieveConfigurationObjects](./section3.x/RetrieveConfigurationObjects.md) request.

#### SmartMeteringConfiguration
- **[SetSpecialDays](./section3.x/SetSpecialDays.md)** is a request to set a dayId profile and its tariffs for a specific date on a device.
- **[GetSetSpecialDaysResponse](./section3.x/GetSetSpecialDaysResponse.md)** is a request which returns the response from the [SetSpecialDays](./section3.x/SetSpecialDays.md) request.
- **[SetConfigurationObject](./section3.x/SetConfigurationObject.md)** is a request to set ConfigurationObject settings on a device to specify behaviour and connection options. 
- **[GetSetConfigurationObjectResponse](./section3.x/GetSetConfigurationObjectResponse.md)** is a request which returns the response from the [SetConfigurationObject](./section3.x/SetConfigurationObject.md) request.
- **[SetPushSetupAlarm](./section3.x/SetPushSetupAlarm.md)** is a request that pushes received alarm messages to OSGP.
- **[GetSetPushSetupAlarmResponse](./section3.x/GetSetPushSetupAlarmResponse.md)** is a request which returns the response from the [SetPushSetupAlarm](./section3.x/SetPushSetupAlarm.md) request.
- **[SetPushSetupSms](./section3.x/SetPushSetupSms.md)** is a request to set an endpoint in a device which tells the device where to connect to when it is waked up.
- **[GetSetPushSetupSmsResponse](./section3.x/GetSetPushSetupSmsResponse.md)** is a request which returns the response from the [SetPushSetupSms](./section3.x/SetPushSetupSms.md) request.
- **[SetAlarmNotifications](./section3.x/SetAlarmNotifications.md)** is a request to set the types of alarmnotifications that must be notified from the device when they occur.
- **[GetSetAlarmNotificationsResponse](./section3.x/GetSetAlarmNotificationsResponse.md)** is a request which returns the response from the [SetAlarmNotifications](./section3.x/SetAlarmNotifications.md) request.
- **[SetEncryptionKeyExchangeOnGMeter](./section3.x/SetEncryptionKeyExchangeOnGMeter.md)** is a request to transfer and set a G-meter key on a device.
- **[GetSetEncryptionKeyExchangeOnGMeterResponse](./section3.x/GetSetEncryptionKeyExchangeOnGMeterResponse.md)** is a request which returns the response from the [SetEncryptionKeyExchangeOnGMeter](./section3.x/SetEncryptionKeyExchangeOnGMeter.md) request.
- **[SetActivityCalendar](./section3.x/SetActivityCalendar.md)** is a request to set several parameters on an E-meter such as tariffs per day in a weekprofile.
- **[GetSetActivityCalendarResponse](./section3.x/GetSetActivityCalendarResponse.md)** is a request which returns the response from the [SetActivityCalendar](./section3.x/SetActivityCalendar.md) request.
- **[GetAdministrativeStatus](./section3.x/GetAdministrativeStatus.md)** is a request to retrieve the current AdministrativeStatus setting.
- **[GetGetAdministrativeStatusResponse](./section3.x/GetGetAdministrativeStatusResponse.md)** is a request which returns the response from the [GetAdministrativeStatus](./section3.x/GetAdministrativeStatus.md) request.
- **[SetAdministrativeStatus](./section3.x/SetAdministrativeStatus.md)** is a request to set the AdministrativeStatus.
- **[GetSetAdministrativeStatusResponse](./section3.x/GetSetAdministrativeStatusResponse.md)** is a request which returns the response from the [SetAdministrativeStatus](./section3.x/SetAdministrativeStatus.md) request.
- **[ReplaceKeys](./section3.x/ReplaceKeys.md)** is a request to change the keys on a E-meter.
- **[GetReplaceKeysResponse](./section3.x/GetReplaceKeysResponse.md)** is a request which returns the response from the [ReplaceKeys](./section3.x/ReplaceKeys.md) request.

#### SmartMeteringInstallation
- **[AddDevice](./section3.x/AddDevice.md)** is a request to add a device to the OSGP database.
- **[GetAddDeviceReponse](./section3.x/GetAddDeviceReponse.md)** is a request which returns the response from the [AddDevice](./section3.x/AddDevice.md) request.

#### SmartMeteringManagement
- **[FindEvents](./section3.x/FindEvents.md)** is a request to retrieve events logging from a device.
- **[GetFindEventsResponse](./section3.x/GetFindEventsResponse.md)** is a request which returns the response from the [FindEvents](./section3.x/FindEvents.md) request.
- **[GetDevices](./section3.x/GetDevices.md)** is a request to retrieve the last known relay statuses for a group of devices.

#### SmartMeteringMonitoring
- **[ActualMeterReads](./section3.x/ActualMeterReads.md)** is a request to retrieve the actual meter reads from an E-meter.
- **[GetActualMeterReadsResponse](./section3.x/GetActualMeterReadsResponse.md)** is a request which returns the response from the [ActualMeterReads](./section3.x/ActualMeterReads.md) request.
- **[ActualMeterReadsGas](./section3.x/ActualMeterReadsGas.md)** is a request to retrieve the actual meter reads from a G-meter.
- **[GetActualMeterReadsGasResponse](./section3.x/GetActualMeterReadsGasResponse.md)** is a request which returns the response from the [ActualMeterReadsGas](./section3.x/ActualMeterReadsGas.md) request.
- **[PeriodicMeterReads](./section3.x/PeriodicMeterReads.md)** is a request to retrieve the periodic meter reads from an E-meter.
- **[GetPeriodicMeterReadsResponse](./section3.x/GetPeriodicMeterReadsResponse.md)** is a request which returns the response from the [PeriodicMeterReads](./section3.x/PeriodicMeterReads.md) request.
- **[PeriodicMeterReadsGas](./section3.x/PeriodicMeterReadsGas.md)** is a request to retrieve the periodic meter reads from a G-meter.
- **[GetPeriodicMeterReadsGasResponse](./section3.x/GetPeriodicMeterReadsGasResponse.md)** is a request which returns the response from the [PeriodicMeterReadsGas](./section3.x/PeriodicMeterReadsGas.md) request.
- **[ReadAlarmRegister](./section3.x/ReadAlarmRegister.md)** is a request to read the alarm register from a device.
- **[GetReadAlarmRegisterResponse](./section3.x/GetReadAlarmRegisterResponse.md)** is a request which returns the response from the [ReadAlarmRegister](./section3.x/ReadAlarmRegister.md) request.
- **[RetrievePushNotificationAlarm](./section3.x/RetrievePushNotificationAlarm.md)** is a request to push retrieved alarm notifications to OSGP.

#### SmartMeteringNotification
- **[SendNotification](./section3.x/SendNotification.md)**

