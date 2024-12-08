# CODEX: Cyber Operations Data Entity eXchange

**CODEX** is a cybersecurity data framework focused on defining and classifying log data entities, attributes, and relationships. Designed for flexibility and extensibility, CODEX provides a set of standards for handling log data, classifying it into well-structured entities, and ensuring compatibility with various storage systems.

## Overview

CODEX provides a comprehensive, well-documented approach to organizing cybersecurity log data. It focuses on defining the entities (e.g., IP addresses, users, and events), their attributes (e.g., timestamps, actions), and types (e.g., logs, events, risks) for efficient data classification. The framework is highly extensible, allowing for new definitions to be added as log formats evolve or new data types are introduced.

### Core Documents

The CODEX project is structured around several key definitions documents, which detail the classification, attributes, and relationships of log data:

- **Entity Definitions**: Defines the key entities, such as hosts, users, and services, and their relationships within the cybersecurity landscape.
- **Attribute Classifications**: Describes the attributes associated with each entity (e.g., timestamps, actions, event types).
- **Type Definitions**: Specifies the types of data handled (e.g., Log, Event, Agent, Device, Source, Destination, Network, File, Request, Application, Risk) and how these types are categorized within the system.
- **Relationship Models**: Details how different entities and attributes relate to each other, enabling complex queries and integrations.

## Entity Definitions

The **Entities** define the key components tracked within your cybersecurity data. These are typically the core subjects that your log data records are associated with.

1. **Account**: The user or system account involved in an event or log entry.
2. **User Name**: The user who is associated with the event or action.
3. **Host Name**: The name of the machine or host involved in an event.
4. **IP Address**: The network address associated with a system, user, or device.
5. **MAC Address**: The hardware address for network interfaces on a device.
6. **Email Address**: The email address tied to the event, potentially used for phishing, logins, or alerts.
7. **Resource**: The specific resource being accessed, used, or targeted.
8. **Domain**: The domain related to the event, such as a DNS domain or a domain name system.
9. **URL**: The uniform resource locator involved in the event, usually for web interactions.
10. **Path**: The directory or file path associated with the event.
11. **Command**: The action or command issued by a user or system process.
12. **Process Name**: The name of a running process that is logged during an event.
13. **Registry Key**: A Windows registry key that relates to the event, typically used in system events or malware investigations.
14. **Protocol**: The communication protocol involved (e.g., TCP, HTTP, FTP).
15. **Hash**: A cryptographic hash used to verify file integrity or identify files.

---

## Attribute Definitions

The **Attributes** define the specific data points or characteristics associated with the entities in the logs. These attributes provide further detail and context to the entity.

1. **ID**: A unique identifier associated with the log or event.
2. **Severity**: The severity level of the event, often used to classify the event's importance or threat level.
3. **Type**: The type of event (e.g., authentication attempt, access violation).
4. **Action**: The specific action performed in the event (e.g., file created, login succeeded).
5. **Outcome**: The result of the event (e.g., success, failure, warning).
6. **Receipt Time**: The time the event or log entry was received.
7. **Create Time**: The time at which the event or data was originally created.
8. **Modified Time**: The time when the data or event was modified.
9. **Message**: The message or description that accompanies an event.
10. **Reason**: The reason or rationale behind the event (e.g., login failure, action denied).
11. **Port**: The network port used during the communication.
12. **Bytes**: The volume of data transmitted during the event.
13. **Product**: The product involved in the event, such as the software or hardware that generated the log.
14. **Method**: The method or technique used in the event (e.g., HTTP method like GET or POST).
15. **Name**: The name or title of the event, entity, or resource.

### Type Definitions

- **Log**: A record of an event or activity, typically associated with a system or application (e.g., web server log, firewall log).
- **Event**: A discrete occurrence or action, such as a login attempt, file access, or policy violation.
- **Agent**: A software component or system that generates or collects data (e.g., endpoint agent, SIEM agent).
- **Device**: Hardware or virtual devices involved in the data transaction or log generation (e.g., routers, firewalls, servers).
- **Source**: The origin of the log data or event, such as an IP address or an external device.
- **Destination**: The target or endpoint affected by the event or data transmission (e.g., destination IP address, application).
- **Network**: Defines the network layer, connections, and flow of data across devices and systems.
- **File**: Represents files or data objects that are being accessed, transferred, or modified in relation to the event (e.g., file name, path).
- **Request**: Describes requests made between systems or users, such as HTTP requests, API calls, or database queries.
- **Application**: Software or services that interact with the data, such as web applications, databases, or security tools.
- **Risk**: The level of threat or exposure associated with an event or log entry, usually assessed based on severity or impact.

