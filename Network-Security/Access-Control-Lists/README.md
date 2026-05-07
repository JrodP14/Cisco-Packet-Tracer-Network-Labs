# Access Control Lists (ACLs) Lab

## Overview
The Access Control Lists (ACLs) Lab focuses on implementing standard and extended ACLs on Cisco routers to control network traffic and secure administrative access. This lab demonstrates packet filtering based on source addresses, destination addresses, protocols, and ports while reinforcing enterprise network security concepts.

The objective of this project was to configure ACLs to restrict host communication, secure remote router management, and limit insecure web traffic access.

---

## Skills Demonstrated
- Standard ACL configuration
- Extended ACL configuration
- Interface ACL application
- VTY line access control
- Traffic filtering
- Network security implementation
- Cisco IOS CLI configuration
- ACL troubleshooting and verification

---

## Technologies Used
- Cisco IOS
- Access Control Lists (ACLs)
- Cisco Routers
- Cisco Switches
- Packet Tracer

---

## Lab Objectives
- Create standard ACLs
- Create extended ACLs
- Apply ACLs to interfaces
- Apply ACLs to VTY lines
- Restrict host access between networks
- Secure remote management access
- Filter insecure internet traffic

---

# ACL Rules & Concepts

## Standard ACLs
### Characteristics
- Numbered range: `1–99`
- Filter based on source IP address only
- Typically placed closest to the destination

### Syntax
```bash
(config)#access-list <1-99> <permit | deny> <source-ipv4> <wildcard-mask>
```

---

## Extended ACLs
### Characteristics
- Numbered range: `100–199`
- Filter based on:
  - Protocol
  - Source IP
  - Destination IP
  - Port numbers
- Typically placed closest to the source

### Syntax
```bash
(config)#access-list <100-199> <permit | deny> <protocol> <source-ipv4> <source-wildcard-mask> <destination-ipv4> <destination-wildcard-mask> eq <port>
```

---

# ACL Requirements

## Requirement 1
Deny host `192.168.100.50` from accessing network:
```text
10.10.10.0/24
```

---

## Requirement 2
Permit only network:
```text
10.10.10.0/24
```
to remotely access the router through VTY lines.

---

## Requirement 3
Prevent host:
```text
10.10.10.50
```
from accessing non-secure web pages on the internet.

---

# Configure Standard ACL

## Example Standard ACL
```bash
(config)#access-list 10 deny host 192.168.100.50
(config)#access-list 10 permit any
```

### Purpose
Blocks traffic from host:
```text
192.168.100.50
```

---

# Apply ACL to Interface

## Interface ACL Configuration
```bash
(config-if)#ip access-group 10 in
```

### Syntax
```bash
(config-if)#ip access-group <acl-number/name> <in | out>
```

### Expected Results
- ACL filters traffic entering or leaving interface
- Restricted host unable to reach destination network

---

# Configure Extended ACL

## Example Extended ACL
```bash
(config)#access-list 101 deny tcp host 10.10.10.50 any eq 80
(config)#access-list 101 permit ip any any
```

### Purpose
Blocks insecure HTTP web traffic from:
```text
10.10.10.50
```

---

# Apply ACL to VTY Lines

## Restrict Router Management Access
```bash
(config-line)#access-class 10 in
```

### Syntax
```bash
(config-line)#access-class <acl-number/name> <in | out>
```

### Expected Results
- Only permitted network can access router remotely
- Unauthorized hosts denied VTY access

---

# Verification Tasks

## Verify ACL Configuration
```bash
show access-lists
```

### Expected Results
- ACL entries displayed
- Hit counters increment during testing

---

## Verify Interface ACL Application
```bash
show running-config
```

### Expected Results
- ACLs applied to interfaces
- Correct direction configured

---

## Verify VTY Restrictions
Attempt remote access from:
- Allowed network → Success
- Denied network → Failure

---

## Verify Traffic Filtering

### Test Denied Access
```bash
ping 10.10.10.x
```

Expected:
- Blocked host unable to communicate

---

## Verify Web Restrictions
Attempt HTTP browsing from:
```text
10.10.10.50
```

Expected:
- HTTP traffic blocked
- HTTPS traffic may still function if permitted

---

# Troubleshooting Concepts Learned
- ACL processing order
- Implicit deny behavior
- Standard vs Extended ACL placement
- Interface traffic filtering
- Remote management security
- Protocol and port filtering
- ACL verification and debugging

---

# Business Value
ACLs are one of the most important foundational security technologies in enterprise networking. They are used to enforce traffic policies, segment networks, restrict unauthorized access, and protect infrastructure devices. Understanding ACL implementation is critical for network engineers, SOC analysts, and cybersecurity professionals managing secure enterprise environments.

---

# Files Included
- `Access-Control-Lists.pkt`
- `Topology.png`
- `ZTE-Router-Config.txt`
- `ZTE-Switch1-Config.txt`
- `ZTE-Switch2-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional