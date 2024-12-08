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

The entity and attributes are prefixed with types, giving the available table of keys:

# Generated Keys for CODEX

The following table lists all possible keys generated by combining Types, Entities, and Attributes:

| Type \ Entity/Attribute | account | user_name | host_name | ip_address | mac_address | email_address | resource | domain | url | path | command | process_name | registry_key | protocol | hash | receipt_time | create_time | modified_time | port | bytes | message | reason | id | product | method | severity | type | action | outcome | name |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Log | `log.account` | `log.user_name` | `log.host_name` | `log.ip_address` | `log.mac_address` | `log.email_address` | `log.resource` | `log.domain` | `log.url` | `log.path` | `log.command` | `log.process_name` | `log.registry_key` | `log.protocol` | `log.hash` | `log.receipt_time` | `log.create_time` | `log.modified_time` | `log.port` | `log.bytes` | `log.message` | `log.reason` | `log.id` | `log.product` | `log.method` | `log.severity` | `log.type` | `log.action` | `log.outcome` | `log.name` |
| Event | `event.account` | `event.user_name` | `event.host_name` | `event.ip_address` | `event.mac_address` | `event.email_address` | `event.resource` | `event.domain` | `event.url` | `event.path` | `event.command` | `event.process_name` | `event.registry_key` | `event.protocol` | `event.hash` | `event.receipt_time` | `event.create_time` | `event.modified_time` | `event.port` | `event.bytes` | `event.message` | `event.reason` | `event.id` | `event.product` | `event.method` | `event.severity` | `event.type` | `event.action` | `event.outcome` | `event.name` |
| Agent | `agent.account` | `agent.user_name` | `agent.host_name` | `agent.ip_address` | `agent.mac_address` | `agent.email_address` | `agent.resource` | `agent.domain` | `agent.url` | `agent.path` | `agent.command` | `agent.process_name` | `agent.registry_key` | `agent.protocol` | `agent.hash` | `agent.receipt_time` | `agent.create_time` | `agent.modified_time` | `agent.port` | `agent.bytes` | `agent.message` | `agent.reason` | `agent.id` | `agent.product` | `agent.method` | `agent.severity` | `agent.type` | `agent.action` | `agent.outcome` | `agent.name` |
| Device | `device.account` | `device.user_name` | `device.host_name` | `device.ip_address` | `device.mac_address` | `device.email_address` | `device.resource` | `device.domain` | `device.url` | `device.path` | `device.command` | `device.process_name` | `device.registry_key` | `device.protocol` | `device.hash` | `device.receipt_time` | `device.create_time` | `device.modified_time` | `device.port` | `device.bytes` | `device.message` | `device.reason` | `device.id` | `device.product` | `device.method` | `device.severity` | `device.type` | `device.action` | `device.outcome` | `device.name` |
| Source | `source.account` | `source.user_name` | `source.host_name` | `source.ip_address` | `source.mac_address` | `source.email_address` | `source.resource` | `source.domain` | `source.url` | `source.path` | `source.command` | `source.process_name` | `source.registry_key` | `source.protocol` | `source.hash` | `source.receipt_time` | `source.create_time` | `source.modified_time` | `source.port` | `source.bytes` | `source.message` | `source.reason` | `source.id` | `source.product` | `source.method` | `source.severity` | `source.type` | `source.action` | `source.outcome` | `source.name` |
| Destination | `destination.account` | `destination.user_name` | `destination.host_name` | `destination.ip_address` | `destination.mac_address` | `destination.email_address` | `destination.resource` | `destination.domain` | `destination.url` | `destination.path` | `destination.command` | `destination.process_name` | `destination.registry_key` | `destination.protocol` | `destination.hash` | `destination.receipt_time` | `destination.create_time` | `destination.modified_time` | `destination.port` | `destination.bytes` | `destination.message` | `destination.reason` | `destination.id` | `destination.product` | `destination.method` | `destination.severity` | `destination.type` | `destination.action` | `destination.outcome` | `destination.name` |
| Network | `network.account` | `network.user_name` | `network.host_name` | `network.ip_address` | `network.mac_address` | `network.email_address` | `network.resource` | `network.domain` | `network.url` | `network.path` | `network.command` | `network.process_name` | `network.registry_key` | `network.protocol` | `network.hash` | `network.receipt_time` | `network.create_time` | `network.modified_time` | `network.port` | `network.bytes` | `network.message` | `network.reason` | `network.id` | `network.product` | `network.method` | `network.severity` | `network.type` | `network.action` | `network.outcome` | `network.name` |
| File | `file.account` | `file.user_name` | `file.host_name` | `file.ip_address` | `file.mac_address` | `file.email_address` | `file.resource` | `file.domain` | `file.url` | `file.path` | `file.command` | `file.process_name` | `file.registry_key` | `file.protocol` | `file.hash` | `file.receipt_time` | `file.create_time` | `file.modified_time` | `file.port` | `file.bytes` | `file.message` | `file.reason` | `file.id` | `file.product` | `file.method` | `file.severity` | `file.type` | `file.action` | `file.outcome` | `file.name` |
| Request | `request.account` | `request.user_name` | `request.host_name` | `request.ip_address` | `request.mac_address` | `request.email_address` | `request.resource` | `request.domain` | `request.url` | `request.path` | `request.command` | `request.process_name` | `request.registry_key` | `request.protocol` | `request.hash` | `request.receipt_time` | `request.create_time` | `request.modified_time` | `request.port` | `request.bytes` | `request.message` | `request.reason` | `request.id` | `request.product` | `request.method` | `request.severity` | `request.type` | `request.action` | `request.outcome` | `request.name` |
| Application | `application.account` | `application.user_name` | `application.host_name` | `application.ip_address` | `application.mac_address` | `application.email_address` | `application.resource` | `application.domain` | `application.url` | `application.path` | `application.command` | `application.process_name` | `application.registry_key` | `application.protocol` | `application.hash` | `application.receipt_time` | `application.create_time` | `application.modified_time` | `application.port` | `application.bytes` | `application.message` | `application.reason` | `application.id` | `application.product` | `application.method` | `application.severity` | `application.type` | `application.action` | `application.outcome` | `application.name` |
| Risk | `risk.account` | `risk.user_name` | `risk.host_name` | `risk.ip_address` | `risk.mac_address` | `risk.email_address` | `risk.resource` | `risk.domain` | `risk.url` | `risk.path` | `risk.command` | `risk.process_name` | `risk.registry_key` | `risk.protocol` | `risk.hash` | `risk.receipt_time` | `risk.create_time` | `risk.modified_time` | `risk.port` | `risk.bytes` | `risk.message` | `risk.reason` | `risk.id` | `risk.product` | `risk.method` | `risk.severity` | `risk.type` | `risk.action` | `risk.outcome` | `risk.name` |


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
