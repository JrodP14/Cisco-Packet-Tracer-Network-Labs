# License Management Lab

## Overview
The License Management Lab focuses on enabling Cisco router security features using a Right-To-Use (RTU) technology package license. This lab demonstrates how enterprise routers activate additional feature sets such as Securityk9 through Cisco IOS licensing mechanisms.

The objective of this project was to activate the Security technology package on a Cisco 1941 router, reload the device, and verify successful license activation.

---

## Skills Demonstrated
- Cisco IOS license management
- Right-To-Use (RTU) licensing
- Technology package activation
- Router reload procedures
- Cisco IOS verification commands
- Enterprise router administration
- Security feature enablement
- Infrastructure maintenance

---

## Technologies Used
- Cisco IOS
- Cisco 1941 Router
- Securityk9 License
- Right-To-Use Licensing
- Packet Tracer

---

## Lab Objectives
- Enable Cisco security technology package
- Activate Securityk9 license
- Reload router to apply license
- Verify active technology packages
- Understand Cisco licensing concepts

---

# Enable Security Features via RTU License

## Configure Security Technology Package
```bash
(config)#license boot module c1900 technology-package securityk9
```

### Purpose
Activates the:
```text
securityk9
```
technology package on the Cisco 1900 series router.

### Features Enabled
Depending on IOS version, Securityk9 may enable:
- VPN services
- Firewall capabilities
- IPS/IDS functionality
- Advanced security features

---

# Reload Router

## Reboot Device
```bash
reload
```

### Purpose
Applies the new license package during startup.

### Expected Results
- Router reloads successfully
- Security package activates after reboot

---

# Verify License Features

## Display License Information
```bash
show license feature
```

### Expected Results
- Securityk9 package listed
- License status displayed as enabled/active

---

# Verification Tasks

## Verify License Activation
```bash
show license feature
```

Expected:
- `securityk9` listed as active

---

## Verify Boot Configuration
```bash
show running-config
```

Expected:
- License boot command present

---

## Verify Router Reload
```bash
show version
```

Expected:
- Router operating normally after reload
- Technology package information visible

---

# Troubleshooting Concepts Learned
- Cisco RTU licensing
- Technology package activation
- Feature licensing verification
- Router reboot procedures
- Enterprise feature management
- Security package enablement

---

# Business Value
Cisco licensing management is an important enterprise networking skill used to enable advanced routing, security, and VPN capabilities on infrastructure devices. Understanding technology package activation is essential for network administrators and cybersecurity professionals managing secure enterprise environments.

---

# Files Included
- `License-Management.pkt`
- `Topology.png`
- `Router0-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional