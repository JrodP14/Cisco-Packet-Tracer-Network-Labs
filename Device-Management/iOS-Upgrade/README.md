# IOS Upgrade Lab

## Overview
The IOS Upgrade Lab focuses on upgrading the Cisco IOS image on a router using an FTP server. This lab demonstrates the complete IOS upgrade lifecycle including compatibility verification, memory validation, IOS image transfer, boot variable configuration, and router reload procedures.

The objective of this project was to safely upgrade Router0 to a newer Cisco IOS version while validating storage requirements and ensuring successful boot from the upgraded image.

---

## Skills Demonstrated
- Cisco IOS upgrade procedures
- Flash memory management
- DRAM and Flash verification
- FTP file transfers
- Boot variable configuration
- IOS image verification
- Router reload procedures
- Enterprise infrastructure maintenance

---

## Technologies Used
- Cisco IOS
- FTP
- Cisco Routers
- Flash Storage
- IOS Boot System
- Packet Tracer

---

## Lab Objectives
- Verify hardware compatibility for IOS upgrade
- Validate available flash memory
- Transfer IOS image from FTP server
- Configure boot system variables
- Reload router into upgraded IOS
- Verify successful IOS upgrade

---

# IOS Upgrade Planning

## Important Note
IOS upgrades should typically be:
- Scheduled during maintenance windows
- Performed after business hours
- Backed up prior to implementation

---

# Verify DRAM & Flash Compatibility

## Display System Information
```bash
show version
```

### Verify:
- DRAM memory capacity
- Flash memory size
- CompactFlash storage availability
- Current IOS version

### Expected Results
- Router meets minimum IOS requirements
- Hardware supports upgraded image

---

# Verify Available Flash Memory

## Display Flash Storage
```bash
dir flash:
```

### Verify:
- Available free space
- Existing IOS image files
- Sufficient storage for new IOS image

### Expected Results
- Enough free space to store upgraded IOS

---

# Transfer IOS from FTP Server to Router

## Copy IOS Image to Flash
```bash
copy ftp flash
```

### Expected Results
- Router connects to FTP server
- IOS image downloads successfully
- New IOS file stored in flash memory

---

# Verify IOS File Integrity

## Perform MD5 Verification
```bash
verify md5 <local-file> <md5-hash>
```

### Purpose
Confirms file integrity and validates the IOS image was not corrupted during transfer.

### Note
```text
MD5 verification is not available in Packet Tracer.
```

---

# Configure Boot System Command

## Set Router to Boot New IOS
```bash
(config)#boot system flash:<file-name-of-new-ios>
```

### Example
```bash
(config)#boot system flash:c2900-universalk9-mz.SPA.151-4.M4.bin
```

### Expected Results
- Router configured to load new IOS during startup

---

# Reload Router

## Reboot Device
```bash
reload
```

### Expected Results
- Router reloads successfully
- Device boots using new IOS image

---

# Verification Tasks

## Verify Current IOS Version
```bash
show version
```

Expected:
- New IOS version displayed
- Correct boot image loaded

---

## Verify Boot Variables
```bash
show running-config
```

Expected:
- `boot system flash:` command present

---

## Verify Flash Contents
```bash
dir flash:
```

Expected:
- New IOS image stored in flash memory

---

## Verify Available Memory
```bash
show version
```

Expected:
- DRAM and Flash resources visible

---

# Troubleshooting Concepts Learned
- IOS upgrade planning
- Flash memory management
- IOS image transfers
- Boot variable configuration
- System reload procedures
- Firmware integrity verification
- Enterprise maintenance operations

---

# Business Value
IOS upgrades are critical enterprise maintenance operations used to apply security patches, improve stability, and enable new networking features. Understanding upgrade procedures is essential for network administrators and cybersecurity professionals responsible for maintaining secure and reliable infrastructure devices.

---

# Files Included
- `iOS-Upgrade.pkt`
- `Topology.png`
- `Server-FTP-iOS-File.png`
- `Router0-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional