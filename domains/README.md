<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Domains

Chapter 4 Domain This chapter describes the separate domain in the open smart grid platform.

## Web Service Adapters

The web service adapters use Spring Web Service, contract first. JAXB is used to generate Java classes from the XSD's. All SOAP operations are bound to an endpoint. The incoming SOAP requests are authenticated by organization identification \(plus certificates\). Organization authorizations are checked for the desired operation. If the request is OK, a JMS message is sent to a domain adapter component.

## Domain Adapters

Domain adapters contain business logic and persistence. Domain adapters process and forward the JMS message to the Core component.

## Domain Components

Domain components contain entities and value objects.

