<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Developers 101

## Developer tools, technical guidelines and continuous integration

## Tools Used

The technology and tools used can be found in the [Technology stack](../architecture/technicaloverview/technologystack.md) section.

## Code Guidelines and Code Tests

* To prevent formatting issues caused by using different IDEs, the formatting style for the code is based on [Google Java Format](https://github.com/google/google-java-format) with some extra additions based on the Eclipse based conventions that were already in use.

  Check the explanation of the [general ideas](https://github.com/OSGP/Config/tree/development/code-format-settings) as well as the instructions how to configure your idea to be able to format according to the conventions \(available for [Eclipse](https://github.com/OSGP/Config/tree/development/code-format-settings/eclipse) and [IntelliJ](https://github.com/OSGP/Config/tree/development/code-format-settings/intellij)\).

* Follow [GitFlow](http://nvie.com/posts/a-successful-git-branching-model/) approach for branching
* Write behaviour driven tests using [Cucumber and Gherkin](https://cucumber.io), see the [Integration-Tests](https://github.com/OSGP/open-smart-grid-platform/tree/development/integration-tests)
* In case you are not familiar with behaviour driven tests, include unit tests
* Fix SonarQube issues
* Issue pull request \(preferable to development branch\)

## Continuous Integration

All changes pushed to GitHub are built by our build server. Pull requests to master branch or development branch are also built. SonarQube performs static code analysis to help improve the quality level of the code base.

* [Jenkins buildserver](http://ci.opensmartgridplatform.org): An open source continuous integration tool written in Java.
* [SonarQube](http://ci.opensmartgridplatform.org/sonarqube): SonarQube is an open platform to manage code quality.

## Technical Conventions and Rules for New Code

This project is engineered, built and tested using Domain Driven Design and Behaviour Driven Tests.

* Use the Frameworks, don't roll your own
* Single class, single responsibility
* Value objects are immutable
* Map generated objects to value objects or entities
* Transferring an object means using a DTO
* Use base classes for common logic
* Interfaces are good, but 'impl' is bad
* Extend classes, don't expand classes
* Migrate databases using Flyway
* JMS for messaging
* Extend the authorization logic if needed, don't bypass it
* Log errors/exceptions
* Add meaningful comments to the code
* Follow the code guidelines

## Development Guide per Component

### Web Service Adapters

The web service adapters use Spring Web Service, contract first. JAXB is used to generate Java classes from the XSD's. All SOAP operations are bound to an endpoint. The incoming SOAP requests are authenticated by organization identification \(plus certificates\). Organization authorizations are checked for the desired operation. If the request is OK, a JMS message is sent to a domain adapter component.

### Domain Adapters

Domain adapters contain business logic and persistence. Domain adapters process and forward the JMS message to the Core component.

### Domain Components

Domain components contain entities and value objects.

### Core

The Core component routes messages from domain adapter components to protocol adapter components and vice versa. Furthermore, it offers read-only database access for protocol adapter components.

### Protocol Adapters

Protocol Adapter components translate a message from domain adapter components into a protocol message for a smart device. Protocol Adapter components send the protocol message to a smart device using a network connection. The response from the smart device is translated into a domain response message which will be sent to the Core components \(which will route it to the domain adapter which issued the request\).

#### OSLP

For the OSLP implementation, two components are used. The first component is the protocol adapter for the protocol. It can translate message into the protocol message for SSLD's. Second there's the signing-server component. It is responsible for signing the protocol message using the private key of the platform. The components communicate using a key-pair. The signing-server can handle multiple protocol adapter instances by utilizing a reply-to queue per protocol adapter instance. Since the protocol adapter component needs to be reachable from a network, it is a requirement that the private key may not be used by the protocol adapter directly. The signing server component can be deployed in such a way that no network access is available to this component, as the only coupling needed are the queues / the message broker.

## Other Guides

### Installation Guide

If a full installation is desired, have a look at our [Installation Guide](../userguide/installationguide).

### Create New Domain Guide

In order to add a new domain to OSGP, you can benefit from the information in the [Create New Domain Guide](../domains/createnewdomain.md).

