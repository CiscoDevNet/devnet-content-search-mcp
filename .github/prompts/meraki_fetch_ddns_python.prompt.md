---
agent: 'meraki-code-assist.agents'
description: 'Fetch the DDNS names (active URLs) for devices in a Meraki organization using the Python SDK.'
---

# Fetch DDNS Names in Meraki Organization (Python SDK)

## Task Requirements

Retrieve DDNS hostnames (`activeDdnsHostname`) from device WAN details across all networks in a Meraki organization.

## Specific Requirements
1. Use the Meraki API key to connect and discover the organization(s).
2. Retrieve all networks in each organization.
3. Retrieve all devices in each network.
4. Extract the `activeDdnsHostname` from the WAN details of each device (if available).
5. Handle cases where the DDNS hostname is missing or not supported for a device.


## Expected Output
List of devices with their DDNS hostnames, grouped by network/organization.