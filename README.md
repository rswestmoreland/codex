# CODEX: Cyber Operations Data Entity eXchange

**CODEX** is a cybersecurity data framework focused on defining and classifying log data entities, attributes, and relationships. Designed for flexibility and extensibility, CODEX provides a set of standards for handling log data, classifying it into well-structured entities, and ensuring compatibility with various storage systems.

## Overview

CODEX provides a comprehensive, well-documented approach to organizing cybersecurity log data. It focuses on defining the entities (e.g., IP addresses, users, and events), their attributes (e.g., timestamps, actions), and types (e.g., logs, events, risks) for efficient data classification. The framework is highly extensible, allowing for new definitions to be added as log formats evolve or new data types are introduced.

### Core Documents

The CODEX project is structured around several key definitions documents, which detail the classification, attributes, and relationships of log data:

- **Type Definitions**: Specifies the types of data handled (e.g., Log, Event, Agent, Device, Source, Destination, Network, File, Request, Application, Risk) and how these types are categorized within the system.
- **Entity Definitions**: Defines the key entities, such as hosts, users, and services, and their relationships within the cybersecurity landscape.
- **Attribute Classifications**: Describes the attributes associated with each entity (e.g., timestamps, actions, event types).
- **Relationship Models**: Details how different entities and attributes relate to each other, enabling complex queries and integrations.

---

## Type Definitions

The **Types** define the context of the entities and attributes, and serve as a root of the taxonomy.  In data processing systems this can be used to quickly match against certain kinds of events for routing or filtering, either by an exact match (e.g. record.type == 'src') or an anchored pattern (e.g. record =~ /^src\./).

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

---

### Taxonomy Matrix

The following table lists all possible keys generated by combining Types, Entities, and Attributes.  By default keys are written using snake case:

