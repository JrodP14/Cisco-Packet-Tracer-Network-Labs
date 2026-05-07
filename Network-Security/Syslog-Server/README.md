# Syslog Server Configuration Lab

## Overview
The Syslog Server Lab focuses on configuring Cisco IOS logging features and forwarding system log messages to an external Syslog server for centralized monitoring and event management. This lab demonstrates how enterprise network devices generate, synchronize, and transmit logging information for operational visibility and security monitoring.

The objective of this project was to configure router logging, enable remote Syslog forwarding, synchronize console logging messages, and verify centralized log collection.

---

## Skills Demonstrated
- Cisco IOS logging configuration
- Syslog server integration
- Remote log forwarding
- Logging severity configuration
- Console logging synchronization
- Network monitoring concepts
- Enterprise troubleshooting
- Security event visibility

---

## Technologies Used
- Cisco IOS
- Syslog
- Cisco Routers
- Logging Services
- Packet Tracer

---

## Lab Objectives
- View local router logging information
- Configure remote Syslog logging
- Configure logging severity levels
- Synchronize console logging messages
- Modify logging destinations
- Verify centralized logging functionality

---

# View Logging Information on Router0

## Display Local Logs
```bash
show logging
```

### Expected Results
- System logging messages displayed
- Logging buffer information visible
- Logging severity levels shown

---

# Configure Logging to an External Server

## Configure Remote Syslog Server
```bash
(config)#logging <ip address>
```

### Example
```bash
(config)#logging 192.168.1.100
```

### Purpose
Forwards router log messages to a centralized Syslog server.

---

## Configure Logging Severity Level
```bash
(config)#logging trap debugging
```

### Explanation
The `logging trap debugging` command:
- Enables verbose logging
- Sends highly detailed log messages
- Useful for troubleshooting and monitoring

---

# Synchronize Logging Messages with Console

## Configure Console Logging Synchronization
```bash
(config)#line console 0
(config-line)#logging synchronous
```

### Purpose
Prevents logging messages from interrupting command-line input while typing on the console.

---

# Modify Logging Settings

## Disable Console Logging
```bash
(config)#no logging console
```

### Purpose
Stops logging messages from appearing directly on the console.

---

## Enable Monitor Logging
```bash
(config)#logging monitor
```

### Purpose
Displays logging messages on terminal monitor sessions.

---

## Configure Buffered Logging
```bash
(config)#logging buffered
```

### Purpose
Stores logging messages in router memory for later review.

---

# Verification Tasks

## Verify Logging Configuration
```bash
show logging
```

### Expected Results
- Logging server IP displayed
- Logging trap level configured
- Buffered logging enabled
- Active logging destinations shown

---

## Verify Syslog Server Connectivity
```bash
ping <syslog-server-ip>
```

### Expected Results
- Successful connectivity to Syslog server

---

## Verify Remote Log Collection
Generate router events such as:
```bash
shutdown/no shutdown
```

### Expected Results
- Log messages appear on external Syslog server
- Event timestamps recorded

---

## Verify Console Synchronization
Type commands on console while logs generate.

### Expected Results
- Console input remains readable
- Logging messages do not interrupt command entry

---

# Troubleshooting Concepts Learned
- Syslog server communication
- Logging severity levels
- Buffered vs console logging
- Remote event monitoring
- Logging synchronization
- Enterprise log management concepts

---

# Business Value
Centralized Syslog logging is a critical component of enterprise network monitoring, troubleshooting, and cybersecurity operations. Syslog servers enable security teams and network administrators to collect, analyze, and retain logs for incident response, compliance, and operational visibility.

---

# Files Included
- `Syslog-Server.pkt`
- `Topology.png`
- `Router0-Config.txt`
- `Router0-Logging-cmd.txt`
- `Switch1-Config.txt`
- `Switch2-Config.txt`
- `Server-Addresses.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional