## 3.1 Developer tools, technical guidelines and continuous integration

## 3.1.1 Tools Used

- [Apache ActiveMQ](http://activemq.apache.org/): Open source messaging server, used to relay messages between components of OSGP. ActiveMQ is an open source message broker written in Java together with a full Java Message Service (JMS) client. It provides "Enterprise Features" which in this case means fostering the communication from more than one client or server.
- [Apache HTTP server](http://httpd.apache.org/): Webserver, used as front for Apache Tomcat.
- [Apache JMeter](http://jmeter.apache.org/): Application designed to load test functional behaviour and measure performance.
- [Apache Tomcat](http://tomcat.apache.org/): Provides a "pure Java" HTTP web server environment for Java code to run in.
- [Bower](http://bower.io/): Package manager for Javascript packages. Web sites are made of lots of things - frameworks, libraries, assets, utilities, and rainbows. Bower manages all these things for you.
- [Eclipse](https://eclipse.org/): IDE for developing software.
- [FileZilla](https://filezilla-project.org/): FTP application.
- [Fitnesse](http://www.fitnesse.org/): A test tool, used to write behaviour driven tests.
- [Git](https://git-scm.com/): Version control system.
- [GivWenZen](https://github.com/weswilliams/GivWenZen): BDD extension for Fitnesse.
- [NodeJS](https://nodejs.org/): Tooling suite with various Javascript tools.
- [Notepad++](https://notepad-plus-plus.org/): A free source code editor.
- [NPM](https://www.npmjs.com/): Package manager for the NodeJS Javascript applications.
- [pgAdmin-III](http://www.pgadmin.org/): PostgreSQL administration and management tools.
- [Protobuf (Google Protocol Buffers)](https://github.com/google/protobuf/): A language-neutral, platform-neutral, extensible way of serializing structured data for use in communications protocols, data storage, and more.
- [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/): A free and open-source terminal emulator, serial console and network file transfer application.
- [SourceTree](https://www.sourcetreeapp.com/): SourceTree is a powerful Git and Mercurial desktop client for developers on Mac or Windows.
- [Vim](http://www.vim.org/): Source code editor.

## 3.1.2 Code Guidelines and Code Tests

- Use the code formatting rules < link needed >
- Use the save action rules < link needed >
- Follow [GitFlow](http://nvie.com/posts/a-successful-git-branching-model/) approach for branching
- Write behaviour driven tests using [Fitnesse](http://www.fitnesse.org/), see the [Integration-Tests repo](https://github.com/OSGP/Integration-Tests)
- Fix SonarQube issues
- Issue pull request (preferable to development branch)

## 3.1.3 Continuous Integration

All pushed to GitHub are built by our buildserver. Pull requests to master branch or development branch are also built. SonarQube performs static code analysis to help improving the quality of the code base.

- [Jenkins buildserver](http://54.77.62.182/): An open source continuous integration tool written in Java.
- [SonarQube](http://54.77.62.182/sonarqube): SonarQube is an open platform to manage code quality.

## 3.1.4 Technical Conventions and Rules for New Code

This project is engineered, built and tested using Domain Driven Design and Behaviour Driven Tests.

- Use the Frameworks, don't roll your own
- Single class, single responsibility
- Value objects are immutable
- Map generated object to value objects or entities
- Transferring an object means using a DTO
- Use base classes for common logic
- Interfaces are good, but 'impl' is bad
- Extend classes, don't expand classes
- Migrate databases using Flyway
- JMS for messaging
- Extend the authorization logic if needed, don't bypass it
- Log errors/exceptions
- Add meaningful comments to the code
- Follow the code guidelines
