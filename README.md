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
- **Specialized AI Agents**: Pre-configured agents for [Catalyst Center Code Assist](#catalyst-center-code-assist-agent) and [Meraki Code Assist](#meraki-code-assist-agent) with intelligent solution complexity options
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

## AI Agents for Enhanced Development (Experimental)

This MCP server includes specialized AI agents that provide intelligent code generation and automation assistance for Cisco platforms. These experimental agents automatically fetch the latest API documentation and help you code with either simple standalone scripts or enterprise‑level coding guidance.

> **⚠️ Important Notice:**  
> Generative AI may produce inaccurate information regarding sample code, APIs, automation scripts, step-by-step instructions or facts. Please review and test code in test environment.

> Experimental: Agent files and flows are subject to change. Requires VS Code 1.106+ custom agents (see "Chat modes renamed to custom agents").  
> https://code.visualstudio.com/updates/v1_106#_chat-modes-renamed-to-custom-agents

### Common Agent Behavior (applies to all agents)
- Preflight: Check that the DevNet MCP server is installed and reachable; if missing, show one‑click install links and stop.
- Documentation-first: Call the appropriate search tool first (keyword or operationId) and extract `api_path`, `api_method`, `api_operation_id`, and `documentation_url`.
- Solution complexity choice: Ask the user whether they want a simple script or an enterprise‑grade solution, then tailor output accordingly.
- Output: Provide code first, and cite the official `documentation_url`.

### Use these agents in your own repository
Add the agent file to the active workspace so VS Code can load it:

```bash
mkdir -p .github/agents
curl -fsSL -o .github/agents/meraki-code-assist.agents.md \
  https://raw.githubusercontent.com/CiscoDevNet/devnet-content-search-mcp/main/.github/agents/meraki-code-assist.agents.md
git add .github/agents/meraki-code-assist.agents.md && git commit -m "Add Meraki Code Assist agent"
```

### Meraki Code Assist Agent

**Agent File**: [`.github/agents/meraki-code-assist.agents.md`](./.github/agents/meraki-code-assist.agents.md)

**Description (Experimental)**: Generate Meraki automation code using the latest API documentation. Supports two modes: simple standalone scripts or enterprise‑level coding guidance. Specializes in network management, device monitoring, security configuration, and operational reporting.

**Key Capabilities:**
- **Documentation-First Approach**: Always fetches latest Meraki API documentation before coding
- **Flexible Solution Complexity**: Choose between simple scripts (50-150 lines) or enterprise-grade solutions (300+ lines)
- **Organization-Wide Operations**: Handle multi-network and multi-organization scenarios
- **Advanced Features**: Pagination handling, rate limiting, comprehensive error handling

<details>
<summary><strong>Example Use Cases</strong></summary>

- **Simple Scripts**: "Create a simple script to list all networks in my organization"
- **Enterprise Solutions**: "Enterprise device fleet management system with full reporting"
- **Security Management**: "Comprehensive network security compliance framework"
- **Analytics Platform**: "Complete network analytics platform with dashboard integration"
  
</details>

<details>
<summary><strong>Sample Generated Features</strong></summary>

```python
# Simple approach - function-based, 50-150 lines
def get_organization_networks():
    # Basic API calls, console output
    
# Enterprise approach - class-based, 300+ lines
class MerakiAutomation:
    def __init__(self, config):
        # Organization management, bulk operations
        # Multiple output formats, advanced monitoring
```
  
</details>

#### Predefined Prompts

All predefined prompts are composed on top of the **Meraki Code Assist agent**. These prompts are designed to simplify development by focusing on specific tasks, such as fetching network IDs, scheduling firmware upgrades, or detecting orphan devices. By narrowing the scope of each prompt, developers can quickly generate targeted solutions without unnecessary complexity.

#### Available Prompts

The following prompts are currently available:

- **Detect Orphan Devices**: Identify devices not assigned to any network in a Meraki organization.
- **Fetch AP Serial Numbers**: Retrieve serial numbers of all Access Points (APs) in a Meraki organization.
- **Fetch DDNS Names**: Extract DDNS hostnames for devices in a Meraki organization.
- **Fetch All Network IDs**: Retrieve all network IDs in a Meraki organization.
- **Schedule Framework Upgrade**: Schedule a framework upgrade for a Meraki network.

#### Using Prompts

> **⚠️ Important Notice:**  
> Generative AI may produce inaccurate information regarding sample code, APIs, automation scripts, step-by-step instructions or facts. Please review and test code in test environment.

To use the prompts, follow these steps:

1. **Locate the Prompt**: Prompts are stored in the `.github/prompts` directory. Each file corresponds to a specific task. You can browse and download them from the [GitHub repository](https://github.com/CiscoDevNet/devnet-content-search-mcp/tree/main/.github/prompts).
2. **Download the Prompts**: Use the following commands to download all prompts to your local workspace:
   ```bash
   mkdir -p .github/prompts
   for prompt in meraki_fetch_network_ids_python meraki_scheduled_framework_update_python \
                 meraki_fetch_ddns_python meraki_fetch_ap_serials_python \
                 meraki_detect_orphan_devices_python; do
       curl -fsSL -o .github/prompts/${prompt}.prompt.md \
           https://raw.githubusercontent.com/CiscoDevNet/devnet-content-search-mcp/main/.github/prompts/${prompt}.prompt.md
   done
   git add .github/prompts/* && git commit -m "Add Meraki Code Prompts"
   ```
3. **Understand the Task**: Open the prompt file to review the task description, requirements, and expected outputs.
4. **Generate Code**: Use the `meraki-code-assist` agent in the VS Code Copilot chat panel to generate code based on the prompt.
5. **Test and Validate**: Run the generated or written script to ensure it meets the requirements and produces the expected output.


### Catalyst Center Code Assist Agent

**Agent File**: [`.github/agents/catalyst-center-code-assist.agents.md`](./.github/agents/catalyst-center-code-assist.agents.md)

**Description (Experimental)**: Generate Cisco Catalyst Center automation code using the latest API documentation. Supports two modes: simple standalone scripts or enterprise‑level coding guidance. Specializes in enterprise network management, device monitoring, compliance reporting, and operational analytics.

**Key Capabilities:**
- **Documentation-First Approach**: Always fetches latest Catalyst Center API documentation before coding
- **Flexible Solution Complexity**: Choose between simple scripts (50-150 lines) or enterprise-grade solutions (300+ lines)
- **Enterprise Features**: Advanced error handling, pagination, rate limiting, rollback capabilities
- **Comprehensive Coverage**: Device management, site health monitoring, template deployment, compliance reporting

<details>
<summary><strong>Example Use Cases</strong></summary>

- **Simple Scripts**: "Create a simple script to find all unreachable devices"
- **Enterprise Solutions**: "Enterprise device inventory management system with full reporting"
- **Template Automation**: "Comprehensive template deployment automation with rollback capabilities"
- **Compliance Monitoring**: "Advanced compliance monitoring with multiple output formats"
  
</details>

<details>
<summary><strong>Sample Generated Features</strong></summary>

```python
# Simple approach - function-based, 50-150 lines
def get_unreachable_devices():
    # Basic error handling, console output
    
# Enterprise approach - class-based, 300+ lines  
class CatalystCenterAutomation:
    def __init__(self, config):
        # Comprehensive error handling, multiple output formats
        # Authentication management, rate limiting
```
  
</details>

### How to Use the AI Agents

#### In VS Code with GitHub Copilot
1. Install the DevNet Content Search MCP server (see installation section above)
2. The agents are automatically available through the MCP integration
3. Ask questions like:
   ```
   Generate a Catalyst Center script to deploy templates across device groups
   ```
   ```
   Create a Meraki automation for managing organization-wide firewall rules
   ```

#### In Cursor IDE
1. Install the DevNet Content Search MCP server
2. The agents work seamlessly with Cursor's AI features
3. Request specific solutions:
   ```
   I need a simple Meraki script to check device status
   ```
   ```
   Build an enterprise Catalyst Center monitoring system
   ```

#### Key Benefits

**🎯 Solution Complexity Choice**
- **Always asks first**: "Would you like a simple, focused script or a comprehensive enterprise-grade solution?"
- **Simple Scripts**: Perfect for learning, quick tasks, and proof-of-concepts
- **Enterprise Solutions**: Production-ready with comprehensive features and error handling

**📚 Documentation Integration**
- Automatically fetches latest API documentation
- Validates API endpoints and parameters
- Includes official documentation URLs in generated code
- Ensures compatibility with current API versions

**🏗️ Architecture Flexibility**
- **Simple**: Function-based approach with linear logic
- **Enterprise**: Class-based architecture with modular design
- **Scalable**: Easy upgrade path from simple to enterprise solutions

**🔧 Platform-Specific Features**
- **Catalyst Center**: Site hierarchy, device groups, template management, compliance reporting
- **Meraki**: Organization management, network operations, security policies, analytics

### Getting Started with AI Agents

1. **Install MCP Server**: Use the one-click installation links above
2. **Choose Your Platform**: Catalyst Center or Meraki
3. **Specify Complexity**: Simple script or enterprise solution
4. **Describe Your Need**: The agent will generate appropriate code

**Example Interaction:**
```
User: "Automate template deployment across device groups in Catalyst Center"

Agent: "Would you like a simple, focused script or a comprehensive enterprise-grade solution?"

User: "Enterprise solution"

Agent: [Generates 300+ line enterprise solution with:
- Class-based architecture
- Comprehensive error handling
- Progress monitoring
- Rollback capabilities
- Multiple output formats
- Rate limiting compliance]
```

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