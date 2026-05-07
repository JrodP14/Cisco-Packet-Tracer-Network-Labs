# FSNA Final Lab

## Overview
The FSNA Final Lab is a comprehensive Cisco Packet Tracer project designed to simulate a small enterprise network environment. This lab demonstrates foundational networking concepts including VLAN segmentation, inter-VLAN routing, DHCP services, SSH hardening, trunking, VoIP integration, wireless networking, QoS, and internet connectivity.

This project was completed as part of hands-on Cisco networking and infrastructure training to strengthen practical enterprise networking skills.

---

## Skills Demonstrated
- Cisco IOS configuration
- VLAN creation and segmentation
- Inter-VLAN routing (Router-on-a-Stick)
- Layer 2 switching
- Spanning Tree Protocol (STP)
- SSH hardening and remote management
- DHCP configuration
- NAT and default routing
- VoIP phone configuration
- Wireless access point setup
- QoS configuration for voice traffic
- Network troubleshooting and verification

---

## Network Topology
### Devices Used
- 2 Cisco Switches
  - FSNA-SW1
  - FSNA-SW2
- 1 Cisco Router
  - FSNA-RTR
- Wireless Access Point
- VoIP Phones
- End-user PCs
- Tablet-PC Wireless Client

---

## VLAN Structure

| VLAN | Name  | Purpose |
|------|-------|----------|
| 100 | MGMT | Management |
| 150 | VOICE | Voice Traffic |
| 200 | DATA | User Data |

---

## Key Configurations

### Switching
- Access and trunk port configuration
- STP root bridge configuration
- QoS trust settings
- VLAN implementation

### Security
- SSH-only remote access
- Local user authentication
- Encrypted passwords
- ACL restrictions on VTY access

### Routing
- Router-on-a-Stick inter-VLAN routing
- Default static route
- NAT configuration

### Services
- DHCP pool deployment
- VoIP ephone registration
- WPA2 wireless security

---

## Verification Tasks
The following validations were completed:

### Connectivity
- End devices obtained DHCP addresses
- Successful inter-VLAN communication
- Internet connectivity verified using:
  - `ping 8.8.8.8`
  - Web browser testing

### Switching
- VLAN assignments verified
- Trunk interfaces operational
- STP root bridge confirmed

### Voice
- VoIP phones registered successfully
- Internal calls functional

### Wireless
- Wireless clients authenticated using WPA2
- DHCP assignment successful
- Internet access verified

---

## Business Value
This project simulates real-world enterprise network deployment and troubleshooting scenarios commonly encountered in IT support, network administration, and cybersecurity environments. The lab reinforces core networking concepts required for Cisco networking roles and security-focused infrastructure positions.

---

## Files Included
- 'FSNA-Final-Lab.pkt'
- 'Topology.png'
- 'FSNA-WirelessAP-Config.png'
- 'FSNA-Switch1-Config.txt'
- 'FSNA-Switch2-Config.txt'
- 'FSNA-Router-Config.txt'
- 'NOC-PC-Addressing.txt'
- 'UserA-Addressing.txt'
- 'UserB-Addressing.txt'
- 'TabletPC-Addressing.txt'

---
## Author
Jarrod Pettis
Aspiring Cybersecurity & Network Professional