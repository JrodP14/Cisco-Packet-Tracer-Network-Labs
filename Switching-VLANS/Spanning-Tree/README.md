# Spanning Tree Protocol (STP) Lab

## Overview
The Spanning Tree Protocol (STP) Lab focuses on configuring and analyzing STP behavior in a switched network with redundant links. This lab demonstrates how STP prevents Layer 2 switching loops by electing a root bridge and placing redundant ports into blocking states until needed for failover.

The objective of this project was to observe STP convergence, root bridge election, redundant path activation, and network recovery during link failures.

---

## Skills Demonstrated
- Spanning Tree Protocol (STP)
- Root bridge election
- Redundant link failover
- Cisco IOS CLI configuration
- Layer 2 loop prevention
- Port state analysis
- Enterprise switching concepts
- Network troubleshooting

---

## Technologies Used
- Cisco IOS
- STP
- Cisco Switches
- Layer 2 Switching
- Packet Tracer

---

## Lab Objectives
- View STP status on multiple switches
- Identify the root bridge
- Observe STP port states
- Simulate link failure and recovery
- Observe STP recalculation and convergence
- Configure manual root bridge priority

---

# View STP on SW-0

## Display STP Information
```bash
show spanning-tree
```

### Tasks
- Identify the root bridge
- Observe root ports
- Observe designated ports
- Observe blocked ports

---

# View STP on SW-1 and SW-2

## Display STP Information
```bash
show spanning-tree
```

### Tasks
- Compare STP output across switches
- Observe port roles and states
- Identify redundant links placed into blocking state

---

# Continuous Connectivity Test

## From PC-1
Open Command Prompt:
```bash
ping -t 10.20.30.3
```

### Purpose
- Monitor network connectivity during topology changes
- Observe temporary packet loss during STP recalculation

---

# Simulate Link Failure

## Disconnect Cable
- Remove the cable between SW-2 and SW-0

### Expected Results
- STP detects topology change
- Previously blocked redundant link transitions to forwarding state
- Network connectivity restored automatically

---

# Observe STP Recovery

## Verify STP Status
```bash
show spanning-tree
```

### Tasks
- Observe new root port selection
- Observe updated forwarding/blocking states
- Monitor convergence process

---

# Restore Original Topology

## Reconnect Cable
- Re-attach cable between SW-2 and SW-0

### Expected Results
- STP recalculates topology
- Redundant path returns to blocking state
- Loop prevention maintained

---

# Manually Configure Root Bridge

## Set Switch Priority
```bash
(config)#spanning-tree vlan 1-4096 priority 0
```

### Expected Results
- Switch becomes root bridge
- STP topology recalculates
- Root bridge election changes

---

# Verification Tasks

## Verify Root Bridge
```bash
show spanning-tree
```

Expected:
- Root bridge clearly identified
- Bridge priority displayed

---

## Verify Port Roles & States
```bash
show spanning-tree
```

Expected:
- Root ports identified
- Designated ports forwarding
- Redundant ports blocking

---

## Verify Network Redundancy
```bash
ping -t 10.20.30.3
```

Expected:
- Temporary interruption during failover
- Connectivity restored automatically

---

## Verify Manual Root Bridge Election
```bash
show spanning-tree
```

Expected:
- Configured switch elected as root bridge

---

# STP Concepts Learned
- Layer 2 loop prevention
- Root bridge election
- Root port selection
- Designated and blocked ports
- STP convergence behavior
- Redundant path failover
- Topology recalculation

---

# Business Value
STP is a critical enterprise networking protocol that prevents broadcast storms and switching loops in redundant Layer 2 environments. Understanding STP operation is essential for network engineers and cybersecurity professionals responsible for maintaining resilient and highly available enterprise networks.

---

# Files Included
- `Spanning-Tree.pkt`
- `Topology.png`
- `Switch0-Config.txt`
- `Switch1-Config.txt`
- `Switch2-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional