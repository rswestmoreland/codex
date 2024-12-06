# CODEX: Cyber Operations Data eXchange and Extensibility

**CODEX** is a cybersecurity data framework focused on defining and classifying log data entities, attributes, and relationships. Designed for flexibility and extensibility, CODEX provides a set of standards for handling log data, classifying it into well-structured entities, and ensuring compatibility with various storage systems.

## Overview

CODEX provides a comprehensive, well-documented approach to organizing cybersecurity log data. It focuses on defining the entities (e.g., IP addresses, users, events), their attributes (e.g., timestamps, actions), and types (e.g., logs, events, risks) for efficient data classification. The framework is highly extensible, allowing for new definitions to be added as log formats evolve or new data types are introduced.

### Core Documents

The CODEX project is structured around several key definitions documents, which detail the classification, attributes, and relationships of log data:

- **Entity Definitions**: Defines the key entities, such as hosts, users, and services, and their relationships within the cybersecurity landscape.
- **Attribute Classifications**: Describes the attributes associated with each entity (e.g., timestamps, actions, event types).
- **Type Definitions**: Specifies the types of data handled (e.g., Log, Event, Agent, Device, Source, Destination, Network, File, Request, Application, Risk) and how these types are categorized within the system.
- **Relationship Models**: Details how different entities and attributes relate to each other, enabling complex queries and integrations.

## Entity Definitions

The **Entities** define the key components tracked within your cybersecurity data. These are typically the core subjects that your log data records are associated with.

1. **Account**: The user or system account involved in an event or log entry.
2. **Resource**: The specific resource being accessed, used, or targeted.
3. **Command**: The action or command issued by a user or system process.
4. **Host Name**: The name of the machine or host involved in an event.
5. **IP Address**: The network address associated with a system, user, or device.
6. **MAC Address**: The hardware address for network interfaces on a device.
7. **Protocol**: The communication protocol involved (e.g., TCP, HTTP, FTP).
8. **Domain**: The domain related to the event, such as a DNS domain or a domain name system.
9. **URL**: The uniform resource locator involved in the event, usually for web interactions.
10. **Path**: The directory or file path associated with the event.
11. **Hash**: A cryptographic hash used to verify file integrity or identify files.
12. **Process Name**: The name of a running process that is logged during an event.
13. **Registry Key**: A Windows registry key that relates to the event, typically used in system events or malware investigations.
14. **User Name**: The user who is associated with the event or action.
15. **Email Address**: The email address tied to the event, potentially used for phishing, logins, or alerts.

## Attribute Definitions

The **Attributes** define the specific data points or characteristics associated with the entities in the logs. These attributes provide further detail and context to the entity.

1. **Receipt Time**: The time the event or log entry was received.
2. **Create Time**: The time at which the event or data was originally created.
3. **Modified Time**: The time when the data or event was modified.
4. **Port**: The network port used during the communication.
5. **Bytes**: The volume of data transmitted during the event.
6. **Message**: The message or description that accompanies an event.
7. **Reason**: The reason or rationale behind the event (e.g., login failure, action denied).
8. **ID**: A unique identifier associated with the log or event.
9. **Product**: The product involved in the event, such as the software or hardware that generated the log.
10. **Method**: The method or technique used in the event (e.g., HTTP method like GET or POST).
11. **Severity**: The severity level of the event, often used to classify the event's importance or threat level.
12. **Type**: The type of event (e.g., authentication attempt, access violation).
13. **Action**: The specific action performed in the event (e.g., file created, login succeeded).
14. **Outcome**: The result of the event (e.g., success, failure, warning).
15. **Name**: The name or title of the event, entity, or resource.

### Example: Type Definitions

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

## Extending CODEX

CODEX is designed to be flexible and easily extensible. You can add new entity definitions, attributes, and relationships as your needs evolve. This extensibility ensures the framework can accommodate new log formats, data types, and evolving cybersecurity use cases.

### Adding New Definitions

To extend CODEX, simply add a new entry in the appropriate document:

1. **Entity Definitions**: Define new entities as they appear in your logs (e.g., "Firewall", "Endpoint").
2. **Attribute Classifications**: Introduce new attributes that are relevant to your log data.
3. **Relationship Models**: If your entities interact in new ways (e.g., a "User" accesses a "Firewall"), define this relationship clearly. (TBD)

By following this approach, you can maintain a dynamic and scalable data model that adapts to the latest cybersecurity trends and technologies.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

We thank the cybersecurity community for their ongoing contributions and inspiration. Special thanks to the developers of open-source tools that have influenced this framework.
