# CODEX: Cyber Operations Data Entity eXchange

**CODEX** is a cybersecurity data framework focused on defining and classifying log data entities, attributes, and relationships. Designed for flexibility and extensibility, CODEX provides a set of standards for handling log data, classifying it into well-structured entities, and ensuring compatibility with various storage systems.

## Overview

CODEX provides a comprehensive, well-documented approach to organizing cybersecurity log data. It focuses on defining the entities (e.g., IP addresses, users, and events), their attributes (e.g., timestamps, actions), and categories (e.g., logs, events, risks) for efficient data classification. The framework is highly extensible, allowing for new definitions to be added as log formats evolve or new data types are introduced.

### Core Documents

The CODEX project is structured around several key definitions documents, which detail the classification, attributes, and relationships of log data:

- **Category Definitions**: Specifies the types of data handled (e.g., Log, Event, Agent, Device, Source, Destination, Network, File, Request, Application, Risk) and how these types are categorized within the system.
- **Entity Definitions**: Defines the key entities, such as hosts, users, and services, and their relationships within the cybersecurity landscape.
- **Attribute Classifications**: Describes the attributes associated with each entity (e.g., timestamps, actions, event types).
- **Relationship Models**: Details how different entities and attributes relate to each other, enabling complex queries and integrations.

---

## Category Definitions

The **Categories** define the context of the entities and attributes, and serve as a root of the taxonomy. Key names use a lowercase short-form. In data processing systems this can be used to quickly match against certain kinds of events for routing or filtering, either by an exact match (e.g. record.category == 'src') or an anchored pattern (e.g. record =~ /^src_/).

- **Log** (log): A record of an event or activity, typically associated with a system or application (e.g., web server log, firewall log).
- **Event** (evt): A discrete occurrence or action, such as a login attempt, file access, or policy violation.
- **Agent** (agt): A software component or system that generates or collects data (e.g., endpoint agent, SIEM agent).
- **Device** (dvc): Hardware or virtual devices involved in the data transaction or log generation (e.g., routers, firewalls, servers).
- **Source** (src): The origin of the log data or event, such as an IP address or an external device.
- **Destination** (dest): The target or endpoint affected by the event or data transmission (e.g., destination IP address, application).
- **Network** (net): Defines the network layer, connections, and flow of data across devices and systems.
- **File** (file): Represents files or data objects that are being accessed, transferred, or modified in relation to the event (e.g., file name, path).
- **Request** (req): Describes requests made between systems or users, such as HTTP requests, API calls, or database queries.
- **Application** (app): Software or services that interact with the data, such as web applications, databases, or security tools.
- **Risk** (risk): The level of threat or exposure associated with an event or log entry, usually assessed based on severity or impact.

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
16. **Count**: The total occurrences tracked by the originator of the event (e.g., IDS or SIEM).

---

### Taxonomy Matrix

The following table lists all possible keys generated by combining Categories, Entities, and Attributes. By default keys are written using snake case:

