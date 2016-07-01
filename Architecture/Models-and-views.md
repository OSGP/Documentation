## 1.8 Models and Views

### 1.8.1 Design view

The image below shows a high-level view of the system's components.

![alt text](./design-view.png "Design View")

### 1.8.2 Data model platform

_Image, Overview of platform data model_
![alt text](./data-model.png "Data Model")

Data model explanation:

| **Table** | **Description** |
| --- | --- |
| devices | Devices table |
| device\_authorisation | Authorisation table, function group column concerns the device functions (AD\_HOC, INSTALLATION, etc) |
| organization | Organization table, function group column concerns the platform functions (ADMIN of USER) |
| event | Events table |
| oslp\_log\_item | Table for logging of OSLP messages. |
| webservice monitor log item | Audit record for tracking webservice activity. |

### 1.8.3 Data model web application

_Image showing the datamodel for the owners and management application_
![alt text](./data-model-web-application.png "Data Model Web Application")

Data model explanation:

| **Table** | **Description** |
| --- | --- |
| devices | Devices tabel |
| organizations | Organization table with userinfo. |
| lightmeasurementdevices | Light measurement table for linking to devices and conversion to transitions (via sms\_type and sms\_index) of incoming light measurement texts. |
| groups | Device groups. Device can exist only in 0 or 1 group. |
| Lighting schedule | Available lighting schedules linked to device (after upload of schedule). |
| Tariff schedule | Available tariff schedules linked to device (after upload of schedule). |
| Keyvalue settings | Key/value pairing to store dynamic configuration. Organisations have their own configuration. |
| Burninghour reports | Monthly Burninghour reports |
| Burninghour report devices | Device informatie burninghour report |
| Burninghour report data | Data related to a device in burninghour report. |

### 1.8.4 Logical view

The logical view is a high-level overview of the system . The image below displays the main components and interfaces between these components.

 ![alt text](./logical-view.png "Logical View")

### 1.8.7 Technology selection

Open LDAP is not applied. A database solution was chosen instead of Directory services for authorisation.
