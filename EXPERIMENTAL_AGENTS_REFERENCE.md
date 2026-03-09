# Experimental reference: Example agents and prompts

If you are new to **agents** and **prompts** in AI-assisted development: in tools like VS Code (with Copilot) and Cursor, an **agent** is a set of instructions that tell the AI how to behave — for example, "always fetch the latest API documentation first" or "ask the user whether they want a simple script or an enterprise solution." A **prompt** is a predefined task description (e.g. "detect orphan devices in my Meraki organization") that you can give to an agent so the AI has a clear, repeatable starting point. Together, agents and prompts let you get more structured, repeatable help for tasks like Meraki or Catalyst Center automation.

This document is an **experimental reference**: it provides example agent and prompt definitions that call the DevNet Content Search MCP server. You can use or adapt these examples in your own workspace. They are not official solutions. **Do not use them to generate or operate production environments or code.** Treat the output as an associate developer: review, update, and approve any generated code before using it. If you want to learn more about how your IDE supports agents and prompts, see the product documentation: [VS Code — Chat modes renamed to custom agents](https://code.visualstudio.com/updates/v1_106#_chat-modes-renamed-to-custom-agents) and [Cursor — Context and skills](https://cursor.com/docs/context/skills).

> This feature uses artificial intelligence to enhance its capabilities. Please note that AI-generated results may sometimes be inaccurate or incomplete.

This document is optional. To install and use the DevNet Content Search MCP server, see the [main README](README.md).

The content below provides **example** agent and prompt definitions that use the DevNet Content Search MCP tools for more complex scenarios. They are for reference only — not official solutions. Use or adapt them as needed for your workflow.

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

**Agent File**: [`.github/agents/meraki-code-assist.agents.md`](.github/agents/meraki-code-assist.agents.md)

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

**Agent File**: [`.github/agents/catalyst-center-code-assist.agents.md`](.github/agents/catalyst-center-code-assist.agents.md)

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
1. Install the DevNet Content Search MCP server (see [Installation and Setup](README.md#installation-and-setup) in the main README)
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

**Solution Complexity Choice**
- **Always asks first**: "Would you like a simple, focused script or a comprehensive enterprise-grade solution?"
- **Simple Scripts**: Perfect for learning, quick tasks, and proof-of-concepts
- **Enterprise Solutions**: Production-ready with comprehensive features and error handling

**Documentation Integration**
- Automatically fetches latest API documentation
- Validates API endpoints and parameters
- Includes official documentation URLs in generated code
- Ensures compatibility with current API versions

**Architecture Flexibility**
- **Simple**: Function-based approach with linear logic
- **Enterprise**: Class-based architecture with modular design
- **Scalable**: Easy upgrade path from simple to enterprise solutions

**Platform-Specific Features**
- **Catalyst Center**: Site hierarchy, device groups, template management, compliance reporting
- **Meraki**: Organization management, network operations, security policies, analytics

### Getting Started with AI Agents

1. **Install MCP Server**: Use the one-click installation links in the [main README](README.md#installation-and-setup)
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
