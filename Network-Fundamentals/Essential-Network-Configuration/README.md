# Essential Networking Lab

## Overview
The Essential Networking Lab is a foundational Cisco networking project focused on configuring basic router and switch connectivity between two LANs. This lab demonstrates core networking concepts including interface configuration, IP addressing, default gateways, Layer 2 switching, and configuration persistence.

The objective of this project was to establish communication between multiple network segments while practicing essential Cisco IOS configuration commands.

---

## Skills Demonstrated
- Cisco IOS CLI navigation
- Basic router configuration
- Basic switch configuration
- Interface configuration
- IPv4 addressing
- Default gateway configuration
- LAN connectivity setup
- Network device management
- Configuration saving and persistence
- Basic troubleshooting

---

## Devices Used
- 1 Cisco Router
  - ICND1-RTR
- 1 Cisco Switch
  - ICND1-SW
- End-user hosts/workstations

---

## Network Configuration

### Router Interfaces

| Interface | IP Address | Description |
|---|---|---|
| G0/0 | 10.20.30.1/24 | LAN 1 Gateway |
| G0/1 | 172.16.50.1/24 | LAN 2 Gateway |

### Switch Management Interface

| Interface | IP Address | Purpose |
|---|---|---|
| VLAN 1 | 10.20.30.254/24 | Switch Management |

### Default Gateway
```bash
10.20.30.1
```

---

## Key Configurations

### Router Configuration
- Configured hostname
- Enabled router interfaces
- Assigned IPv4 addresses
- Added interface descriptions

### Switch Configuration
- Configured hostname
- Configured management VLAN interface
- Assigned management IP address
- Configured default gateway
- Enabled uplink interface

### Configuration Persistence
- Saved running configuration to startup configuration

---

## Verification Tasks

### Router Verification

#### Verify Interface Status
```bash
show ip interface brief
```

Expected:
- G0/0 = up/up
- G0/1 = up/up

#### Verify Running Configuration
```bash
show running-config
```

Expected:
- Correct hostname
- Correct interface IP addresses
- Interface descriptions present

#### Verify Connectivity
```bash
ping 10.20.30.254
```

Expected:
- Successful replies from switch management interface

---

### Switch Verification

#### Verify VLAN Interface
```bash
show ip interface brief
```

Expected:
- VLAN 1 = up/up
- IP Address = 10.20.30.254

#### Verify Default Gateway
```bash
show running-config | include default-gateway
```

Expected:
```bash
ip default-gateway 10.20.30.1
```

#### Verify Interface Status
```bash
show interfaces status
```

Expected:
- G0/1 connected to router
- Interface status operational

---

### End Device Verification

#### Verify Host IP Configuration
```bash
ipconfig
```

Expected:
- Valid IP address in correct subnet
- Proper default gateway assigned

#### Verify Network Connectivity
```bash
ping 10.20.30.1
ping 172.16.50.1
```

Expected:
- Successful ping replies

---

## Business Value
This lab builds foundational networking knowledge required for IT support, network administration, and cybersecurity roles. Understanding basic router and switch configuration is critical for troubleshooting enterprise environments and supporting secure network infrastructure.

---

## Files Included
- `Essential-Networking-Lab.pkt`
- `Topology.png`
- `LAN1-Switch-Config.txt`
- `Router-Config.txt`

---

## Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional