# Official and core MCP repositories

## Contents

- [Code repositories](#code-repositories)
- [Security scanners and defensive tools](#security-scanners-and-defensive-tools)
- [Frameworks, adapters, and server builders](#frameworks-adapters-and-server-builders)
- [Server discovery and awesome lists](#server-discovery-and-awesome-lists)

## Code repositories

[TypeScript SDK][link_github_com_modelcontextprotocol_typescript_sdk]

[Python SDK][link_github_com_modelcontextprotocol_python_sdk]

[C# SDK][link_github_com_modelcontextprotocol_csharp_sdk]

[Go SDK][link_github_com_modelcontextprotocol_go_sdk]

[Java SDK][link_github_com_modelcontextprotocol_java_sdk]

[Rust SDK][link_github_com_modelcontextprotocol_rust_sdk]

[Servers][link_github_com_modelcontextprotocol_servers]

[Registry][link_github_com_modelcontextprotocol_registry]

[GitHub MCP Server][link_github_com_github_github_mcp_server]

## Security scanners and defensive tools

| Repository / Tool                                                                                                                                                                                                                                                                                                                                                                                                             | What It Helps With                                                                                          | Security Notes                                            |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| [Agent Scan][link_github_com_snyk_agent_scan]                                                                                                                                                                                                                                                                                                                                                               | Scans agent components for prompt injection, tool poisoning, toxic flows, and related risks                 | Useful for developer workflow and CI-style scanning       |
| [MCP Scanner][link_github_com_cisco_ai_defense_mcp_scanner]                                                                                                                                                                                                                                                                                                                                     | Scans MCP servers/tools using multiple engines                                                              | Useful for server security review                         |
| [MCP Security][link_github_com_antgroup_mcp_security] (MCPScan)                                                                                                                                                                                                                                                                                                                                         | Detects metadata pollution, tool poisoning, malicious URLs, unsafe code snippets, and exfiltration patterns | Review rules, false positives, and offline/cloud behavior |
| [MCP Scan][link_github_com_rodolfboctor_mcp_scan] · [MCP Security Scanner][link_github_com_ogulcanaydogan_mcp_security_scanner]                                                                                                                                                                                                                                         | Scans installed MCP server configs and manifests                                                            | Useful for local developer machines and CI gates          |
| [MCP Shield][link_github_com_riseandignite_mcp_shield] · [Mcpshield][link_github_com_mcpshield_mcpshield] · [MCP Shield][link_github_com_gaboitb_mcp_shield]                                                                                                                                                                                           | Detects tool poisoning, exfiltration channels, and cross-origin escalation patterns                         | Verify maintainer and current repository                  |
| [MCP Guardian][link_github_com_eqtylab_mcp_guardian]                                                                                                                                                                                                                                                                                                                                                     | Helps manage assistant access to MCP servers                                                                | Useful for human approval and local control               |
| [Mcpproxy Go][link_github_com_smart_mcp_proxy_mcpproxy_go]                                                                                                                                                                                                                                                                                                                                       | Routes and manages access to multiple MCP servers                                                           | Review sandboxing, quarantine, and policy features        |
| [Mcpwatch][link_github_com_lazymac2x_mcpwatch]                                                                                                                                                                                                                                                                                                                                                         | MCP server security scanning                                                                                | Track capabilities and maintenance status                 |
| [MCP Doctor][link_github_com_realwigu_mcp_doctor] · [MCP Doctor][link_github_com_agentopssec_mcp_doctor]                                                                                                                                                                                                                                                                       | Detects broken or risky MCP configs                                                                         | Useful for developer hygiene                              |

### Last updated

May 5, 2026

## Frameworks, adapters, and server builders

| Repository / Tool                                                                                                                                                                                                     | Why It Matters                                    | Security Notes                                                   |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- | ---------------------------------------------------------------- |
| [Fastmcp][link_github_com_prefecthq_fastmcp]                                                                                                                                                   | Rapid MCP server development                      | Ensure safe defaults, auth, and tool review                      |
| [Langchain MCP Adapters][link_github_com_langchain_ai_langchain_mcp_adapters]                                                                                                             | Lets LangChain agents use MCP tools               | Review tool routing and untrusted output handling                |
| [Spring Ai][link_github_com_spring_projects_spring_ai]                                                                                                                                   | Java/Spring MCP client/server support             | Review OAuth, API key handling, and enterprise policy support    |
| [MCP Handler][link_github_com_vercel_mcp_handler]                                                                                                                                                 | Deploy MCP servers in web/serverless environments | Review remote auth and tenant isolation                          |
| [Fastapi MCP][link_github_com_tadata_org_fastapi_mcp] · [Fastapi MCP][link_github_com_lakshmana64_fastapi_mcp]                                                       | Exposes APIs as MCP tools                         | High risk if endpoints are exposed without review                |
| [Modelfetch][link_github_com_phuctm97_modelfetch] · [Easymcp][link_github_com_secretiveshell_easymcp]                                                             | Boilerplates and helper libraries                 | Check for auth, validation, logging, and maintained dependencies |

### Last updated

May 5, 2026

## Server discovery and awesome lists

| Repository / Source                                                                                                                                                                                                       | Why It Matters                                 | Security Notes                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- | -------------------------------------------------------- |
| [Awesome MCP Servers][link_github_com_punkpeye_awesome_mcp_servers]                                                                                                                                  | Large community list of MCP servers            | Discovery source only; verify each server independently  |
| [Awesome MCP Servers][link_github_com_wong2_awesome_mcp_servers] · [mcpservers.org][link_mcpservers_org]                                                                                          | Categorized MCP server discovery               | Validate freshness, repo ownership, and install commands |
| [Awesome MCP Servers][link_github_com_appcypher_awesome_mcp_servers]                                                                                                                              | Another curated server list                    | Cross-check duplicates and abandoned entries             |
| [mcp.so][link_mcp_so]                                                                                                                                                                                                   | Broad ecosystem discovery                      | Validate publisher, permissions, and package provenance  |
| [PulseMCP][link_pulsemcp_com] · [Github][link_github_com_pulsemcp]                                                                                                                                  | Tracks clients, servers, and ecosystem updates | Useful for discovery, not a trust boundary               |
| [Glama MCP directory][link_glama_ai_mcp_servers]                                                                                                                                                                         | Server discovery and metadata                  | Review verification model before trusting entries        |

### Last updated

May 5, 2026


[link_github_com_agentopssec_mcp_doctor]: https://github.com/AgentOpsSec/mcp-doctor
[link_github_com_antgroup_mcp_security]: https://github.com/antgroup/MCP-Security
[link_github_com_appcypher_awesome_mcp_servers]: https://github.com/appcypher/awesome-mcp-servers
[link_github_com_cisco_ai_defense_mcp_scanner]: https://github.com/cisco-ai-defense/mcp-scanner
[link_github_com_eqtylab_mcp_guardian]: https://github.com/eqtylab/mcp-guardian
[link_github_com_gaboitb_mcp_shield]: https://github.com/GaboITB/mcp-shield
[link_github_com_github_github_mcp_server]: https://github.com/github/github-mcp-server
[link_github_com_lakshmana64_fastapi_mcp]: https://github.com/lakshmana64/fastapi-mcp
[link_github_com_langchain_ai_langchain_mcp_adapters]: https://github.com/langchain-ai/langchain-mcp-adapters
[link_github_com_lazymac2x_mcpwatch]: https://github.com/lazymac2x/mcpwatch
[link_github_com_mcpshield_mcpshield]: https://github.com/mcpshield/mcpshield
[link_github_com_modelcontextprotocol_csharp_sdk]: https://github.com/modelcontextprotocol/csharp-sdk
[link_github_com_modelcontextprotocol_go_sdk]: https://github.com/modelcontextprotocol/go-sdk
[link_github_com_modelcontextprotocol_java_sdk]: https://github.com/modelcontextprotocol/java-sdk
[link_github_com_modelcontextprotocol_python_sdk]: https://github.com/modelcontextprotocol/python-sdk
[link_github_com_modelcontextprotocol_registry]: https://github.com/modelcontextprotocol/registry
[link_github_com_modelcontextprotocol_rust_sdk]: https://github.com/modelcontextprotocol/rust-sdk
[link_github_com_modelcontextprotocol_servers]: https://github.com/modelcontextprotocol/servers
[link_github_com_modelcontextprotocol_typescript_sdk]: https://github.com/modelcontextprotocol/typescript-sdk
[link_github_com_ogulcanaydogan_mcp_security_scanner]: https://github.com/ogulcanaydogan/mcp-security-scanner
[link_github_com_phuctm97_modelfetch]: https://github.com/phuctm97/modelfetch
[link_github_com_prefecthq_fastmcp]: https://github.com/PrefectHQ/fastmcp
[link_github_com_pulsemcp]: https://github.com/pulsemcp
[link_github_com_punkpeye_awesome_mcp_servers]: https://github.com/punkpeye/awesome-mcp-servers
[link_github_com_realwigu_mcp_doctor]: https://github.com/realwigu/mcp-doctor
[link_github_com_riseandignite_mcp_shield]: https://github.com/riseandignite/mcp-shield
[link_github_com_rodolfboctor_mcp_scan]: https://github.com/rodolfboctor/mcp-scan
[link_github_com_secretiveshell_easymcp]: https://github.com/SecretiveShell/easymcp
[link_github_com_smart_mcp_proxy_mcpproxy_go]: https://github.com/smart-mcp-proxy/mcpproxy-go
[link_github_com_snyk_agent_scan]: https://github.com/snyk/agent-scan
[link_github_com_spring_projects_spring_ai]: https://github.com/spring-projects/spring-ai
[link_github_com_tadata_org_fastapi_mcp]: https://github.com/tadata-org/fastapi_mcp
[link_github_com_vercel_mcp_handler]: https://github.com/vercel/mcp-handler
[link_github_com_wong2_awesome_mcp_servers]: https://github.com/wong2/awesome-mcp-servers
[link_glama_ai_mcp_servers]: https://glama.ai/mcp/servers
[link_mcp_so]: https://mcp.so/
[link_mcpservers_org]: https://mcpservers.org/
[link_pulsemcp_com]: https://www.pulsemcp.com/
