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
**[ActualMeterReads](./section3.x/ActualMeterReads.md)**
**[ActualMeterReadsGas](./section3.x/ActualMeterReadsGas.md)**
**[AddDevice](./section3.x/AddDevice.md)**
**[FindEvents](./section3.x/FindEvents.md)**
**[GetAdministrativeStatus](./section3.x/GetAdministrativeStatus.md)**
**[GetDevices](./section3.x/GetDevices.md)**
**[GetSmsDetails](./section3.x/GetSmsDetails.md)**
**[PeriodicMeterReads](./section3.x/PeriodicMeterReads.md)**
**[PeriodicMeterReadsGas](./section3.x/PeriodicMeterReadsGas.md)**
**[ReadAlarmRegister](./section3.x/ReadAlarmRegister.md)**
**[ReplaceKeys](./section3.x/ReplaceKeys.md)**
**[RetrieveConfigurationObjects](./section3.x/RetrieveConfigurationObjects.md)**
**[RetrievePushNotificationAlarm](./section3.x/RetrievePushNotificationAlarm.md)**
**[SendNotification](./section3.x/SendNotification.md)**
**[SendWakeupSms](./section3.x/SendWakeupSms.md)**
**[SetActivityCalendar](./section3.x/SetActivityCalendar.md)**
**[SetAdministrativeStatus](./section3.x/SetAdministrativeStatus.md)**
**[SetAlarmNotifications](./section3.x/SetAlarmNotifications.md)**
**[SetConfigurationObject](./section3.x/SetConfigurationObject.md)**
**[SetEncryptionKeyExchangeOnGMeter](./section3.x/SetEncryptionKeyExchangeOnGMeter.md)**
**[SetPushSetupAlarm](./section3.x/SetPushSetupAlarm.md)**
**[SetPushSetupSms](./section3.x/SetPushSetupSms.md)**
**[SetSpecialDays](./section3.x/SetSpecialDays.md)**
**[SynchronizeTime](./section3.x/SynchronizeTime.md)**

