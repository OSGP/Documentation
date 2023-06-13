<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Web Services Layer

The Web Services layer contains the web services that are used to communicate with the Platform. The Open Source Smart Grid Platform uses the Simple Object Access Protocol or SOAP to expose its interfaces. The Web Services Adapter receives requests and sends those to the Domain Adapter. An incoming request is converted to a Domain Object, and put on the MessageQueue of the Domain layer. The Web Services layer also has a queue for incoming responses from the Domain adapter.

Each domain of the Platform has its own web services:

### Generic

* Core - osgp-adapter-ws-core: Contains the Core \(common\) web services.
* Admin - osgp-adapter-ws-admin: Contains the Admin web services.
* Shared - osgp-adapter-ws-shared: Contains shared endpoints, such as header authorization
* Database - osgp-adapter-ws-db: Contains repositories for persistence.

### Domain

* Public Lighting - osgp-adapter-ws-publiclighting: Contains the Public Lighting web services.
* Smart Metering - osgp-adapter-ws-smartmetering: Contains the Smart Metering web services.
* Tariff Swithcing - osgp-adapter-ws-tariffswitching: Contains the Tariff Switching web services.
* Microgrids - osgp-adapter-ws-microgrids: Contains the Micro Grids web services.
* Distribution Automation - osgp-adapter-ws-distributionautomation: Contains the Distribution Automation web services.

For a description of the WSDL's see the [Domain Chapter](../../domains).

## General Package structure

A description of the general package structure of a web service component.

### application

* config: Contains the configuration files for the Component. Uses the property files in /etc/osp/.

  -- ApplicationContext

  -- AdapterInitializer

  -- MessagingConfig

  -- PersistenceConfig

  -- WebServiceConfig

* exceptionhandling: Exceptions are defined here.
* mapping: Custom Orika converters.
* services: Contains services used by the domain, such as AdHocManagement. These are called by the end points and convert the request to a Domain Object and put the request on the domain message queue using the JMS classes.

### endpoints

* EndPoints for the web services: contain a reference to a service that proceeds with handling the request.

### infra

* jms: contains the JMS classes such as:

  -- MessageSender\(s\)

  -- MessageType

  -- ResponseMessageFinder

### webapp

The WSDL and schema definitions can be found under main/webapp/WEB\_INF/wsdl.