### Taxonomy Matrix

The following table lists all possible keys generated by combining Types, Entities, and Attributes:

| Type x Entity/Attribute | account | user_name | host_name | ip_address | mac_address | email_address | resource | domain | url | path | command | process_name | registry_key | protocol | hash | receipt_time | create_time | modified_time | port | bytes | message | reason | id | product | method | severity | type | action | outcome | name |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| log | `log.account` | `log.user_name` | `log.host_name` | `log.ip_address` | `log.mac_address` | `log.email_address` | `log.resource` | `log.domain` | `log.url` | `log.path` | `log.command` | `log.process_name` | `log.registry_key` | `log.protocol` | `log.hash` | `log.receipt_time` | `log.create_time` | `log.modified_time` | `log.port` | `log.bytes` | `log.message` | `log.reason` | `log.id` | `log.product` | `log.method` | `log.severity` | `log.type` | `log.action` | `log.outcome` | `log.name` |
| evt | `evt.account` | `evt.user_name` | `evt.host_name` | `evt.ip_address` | `evt.mac_address` | `evt.email_address` | `evt.resource` | `evt.domain` | `evt.url` | `evt.path` | `evt.command` | `evt.process_name` | `evt.registry_key` | `evt.protocol` | `evt.hash` | `evt.receipt_time` | `evt.create_time` | `evt.modified_time` | `evt.port` | `evt.bytes` | `evt.message` | `evt.reason` | `evt.id` | `evt.product` | `evt.method` | `evt.severity` | `evt.type` | `evt.action` | `evt.outcome` | `evt.name` |
| agt | `agt.account` | `agt.user_name` | `agt.host_name` | `agt.ip_address` | `agt.mac_address` | `agt.email_address` | `agt.resource` | `agt.domain` | `agt.url` | `agt.path` | `agt.command` | `agt.process_name` | `agt.registry_key` | `agt.protocol` | `agt.hash` | `agt.receipt_time` | `agt.create_time` | `agt.modified_time` | `agt.port` | `agt.bytes` | `agt.message` | `agt.reason` | `agt.id` | `agt.product` | `agt.method` | `agt.severity` | `agt.type` | `agt.action` | `agt.outcome` | `agt.name` |
| dvc | `dvc.account` | `dvc.user_name` | `dvc.host_name` | `dvc.ip_address` | `dvc.mac_address` | `dvc.email_address` | `dvc.resource` | `dvc.domain` | `dvc.url` | `dvc.path` | `dvc.command` | `dvc.process_name` | `dvc.registry_key` | `dvc.protocol` | `dvc.hash` | `dvc.receipt_time` | `dvc.create_time` | `dvc.modified_time` | `dvc.port` | `dvc.bytes` | `dvc.message` | `dvc.reason` | `dvc.id` | `dvc.product` | `dvc.method` | `dvc.severity` | `dvc.type` | `dvc.action` | `dvc.outcome` | `dvc.name` |
| src | `src.account` | `src.user_name` | `src.host_name` | `src.ip_address` | `src.mac_address` | `src.email_address` | `src.resource` | `src.domain` | `src.url` | `src.path` | `src.command` | `src.process_name` | `src.registry_key` | `src.protocol` | `src.hash` | `src.receipt_time` | `src.create_time` | `src.modified_time` | `src.port` | `src.bytes` | `src.message` | `src.reason` | `src.id` | `src.product` | `src.method` | `src.severity` | `src.type` | `src.action` | `src.outcome` | `src.name` |
| dest | `dest.account` | `dest.user_name` | `dest.host_name` | `dest.ip_address` | `dest.mac_address` | `dest.email_address` | `dest.resource` | `dest.domain` | `dest.url` | `dest.path` | `dest.command` | `dest.process_name` | `dest.registry_key` | `dest.protocol` | `dest.hash` | `dest.receipt_time` | `dest.create_time` | `dest.modified_time` | `dest.port` | `dest.bytes` | `dest.message` | `dest.reason` | `dest.id` | `dest.product` | `dest.method` | `dest.severity` | `dest.type` | `dest.action` | `dest.outcome` | `dest.name` |
| net | `net.account` | `net.user_name` | `net.host_name` | `net.ip_address` | `net.mac_address` | `net.email_address` | `net.resource` | `net.domain` | `net.url` | `net.path` | `net.command` | `net.process_name` | `net.registry_key` | `net.protocol` | `net.hash` | `net.receipt_time` | `net.create_time` | `net.modified_time` | `net.port` | `net.bytes` | `net.message` | `net.reason` | `net.id` | `net.product` | `net.method` | `net.severity` | `net.type` | `net.action` | `net.outcome` | `net.name` |
| file | `file.account` | `file.user_name` | `file.host_name` | `file.ip_address` | `file.mac_address` | `file.email_address` | `file.resource` | `file.domain` | `file.url` | `file.path` | `file.command` | `file.process_name` | `file.registry_key` | `file.protocol` | `file.hash` | `file.receipt_time` | `file.create_time` | `file.modified_time` | `file.port` | `file.bytes` | `file.message` | `file.reason` | `file.id` | `file.product` | `file.method` | `file.severity` | `file.type` | `file.action` | `file.outcome` | `file.name` |
| req | `req.account` | `req.user_name` | `req.host_name` | `req.ip_address` | `req.mac_address` | `req.email_address` | `req.resource` | `req.domain` | `req.url` | `req.path` | `req.command` | `req.process_name` | `req.registry_key` | `req.protocol` | `req.hash` | `req.receipt_time` | `req.create_time` | `req.modified_time` | `req.port` | `req.bytes` | `req.message` | `req.reason` | `req.id` | `req.product` | `req.method` | `req.severity` | `req.type` | `req.action` | `req.outcome` | `req.name` |
| app | `app.account` | `app.user_name` | `app.host_name` | `app.ip_address` | `app.mac_address` | `app.email_address` | `app.resource` | `app.domain` | `app.url` | `app.path` | `app.command` | `app.process_name` | `app.registry_key` | `app.protocol` | `app.hash` | `app.receipt_time` | `app.create_time` | `app.modified_time` | `app.port` | `app.bytes` | `app.message` | `app.reason` | `app.id` | `app.product` | `app.method` | `app.severity` | `app.type` | `app.action` | `app.outcome` | `app.name` |
| risk | `risk.account` | `risk.user_name` | `risk.host_name` | `risk.ip_address` | `risk.mac_address` | `risk.email_address` | `risk.resource` | `risk.domain` | `risk.url` | `risk.path` | `risk.command` | `risk.process_name` | `risk.registry_key` | `risk.protocol` | `risk.hash` | `risk.receipt_time` | `risk.create_time` | `risk.modified_time` | `risk.port` | `risk.bytes` | `risk.message` | `risk.reason` | `risk.id` | `risk.product` | `risk.method` | `risk.severity` | `risk.type` | `risk.action` | `risk.outcome` | `risk.name` |



## Extending CODEX

CODEX is designed to be flexible and easily extensible. You can add new entity definitions, attributes, and relationships as your needs evolve. This extensibility ensures the framework can accommodate new log formats, data types, and evolving cybersecurity use cases.

### Adding New Definitions

To extend CODEX, simply add a new entry in the appropriate document:

1. **Entity Definitions**: Define new entities as they appear in your logs (e.g., "Firewall", "Endpoint").
2. **Attribute Classifications**: Introduce new attributes that are relevant to your log data.
3. **Relationship Models**: If your entities interact in new ways (e.g., a "User" accesses a "Firewall"), define this relationship clearly.

By following this approach, you can maintain a dynamic and scalable data model that adapts to the latest cybersecurity trends and technologies.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

We thank the cybersecurity community for their ongoing contributions and inspiration. Special thanks to the developers of open-source tools that have influenced this framework.
