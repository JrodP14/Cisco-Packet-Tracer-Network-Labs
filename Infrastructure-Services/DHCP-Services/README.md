# DHCP Configuration Lab

## Overview
The DHCP Configuration Lab focuses on configuring Dynamic Host Configuration Protocol (DHCP) services on a Cisco router and later transitioning DHCP services to a centralized server using DHCP relay. This lab demonstrates automated IP address management, client configuration, and enterprise DHCP deployment concepts.

The objective of this project was to automate host IP assignment across multiple LANs and implement DHCP relay functionality for centralized address management.

---

## Skills Demonstrated
- Cisco IOS DHCP configuration
- DHCP pool creation
- DHCP exclusions
- DHCP relay configuration
- Centralized DHCP services
- IP address management
- Network troubleshooting
- Host connectivity verification

---

## Technologies Used
- Cisco IOS
- DHCP
- DHCP Relay (IP Helper Address)
- Cisco Routers
- Servers
- Packet Tracer

---

## Network Information

| Network | Gateway | DHCP Scope |
|---|---|---|
| LAN 1 | 10.20.30.1 | 10.20.30.100+ |
| LAN 2 | 172.16.50.1 | 172.16.50.100+ |

### DNS Server
```bash
8.8.8.8
```

---

# Configure DHCP on R0 for LAN 1

### Exclude Static Addresses
```bash
(config)#ip dhcp excluded-address 10.20.30.1 10.20.30.99
```

### Create DHCP Pool
```bash
(config)#ip dhcp pool LAN1
(dhcp-config)#network 10.20.30.0 255.255.255.0
(dhcp-config)#default-router 10.20.30.1
(dhcp-config)#dns-server 8.8.8.8
```

---

# Configure DHCP on R0 for LAN 2

### Exclude Static Addresses
```bash
(config)#ip dhcp excluded-address 172.16.50.1 172.16.50.99
```

### Create DHCP Pool
```bash
(config)#ip dhcp pool LAN2
(dhcp-config)#network 172.16.50.0 255.255.255.0
(dhcp-config)#default-router 172.16.50.1
(dhcp-config)#dns-server 8.8.8.8
```

---

# DHCP Verification

## Verify DHCP Pools
```bash
show ip dhcp pool
```

Expected:
- LAN1 and LAN2 pools visible
- Available leases displayed

---

## Verify DHCP Bindings
```bash
show ip dhcp binding
```

Expected:
- Client MAC addresses listed
- Assigned IP addresses visible

---

## Verify DHCP Processes
```bash
show ip dhcp server statistics
```

Expected:
- DHCP discover/offer/request counters incrementing

---

# Verify Client Connectivity

## Windows Host Verification
```bash
ipconfig
```

Expected:
- Hosts receive valid DHCP addresses
- Correct subnet mask
- Correct default gateway
- DNS server assigned

---

## Connectivity Testing
```bash
ping 10.20.30.1
ping 172.16.50.1
ping 8.8.8.8
```

Expected:
- Successful connectivity to gateways and internet

---

# Move DHCP Services to a Server

## Configure DHCP Services on the Server
- Enable DHCP services on centralized server
- Create DHCP scopes for LAN1 and LAN2

---

## Configure DHCP Relay for LAN 2

### Configure IP Helper Address
```bash
(config)#interface g0/1
(config-if)#ip helper-address 10.20.30.99
```

### Purpose
The `ip helper-address` command forwards DHCP broadcast traffic from LAN 2 clients to the centralized DHCP server located in LAN 1.

---

# Verification Tasks

## Verify DHCP Relay Configuration
```bash
show running-config interface g0/1
```

Expected:
- `ip helper-address 10.20.30.99` present

---

## Verify Clients Receive Addresses from Server
```bash
ipconfig /renew
ipconfig
```

Expected:
- New leases obtained successfully
- Clients continue receiving valid IP addresses

---

## Verify DHCP Server Operation
```bash
show ip dhcp binding
```

Expected:
- Active leases displayed
- Multiple clients assigned addresses

---

# Troubleshooting Concepts Learned
- DHCP scope configuration
- Address exclusion best practices
- DHCP lease verification
- Broadcast forwarding with IP helper
- Centralized DHCP architecture
- Client lease troubleshooting

---

# Business Value
DHCP is a critical enterprise service that automates IP address management and reduces manual configuration errors. Understanding DHCP deployment, troubleshooting, and relay configuration is essential for network administrators and cybersecurity professionals managing scalable enterprise environments.

---

# Files Included
- `DHCP-Services.pkt`
- `Topology.png`
- `Server-DHCP-Config.png`
- `Lan1-Switch-Config.txt`
- `Lan2-Switch-Config.txt`
- `Router0-Config.txt`
- `Server-Addressing.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional