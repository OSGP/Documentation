<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Technology Stack

## Platform

* [Apache ActiveMQ](http://activemq.apache.org/): Open source messaging server, used to relay messages between components of the open smart grid platform. ActiveMQ is an open source message broker written in Java and a full Java Message Service \(JMS\) client. It provides "Enterprise Features" which in this case means fostering the communication from more than one client or server.
* [Apache HTTP server](http://httpd.apache.org/): Web server, used as front for Apache Tomcat.
* [Apache Tomcat](http://tomcat.apache.org/): Provides a "pure Java" servlet container for Java code to run in.
* [pgAdmin-III](http://www.pgadmin.org/): PostgreSQL administration and management tools.
* [Protobuf \(Google Protocol Buffers\)](https://github.com/google/protobuf/): A language-neutral, platform-neutral, extensible way of serializing structured data for use in communications protocols, data storage, and more.
* [Flyway](https://flywaydb.org/): Agile database migration framework for Java
* [HikariCP](https://brettwooldridge.github.io/HikariCP/): JDBC connection pool
* [Hibernate](http://hibernate.org/): Object/Relational mapping
* [Netty](http://netty.io/): Network application framework for protocol servers & clients
* [OpenMUC](https://www.openmuc.org/): Library implementing the IEC61850 and DLMS/COSEM communication standard
* [Orika](http://orika-mapper.github.io/orika-docs/intro.html): Java bean mapping
* [Spring](https://spring.io/): Application development framework. Several Spring libraries are used, including Spring Data, Spring Security and Spring WS.
* [Puppet](https://puppet.com/): Application for Automatically delivering, operating and securing your infrastructure

## Development

* [Bower](http://bower.io/): Package manager for Javascript packages. Web applications consist of various components; frameworks, libraries, assets, utilities, and rainbows. Bower manages all these things for you.
* [Eclipse](https://eclipse.org/): IDE for developing software.
* [FileZilla](https://filezilla-project.org/): FTP application.
* [Git](https://git-scm.com/): Version control system.
* [NodeJS](https://nodejs.org/): Tooling suite with various Javascript tools.
* [NPM](https://www.npmjs.com/): Package manager for the NodeJS Javascript applications.
* [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/): A free and open-source terminal emulator, serial console and network file transfer application.
* [Vim](http://www.vim.org/): Source code editor.
* [Apache Maven](https://maven.apache.org/): Software project management tool.
* [GIT & GitHub](https://github.com/osgp): Source code management.

## Testing &QA

* [Apache JMeter](http://jmeter.apache.org/): Application designed to load test functional behaviour and measure performance.
* [Cucumber](https://cucumber.io/): automated acceptance testing framework.
* [Gherkin](https://cucumber.io/docs/reference): DSL for acceptence testing framework.
* [Sonarqube](http://www.sonarqube.org/): Quality management platform.
* [SoapUI](https://www.soapui.org/): Functional testing tool for testing web services.
* [JUnit](http://junit.org/): Unit testing.
* [Mockito](http://mockito.org/): A Mock framework for Unit testing.

The following table presents an overview of the components and the most important technical choices per component.

| **Component** | **Technology** |
| :--- | :--- |
| Open Smart Grid Platform | Java, Spring Framework, Hibernate, Netty |
| Demo application | Java, Spring Framework, Spring MVC |
| Web services | SOAP, WSDL |
| OSLP Protocol | Google Protocol Buffers |

| **Component \(not open source\)** | **Technology** |
| :--- | :--- |
| OSGP Management application | Java, Spring Framework, Spring MVC |
| Net-Management application | Java, Spring Framework, JAX-RS, AngularJS |
| Liander Installatie application | Java, Spring Framework, JAX-RS, AngularJS |