| Category x Entity/Attribute | log | evt | agt | dvc | src | dest | net | file | req | app | risk |
|---|---|---|---|---|---|---|---|---|---|---|---|
| account | `log_account` | `evt_account` | `agt_account` | `dvc_account` | `src_account` | `dest_account` | `net_account` | `file_account` | `req_account` | `app_account` | `risk_account` |
| user_name | `log_user_name` | `evt_user_name` | `agt_user_name` | `dvc_user_name` | `src_user_name` | `dest_user_name` | `net_user_name` | `file_user_name` | `req_user_name` | `app_user_name` | `risk_user_name` |
| host_name | `log_host_name` | `evt_host_name` | `agt_host_name` | `dvc_host_name` | `src_host_name` | `dest_host_name` | `net_host_name` | `file_host_name` | `req_host_name` | `app_host_name` | `risk_host_name` |
| ip_address | `log_ip_address` | `evt_ip_address` | `agt_ip_address` | `dvc_ip_address` | `src_ip_address` | `dest_ip_address` | `net_ip_address` | `file_ip_address` | `req_ip_address` | `app_ip_address` | `risk_ip_address` |
| mac_address | `log_mac_address` | `evt_mac_address` | `agt_mac_address` | `dvc_mac_address` | `src_mac_address` | `dest_mac_address` | `net_mac_address` | `file_mac_address` | `req_mac_address` | `app_mac_address` | `risk_mac_address` |
| email_address | `log_email_address` | `evt_email_address` | `agt_email_address` | `dvc_email_address` | `src_email_address` | `dest_email_address` | `net_email_address` | `file_email_address` | `req_email_address` | `app_email_address` | `risk_email_address` |
| resource | `log_resource` | `evt_resource` | `agt_resource` | `dvc_resource` | `src_resource` | `dest_resource` | `net_resource` | `file_resource` | `req_resource` | `app_resource` | `risk_resource` |
| domain | `log_domain` | `evt_domain` | `agt_domain` | `dvc_domain` | `src_domain` | `dest_domain` | `net_domain` | `file_domain` | `req_domain` | `app_domain` | `risk_domain` |
| url | `log_url` | `evt_url` | `agt_url` | `dvc_url` | `src_url` | `dest_url` | `net_url` | `file_url` | `req_url` | `app_url` | `risk_url` |
| path | `log_path` | `evt_path` | `agt_path` | `dvc_path` | `src_path` | `dest_path` | `net_path` | `file_path` | `req_path` | `app_path` | `risk_path` |
| command | `log_command` | `evt_command` | `agt_command` | `dvc_command` | `src_command` | `dest_command` | `net_command` | `file_command` | `req_command` | `app_command` | `risk_command` |
| process_name | `log_process_name` | `evt_process_name` | `agt_process_name` | `dvc_process_name` | `src_process_name` | `dest_process_name` | `net_process_name` | `file_process_name` | `req_process_name` | `app_process_name` | `risk_process_name` |
| registry_key | `log_registry_key` | `evt_registry_key` | `agt_registry_key` | `dvc_registry_key` | `src_registry_key` | `dest_registry_key` | `net_registry_key` | `file_registry_key` | `req_registry_key` | `app_registry_key` | `risk_registry_key` |
| protocol | `log_protocol` | `evt_protocol` | `agt_protocol` | `dvc_protocol` | `src_protocol` | `dest_protocol` | `net_protocol` | `file_protocol` | `req_protocol` | `app_protocol` | `risk_protocol` |
| hash | `log_hash` | `evt_hash` | `agt_hash` | `dvc_hash` | `src_hash` | `dest_hash` | `net_hash` | `file_hash` | `req_hash` | `app_hash` | `risk_hash` |
| id | `log_id` | `evt_id` | `agt_id` | `dvc_id` | `src_id` | `dest_id` | `net_id` | `file_id` | `req_id` | `app_id` | `risk_id` |
| severity | `log_severity` | `evt_severity` | `agt_severity` | `dvc_severity` | `src_severity` | `dest_severity` | `net_severity` | `file_severity` | `req_severity` | `app_severity` | `risk_severity` |
| type | `log_type` | `evt_type` | `agt_type` | `dvc_type` | `src_type` | `dest_type` | `net_type` | `file_type` | `req_type` | `app_type` | `risk_type` |
| action | `log_action` | `evt_action` | `agt_action` | `dvc_action` | `src_action` | `dest_action` | `net_action` | `file_action` | `req_action` | `app_action` | `risk_action` |
| outcome | `log_outcome` | `evt_outcome` | `agt_outcome` | `dvc_outcome` | `src_outcome` | `dest_outcome` | `net_outcome` | `file_outcome` | `req_outcome` | `app_outcome` | `risk_outcome` |
| receipt_time | `log_receipt_time` | `evt_receipt_time` | `agt_receipt_time` | `dvc_receipt_time` | `src_receipt_time` | `dest_receipt_time` | `net_receipt_time` | `file_receipt_time` | `req_receipt_time` | `app_receipt_time` | `risk_receipt_time` |
| create_time | `log_create_time` | `evt_create_time` | `agt_create_time` | `dvc_create_time` | `src_create_time` | `dest_create_time` | `net_create_time` | `file_create_time` | `req_create_time` | `app_create_time` | `risk_create_time` |
| modified_time | `log_modified_time` | `evt_modified_time` | `agt_modified_time` | `dvc_modified_time` | `src_modified_time` | `dest_modified_time` | `net_modified_time` | `file_modified_time` | `req_modified_time` | `app_modified_time` | `risk_modified_time` |
| message | `log_message` | `evt_message` | `agt_message` | `dvc_message` | `src_message` | `dest_message` | `net_message` | `file_message` | `req_message` | `app_message` | `risk_message` |
| reason | `log_reason` | `evt_reason` | `agt_reason` | `dvc_reason` | `src_reason` | `dest_reason` | `net_reason` | `file_reason` | `req_reason` | `app_reason` | `risk_reason` |
| port | `log_port` | `evt_port` | `agt_port` | `dvc_port` | `src_port` | `dest_port` | `net_port` | `file_port` | `req_port` | `app_port` | `risk_port` |
| bytes | `log_bytes` | `evt_bytes` | `agt_bytes` | `dvc_bytes` | `src_bytes` | `dest_bytes` | `net_bytes` | `file_bytes` | `req_bytes` | `app_bytes` | `risk_bytes` |
| product | `log_product` | `evt_product` | `agt_product` | `dvc_product` | `src_product` | `dest_product` | `net_product` | `file_product` | `req_product` | `app_product` | `risk_product` |
| method | `log_method` | `evt_method` | `agt_method` | `dvc_method` | `src_method` | `dest_method` | `net_method` | `file_method` | `req_method` | `app_method` | `risk_method` |
| name | `log_name` | `evt_name` | `agt_name` | `dvc_name` | `src_name` | `dest_name` | `net_name` | `file_name` | `req_name` | `app_name` | `risk_name` |

Many of these keys are not used in practice (e.g., risk_registry_key, file_mac_address) and simply serve to showcase the taxonomy.

## Extending CODEX

CODEX is designed to be flexible and easily extensible. You can add new entity definitions, attributes, and relationships as your needs evolve. This extensibility ensures the framework can accommodate new log formats, data types, and evolving cybersecurity use cases.

### XML Schema File

XML Schema Definition for CODEX [codex.xsd](codex.xsd)

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
