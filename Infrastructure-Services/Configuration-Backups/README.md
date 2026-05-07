# Configuration Backup Lab

## Overview
The Configuration Backup Lab focuses on backing up Cisco router configurations and IOS image files using TFTP and FTP servers. This lab demonstrates enterprise backup procedures used to preserve device configurations, support disaster recovery, and maintain network infrastructure integrity.

The objective of this project was to configure file transfer services, back up startup configurations, and transfer IOS images to remote servers for centralized storage and recovery purposes.

---

## Skills Demonstrated
- Cisco IOS file management
- TFTP configuration backups
- FTP file transfers
- IOS image backup procedures
- Network device recovery concepts
- Cisco IOS CLI operations
- Infrastructure management
- Enterprise backup practices

---

## Technologies Used
- Cisco IOS
- TFTP
- FTP
- Cisco Routers
- File Transfer Services
- Packet Tracer

---

## Lab Objectives
- View startup configuration files
- Back up startup configuration using TFTP
- Configure FTP credentials
- Back up startup configuration using FTP
- Back up IOS image files
- Verify successful file transfers

---

# Back Up Startup Configuration via TFTP

## View Startup Configuration in NVRAM
```bash
dir nvram:
```

### Purpose
Displays files stored in NVRAM including:
```text
startup-config
```

---

## Copy Startup Configuration to TFTP Server
```bash
copy startup-config tftp
```

### Prompts
```text
Address or name of remote host? 10.20.30.99
Destination filename? <press Enter for default>
```

### Expected Results
- Configuration file transferred successfully
- Confirmation message displayed

---

## Verify File Transfer
- Check TFTP server storage
- Confirm startup configuration file exists

---

# Configure FTP Credentials on Router0

## Configure FTP Username
```bash
(config)#ip ftp username cisco
```

---

## Configure FTP Password
```bash
(config)#ip ftp password cisco
```

### Purpose
Provides authentication credentials for FTP transfers.

---

# Back Up Startup Configuration via FTP

## Copy Startup Configuration
```bash
copy startup-config ftp
```

### Expected Results
- Router authenticates to FTP server
- Configuration file transferred successfully

---

## Verify FTP Transfer
- Check FTP server storage
- Confirm configuration file exists

---

# Back Up IOS Image File via FTP

## View IOS Image in Flash Memory
```bash
dir flash:
```

### Purpose
Displays IOS image files stored in flash memory.

---

## Copy IOS Image to FTP Server
```bash
copy flash: ftp
```

### Prompts
When prompted:
- Enter the IOS filename exactly as shown in flash storage

### Expected Results
- IOS image transferred successfully
- File available on FTP server

---

## Verify IOS Backup
- Confirm IOS image file exists on FTP server
- Verify file size appears correct

---

# Verification Tasks

## Verify NVRAM Contents
```bash
dir nvram:
```

Expected:
- Startup configuration visible

---

## Verify Flash Contents
```bash
dir flash:
```

Expected:
- IOS image files displayed

---

## Verify FTP Credentials
```bash
show running-config
```

Expected:
- FTP username and password configured

---

## Verify File Transfers
- Check TFTP server files
- Check FTP server files

Expected:
- Startup configuration backed up successfully
- IOS image copied successfully

---

# Troubleshooting Concepts Learned
- TFTP file transfer operations
- FTP authentication configuration
- Cisco IOS file systems
- NVRAM and flash storage management
- Backup verification procedures
- Enterprise disaster recovery concepts

---

# Business Value
Configuration backups and IOS image management are critical enterprise operations that support disaster recovery, change management, and infrastructure resilience. Understanding secure backup procedures is essential for network administrators and cybersecurity professionals responsible for maintaining operational continuity.

---

# Files Included
- `Configuration-Backup.pkt`
- `Topology.png`
- `Server-FTP-Backup-File.png`
- `Server-TFTP-Backup-File.png`
- `Router0-Config.txt`
- `LAN1-Switch-Config.txt`
- `LAN2-Switch-Config.txt`
- `Server-Addressing.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional