---
agent: 'meraki-code-assist.agents'
description: 'Fetch the serial numbers of all Access Points (APs) in a Meraki organization using the Python SDK.'
---

# Fetch AP Serial Numbers in Meraki Organization (Python SDK)

## Task Objective

Create a Python script using Meraki SDK to fetch serial numbers of all Access Points in an organization.

## Core Requirements

1. Dynamically discover all organizations and identify target by name
2. Fetch all devices and filter for Access Points (model starts with `MR`)
3. Output serial numbers with organization name
