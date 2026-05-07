# NAT & PAT Configuration Lab

## Overview
The NAT & PAT Lab focuses on configuring Network Address Translation (NAT) and Port Address Translation (PAT) on a Cisco router to allow internal private networks to access external public networks using a shared public IP address. This lab demonstrates inside/outside NAT configuration, ACL-based NAT matching, and translation verification.

The objective of this project was to configure dynamic PAT overload for internal hosts and verify successful address translation and internet connectivity.

---

## Skills Demonstrated
- Network Address Translation (NAT)
- Port Address Translation (PAT)
- Dynamic NAT overload configuration
- ACL-based NAT configuration
- Cisco IOS CLI configuration
- Private-to-public address translation
- Routing and internet connectivity
- Network troubleshooting

---

## Technologies Used
- Cisco IOS
- NAT
- PAT
- Cisco Routers
- Access Control Lists (ACLs)
- Packet Tracer

---

## Lab Objectives
- Define inside local networks with ACLs
- Configure PAT overload
- Configure NAT inside/outside interfaces
- Verify NAT translations
- Validate internet connectivity
- Understand enterprise edge routing concepts

---

# Define the Inside Network with an ACL

## Create Standard ACL
```bash
(config)#ip access-list standard INSIDE
(config-std-nacl)#permit 192.168.10.0 0.0.0.255
(config-std-nacl)#end
```

### Purpose
Defines which internal addresses are eligible for NAT translation.

---

## Verify ACL
```bash
show access-list
```

### Expected Results
- ACL named `INSIDE` displayed
- Internal subnet permitted

---

# Configure PAT Overload

## Configure NAT Overload
```bash
(config)#ip nat inside source list INSIDE interface GigabitEthernet0/1 overload
```

### Purpose
- Translates multiple internal private IPs
- Uses a single public IP address
- Differentiates sessions using port numbers

---

# Configure NAT Inside/Outside Interfaces

## Configure Inside Interface
```bash
(config)#interface g0/0
(config-if)#ip nat inside
```

---

## Configure Outside Interface
```bash
(config)#interface g0/1
(config-if)#ip nat outside
```

### Expected Results
- G0/0 identified as internal interface
- G0/1 identified as external/public interface

---

# Verify NAT Translations

## Display NAT Translation Table
```bash
show ip nat translations
```

### Expected Results
- Inside local addresses translated to public IP
- Active translations displayed
- Port mappings visible

---

# Additional Internet Connectivity Requirements

The following items are also required for full internet access and are already configured within the lab:

1. Configure a default route
2. Create/apply ACL protecting the internet connection
3. Create/apply Cisco IOS firewall inspection rules

---

# Verification Tasks

## Verify ACL Configuration
```bash
show access-list
```

Expected:
- ACL named `INSIDE`
- Correct subnet permitted

---

## Verify NAT Configuration
```bash
show running-config
```

Expected:
- NAT overload configuration present
- Inside/outside interfaces configured correctly

---

## Verify NAT Translations
```bash
show ip nat translations
```

Expected:
- Dynamic translations visible
- Internal IP addresses mapped to external address

---

## Verify NAT Statistics
```bash
show ip nat statistics
```

Expected:
- Translation counters incrementing
- Active translation entries displayed

---

## Verify Connectivity
```bash
ping 8.8.8.8
```

Expected:
- Successful internet connectivity

---

# Troubleshooting Concepts Learned
- NAT inside vs outside interfaces
- ACL-controlled NAT matching
- PAT overload functionality
- Translation table verification
- Internet edge routing concepts
- Public/private IP address translation
- NAT troubleshooting procedures

---

# Business Value
NAT and PAT are essential technologies used in nearly every enterprise network to conserve public IPv4 addresses and securely allow internal hosts to access external resources. Understanding NAT operation is critical for network administration, firewall management, and cybersecurity operations involving edge networking and internet connectivity.

---

# Files Included
- `NAT-PAT.pkt`
- `Topology.png`
- `Router0-Config.txt`
- `Switch-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional