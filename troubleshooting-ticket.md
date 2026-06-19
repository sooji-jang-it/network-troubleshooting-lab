# Incident Ticket: Network Connectivity Issue

## Problem
Client1 had no internet access and could not access external websites.

## Investigation
- Checked IP configuration using ipconfig /all
- Observed IP: 192.168.56.x
- No default gateway assigned
- Ping tests to 8.8.8.8 and google.com failed

## Root Cause
VirtualBox network adapter was incorrectly set to Host-Only instead of NAT.

## Resolution
- Changed adapter to NAT
- Disabled secondary adapter
- Restarted virtual machine
- Verified new IP: 10.0.2.15

## Result
Internet connectivity was restored successfully.
