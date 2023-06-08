<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Protocol Layer

The Protocol Adapters are responsible for the actual communication to and from a device. They usually operate in a certain domain, and might use common/ generic functions from the platform.

The Open Smart Grid Platform currently has the following protocol adapters:

* Protocol-Adapter-DLMS: Smart Metering
* Protocol-Adapter-IEC61850: Public Lighting, Micro Grids and Distribution Automation
* Protocol-Adapter-OSLP: Public Lighting and Micro Grids

## General package structure

### application

* config: Contains the configuration files for the Component. Uses the property files in /etc/osp/.

  -- ApplicationContext

  -- MessagingConfig

  -- OsgpProtocolAdapterOslpInitializer

  -- OslpConfig

  -- OslpPersistenceConfig

* mapping: Custom Orika converters.
* services: Contains the \(functional\) services that control communication from \(and to\) the device. Also persists requests and responses, and deals with security. Actual communication is done through the classes in the infra package.

### device

Contains the Protocol Adapter Objects used for the Protocol Adapter.

* requests: Objects representing the requests that are supported by this adapter.
* responses: Objects representing the responses that are supported by this adapter.

### domain

* entities: Entities used for persistence.
* repositories: Repositories used for persistence.

### exceptions

Contains the exceptions that might be thrown while communication with a device, e.g. ValidationException, MessageRejectedException, etc.

### infra

This package contains all the code for communication through JMS \(Platform\) and Networking \(Device\).

* messaging: Contains the JMS Messages, MessageListeners, MessageSenders and MessageProcessors.
* networking: Contains the classes that are responsible for connecting to a device using a certain protocol.

### services

Services used to check the request status.

