---
agent: 'meraki-code-assist.agents'
description: 'Schedule a framework upgrade for a Meraki network using the official Meraki Python SDK. The script should allow users to specify the network ID, firmware version, and schedule time dynamically.'
---

# Schedule Framework Upgrade for Meraki Network (Python SDK)

## Objective
Automate the scheduling of a framework upgrade for a Meraki network using the official Meraki Python SDK.

## Instructions
- Allow users to specify the following inputs:
  - Network ID
  - Firmware version ID
  - Scheduled time for the upgrade (in ISO-8601 format).
- Use the `createNetworkFirmwareUpgradesStagedEvent` API endpoint to schedule the upgrade.
- Validate the inputs and handle errors gracefully.
- Output a confirmation message with the details of the scheduled upgrade.

### Output
- Confirmation message with scheduled upgrade details
- Include: network ID, firmware version, scheduled time, event ID
