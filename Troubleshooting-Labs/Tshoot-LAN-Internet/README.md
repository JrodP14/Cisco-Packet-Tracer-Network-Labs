# LAN to Internet Troubleshooting Lab

## Overview
The LAN to Internet Troubleshooting Lab focuses on diagnosing and resolving end-to-end connectivity failures between a LAN host and internet resources. This lab demonstrates structured troubleshooting techniques including DNS testing, Layer 3 connectivity verification, traceroute analysis, and router interface configuration correction.

The objective of this project was to identify why PC1 could not access internet resources, trace the failure point through the network path, correct router IP addressing, and restore full internet connectivity.

---

## Skills Demonstrated
- Network troubleshooting methodology
- DNS troubleshooting
- Layer 3 connectivity testing
- Traceroute analysis
- Router interface configuration
- IP addressing verification
- Cisco IOS CLI configuration
- End-to-end connectivity restoration

---

## Technologies Used
- Cisco IOS
- ICMP/Ping
- Traceroute
- DNS
- Cisco Routers
- Packet Tracer

---

## Lab Objectives
- Verify internet connectivity
- Test DNS functionality
- Test Layer 3 communication
- Trace network path failures
- Identify incorrect router configuration
- Restore internet access

---

# Open Packet Tracer Lab

## Lab File
```text
Tshoot-LAN-Internet.pkt
```

---

# Confirm PC1 Internet Access

## Steps
1. Open:
```text
PC1 Desktop → Web Browser
```

2. Browse to:
```text
www.google.com
```

3. Confirm:
- Web page does not load

### Expected Results
- Internet access failure observed

---

# Troubleshoot PC1 Internet Access

## Step 1 – Verify DNS Resolution

### Open Command Prompt
```text
PC1 Desktop → Command Prompt
```

### Run NSLOOKUP
```bash
nslookup www.google.com
```

### Expected Results
- DNS lookup fails

---

# Step 2 – Verify Layer 3 Connectivity

## Ping Public DNS Server
```bash
ping 8.8.8.8
```

### Expected Results
- Ping fails
- Indicates Layer 3 connectivity issue

---

# Troubleshooting Analysis

## Observation
- DNS does not work
- Layer 3 connectivity also fails

### Conclusion
Problem likely exists:
- Somewhere in routed network path
- Router interface or IP addressing issue

---

# Step 3 – Perform Traceroute

## Trace Network Path
```bash
tracert 8.8.8.8
```

### Purpose
Identifies where connectivity fails along the network path.

### Expected Results
- Traceroute stops at failed hop
- Problem router/path identified

---

# Step 4 – Investigate Router Path

## Verify Router Configurations
Check:
- Interface IP addresses
- Subnet masks
- Connected networks
- Routing configurations

### Focus
WAN-RTR interface configuration

---

# Correct WAN-RTR Private IP Address

## Configure Interface FastEthernet0/0
```bash
(config)#interface fastethernet0/0
(config-if)#ip address 10.10.10.1 255.255.255.252
(config-if)#end
```

### Purpose
Corrects WAN interface addressing to restore routed connectivity.

---

# Save Configuration

## Save Running Configuration
```bash
copy running-config startup-config
```

### Expected Results
- Configuration saved successfully

---

# Verify Connectivity Restoration

## Test Layer 3 Connectivity
```bash
ping 8.8.8.8
```

### Expected Results
- Successful replies received

---

## Verify DNS Resolution
```bash
nslookup www.google.com
```

### Expected Results
- Successful DNS resolution

---

## Verify Web Access
Open browser:
```text
www.google.com
```

### Expected Results
- Website loads successfully
- Full internet connectivity restored

---

# Verification Tasks

## Verify Interface Configuration
```bash
show ip interface brief
```

Expected:
- Correct WAN interface IP configured
- Interface operational

---

## Verify Connectivity
```bash
ping 8.8.8.8
```

Expected:
- Successful ping replies

---

## Verify Traceroute
```bash
tracert 8.8.8.8
```

Expected:
- Complete route path displayed

---

## Verify DNS Resolution
```bash
nslookup www.google.com
```

Expected:
- Successful name resolution

---

# Troubleshooting Concepts Learned
- Structured troubleshooting methodology
- DNS vs Layer 3 failure analysis
- Traceroute path analysis
- Router interface verification
- WAN connectivity troubleshooting
- IP addressing correction
- End-to-end connectivity restoration

---

# Business Value
Troubleshooting routed network connectivity is a core responsibility for network administrators, help desk technicians, and cybersecurity professionals. Understanding how to isolate failures using ping, traceroute, DNS testing, and interface verification is essential for maintaining reliable enterprise network operations.

---

# Files Included
- `Tshoot-LAN-Internet.pkt`
- `Topology.png`
- `LAN-Router-Config.txt`
- `WAN-Router-Config.txt`
- `PC1-Addressing.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional