## 3.5 SmartMetering Documentation


### 3.5.1 Integration tests

In this paragraph you will find an approach for developing integration tests. The tests are based on surefire, failsafe, spring-test and a package naming convention.

1. **package naming convention**  
Just put your integration tests in a package with "integrationtests" somewhere in the name  
2. **pom.xml**  
  * dependencies:  

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

  * property:  

        <skipITs>true</skipITs>
    </properties>

  * plugins:  

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


3. **example test**  

```
/**
 * This integration test requires a running up to date postgres db that can be
 * accessed using user and password from test.properties and an up and running
 * E-meter with device id E0004001515495114 and the ip address in this test.
 * Tests under the integrationtests package will only be run with
 * "-DskipITs=false"
 * 
 * @author dev
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
        DlmsDeviceMessageMetadata dlmsDeviceMessageMetadata = new DlmsDeviceMessageMetadata();
        dlmsDeviceMessageMetadata.setDeviceIdentification("E0004001515495114");
        dlmsDeviceMessageMetadata.setIpAddress("89.200.96.223");

        LnClientConnection connection = dlmsConnectionFactory
                .getConnection(domainHelperService.findDlmsDevice(dlmsDeviceMessageMetadata));

        ScalerUnitTestResponse execute = commandExecutor.execute(connection, new TestChannelQuery());

        Assert.assertEquals(execute.getScalerUnit().getDlmsUnit(), DlmsUnit.wh);

    }

}
```
4. **running**  

mvn -DskipITs=false verify
