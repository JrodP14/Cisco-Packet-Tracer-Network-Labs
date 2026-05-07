# DNS Host Troubleshooting Lab

## Overview
The DNS Host Troubleshooting Lab focuses on diagnosing and resolving DNS-related connectivity issues on a client workstation. This lab demonstrates how a host can have working Layer 3 connectivity while still failing to access websites due to missing or incorrect DNS configuration.

The objective of this project was to troubleshoot PC2’s inability to browse the internet, identify the DNS configuration issue, and restore proper web access functionality.

---

## Skills Demonstrated
- DNS troubleshooting
- Host network diagnostics
- Layer 3 connectivity testing
- Name resolution verification
- Windows command-line troubleshooting
- Client IP configuration analysis
- Network troubleshooting methodology
- End-user support concepts

---

## Technologies Used
- DNS
- Cisco Packet Tracer
- Windows Command Prompt
- ICMP/Ping
- Web Browser Testing

---

## Lab Objectives
- Verify internet connectivity on hosts
- Test DNS resolution
- Verify Layer 3 communication
- Identify missing DNS configuration
- Restore DNS functionality
- Confirm successful web browsing

---

# Open Packet Tracer Lab

## Lab File
```text
Tshoot-DNS-Host.pkt
```

---

# Confirm PC1 Internet Access

## Steps
1. Open:
```text
PC1 Desktop → Web Browser
```

2. Browse to:
```text
www.google.com
```

3. Confirm:
- Web page loads successfully
- DNS resolution functions properly

### Expected Results
- PC1 successfully accesses the website

---

# Confirm PC2 Internet Access

## Steps
1. Open:
```text
PC2 Desktop → Web Browser
```

2. Browse to:
```text
www.google.com
```

### Expected Results
- Web page fails to load
- Indicates possible DNS issue

---

# Troubleshoot PC2 Internet Access

## Step 1 – Verify DNS Resolution

### Open Command Prompt
```text
PC2 Desktop → Command Prompt
```

### Run NSLOOKUP
```bash
nslookup www.google.com
```

### Expected Results
- DNS lookup fails
- Name resolution unsuccessful

---

# Step 2 – Verify Layer 3 Connectivity

## Ping Public IP Address
```bash
ping 8.8.8.8
```

### Expected Results
- Successful replies received
- Confirms Layer 3 network connectivity works properly

---

# Troubleshooting Analysis

## Observation
- Internet connectivity exists
- DNS name resolution fails

### Conclusion
Problem is likely:
- Missing DNS server configuration
- Incorrect DNS server settings on PC2

---

# Step 3 – Verify Host IP Configuration

## Check IP Settings
Open:
```text
Desktop → IP Configuration
```

### Verify:
- IP address
- Subnet mask
- Default gateway
- DNS server settings

---

# Step 4 – Configure DNS Server

## Add Correct DNS Server
Example:
```text
8.8.8.8
```

### Expected Results
- DNS resolution restored
- Web browsing functions correctly

---

# Step 5 – Retest Internet Access

## Retest Website Access
Browse to:
```text
www.google.com
```

### Expected Results
- Website loads successfully
- DNS issue resolved

---

# Verification Tasks

## Verify DNS Resolution
```bash
nslookup www.google.com
```

Expected:
- Successful DNS response

---

## Verify Layer 3 Connectivity
```bash
ping 8.8.8.8
```

Expected:
- Successful ping replies

---

## Verify Web Access
Open browser:
```text
www.google.com
```

Expected:
- Website accessible

---

## Verify Host Configuration
Check:
```text
Desktop → IP Configuration
```

Expected:
- DNS server configured correctly

---

# Troubleshooting Concepts Learned
- DNS resolution process
- Difference between Layer 3 and DNS failures
- Host IP configuration analysis
- ICMP connectivity testing
- End-user troubleshooting methodology
- Internet connectivity diagnostics

---

# Business Value
DNS troubleshooting is one of the most common real-world IT support and network operations tasks. Understanding how to isolate DNS issues from general connectivity problems is critical for help desk technicians, network administrators, SOC analysts, and cybersecurity professionals supporting enterprise environments.

---

# Files Included
- `Tshoot-DNS-Host.pkt`
- `Topology.png`
- `PC1-Addressing.txt`
- `PC2-Addressing.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional