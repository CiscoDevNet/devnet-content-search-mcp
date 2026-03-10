[![Install MCP Server](https://img.shields.io/badge/VS%20Code-Install%20DevNet%20Content%20Search-blue?style=for-the-badge&logo=visualstudiocode)](https://vscode.dev/redirect/mcp/install?name=devnet-content-search&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fdevnet.cisco.com%2Fv1%2Ffoundation-search-mcp%2Fmcp%22%7D) [![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en-US/install-mcp?name=devnet-content-search&config=eyJ1cmwiOiJodHRwczovL2Rldm5ldC5jaXNjby5jb20vdjEvZm91bmRhdGlvbi1zZWFyY2gtbWNwL21jcCJ9)

# DevNet Content Search MCP Server

MCP server enabling IDE agents to semantically search Cisco product API documentation hosted on DevNet.

The DevNet Content Search MCP server provides seamless access to Cisco's extensive API documentation and development resources through the Model Context Protocol (MCP). This server enables AI assistants and development tools like VS Code Copilot, Cursor, and other MCP-compatible IDEs to search, retrieve, and understand Cisco DevNet content for enhanced code generation and network automation tasks.

## Overview

This MCP server acts as a bridge between AI-powered development environments and Cisco's comprehensive API documentation ecosystem, providing intelligent search capabilities across multiple Cisco platforms and technologies.

## Key Features

- **Comprehensive API Search**: Access Meraki and Catalyst Center API documentation with intelligent keyword search
- **Precise Operation Lookup**: Retrieve specific API endpoints using operation IDs for exact matches  
- **Rich Documentation Context**: Get complete OpenAPI specifications, code examples, and implementation guides
- **AI-Optimized Responses**: Structured data format designed for seamless AI assistant integration
- **Real-time Access**: Direct connection to latest DevNet documentation and API specifications
- **Experimental**: Example agents and prompts for complex scenarios — see [Experimental reference: Example agents and prompts](EXPERIMENTAL_AGENTS_REFERENCE.md)
- **Expanding Platform Support**: Currently supports Meraki & Catalyst Center APIs, with additional Cisco platforms coming soon

> **Need a specific product API?** [Create an issue](https://github.com/CiscoDevNet/devnet-content-search-mcp/issues) to help us prioritize which APIs to add next!

## Installation and Setup

### VS Code with Copilot

**One-Click Installation:**   
[![Install MCP Server](https://img.shields.io/badge/VS%20Code-Install%20DevNet%20Content%20Search-blue?style=for-the-badge&logo=visualstudiocode)](https://vscode.dev/redirect/mcp/install?name=devnet-content-search&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fdevnet.cisco.com%2Fv1%2Ffoundation-search-mcp%2Fmcp%22%7D)

<details>
<summary>Manual Configuration</summary>

1. Open VS Code Command Palette: `Cmd+Shift+P` (Mac) or `Ctrl+Shift+P` (Windows/Linux)
2. Type and select: `MCP: Add Server`
3. Choose Server Type: `HTTP`
4. Enter Server URL: `https://devnet.cisco.com/v1/foundation-search-mcp/mcp`
5. Set Server ID: `devnet-content-search`
6. Restart VS Code to activate the server

</details>

**Getting Started:**
After installation, test the connection by asking Copilot:
```
Find Meraki L3 firewall API endpoints for configuring traffic rules
```

![DevNet Content Search Example](./images/devnet-content-search-example.gif)

### Cursor IDE

**One-Click Installation:**  
[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en-US/install-mcp?name=devnet-content-search&config=eyJ1cmwiOiJodHRwczovL2Rldm5ldC5jaXNjby5jb20vdjEvZm91bmRhdGlvbi1zZWFyY2gtbWNwL21jcCJ9)

<details>
<summary>Manual Configuration</summary>

1. Open Cursor Settings: `Cmd+Shift+P` (Mac) or `Ctrl+Shift+P` (Windows/Linux)
2. Navigate to MCP Tools: In the settings menu, find and select `Tools & MCP`
3. Click `Add Custom MCP` and configure:
   ```json
   {
     "mcpServers": {
       "devnet-content-search": {
         "url": "https://devnet.cisco.com/v1/foundation-search-mcp/mcp"
       }
     }
   }
   ```

</details>

### Other MCP-Compatible Clients

This server follows the standard MCP protocol and works with any compatible client. For implementation details, refer to the MCP specification.

**Generic MCP Configuration:**
Note: Some AI agents require choosing a transport type. If prompted, select `http` (or `stream` as your client names it) for this server URL.
Add this configuration to your MCP client's `config.json`:
```json
{
  "mcpServers": {
    "devnet-content-search": {
      "url": "https://devnet.cisco.com/v1/foundation-search-mcp/mcp"
    }
  }
}
```

## Example Queries

### Quick Start - Copy & Try These

**Copy → Paste → See Results:**

```
Show me the latest API docs for Meraki L3 firewall settings
```
```
Find Meraki OAuth 2.0 API authentication documentation with setup flow
```
```
Find network device inventory management APIs for Catalyst Center
```
```
Show me details for createNetworkMerakiAuthUser operation
```

### Real-World Developer Scenarios

**🔒 "I need to secure my network"**
```
Show me L3 firewall rules configuration for Meraki
```
```
Find wireless SSID firewall policies for Meraki
```
```
How do I configure network security group rules in Meraki?
```

**👤 "I'm building an authentication system"**  
```
Find OAuth authentication setup for Meraki APIs
```
```
Show me RADIUS server configuration API documentation for Meraki
```
```
How do I configure splash page captive portal using Meraki API?
```

**⚙️ "I want to automate network management"**
```
Show me VLAN management REST API documentation for Meraki
```
```
Find wireless access point configuration APIs for Meraki
```
```
How do I configure switch ports using Meraki API?
```

**📊 "I need monitoring and troubleshooting"**
```
Show me network device health monitoring APIs for Meraki
```
```
Find traffic analytics API endpoints in Meraki documentation
```
```
How do I set up webhook event notifications for Meraki?
```
```
Find assurance and troubleshooting APIs in Catalyst Center documentation
```

**🎯 "I know exactly what I want"**
```
Find details for createNetworkMerakiAuthUser operation
```
```
Show me updateNetworkApplianceFirewallL3FirewallRules API specification
```

### 🏢 Catalyst Center Specific Examples

**Enterprise Network Management:**
```
Show me network device inventory management APIs for Catalyst Center
```
```
Find device discovery and onboarding APIs for Catalyst Center
```
```
How do I manage network device configurations in Catalyst Center?
```

**Policy and Compliance:**
```
Find policy automation workflows for Catalyst Center
```
```
Show me compliance reporting APIs for Catalyst Center
```
```
How do I configure network segmentation policies in Catalyst Center?
```

**Monitoring and Assurance:**
```
Find assurance and troubleshooting APIs in Catalyst Center documentation
```
```
Show me network performance monitoring APIs for Catalyst Center
```
```
How do I get network health analytics from Catalyst Center?
```

**Site and Topology Management:**
```
Show me site hierarchy management APIs for Catalyst Center
```
```
Find network topology discovery APIs for Catalyst Center
```
```
How do I manage campus and branch locations in Catalyst Center?
```

### Pro Tips for Better Results

**✅ Be Specific**: "L3 firewall rules" → Better than "firewall"  
**✅ Include Platform**: "Meraki wireless access point API" → Better than "access point setup"  
**✅ Use Tech Terms**: "VLAN management REST endpoints" → Better than "network segments"

### Alternative: Direct Tool Syntax

For users who prefer direct tool invocation:

```
#Meraki-API-Doc-Search L3 firewall rules configuration
```

## Available Tools

### Meraki API Documentation Search
**Tool ID**: `Meraki-API-Doc-Search`

<details>
<summary>Tool Details and Parameters</summary>

Search comprehensive Meraki API documentation covering network infrastructure management, security policies, wireless configuration, and monitoring capabilities.

**Parameters:**
- `keyword` (required): Search terms for finding relevant documentation
- `return_api_only` (optional): Set to `true` for API specs only, `false` for complete documentation context
- `top_k` (optional): Number of results to return (default: 3, max: 10)

**Use Cases:**
- Finding API endpoints for specific network operations
- Understanding authentication and authorization methods  
- Exploring webhook and event handling capabilities
- Discovering monitoring and analytics APIs

</details>

<details>
<summary>Response Format and Example</summary>

**Response Structure:**
All responses include structured data with these key fields:

**Core Information:**
- `name`: Document or API endpoint title
- `description`: Brief summary of functionality
- `content`: Full text content when applicable

**Metadata:**
- `products`: Associated Cisco product lines
- `tags`: Searchable keywords and categories  
- `categories`: Primary classification (e.g., "Networking", "Security")

**API-Specific Fields:**
- `api_path`: RESTful endpoint URL pattern
- `api_method`: HTTP verb (GET, POST, PUT, DELETE)
- `api_operation_id`: Unique OpenAPI operation identifier
- `openapi_specification`: Complete API specification (JSON string)
- `documentation_url`: Direct link to official documentation

**Sample Response:**
```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": {
    "content": [
      {
        "type": "text", 
        "text": "Found 2 results for Meraki authentication APIs:\n\n1. Create Network Meraki Auth User\n2. OAuth 2.0 Authentication Overview"
      }
    ],
    "structuredContent": {
      "result": [
        {
          "name": "Create Network Meraki Auth User",
          "description": "Authorize a user configured with Meraki Authentication for a network",
          "products": ["Meraki"],
          "tags": ["networks", "configure", "merakiAuthUsers"],
          "categories": ["Networking"],
          "api_path": "/networks/{networkId}/merakiAuthUsers",
          "api_method": "post", 
          "api_operation_id": "createNetworkMerakiAuthUser",
          "openapi_specification": "{\"description\": \"Authorize a user...\", \"operationId\": \"createNetworkMerakiAuthUser\", \"parameters\": [...], \"requestBody\": {...}, \"responses\": {...}}",
          "documentation_url": "https://developer.cisco.com/meraki/api-v1/create-network-meraki-auth-user"
        }
      ]
    },
    "isError": false
  }
}
```

</details>

### Catalyst Center API Documentation Search  
**Tool ID**: `CatalystCenter-API-Doc-Search`

<details>
<summary>Tool Details and Parameters</summary>

Access Catalyst Center API documentation for enterprise network management, automation workflows, and infrastructure orchestration.

**Parameters:**
- `keyword` (required): Search terms for relevant documentation
- `return_api_only` (optional): Filter for API specifications vs. general documentation  
- `top_k` (optional): Maximum results to return

**Use Cases:**
- Network device management and configuration
- Policy and compliance automation
- Performance monitoring and analytics
- Troubleshooting and diagnostic tools

</details>

### Meraki Operation ID Lookup
**Tool ID**: `Meraki-API-OperationId-Search` 

<details>
<summary>Tool Details and Parameters</summary>

Retrieve specific API endpoint details using exact operation identifiers for precise documentation lookup.

**Parameters:**
- `operation_id` (required): The exact OpenAPI operation ID (e.g., `createNetworkMerakiAuthUser`)

**Use Cases:**
- Getting complete specifications for known API operations
- Validating parameter requirements and response formats
- Finding related endpoints and dependencies

</details>

## Experimental reference: Example agents and prompts

> This feature uses artificial intelligence to enhance its capabilities. Please note that AI-generated results may sometimes be inaccurate or incomplete.

For example agent and prompt definitions that use this MCP server for more complex scenarios, see [Experimental reference: Example agents and prompts](EXPERIMENTAL_AGENTS_REFERENCE.md).

## Troubleshooting and Support

<details>
<summary><strong>Open troubleshooting guide</strong></summary>

### When Your AI Assistant Isn't Finding DevNet Content

If your assistant responds with generic networking advice instead of specific Cisco API documentation, try these approaches:

#### 🎯 Making Your Requests More Specific

**Instead of:** "How do I configure a firewall?"  
**Try:** "Show me the Meraki L3 firewall API endpoints for configuring traffic rules"

**Instead of:** "I need network monitoring tools"  
**Try:** "Find Catalyst Center APIs for collecting device performance metrics"

#### 🔍 Framing Your Questions for DevNet Search

**Technology-Specific + Action-Oriented:**
- "Find Meraki L3 firewall API endpoints for configuring traffic rules"
- "Show me Catalyst Center APIs for network device inventory management"
- "I need the OpenAPI specification for Meraki wireless SSID configuration"

**Current Documentation Requests:**
- "What are the current Catalyst Center APIs for compliance reporting?"
- "Find the latest Meraki Dashboard APIs for switch port management" 
- "Get current DevNet documentation for OAuth 2.0 authentication"

**Problem-Solution Approach:**
- "I'm building network automation - find relevant Catalyst Center APIs"
- "My monitoring dashboard needs Meraki device status data - what APIs exist?"
- "Help me integrate Catalyst Center with my ITSM system"

#### ⚙️ IDE Assistant Configuration Tips

Some development environments allow you to customize AI assistant behavior. Configure your IDE with specific instructions to ensure reliable tool usage:

**VS Code/Cursor Custom Instructions:**
```
For Cisco networking questions, always search official DevNet documentation first.
Use the available MCP tools for current API specifications rather than 
providing general networking advice. Focus on specific Cisco platforms:
Meraki Dashboard, Catalyst Center, and DevNet resources.
```

**Avoid Generic Terms That May Not Trigger Tools:**
- ❌ "networking tools" → ✅ "Meraki network management APIs"
- ❌ "device configuration" → ✅ "Catalyst Center device provisioning endpoints"  
- ❌ "monitoring solutions" → ✅ "DevNet network analytics API specifications"

### Common Issues and Solutions

| Issue | Description | Solution |
|-------|-------------|----------|
| **Input Validation Errors** | `Error: 'keyword' is a required property` | Ensure all required parameters are provided according to the tool's schema |
| **Rate Limiting** | `Error: Rate limit exceeded. Please wait before sending another request` | Wait before retrying your request. Consider spacing out queries over time |
| **Service Unavailability** | `Error: Search Service is Unavailable` | The backend search engine is experiencing issues. Please contact the DevNet team |
| **No Results Found** | Empty or minimal search results | • Try broader search terms<br>• Check spelling and technical terminology<br>• Use alternative keywords or synonyms |
| **MCP Server Connection** | Server not responding or unavailable | • Verify MCP server configuration<br>• Check network connectivity<br>• Restart IDE or MCP client |
| **Authentication Issues** | API access denied or forbidden | • Verify API credentials<br>• Check organization access permissions<br>• Contact DevNet support for access issues |

### Getting Help

If you encounter issues or need assistance:
1. Check that your MCP client is properly configured
2. Verify your search queries follow the expected format
3. Contact the DevNet team for service-related issues

</details>

## License

This project is licensed under the [Apache License 2.0](./LICENSE).