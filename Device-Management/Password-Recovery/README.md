# Password Recovery Lab

## Overview
The Password Recovery Lab focuses on recovering administrative access to a Cisco router by using ROMMON mode and modifying the configuration register. This lab demonstrates enterprise password recovery procedures used when administrative credentials are lost or inaccessible.

The objective of this project was to enter ROMMON mode, bypass the startup configuration, reset the enable secret password, restore the configuration register, and safely recover full administrative access to the router.

---

## Skills Demonstrated
- Cisco ROMMON access
- Password recovery procedures
- Configuration register management
- Startup configuration recovery
- Cisco IOS CLI configuration
- Administrative access restoration
- Router boot process understanding
- Enterprise troubleshooting

---

## Technologies Used
- Cisco IOS
- ROMMON
- Configuration Register
- Cisco Routers
- Packet Tracer

---

## Lab Objectives
- Enter ROMMON mode
- Modify configuration register values
- Bypass startup configuration
- Recover router configuration
- Reset enable secret password
- Restore normal boot operation

---

# Enter ROMMON Mode

## Steps
1. Connect to the router console
2. Power cycle the router
3. Send the break sequence within 60 seconds during boot

### Expected Results
- Router enters ROMMON mode
- `rommon>` prompt appears

---

# Update the Configuration Register

## Ignore Startup Configuration
```bash
rommon>confreg 0x2142
```

### Purpose
Forces the router to:
- Ignore the startup configuration in NVRAM
- Boot without applying saved passwords

---

## Reload the Router
```bash
rommon>reset
```

### Expected Results
- Router reboots
- Startup configuration bypassed
- Access to router without saved credentials

---

# Restore Startup Configuration into Memory

## Copy Startup Config to Running Config
```bash
copy startup-config running-config
```

### Purpose
Restores the saved router configuration into RAM while allowing password changes.

---

# Reset the Enable Secret Password

## Configure New Password
```bash
(config)#enable secret nexgent
```

### Expected Results
- New privileged EXEC password configured

---

# Restore the Configuration Register

## Configure Normal Boot Value
```bash
(config)#config-register 0x2102
```

### Purpose
Returns router to normal startup behavior.

---

# Save the Configuration

## Save Running Configuration
```bash
copy running-config startup-config
```

### Expected Results
- New password saved permanently
- Router restored to operational state

---

# Configuration Register Values

| Register Value | Purpose |
|---|---|
| 0x2102 | Normal boot |
| 0x2120 | Boot to ROMMON |
| 0x2142 | Ignore NVRAM |

---

# Verification Tasks

## Verify Configuration Register
```bash
show version
```

### Expected Results
- Configuration register set to:
```bash
0x2102
```

---

## Verify New Password
Attempt privileged access:
```bash
enable
```

### Expected Results
- New enable secret password works successfully

---

## Verify Startup Configuration
```bash
show startup-config
```

### Expected Results
- Configuration preserved
- Password updated

---

# Troubleshooting Concepts Learned
- ROMMON recovery procedures
- Configuration register functions
- Startup configuration recovery
- Password reset techniques
- Router boot process troubleshooting
- Administrative access recovery

---

# Business Value
Password recovery procedures are essential administrative and incident response skills used to regain access to critical infrastructure devices. Understanding ROMMON operations and configuration register values is important for network administrators and cybersecurity professionals responsible for maintaining secure and recoverable enterprise environments.

---

# Files Included
- `Password-Recovery.pkt`
- `Topology.png`
- `Router-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional