## 1.2 Architecture Principles

This chapter gives an overview of the principles used defining and implementing the architecture. The following principles were applied:

- Layering
- Domain driven design
- Dependency inversion principle
- Behavior driven development

### 1.2.1 Layering

The use of layers improves the separation of responsibilities. Each application contains the following layers:

- Presentation layer: responsible for providing information to users (persons and/or systems) and the handling of user requests
- Application layer: responsible for executing system tasks including authorisation control
- Domain layer: responsible for the representation of the problem domain.
- Infrastructure: responsible for technical matters supporting other layers. For instance persistence, messaging, etc

_Image, Layers:_
 ![alt text](./layers.png "Layers")

1. Audit logger
2. Webservices
3. Functions
4. Queue
5. Worklow engine
6. Protocol framework
7. Protocol implementations
8. Workflow engine
9. Queue
10. Communication

### 1.2.2 Domain driven design (DDD)

Domain-driven design focusses on the problem domain. DDD's starting point is creating an optimal model for a specific problem domain by having a common language and constructive collaboration between technical and domain experts.

DDD uses the following building blocks:

- Entity: An object not identified by its attributes but by its own identity.
- Value Object: an object with attributes but has no own identity.
- A collection of objects surrounding a specific root entity (or aggregate root). To ensure consistency objects in the aggregate can only be addressed through the aggregate root.
- Service: Contains instructions not related to a specific object. 
- Repository: Serves as a  collection for fetching and saving objects. Creates an abstraction for actual persistent implementations.
- Factory: Contains methods to create domain objects.

### 1.2.3 Dependency inversion principle

The dependency inversion principle promotes an independent connection by inverting dependency relations. This ensures that the domain model can be very 'clean' without knowledge of the underlying infrastructure (POJO classes). To apply this principle the Spring Framework is used.

### 1.2.4 Behavior driven development (BDD)

Behavior driven development is a way of programming that first describes behavior in user stories and then implements this in the code. The user stories contain scenarios with acceptation criteria, which can be automated. This creates a complete test suite for the whole system.

For the application of BDD the following frameworks are used:

- GivWenZen, extension for FitNesse to use Given When Then scenario's
- FitNesse, acceptance testing framework, makes use of wiki.
- Cucumber, automated acceptance testing, based on scenario's from stories.
