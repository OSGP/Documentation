<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Domain Layer

The Domain Adapters are responsible for receiving requests from the Web Services layer, and delivering them to the Core layer. The Domain Layer mainly contains MessageProcessors and Services for request handling.

The Core/Admin components contains the shared functionality, while the Domain components contain additional domain specific functionality.

At the moment the Platform uses the following Domain Adapters:

Generic

* Core - osgp-adapter-domain-core: Contains Core \(common\) functionality;  AdHocManagement, FirmwareManagement, etc.
* Admin - osgp-adapter-domain-admin: Contains Admin functionality, e.g. DeviceManagement.

Domain

* Public Lighting - osgp-adapter-domain-publiclighting: Contains functionality for the Public Lighting Domain.
* Smart Metering - osgp-adapter-domain-smartmetering: Contains functionality for the Smart Metering Domain.
* Tariff Switching - osgp-adapter-domain-tariffswitching: Contains functionality for the Tariff Switching Domain.
* Microgrids - osgp-adapter-domain-microgrids: Contains functionality for the Micro Grids domain.
* Distribution Automation - osgp-adapter-domain-distributionautomation: Contains functionality for the Distribution Automation domain.

## General Package structure

### application

* config: Contains the configuration files for the Component. Uses the property files in /etc/osp/.

  -- ApplicationContext

  -- DomainAdapterInitializer

  -- MessagingConfig

  -- PersistenceConfig

* mapping: Custom Orika converters for mapping to/from DomainObjects/DTO Objects.
* services: Contains most of the domain logic, related to the specific services of the adapter. The service classes converts DTO objects to Domain objects \(or vice versa\), and put the request on the Core queue through the JMS classes.

### infra

* jms.core: Inbound/outbound messages from/to the Core layer.

  This package contains Messages, MessageListeners, MessageSenders and MessageProcessors for sending requests to the Core Queue, or receiving and processing responses from Core.

* jms.ws: Inbound/outbound messages from/to the web services layer.

  This package contains Messages, MessageListeners, MessageSenders and MessageProcessors for sending requests to the Web Services Queue, or receiving and processing responses from the web services layer.

