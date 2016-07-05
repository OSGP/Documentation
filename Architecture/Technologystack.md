
Tools and technology used

### Platform

- [Apache ActiveMQ](http://activemq.apache.org/): Open source messaging server, used to relay messages between components of OSGP. ActiveMQ is an open source message broker written in Java together with a full Java Message Service (JMS) client. It provides "Enterprise Features" which in this case means fostering the communication from more than one client or server.
- [Apache HTTP server](http://httpd.apache.org/): Webserver, used as front for Apache Tomcat.
- [Apache Tomcat](http://tomcat.apache.org/): Provides a "pure Java" HTTP web server environment for Java code to run in.
- [pgAdmin-III](http://www.pgadmin.org/): PostgreSQL administration and management tools.
- [Protobuf (Google Protocol Buffers)](https://github.com/google/protobuf/): A language-neutral, platform-neutral, extensible way of serializing structured data for use in communications protocols, data storage, and more.

### Development

- [Bower](http://bower.io/): Package manager for Javascript packages. Web sites are made of lots of things - frameworks, libraries, assets, utilities, and rainbows. Bower manages all these things for you.
- [Eclipse](https://eclipse.org/): IDE for developing software.
- [FileZilla](https://filezilla-project.org/): FTP application.
- [Git](https://git-scm.com/): Version control system.
- [NodeJS](https://nodejs.org/): Tooling suite with various Javascript tools.
- [Notepad++](https://notepad-plus-plus.org/): A free source code editor.
- [NPM](https://www.npmjs.com/): Package manager for the NodeJS Javascript applications.
- [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/): A free and open-source terminal emulator, serial console and network file transfer application.
- [SourceTree](https://www.sourcetreeapp.com/): SourceTree is a powerful Git and Mercurial desktop client for developers on Mac or Windows.
- [Vim](http://www.vim.org/): Source code editor. 

### Testing

- [Apache JMeter](http://jmeter.apache.org/): Application designed to load test functional behaviour and measure performance.
- [Fitnesse](http://www.fitnesse.org/): A test tool, used to write behaviour driven tests.
- [GivWenZen](https://github.com/weswilliams/GivWenZen): BDD extension for Fitnesse.
- [Cucumber](https://cucumber.io/): automated acceptance testing framework.


This Table presents an overview of the components and the most important technological choices per component.

| **Component** | **Technology** |
| --- | --- |
| OSGP Platform | Java, Spring Framework, Hibernate, Netty |
| Demo applicatie | Java, Spring Framework, Spring MVC |
| Web services | SOAP, WSDL |
| OSLP Protocol | Google Protocol Buffers |


| **Component (not open source)** | **Technology** |
| --- | --- |
| OSGP Management application | Java, Spring Framework, Spring MVC |
| Net-Management application | Java, Spring Framework, JAX-RS, AngularJS |
| Liander Installatie application | Java, Spring Framework, JAX-RS, AngularJS |