| Type x Entity/Attribute | log | evt | agt | dvc | src | dest | net | file | req | app | risk |
|---|---|---|---|---|---|---|---|---|---|---|---|
| account | `log.account` | `evt.account` | `agt.account` | `dvc.account` | `src.account` | `dest.account` | `net.account` | `file.account` | `req.account` | `app.account` | `risk.account` |
| user_name | `log.user_name` | `evt.user_name` | `agt.user_name` | `dvc.user_name` | `src.user_name` | `dest.user_name` | `net.user_name` | `file.user_name` | `req.user_name` | `app.user_name` | `risk.user_name` |
| host_name | `log.host_name` | `evt.host_name` | `agt.host_name` | `dvc.host_name` | `src.host_name` | `dest.host_name` | `net.host_name` | `file.host_name` | `req.host_name` | `app.host_name` | `risk.host_name` |
| ip_address | `log.ip_address` | `evt.ip_address` | `agt.ip_address` | `dvc.ip_address` | `src.ip_address` | `dest.ip_address` | `net.ip_address` | `file.ip_address` | `req.ip_address` | `app.ip_address` | `risk.ip_address` |
| mac_address | `log.mac_address` | `evt.mac_address` | `agt.mac_address` | `dvc.mac_address` | `src.mac_address` | `dest.mac_address` | `net.mac_address` | `file.mac_address` | `req.mac_address` | `app.mac_address` | `risk.mac_address` |
| email_address | `log.email_address` | `evt.email_address` | `agt.email_address` | `dvc.email_address` | `src.email_address` | `dest.email_address` | `net.email_address` | `file.email_address` | `req.email_address` | `app.email_address` | `risk.email_address` |
| resource | `log.resource` | `evt.resource` | `agt.resource` | `dvc.resource` | `src.resource` | `dest.resource` | `net.resource` | `file.resource` | `req.resource` | `app.resource` | `risk.resource` |
| domain | `log.domain` | `evt.domain` | `agt.domain` | `dvc.domain` | `src.domain` | `dest.domain` | `net.domain` | `file.domain` | `req.domain` | `app.domain` | `risk.domain` |
| url | `log.url` | `evt.url` | `agt.url` | `dvc.url` | `src.url` | `dest.url` | `net.url` | `file.url` | `req.url` | `app.url` | `risk.url` |
| path | `log.path` | `evt.path` | `agt.path` | `dvc.path` | `src.path` | `dest.path` | `net.path` | `file.path` | `req.path` | `app.path` | `risk.path` |
| command | `log.command` | `evt.command` | `agt.command` | `dvc.command` | `src.command` | `dest.command` | `net.command` | `file.command` | `req.command` | `app.command` | `risk.command` |
| process_name | `log.process_name` | `evt.process_name` | `agt.process_name` | `dvc.process_name` | `src.process_name` | `dest.process_name` | `net.process_name` | `file.process_name` | `req.process_name` | `app.process_name` | `risk.process_name` |
| registry_key | `log.registry_key` | `evt.registry_key` | `agt.registry_key` | `dvc.registry_key` | `src.registry_key` | `dest.registry_key` | `net.registry_key` | `file.registry_key` | `req.registry_key` | `app.registry_key` | `risk.registry_key` |
| protocol | `log.protocol` | `evt.protocol` | `agt.protocol` | `dvc.protocol` | `src.protocol` | `dest.protocol` | `net.protocol` | `file.protocol` | `req.protocol` | `app.protocol` | `risk.protocol` |
| hash | `log.hash` | `evt.hash` | `agt.hash` | `dvc.hash` | `src.hash` | `dest.hash` | `net.hash` | `file.hash` | `req.hash` | `app.hash` | `risk.hash` |
| id | `log.id` | `evt.id` | `agt.id` | `dvc.id` | `src.id` | `dest.id` | `net.id` | `file.id` | `req.id` | `app.id` | `risk.id` |
| severity | `log.severity` | `evt.severity` | `agt.severity` | `dvc.severity` | `src.severity` | `dest.severity` | `net.severity` | `file.severity` | `req.severity` | `app.severity` | `risk.severity` |
| type | `log.type` | `evt.type` | `agt.type` | `dvc.type` | `src.type` | `dest.type` | `net.type` | `file.type` | `req.type` | `app.type` | `risk.type` |
| action | `log.action` | `evt.action` | `agt.action` | `dvc.action` | `src.action` | `dest.action` | `net.action` | `file.action` | `req.action` | `app.action` | `risk.action` |
| outcome | `log.outcome` | `evt.outcome` | `agt.outcome` | `dvc.outcome` | `src.outcome` | `dest.outcome` | `net.outcome` | `file.outcome` | `req.outcome` | `app.outcome` | `risk.outcome` |
| receipt_time | `log.receipt_time` | `evt.receipt_time` | `agt.receipt_time` | `dvc.receipt_time` | `src.receipt_time` | `dest.receipt_time` | `net.receipt_time` | `file.receipt_time` | `req.receipt_time` | `app.receipt_time` | `risk.receipt_time` |
| create_time | `log.create_time` | `evt.create_time` | `agt.create_time` | `dvc.create_time` | `src.create_time` | `dest.create_time` | `net.create_time` | `file.create_time` | `req.create_time` | `app.create_time` | `risk.create_time` |
| modified_time | `log.modified_time` | `evt.modified_time` | `agt.modified_time` | `dvc.modified_time` | `src.modified_time` | `dest.modified_time` | `net.modified_time` | `file.modified_time` | `req.modified_time` | `app.modified_time` | `risk.modified_time` |
| message | `log.message` | `evt.message` | `agt.message` | `dvc.message` | `src.message` | `dest.message` | `net.message` | `file.message` | `req.message` | `app.message` | `risk.message` |
| reason | `log.reason` | `evt.reason` | `agt.reason` | `dvc.reason` | `src.reason` | `dest.reason` | `net.reason` | `file.reason` | `req.reason` | `app.reason` | `risk.reason` |
| port | `log.port` | `evt.port` | `agt.port` | `dvc.port` | `src.port` | `dest.port` | `net.port` | `file.port` | `req.port` | `app.port` | `risk.port` |
| bytes | `log.bytes` | `evt.bytes` | `agt.bytes` | `dvc.bytes` | `src.bytes` | `dest.bytes` | `net.bytes` | `file.bytes` | `req.bytes` | `app.bytes` | `risk.bytes` |
| product | `log.product` | `evt.product` | `agt.product` | `dvc.product` | `src.product` | `dest.product` | `net.product` | `file.product` | `req.product` | `app.product` | `risk.product` |
| method | `log.method` | `evt.method` | `agt.method` | `dvc.method` | `src.method` | `dest.method` | `net.method` | `file.method` | `req.method` | `app.method` | `risk.method` |
| name | `log.name` | `evt.name` | `agt.name` | `dvc.name` | `src.name` | `dest.name` | `net.name` | `file.name` | `req.name` | `app.name` | `risk.name` |

Many of these keys are not used in practice (e.g., risk.registry_key, file.mac_address) and simply serve to showcase the taxonomy.

## Extending CODEX

CODEX is designed to be flexible and easily extensible. You can add new entity definitions, attributes, and relationships as your needs evolve. This extensibility ensures the framework can accommodate new log formats, data types, and evolving cybersecurity use cases.

### Adding New Definitions

To extend CODEX, simply add a new entry in the appropriate document:

1. **Entity Definitions**: Define new entities as they appear in your logs (e.g., "Serial", "Cookie").
2. **Attribute Classifications**: Introduce new attributes that are relevant to your log data.
3. **Relationship Models**: If your entities interact in new ways (e.g., a "User" accesses a "Firewall"), define this relationship clearly.

By following this approach, you can maintain a dynamic and scalable data model that adapts to the latest cybersecurity trends and technologies.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

We thank the cybersecurity community for their ongoing contributions and inspiration. Special thanks to the developers of open-source tools that have influenced this framework.
