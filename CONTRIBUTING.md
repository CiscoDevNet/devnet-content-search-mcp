# How to Contribute

Thanks for your interest in contributing to `DevNet Content Search MCP Server`! Here are a few
general guidelines on contributing and reporting bugs that we ask you to review.
Following these guidelines helps to communicate that you respect the time of the
contributors managing and developing this open source project. In return, they
should reciprocate that respect in addressing your issue, assessing changes, and
helping you finalize your pull requests. In that spirit of mutual respect, we
endeavor to review incoming issues and pull requests within 10 days, and will
close any lingering issues or pull requests after 60 days of inactivity.

Please note that all of your interactions in the project are subject to our
[Code of Conduct](/CODE_OF_CONDUCT.md). This includes creation of issues or pull
requests, commenting on issues or pull requests, and extends to all interactions
in any real-time space e.g., Slack, Discord, etc.

## Reporting Issues

Before reporting a new issue, please ensure that the issue was not already
reported or fixed by searching through our [issues
list](https://github.com/CiscoDevNet/devnet-content-search-mcp/issues).

When creating a new issue, please be sure to include a **title and clear
description**, as much relevant information as possible, and, if possible, a
test case.

**If you discover a security bug, please do not report it through GitHub.
Instead, please see security procedures in [SECURITY.md](/SECURITY.md).**

## Contributing Agents and Prompts

Agents and Prompts are a great way to extend the usage of `DevNet Content Search MCP Server`. 
We welcome submissions of agents and prompts that solve specific issues or achieve certain 
goals by leveraging this MCP server. Before contributing, please review existing agents and 
prompts to see if your use case is already covered or can be addressed through minor updates.

### Submission Guidelines

When submitting an agent or prompt, please follow these requirements:

- **File placement and naming:**
  - Agent files: `.github/agents/` with naming convention 
    `{platform}-{purpose}.agents.md`
  - Prompt files: `.github/prompts/` with naming convention 
    `{platform}_{task}_{language}.prompt.md`

- **Documentation:**
  - Provide a clear description of which Cisco platform(s) it targets
  - Explain the goal and use case this agent/prompt achieves
  - Document any prerequisites or dependencies

- **API Verification:**
  - Verify all referenced APIs against official DevNet documentation
  - Ensure APIs are current and not deprecated
  - Include API version information if relevant

- **Security:**
  - Ensure no hardcoded secrets (API keys, passwords, tokens)
  - Use environment variables or secure configuration methods for sensitive data

- **Testing:**
  - Test the agent/prompt thoroughly with this MCP server before submission
  - Document the testing environment and steps
  - Include example outputs or screenshots when helpful

- **Documentation of limitations:**
  - Describe any known limitations or edge cases
  - Note any required setup steps or configuration
  - Mention any follow-up work or enhancements needed

### Contribution Tips

- **Start simple:** Begin with agents/prompts targeting a single API or workflow 
  before creating complex multi-step solutions
- **Follow existing patterns:** 
  Review existing agents/prompts to match the established style and structure
- **Provide context:** 
  Include use case examples showing how your agent/prompt solves a real problem
- **Make it reusable:** 
  Design agents/prompts to be adaptable to similar scenarios beyond your specific use case
- **Engage early:** 
  If planning a large contribution, consider opening an issue first to discuss the approach

### Review Criteria

Pull requests will be evaluated based on:

- Clarity of documentation and naming
- Correctness against official API documentation
- Code/prompt quality and adherence to project standards
- Absence of security issues or hardcoded credentials
- Evidence of testing and validation
- Usefulness to the broader community

## Sending Pull Requests

Before sending a new pull request, take a look at existing pull requests and
issues to see if the proposed change or fix has been discussed in the past, or
if the change was already implemented but not yet released.

We expect new pull requests to include tests for any affected behavior, and, as
we follow semantic versioning, we may reserve breaking changes until the next
major version release.

## Other Ways to Contribute

We welcome anyone that wants to contribute to `DevNet Content Search MCP Server` to triage and
reply to open issues to help troubleshoot and fix existing bugs. Here is what
you can do:

- Help ensure that existing issues follows the recommendations from the
  _[Reporting Issues](#reporting-issues)_ section, providing feedback to the
  issue's author on what might be missing.
- Review and update the existing content of our
  [Wiki](https://github.com/CiscoDevNet/devnet-content-search-mcp/wiki) with up-to-date
  instructions and code samples.
- Review existing pull requests, and testing patches against real existing
  applications that use `DevNet Content Search MCP Server`.
- Write a test, or add a missing test case to an existing test.
- Help improve documentation and setup instructions for different IDE configurations.
- Suggest new Cisco API platforms to be added to the search coverage.

Thanks again for your interest on contributing to `DevNet Content Search MCP Server`!

:heart:

