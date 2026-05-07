# Speed & Duplex Configuration Lab

## Overview
The Speed & Duplex Configuration Lab focuses on manually configuring Ethernet interface speed and duplex settings on Cisco switches. This lab demonstrates how mismatched interface settings can impact network connectivity and performance, while reinforcing troubleshooting and verification techniques used in enterprise environments.

The objective of this project was to configure interfaces with matching and mismatched speed/duplex settings and observe the effects on Layer 1 and Layer 2 connectivity.

---

## Skills Demonstrated
- Cisco IOS interface configuration
- Ethernet speed configuration
- Duplex mode configuration
- Network troubleshooting
- Layer 1 diagnostics
- Switch interface verification
- Connectivity testing
- Interface status monitoring

---

## Technologies Used
- Cisco IOS
- Cisco Switches
- Ethernet Networking
- Packet Tracer

---

## Lab Objectives
- Verify interface speed and duplex settings
- Configure Gigabit Ethernet interfaces manually
- Force full duplex operation
- Simulate duplex mismatches
- Simulate speed mismatches
- Observe interface failure and recovery behavior
- Verify interface operational status

---

## Initial Interface Verification

### View Interface Details
```bash
show interface <interface>
```

### View Interface Status (Switches)
```bash
show interface <if> status
```

### Expected Results
- Interfaces initially auto-negotiate speed and duplex
- Interfaces display operational status
- Duplex and speed values visible in output

---

## Configure Matching Speed & Duplex Settings

### Switch 0 – Configure G0/1
```bash
(config)#interface g0/1
(config-if)#speed 1000
(config-if)#duplex full
```

### Switch 1 – Configure G0/1
```bash
(config)#interface g0/1
(config-if)#speed 1000
(config-if)#duplex full
```

### Expected Results
- Interface remains operational
- Link status remains up/up
- No connectivity loss observed

---

## Simulate Duplex Mismatch

### Configure Half Duplex
```bash
(config-if)#duplex half
```

### Expected Results
- Interface connection drops
- Link failure occurs due to mismatch

### Restore Full Duplex
```bash
(config-if)#duplex full
```

### Expected Results
- Link restores successfully
- Interface returns to operational state

---

## Simulate Speed Mismatch

### Configure Incorrect Speed
```bash
(config-if)#speed 100
```

### Expected Results
- Interface connection drops
- Link status changes to down

### Restore Correct Speed
```bash
(config-if)#speed 1000
```

### Expected Results
- Interface reconnects
- Link status returns to operational

---

## Verification Tasks

### Verify Interface Operational Status
```bash
show ip interface brief
```

Expected:
- Interfaces display correct operational state

### Verify Speed & Duplex
```bash
show interface g0/1
```

Expected:
- Speed: 1000Mb/s
- Duplex: Full-duplex

### Verify Interface Status
```bash
show interface g0/1 status
```

Expected:
- Connected status
- Correct VLAN assignment
- Correct speed displayed

---

## Troubleshooting Concepts Learned
- Effects of duplex mismatches
- Effects of speed mismatches
- Link negotiation behavior
- Interface recovery procedures
- Physical connectivity diagnostics

---

## Business Value
Understanding speed and duplex negotiation is essential for troubleshooting real-world enterprise network connectivity issues. Misconfigured interfaces can cause severe performance degradation, collisions, and intermittent outages. This lab reinforces practical troubleshooting skills used by network engineers, infrastructure administrators, and cybersecurity professionals.

---

## Files Included
- `Speed-Duplex-Lab.pkt`
- `Topology.png`
- `Switch0-Config.txt`
- `Switch1-Config.txt`

---

## Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional