# Network Troubleshooting Lab

## Overview
This repository documents a hands-on network troubleshooting lab simulating real-world IT helpdesk scenarios. The lab focuses on diagnosing and resolving client connectivity issues using Windows networking tools and VirtualBox.

---

## Objectives
- Diagnose network connectivity issues
- Troubleshoot DHCP, DNS, and gateway problems
- Understand NAT vs Host-Only networking
- Apply structured IT troubleshooting methodology

---

## Lab Scenario

## Problem
Client1 VM experienced no internet connectivity:
- Unable to ping external IPs (8.8.8.8)
- Unable to resolve domain names (google.com)

---

## Investigation

### Network Configuration Check
- Executed `ipconfig /all`
- Observed:
  - IP Address: 192.168.56.x
  - No valid default gateway
  - DHCP not providing proper external routing

### Connectivity Testing
- `ping 8.8.8.8` failed
- `ping google.com` failed

### Environment Check
- VirtualBox network adapter was set to Host-Only instead of NAT
- No external internet routing available

---

## Root Cause
Incorrect VirtualBox network configuration:
- Host-Only adapter active instead of NAT
- No default gateway assigned
- No external network access

---

## Fix Applied

### VirtualBox Configuration
- Changed Adapter 1 to NAT
- Disabled Adapter 2 (Host-Only)
- Restarted Client1 VM

### Network Refresh
- Renewed IP configuration
- Verified correct DHCP assignment

### Final Configuration
- IP Address: 10.0.2.15
- Default Gateway: 10.0.2.2

---

## Validation

### Connectivity Tests
- ping 8.8.8.8 successful
- ping google.com successful

### Result
- Full internet connectivity restored

---

## Evidence

### Problem State
- network-01-ipconfig-no-gateway.png
- network-02-connectivity-failure.png

### Investigation
- network-03-virtualbox-network-settings.png

### Fix Applied
- network-04-adapter-fixed-nat.png

### Final Validation
- network-05-ipconfig-after-fix.png
- network-06-final-validation.png

---

## Skills Demonstrated

### Networking
- IP configuration analysis
- DHCP troubleshooting
- DNS resolution testing

### Virtualization
- VirtualBox NAT vs Host-Only networking

### IT Support
- Structured troubleshooting methodology
- Problem → Investigation → Root Cause → Fix → Validation

---

## Troubleshooting Flow
Problem → Investigation → Root Cause → Fix → Validation

---

## Outcome
Client network connectivity successfully restored. Lab demonstrates real-world helpdesk and junior network technician troubleshooting skills.
