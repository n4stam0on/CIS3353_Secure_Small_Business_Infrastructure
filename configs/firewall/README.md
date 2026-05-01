# Firewall Configuration

This directory contains documentation and configuration details for the pfSense firewall used in this project.

## Overview
The firewall is used to enforce network segmentation between WAN, LAN, and DMZ environments. Rules were configured to control traffic flow and prevent unauthorized access between network segments.

## Key Configurations
- Allowed outbound traffic from LAN to WAN
- Blocked traffic from DMZ to LAN
- Restricted unnecessary inbound connections from WAN
- Controlled access to the Ubuntu web server in the DMZ

## Security Purpose
These firewall rules were implemented to:
- Enforce network segmentation
- Reduce attack surface
- Prevent lateral movement between network zones
- Protect internal systems from external and DMZ-based threats

## Verification
Firewall effectiveness was tested by:
- Attempting connectivity between restricted zones
- Running scans from Kali Linux
- Confirming blocked and allowed traffic behavior

## Evidence
Screenshots and rule exports demonstrating firewall configurations and test results are included in this folder.
