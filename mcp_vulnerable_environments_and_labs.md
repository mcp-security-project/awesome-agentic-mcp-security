# Vulnerable MCP Environments and Labs

Educational and research environments for MCP security testing. **Tables** summarize difficulty and defenses.

**Last Update**: 2026-05-05

## Contents

- [MCP Goat–style projects (full detail)](#mcp-goatstyle-projects-full-detail)
- [Prompt injection labs](#prompt-injection-labs)
- [Tool poisoning labs](#tool-poisoning-labs)
- [Shadow MCP and misconfiguration labs](#shadow-mcp-and-misconfiguration-labs)
- [Supply chain labs](#supply-chain-labs)

---

## MCP Goat–style projects (full detail)

| Project : Maintainer | MCP components | Vulnerabilities covered | Last Update |
| --- | --- | --- | --- |
| [Damn Vulnerable MCP Server (DVMCP)][link_github_com_harishsg993010_damn_vulnerable_mcp_server] : harishsg993010 | Server, tools, prompts, resources, SSE, client config | Prompt injection, tool poisoning, excessive permissions, rug pull, shadowing, indirect injection, token theft | ![](https://badgen.net/github/last-commit/harishsg993010/damn-vulnerable-MCP-server) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] : Appsecco | Local/remote servers, filesystem, HTTP/SSE, tool output, client config | Path traversal, unsandboxed exec, indirect/remote injection, malicious tools, typosquatting, outdated pkgs, secrets/PII, untrusted content | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [bad-mcp][link_github_com_canack_bad_mcp] : canack | Tool descriptions, schemas, resources, sessions, cross-server | Full-schema poisoning, advanced poisoning, rug pulls, resource poisoning, cross-server shadowing, protocol attacks | ![](https://badgen.net/github/last-commit/canack/bad-mcp) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] : MCP Shark | MCP config, tools, resources, prompts, multi-server harness, Cursor config, YARA-style rules, auth fixtures | Toxic metadata, prompt injection, command injection patterns, oversharing, privilege abuse, bad URLs, env secrets, duplicate tools, bad args, weak authZ | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |
| [MCP Security Summit Workshop (Sherpa)][link_github_com_azure_samples_sherpa] : Microsoft Azure Samples | Servers, Azure ID, OAuth, MI, Key Vault, gateway, private endpoints, content safety, logging, red/blue validation | Auth gaps, over-permissioned access, weak I/O, no monitoring, unsafe cloud patterns | ![](https://badgen.net/github/last-commit/Azure-Samples/sherpa) |
| [MCP Poisoning PoC][link_github_com_gensecaihq_mcp_poisoning_poc] : GenSecAI | Tools, descriptions, agent workflows | Tool poisoning in real-world agent flows | ![](https://badgen.net/github/last-commit/gensecaihq/mcp-poisoning-poc) |

---

## Prompt injection labs

| Project (linked) | Lab / scenario | Summary | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Local indirect prompt injection | Local retrieval returns untrusted docs with hidden instructions; practice instruction/data separation and confirmation gates. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Remote indirect prompt injection | Remote HTTP/SSE content becomes instructions; practice origin trust, auth, isolation, and logging. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [github-mcp-exploit][link_vulnerablemcp_info_vuln_github_mcp_exploit_html] | GitHub toxic agent flow | Malicious issue + broad GitHub token → private data exfil path; practice scoped tokens and approvals. | 2026-05-05 |
| [whatsapp-message-exfiltration][link_vulnerablemcp_info_vuln_whatsapp_message_exfiltration_html] | Messaging bridge exfiltration | Co-installed server alters behavior to read other server messages; practice cross-server isolation and change detection. | 2026-05-05 |

---

## Tool poisoning labs

| Resource | Best for | Exercise ideas (summary) | Last Update |
| --- | --- | --- | --- |
| [bad-mcp][link_github_com_canack_bad_mcp] | Protocol-level attacks, malicious server, tool/schema poisoning | Find hidden instructions; compare metadata pre/post approval; schema fields as instructions; client warnings on definition change | ![](https://badgen.net/github/last-commit/canack/bad-mcp) |
| [MCP Poisoning PoC][link_github_com_gensecaihq_mcp_poisoning_poc] | PoC poisoning in agent workflows | Run basic demo; mutate descriptions; add metadata scanner before/after | ![](https://badgen.net/github/last-commit/gensecaihq/mcp-poisoning-poc) |
| Damn Vulnerable MCP Server (DVMCP) (see “MCP Goat-style projects” above) | CTF: poisoning, rug pulls, shadowing, permissions | Find malicious instruction in tool def; exploit shadowing; fix with stable metadata + approvals | ![](https://badgen.net/github/last-commit/harishsg993010/damn-vulnerable-MCP-server) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] | Scanner / detection engineering | (See main table — toxic corpus, CI, YARA-style rules) | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |

---

## Shadow MCP and misconfiguration labs

| Resource | Relevant labs / focus | Misconfiguration lessons | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Remote HTTP/SSE, secrets/PII, filesystem actions | Network exposure, weak isolation, unsafe file access, untrusted output, secret leakage | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] | Multi-server config, duplicate tool names, bad URLs, env secrets, dangerous args | MCP config is attack surface — scan before use | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |
| [Sherpa MCP Security Workshop][link_github_com_azure_samples_sherpa] | OAuth, MI, gateway, private endpoints, content safety, logging | Defense-in-depth before exposing MCP in cloud/enterprise | ![](https://badgen.net/github/last-commit/Azure-Samples/sherpa) |

---

## Supply chain labs

| Resource | Scenario | Defense exercise | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Namespace typosquatting — Lookalike server name mimics legitimate integration | Package allowlists, provenance, signed verification, registry policy | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Outdated packages — Server ships outdated/vulnerable dependencies | SCA, pin versions, update vulns, CI checks | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] | Supply chain patterns (config) — Risky commands, insecure URLs, env secrets, suspicious tool metadata | Policy-as-code on MCP configs; fail PRs on risky servers | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |


[link_github_com_appsecco_vulnerable_mcp_servers_lab]: https://github.com/appsecco/vulnerable-mcp-servers-lab
[link_github_com_azure_samples_sherpa]: https://github.com/Azure-Samples/sherpa
[link_github_com_canack_bad_mcp]: https://github.com/canack/bad-mcp
[link_github_com_gensecaihq_mcp_poisoning_poc]: https://github.com/gensecaihq/mcp-poisoning-poc
[link_github_com_harishsg993010_damn_vulnerable_mcp_server]: https://github.com/harishsg993010/damn-vulnerable-MCP-server
[link_github_com_mcp_shark_mcp_shark_security_lab]: https://github.com/mcp-shark/mcp-shark-security-lab
[link_vulnerablemcp_info_vuln_github_mcp_exploit_html]: https://vulnerablemcp.info/vuln/github-mcp-exploit.html
[link_vulnerablemcp_info_vuln_whatsapp_message_exfiltration_html]: https://vulnerablemcp.info/vuln/whatsapp-message-exfiltration.html
