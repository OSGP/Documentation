<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# Core Layer

The Core layer of the Open Source Grid Platform is responsible for Validation, Translation, Authorisation and Routing of request messages. It also contains all the Domain Objects.

The core layer consists of two components:

* osgp-domain-core: Shared Domain objects, services, repositories, etc. These classes are used through the entire platform.
* osgp-core: Logic for routing domain requests, scheduling, retrying, etc.

## General Package structure: osgp-domain-core

* entities: Defines the entities used for persistence.
* exceptions: Domain specific exceptions reside here.
* repositories: Repositories that contain logic for persisting entities.
* services: Domain services that reference a repository.
* specifications: Interfaces that define specifications for Devices and Events.
* validations: Validators and constraints.
* valueobjects: Definitions of the Domain Objects.

## General Package structure: osgp-core

### application

* config: Contains the configuration files for the Component. Uses the property files in /etc/osp/.

  -- ApplicationContext

  -- OsgpCoreInitializer

  -- DomainMessagingConfig

  -- PersistenceConfig

  -- ProtocolMessagingConfig

  -- SchedulingConfig

* services: Services that process device requests/ responses. Checks for authorization, and if the request is supported by the platform, it will be routed to the appropriate protocol adapter.
* tasks: Contains task scheduler logic.

### domain.model

These packages contain interfaces for the Services.

* domain: Interfaces for the Domain services.
* protocol: Interfaces for the Protocol services.

### infra.jms

* domain: Contains Messages, MessageListeners and MessageProcessors for Domain related messaging.
* protocol: Contains Messages, MessageListeners and MessageProcessors for Protocol related messaging.

