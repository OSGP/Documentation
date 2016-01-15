## 3.5 SmartMetering Documentation


### 3.5.1 Integration tests

In this paragraph you will find an approach for developing integration tests. The tests are based on surefire, failsafe, spring-test and a package naming convention.

**package naming convention**  
Just put your integration tests in a package with "integrationtests" somewhere in the name
**pom.xml**  
dependencies:  

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

property:  

    <properties>
        ..
        <skipITs>true</skipITs>
    </properties>

    
plugins:  

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


**example test**  
**running**  

