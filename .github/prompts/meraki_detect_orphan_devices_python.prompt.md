---
agent: 'meraki-code-assist.agents'
description: 'Detect orphan devices (devices not attached to any network) in a Meraki organization using the official Meraki Python SDK. The script should dynamically discover all organizations, fetch devices, and identify those not attached to any network.'
---


# Detect Orphan Devices in Meraki Organization (Python SDK)

## Objective
Detect and list devices not attached to any network (orphan devices) in Meraki organizations.

## Requirements
- Discover all accessible organizations
- Fetch all devices per organization
- Look for devices that are in inventory but not assigned to any network(orphan devices)
- Output summary with count and device details

## Expected Output
- Per-organization summary of orphan devices
- Device details: serial, model, name, MAC, type
- Total count of orphan devices across all organizations