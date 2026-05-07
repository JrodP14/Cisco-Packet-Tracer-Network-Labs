# InterVLAN Routing – Router-on-a-Stick Lab

## Overview
The InterVLAN Routing – Router-on-a-Stick Lab focuses on configuring a Cisco router to perform routing between VLANs using 802.1Q sub-interfaces over a single trunk link. This lab demonstrates how multiple VLANs can communicate through one physical router interface connected to a trunk port on a switch.

The objective of this project was to configure router sub-interfaces, establish VLAN trunking between the router and switch, and verify successful communication between VLANs.

---

## Skills Demonstrated
- Router-on-a-Stick configuration
- InterVLAN routing
- 802.1Q trunking
- Router sub-interface configuration
- Cisco IOS CLI configuration
- VLAN gateway deployment
- Layer 3 troubleshooting
- Enterprise network segmentation

---

## Technologies Used
- Cisco IOS
- Router-on-a-Stick
- VLANs
- 802.1Q Trunking
- Cisco Routers
- Cisco Switches
- Packet Tracer

---

## VLAN & Gateway Information

| VLAN | Network | Gateway |
|---|---|---|
| VLAN 100 | 192.168.100.0/24 | 192.168.100.1 |
| VLAN 200 | 10.10.10.0/24 | 10.10.10.1 |

---

# Configure Router Physical Interface

## Configure Interface G0/0
```bash
(config)#interface g0/0
(config-if)#no shutdown
(config-if)#description LAN Gateway
```

### Important Note
No IP address is configured on the physical interface because VLAN routing will be handled using sub-interfaces.

---

## Save Configuration
```bash
copy run start
```

---

## Physical Connectivity
- Connect Router G0/0 to Lab-SW1 G0/2
- Use a straight-through Ethernet cable

---

# Configure Trunk Port on Lab-SW1

## Configure Interface G0/2
```bash
(config)#interface g0/2
(config-if)#switchport mode trunk
(config-if)#description Trunk to Router
```

---

## Save Configuration
```bash
copy run start
```

### Expected Results
- Trunk link becomes operational
- Router and switch establish Layer 2 connectivity

---

# Configure Router Sub-Interfaces

## Configure VLAN 100 Sub-Interface
```bash
(config)#interface g0/0.100
(config-subif)#encapsulation dot1q 100
(config-subif)#ip address 192.168.100.1 255.255.255.0
(config-subif)#description VLAN 100 Gateway
```

---

## Configure VLAN 200 Sub-Interface
```bash
(config)#interface g0/0.200
(config-subif)#encapsulation dot1q 200
(config-subif)#ip address 10.10.10.1 255.255.255.0
(config-subif)#description VLAN 200 Gateway
```

---

# Verification Tasks

## Verify Interface Status
```bash
show ip interface brief
```

Expected:
- G0/0 = up/up
- G0/0.100 = up/up
- G0/0.200 = up/up

---

## Verify Trunk Operation
```bash
show interfaces trunk
```

Expected:
- Trunk operational on switch port G0/2
- VLANs 100 and 200 passing traffic

---

## Verify Router Configuration
```bash
show running-config
```

Expected:
- Sub-interfaces configured correctly
- Dot1Q encapsulation present
- Correct IP addressing assigned

---

# Test InterVLAN Connectivity

## From PC1
```bash
ping 10.10.10.50
ping 10.10.10.51
```

---

## From PC3
```bash
ping 192.168.100.50
ping 192.168.100.51
```

### Expected Results
- Successful communication between VLANs
- InterVLAN routing functioning properly

---

# Additional Connectivity Tests

## Verify Gateway Reachability
Hosts should successfully ping:
```bash
192.168.100.1
10.10.10.1
```

---

## Verify Router Reachability
From the router:
```bash
ping 192.168.100.50
ping 10.10.10.50
```

### Expected Results
- Router can reach all devices
- End hosts can reach gateways and remote VLANs

---

# Troubleshooting Concepts Learned
- Router-on-a-Stick architecture
- 802.1Q encapsulation
- Router sub-interface operation
- VLAN trunk troubleshooting
- InterVLAN routing verification
- Layer 2 and Layer 3 integration

---

# Business Value
Router-on-a-Stick is a widely used networking solution for small-to-medium enterprise environments that require VLAN segmentation with centralized routing. Understanding this architecture strengthens practical networking skills used in network administration, infrastructure engineering, and cybersecurity operations.

---

# Files Included
- `InterVLAN-Router-on-a-Stick.pkt`
- `Topology.png`
- `Router-Config.txt`
- `Switch1-Config.txt`
- `Switch2-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional