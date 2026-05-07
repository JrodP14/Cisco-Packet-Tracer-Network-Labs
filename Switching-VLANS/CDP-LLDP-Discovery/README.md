# CDP & LLDP Networking Lab

## Overview
The CDP & LLDP Networking Lab focuses on configuring and verifying Cisco Discovery Protocol (CDP) and Link Layer Discovery Protocol (LLDP) within a Cisco networking environment. This lab demonstrates how network devices discover neighboring devices, advertise interface information, and assist with network documentation and troubleshooting.

The project provides hands-on experience with enabling, disabling, and verifying Layer 2 neighbor discovery protocols commonly used in enterprise networks.

---

## Skills Demonstrated
- Cisco Discovery Protocol (CDP)
- Link Layer Discovery Protocol (LLDP)
- Cisco IOS CLI configuration
- Layer 2 neighbor discovery
- Interface-level protocol configuration
- Network troubleshooting
- Device discovery verification
- Enterprise network visibility concepts

---

## Technologies Used
- Cisco IOS
- CDP
- LLDP
- Cisco Switches/Routers
- Packet Tracer

---

## Lab Objectives
- Enable and disable CDP globally
- Enable and disable CDP on interfaces
- View neighboring Cisco devices using CDP
- Enable and disable LLDP globally
- Configure LLDP transmit and receive settings
- Verify neighboring devices using LLDP
- Practice network discovery troubleshooting

---

## CDP Configuration

### Enable CDP Globally
```bash
(config)#cdp run
```

### Disable CDP Globally
```bash
(config)#no cdp run
```

### Enable CDP on an Interface
```bash
(config-if)#cdp enable
```

### Disable CDP on an Interface
```bash
(config-if)#no cdp enable
```

---

## CDP Verification Commands

### View CDP Status
```bash
show cdp
```

### View Neighboring Devices
```bash
show cdp neighbors
```

### View Detailed Neighbor Information
```bash
show cdp neighbors detail
```

---

## LLDP Configuration

### Enable LLDP Globally
```bash
(config)#lldp run
```

### Disable LLDP Globally
```bash
(config)#no lldp run
```

### Enable LLDP Transmission
```bash
(config-if)#lldp transmit
```

### Enable LLDP Reception
```bash
(config-if)#lldp receive
```

### Disable LLDP Transmission
```bash
(config-if)#no lldp transmit
```

### Disable LLDP Reception
```bash
(config-if)#no lldp receive
```

---

## LLDP Verification Commands

### View LLDP Status
```bash
show lldp
```

### View LLDP Neighbors
```bash
show lldp neighbors
```

### View Detailed LLDP Neighbor Information
```bash
show lldp neighbors detail
```

---

## Verification Tasks

### CDP Verification

#### Verify CDP is Enabled
```bash
show cdp
```

Expected:
- CDP operational status displayed

#### Verify Neighbor Discovery
```bash
show cdp neighbors
```

Expected:
- Neighboring Cisco devices listed
- Local and remote interfaces displayed

#### Verify Detailed Device Information
```bash
show cdp neighbors detail
```

Expected:
- Device IP addresses
- Platform information
- Interface details

---

### LLDP Verification

#### Verify LLDP is Enabled
```bash
show lldp
```

Expected:
- LLDP operational status displayed

#### Verify LLDP Neighbor Discovery
```bash
show lldp neighbors
```

Expected:
- Neighbor devices discovered
- Port information displayed

#### Verify Detailed LLDP Information
```bash
show lldp neighbors detail
```

Expected:
- Device capabilities
- System name
- Port IDs
- Management addresses

---

## Business Value
CDP and LLDP are critical protocols used by network engineers and cybersecurity professionals for device discovery, topology mapping, troubleshooting, and asset identification. Understanding these protocols improves visibility into enterprise infrastructure and helps streamline network operations and incident response.

---

## Files Included
- `CDP-LLDP-Lab.pkt`
- `Topology.png`
- `LAN1-Switch-Config.txt`
- `LAN2-Switch-Config.txt`
- `Router-Config.txt`

---

## Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional