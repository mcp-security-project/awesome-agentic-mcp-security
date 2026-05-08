# Official and core MCP repositories

---

## Contents

- [Code repositories](#code-repositories)
- [Security scanners and defensive tools](#security-scanners-and-defensive-tools)
- [Checklists and governance artifacts](#checklists-and-governance-artifacts)
- [Representative security-product MCP servers](#representative-security-product-mcp-servers)
- [Frameworks, adapters, and server builders](#frameworks-adapters-and-server-builders)
- [MCP hosting and enterprise runtimes](#mcp-hosting-and-enterprise-runtimes)
- [Server discovery and awesome lists](#server-discovery-and-awesome-lists)
- [MCP security servers and integrations](mcp_security_servers_and_integrations.md) (separate page)

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

| Repository / Tool                                                                                                                                                                                                                                                                                                                                                                                                             | What It Helps With                                                                                          | Summary                                            | Last updated |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- | ------------ |
| [Agent Scan][link_github_com_snyk_agent_scan] (PyPI `snyk-agent-scan`; legacy path `invariantlabs-ai/mcp-scan` redirects here; see [Invariant “Introducing MCP-Scan”][link_invariantlabs_ai_blog_introducing_mcp_scan])                                                                                                                                                                                                                                                                                                                                                               | Scans agent components for prompt injection, tool poisoning, toxic flows, and related risks                 | Useful for developer workflow and CI-style scanning; do not double-count as a separate “Invariant repo” | ![](https://badgen.net/github/last-commit/snyk/agent-scan) |
| [MCP Scanner][link_github_com_cisco_ai_defense_mcp_scanner]                                                                                                                                                                                                                                                                                                                                     | Scans MCP servers/tools using multiple engines                                                              | Useful for server security review                         | ![](https://badgen.net/github/last-commit/cisco-ai-defense/mcp-scanner) |
| [MCP Security][link_github_com_antgroup_mcp_security] (MCPScan)                                                                                                                                                                                                                                                                                                                                         | Detects metadata pollution, tool poisoning, malicious URLs, unsafe code snippets, and exfiltration patterns | Review rules, false positives, and offline/cloud behavior | ![](https://badgen.net/github/last-commit/antgroup/MCP-Security) |
| [MCP Scan][link_github_com_rodolfboctor_mcp_scan] · [MCP Security Scanner][link_github_com_ogulcanaydogan_mcp_security_scanner]                                                                                                                                                                                                                                         | Scans installed MCP server configs and manifests                                                            | Useful for local developer machines and CI gates          | ![](https://badgen.net/github/last-commit/rodolfboctor/mcp-scan) ![](https://badgen.net/github/last-commit/ogulcanaydogan/mcp-security-scanner) |
| [MCP Shield][link_github_com_riseandignite_mcp_shield] · [Mcpshield][link_github_com_mcpshield_mcpshield] · [MCP Shield][link_github_com_gaboitb_mcp_shield]                                                                                                                                                                                           | Detects tool poisoning, exfiltration channels, and cross-origin escalation patterns                         | Verify maintainer and current repository                  | ![](https://badgen.net/github/last-commit/riseandignite/mcp-shield) ![](https://badgen.net/github/last-commit/mcpshield/mcpshield) ![](https://badgen.net/github/last-commit/GaboITB/mcp-shield) |
| [MCP Guardian][link_github_com_eqtylab_mcp_guardian]                                                                                                                                                                                                                                                                                                                                                     | Helps manage assistant access to MCP servers                                                                | Useful for human approval and local control               | ![](https://badgen.net/github/last-commit/eqtylab/mcp-guardian) |
| [Mcpproxy Go][link_github_com_smart_mcp_proxy_mcpproxy_go]                                                                                                                                                                                                                                                                                                                                       | Routes and manages access to multiple MCP servers                                                           | Review sandboxing, quarantine, and policy features        | ![](https://badgen.net/github/last-commit/smart-mcp-proxy/mcpproxy-go) |
| [mcpwatch][link_github_com_lazymac2x_mcpwatch]                                                                                                                                                                                                                                                                                                                                                         | MCP server security scanning (Go; project name **mcpwatch**)                                                                                | Track capabilities and maintenance status; distinct from **mcp-watch** below                 | ![](https://badgen.net/github/last-commit/lazymac2x/mcpwatch) |
| [mcp-watch][link_github_com_kapilduraphe_mcp_watch] (npm `mcp-watch`)                                                                                                                                                                                                                                                                                                                                                         | Descriptor-focused MCP security scanner (Node)                                                                                | Overlaps conceptually with other scanners—pick one per pipeline; not the same repo as mcpwatch                 | ![](https://badgen.net/github/last-commit/kapilduraphe/mcp-watch) |
| [SecureMCP][link_github_com_makalin_securemcp]                                                                                                                                                                                                                                                                                                                                                         | Audits MCP usage: OAuth tokens, prompt injection probes, TLS/auth posture                                                                                | Validate reporting format before executive consumption                 | ![](https://badgen.net/github/last-commit/makalin/SecureMCP) |
| [AI-Infra-Guard][link_github_com_tencent_ai_infra_guard]                                                                                                                                                                                                                                                                                                                                                         | Tencent Zhuque Lab platform: MCP/agent skills scanning, infra checks, jailbreak eval, and related workflows                                                                                | Broad surface—scope which modules you enable; see [conference talks](mcp_conference_talks.md) for MCP briefing PDF                 | ![](https://badgen.net/github/last-commit/Tencent/AI-Infra-Guard) |
| [mcp-context-protector][link_github_com_trailofbits_mcp_context_protector]                                                                                                                                                                                                                                                                                                                                                         | Client-side MCP wrapper emphasizing malicious context / description attacks                                                                                | Complements scanners and gateways; read Trail of Bits blog series for threat model                 | ![](https://badgen.net/github/last-commit/trailofbits/mcp-context-protector) |
| [MCP-Defender][link_github_com_mcp_defender_mcp_defender]                                                                                                                                                                                                                                                                                                                                                         | Desktop proxy that inspects and gates MCP sessions from common AI IDEs                                                                                | AGPL; confirm trust model for signature / LLM-assisted checks                 | ![](https://badgen.net/github/last-commit/MCP-Defender/MCP-Defender) |
| [defenter-proxy][link_github_com_defenter_ai_defenter_proxy]                                                                                                                                                                                                                                                                                                                                                         | Semantic MCP + agent action broker (VS Code / Cursor paths)                                                                                | Cloud-assisted policy—review data handling and availability SLOs                 | ![](https://badgen.net/github/last-commit/Defenter-AI/defenter-proxy) |
| [MCP-Dandan][link_github_com_82ch_mcp_dandan]                                                                                                                                                                                                                                                                                                                                                         | Desktop MCP session monitor (Electron UI)                                                                                | Operational noise vs. security signal—tune before production SOC feeds                 | ![](https://badgen.net/github/last-commit/82ch/MCP-Dandan) |
| [MCP Audit extension][link_github_com_agentity_com_mcp_audit_extension]                                                                                                                                                                                                                                                                                                                                                         | VS Code extension: logs/forwards Copilot MCP tool calls for audit                                                                                | IDE-only visibility; pair with server-side controls                 | ![](https://badgen.net/github/last-commit/Agentity-com/mcp-audit-extension) |
| [MCP Ethical Hacking][link_github_com_cmpxchg16_mcp_ethical_hacking]                                                                                                                                                                                                                                                                                                                                                         | Educational MCP samples illustrating abuse classes                                                                                | **Authorized testing only**; lab isolation                 | ![](https://badgen.net/github/last-commit/cmpxchg16/mcp-ethical-hacking) |
| [octocode-mcp][link_github_com_bgauryy_octocode_mcp]                                                                                                                                                                                                                                                                                                                                                         | Research-oriented MCP tooling for GitHub-centric dev workflows ([octocode.ai](https://octocode.ai))                                                                                | Requires GitHub auth—treat tokens like production secrets                 | ![](https://badgen.net/github/last-commit/bgauryy/octocode-mcp) |
| [MCP Server Scanner][link_mcpserverscanner_com] · [MCPScan.ai][link_mcpscan_ai]                                                                                                                                                                                                                                                                                                                                                         | Web-based MCP assessment / discovery surfaces                                                                                | Read privacy policy before submitting manifests or endpoints                 | 2026-05-06 |
| [MCP Doctor][link_github_com_realwigu_mcp_doctor] · [MCP Doctor][link_github_com_agentopssec_mcp_doctor]                                                                                                                                                                                                                                                                       | Detects broken or risky MCP configs                                                                         | Useful for developer hygiene                              | ![](https://badgen.net/github/last-commit/realwigu/mcp-doctor) ![](https://badgen.net/github/last-commit/AgentOpsSec/mcp-doctor) |

## Checklists and governance artifacts

| Repository / Tool | What It Helps With | Summary | Last updated |
| --- | --- | --- | --- |
| [MCP Security Checklist][link_github_com_slowmist_mcp_security_checklist] | Structured review items for MCP design, deployment, and operations | Complements automated scanners; not a substitute for testing | ![](https://badgen.net/github/last-commit/slowmist/MCP-Security-Checklist) |

## Representative security-product MCP servers

| Repository / Tool | What It Helps With | Summary | Last updated |
| --- | --- | --- | --- |
| [Semgrep MCP][link_github_com_semgrep_mcp] | Run [Semgrep](https://semgrep.dev/) on code from an MCP client | Tokens, deployment mode, and repo scope; treat scan targets as sensitive | ![](https://badgen.net/github/last-commit/semgrep/mcp) |
| [Burp Suite MCP][link_github_com_portswigger_mcp_server] | Drive [Burp Suite](https://portswigger.net/burp) web testing via MCP | **Authorized testing only**; findings and session material need engagement-grade handling | ![](https://badgen.net/github/last-commit/PortSwigger/mcp-server) |
| [Google Security Operations MCP][link_github_com_google_mcp_security] | Access Google security operations / threat intel products via MCP | Cloud identity least privilege; audit API usage and data residency | ![](https://badgen.net/github/last-commit/google/mcp-security) |
| [Ghidra MCP][link_github_com_lauriewired_ghidramcp] | **Reverse engineering:** drive [Ghidra](https://ghidra-sre.org/) from an MCP client | Malware and IP in dedicated labs; see integrations page for alternates (e.g. GhidrAssist) | ![](https://badgen.net/github/last-commit/LaurieWired/GhidraMCP) |
| [radare2-mcp][link_github_com_radareorg_radare2_mcp] | **Reverse engineering:** drive [Radare2](https://rada.re/) from an MCP client | Malware and IP in dedicated labs; confirm tool scope against untrusted binaries | ![](https://badgen.net/github/last-commit/radareorg/radare2-mcp) |
| [ida-pro-mcp][link_github_com_mrexodia_ida_pro_mcp] | **Reverse engineering:** drive [IDA Pro](https://hex-rays.com/ida-pro/) from an MCP client | Commercial license; malware/IP in dedicated labs; see integrations page for headless IDA options | ![](https://badgen.net/github/last-commit/mrexodia/ida-pro-mcp) |
| [binary_ninja_mcp][link_github_com_fosdickio_binary_ninja_mcp] | **Reverse engineering:** drive [Binary Ninja](https://binary.ninja/) from an MCP client | Commercial license; malware and IP in dedicated labs | ![](https://badgen.net/github/last-commit/fosdickio/binary_ninja_mcp) |
| [jadx-ai-mcp][link_github_com_zinja_jadx_ai_mcp] | **Mobile / APK analysis:** drive [JADX](https://github.com/skylot/jadx) from an MCP client | APKs may contain secrets and PII; use isolated analysis; see integrations page for APKTool, MobSF, etc. | ![](https://badgen.net/github/last-commit/zinja-coder/jadx-ai-mcp) |
| [Panther SIEM MCP][link_github_com_panther_labs_mcp_panther] | **SIEM:** query and operate [Panther](https://panther.com/) via MCP | SOC-tier data access; separate credentials from analyst laptops; confirm transport and retention | ![](https://badgen.net/github/last-commit/panther-labs/mcp-panther) |
| [Wazuh MCP][link_github_com_gbrigandi_mcp_server_wazuh] | **SIEM / XDR:** drive [Wazuh](https://wazuh.com/) from an MCP client | SOC-tier data access; least privilege on Wazuh API keys; confirm transport and retention | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-wazuh) |
| [TheHive MCP][link_github_com_gbrigandi_mcp_server_thehive] | **Case management:** drive [TheHive](https://strangebee.com/thehive/) from an MCP client | Incident data is sensitive; restrict API users; confirm transport and retention | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-thehive) |
| [Cortex MCP][link_github_com_gbrigandi_mcp_server_cortex] | **SOAR / analyzers:** drive [Cortex](https://strangebee.com/cortex/) from an MCP client | Analyzer outputs may include secrets; least privilege; confirm transport and retention | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-cortex) |
| [RunReveal MCP][link_runreveal_mcp_docs] | **Log analytics:** use RunReveal via MCP ([vendor MCP docs](https://docs.runreveal.com/reference/model-context-protocol)) | SOC-tier data access; separate credentials; confirm transport and retention per vendor guidance | 2026-05-06 |

## Frameworks, adapters, and server builders

| Repository / Tool                                                                                                                                                                                                     | Why It Matters                                    | Summary                                                   | Last updated |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- | ---------------------------------------------------------------- | ------------ |
| [Fastmcp][link_github_com_prefecthq_fastmcp]                                                                                                                                                   | Rapid MCP server development                      | Ensure safe defaults, auth, and tool review                      | ![](https://badgen.net/github/last-commit/PrefectHQ/fastmcp) |
| [Langchain MCP Adapters][link_github_com_langchain_ai_langchain_mcp_adapters]                                                                                                             | Lets LangChain agents use MCP tools               | Review tool routing and untrusted output handling                | ![](https://badgen.net/github/last-commit/langchain-ai/langchain-mcp-adapters) |
| [Spring Ai][link_github_com_spring_projects_spring_ai]                                                                                                                                   | Java/Spring MCP client/server support             | Review OAuth, API key handling, and enterprise policy support    | ![](https://badgen.net/github/last-commit/spring-projects/spring-ai) |
| [MCP Handler][link_github_com_vercel_mcp_handler]                                                                                                                                                 | Deploy MCP servers in web/serverless environments | Review remote auth and tenant isolation                          | ![](https://badgen.net/github/last-commit/vercel/mcp-handler) |
| [Fastapi MCP][link_github_com_tadata_org_fastapi_mcp] · [Fastapi MCP][link_github_com_lakshmana64_fastapi_mcp]                                                       | Exposes APIs as MCP tools                         | High risk if endpoints are exposed without review                | ![](https://badgen.net/github/last-commit/tadata-org/fastapi_mcp) ![](https://badgen.net/github/last-commit/lakshmana64/fastapi-mcp) |
| [Modelfetch][link_github_com_phuctm97_modelfetch] · [Easymcp][link_github_com_secretiveshell_easymcp]                                                             | Boilerplates and helper libraries                 | Check for auth, validation, logging, and maintained dependencies | ![](https://badgen.net/github/last-commit/phuctm97/modelfetch) ![](https://badgen.net/github/last-commit/SecretiveShell/easymcp) |
| [workers-mcp][link_github_com_cloudflare_workers_mcp]                                                                                                                                                   | Cloudflare Worker ↔ local MCP bridge (CLI + Worker helpers)                      | Remote MCP guidance supersedes some older patterns—follow current Cloudflare Agents docs; sandbox Worker secrets                 | ![](https://badgen.net/github/last-commit/cloudflare/workers-mcp) |

## MCP hosting and enterprise runtimes

| Repository / Tool | Why It Matters | Summary | Last updated |
| --- | --- | --- | --- |
| [ToolHive][link_github_com_stackloklabs_toolhive] | Open-source MCP platform: container-isolated servers, identity hooks, K8s operator, observability | Distinct from [osv-mcp][link_github_com_stackloklabs_osv_mcp] in the integrations catalog—both are Stacklok ecosystem | ![](https://badgen.net/github/last-commit/StacklokLabs/toolhive) |

## Server discovery and awesome lists

| Repository / Source                                                                                                                                                                                                       | Why It Matters                                 | Summary                                           | Last updated |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- | -------------------------------------------------------- | ------------ |
| [punkpeye/awesome-mcp-servers - Awesome MCP Servers][link_github_com_punkpeye_awesome_mcp_servers]                                                                                                                                  | Canonical community awesome-list of MCP server repos; includes a long curated [#security][link_github_com_punkpeye_awesome_mcp_servers_security] section | Discovery only-not a trust boundary; verify each server, maintainer, and install path independently | ![](https://badgen.net/github/last-commit/punkpeye/awesome-mcp-servers) |
| [lirantal/awesome-mcp-best-practices - Awesome MCP Best Practices][link_github_com_lirantal_awesome_mcp_best_practices] | Curated best practices for MCP servers and clients | Use as guidance; still validate each server’s threat model, auth, and permissions | ![](https://badgen.net/github/last-commit/lirantal/awesome-mcp-best-practices) |
| [Awesome MCP Servers][link_github_com_wong2_awesome_mcp_servers] · [mcpservers.org][link_mcpservers_org]                                                                                          | Categorized MCP server discovery               | Validate freshness, repo ownership, and install commands | ![](https://badgen.net/github/last-commit/wong2/awesome-mcp-servers) |
| [Awesome MCP Servers][link_github_com_appcypher_awesome_mcp_servers]                                                                                                                              | Another curated server list                    | Cross-check duplicates and abandoned entries             | ![](https://badgen.net/github/last-commit/appcypher/awesome-mcp-servers) |
| [Arindam200/awesome-ai-apps][link_github_com_arindam200_awesome_ai_apps] | Curated “awesome list” of AI applications and demos | Broad AI app discovery (not MCP-specific); treat as an ideas index and validate each linked repo’s security posture and permissions | ![](https://badgen.net/github/last-commit/Arindam200/awesome-ai-apps) |
| [mcp.so][link_mcp_so]                                                                                                                                                                                                   | Broad ecosystem discovery                      | Validate publisher, permissions, and package provenance  | 2026-05-06 |
| [PulseMCP][link_pulsemcp_com] · [Github][link_github_com_pulsemcp]                                                                                                                                  | Tracks clients, servers, and ecosystem updates | Useful for discovery, not a trust boundary               | 2026-05-06 |
| [Glama MCP directory][link_glama_ai_mcp_servers]                                                                                                                                                                         | Server discovery and metadata                  | Review verification model before trusting entries        | 2026-05-06 |



[link_github_com_82ch_mcp_dandan]: https://github.com/82ch/MCP-Dandan
[link_github_com_agentity_com_mcp_audit_extension]: https://github.com/Agentity-com/mcp-audit-extension
[link_github_com_agentopssec_mcp_doctor]: https://github.com/AgentOpsSec/mcp-doctor
[link_github_com_antgroup_mcp_security]: https://github.com/antgroup/MCP-Security
[link_github_com_appcypher_awesome_mcp_servers]: https://github.com/appcypher/awesome-mcp-servers
[link_github_com_arindam200_awesome_ai_apps]: https://github.com/Arindam200/awesome-ai-apps
[link_github_com_bgauryy_octocode_mcp]: https://github.com/bgauryy/octocode-mcp
[link_github_com_cloudflare_workers_mcp]: https://github.com/cloudflare/workers-mcp
[link_github_com_cmpxchg16_mcp_ethical_hacking]: https://github.com/cmpxchg16/mcp-ethical-hacking
[link_github_com_cisco_ai_defense_mcp_scanner]: https://github.com/cisco-ai-defense/mcp-scanner
[link_github_com_defenter_ai_defenter_proxy]: https://github.com/Defenter-AI/defenter-proxy
[link_github_com_eqtylab_mcp_guardian]: https://github.com/eqtylab/mcp-guardian
[link_github_com_fosdickio_binary_ninja_mcp]: https://github.com/fosdickio/binary_ninja_mcp
[link_github_com_gaboitb_mcp_shield]: https://github.com/GaboITB/mcp-shield
[link_github_com_gbrigandi_mcp_server_cortex]: https://github.com/gbrigandi/mcp-server-cortex
[link_github_com_gbrigandi_mcp_server_thehive]: https://github.com/gbrigandi/mcp-server-thehive
[link_github_com_gbrigandi_mcp_server_wazuh]: https://github.com/gbrigandi/mcp-server-wazuh
[link_github_com_google_mcp_security]: https://github.com/google/mcp-security
[link_github_com_lauriewired_ghidramcp]: https://github.com/LaurieWired/GhidraMCP
[link_github_com_mrexodia_ida_pro_mcp]: https://github.com/mrexodia/ida-pro-mcp
[link_github_com_panther_labs_mcp_panther]: https://github.com/panther-labs/mcp-panther
[link_github_com_portswigger_mcp_server]: https://github.com/PortSwigger/mcp-server
[link_github_com_radareorg_radare2_mcp]: https://github.com/radareorg/radare2-mcp
[link_github_com_semgrep_mcp]: https://github.com/semgrep/mcp
[link_github_com_zinja_jadx_ai_mcp]: https://github.com/zinja-coder/jadx-ai-mcp
[link_runreveal_mcp_docs]: https://docs.runreveal.com/reference/model-context-protocol
[link_github_com_github_github_mcp_server]: https://github.com/github/github-mcp-server
[link_github_com_lakshmana64_fastapi_mcp]: https://github.com/lakshmana64/fastapi-mcp
[link_invariantlabs_ai_blog_introducing_mcp_scan]: https://invariantlabs.ai/blog/introducing-mcp-scan
[link_github_com_kapilduraphe_mcp_watch]: https://github.com/kapilduraphe/mcp-watch
[link_github_com_langchain_ai_langchain_mcp_adapters]: https://github.com/langchain-ai/langchain-mcp-adapters
[link_github_com_lazymac2x_mcpwatch]: https://github.com/lazymac2x/mcpwatch
[link_github_com_lirantal_awesome_mcp_best_practices]: https://github.com/lirantal/awesome-mcp-best-practices
[link_github_com_makalin_securemcp]: https://github.com/makalin/SecureMCP
[link_github_com_mcp_defender_mcp_defender]: https://github.com/MCP-Defender/MCP-Defender
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
[link_github_com_punkpeye_awesome_mcp_servers_security]: https://github.com/punkpeye/awesome-mcp-servers#security
[link_github_com_realwigu_mcp_doctor]: https://github.com/realwigu/mcp-doctor
[link_github_com_riseandignite_mcp_shield]: https://github.com/riseandignite/mcp-shield
[link_github_com_rodolfboctor_mcp_scan]: https://github.com/rodolfboctor/mcp-scan
[link_github_com_secretiveshell_easymcp]: https://github.com/SecretiveShell/easymcp
[link_github_com_smart_mcp_proxy_mcpproxy_go]: https://github.com/smart-mcp-proxy/mcpproxy-go
[link_github_com_snyk_agent_scan]: https://github.com/snyk/agent-scan
[link_github_com_slowmist_mcp_security_checklist]: https://github.com/slowmist/MCP-Security-Checklist
[link_github_com_stackloklabs_osv_mcp]: https://github.com/StacklokLabs/osv-mcp
[link_github_com_stackloklabs_toolhive]: https://github.com/StacklokLabs/toolhive
[link_github_com_spring_projects_spring_ai]: https://github.com/spring-projects/spring-ai
[link_github_com_tencent_ai_infra_guard]: https://github.com/Tencent/AI-Infra-Guard
[link_github_com_trailofbits_mcp_context_protector]: https://github.com/trailofbits/mcp-context-protector
[link_github_com_tadata_org_fastapi_mcp]: https://github.com/tadata-org/fastapi_mcp
[link_github_com_vercel_mcp_handler]: https://github.com/vercel/mcp-handler
[link_github_com_wong2_awesome_mcp_servers]: https://github.com/wong2/awesome-mcp-servers
[link_glama_ai_mcp_servers]: https://glama.ai/mcp/servers
[link_mcp_so]: https://mcp.so/
[link_mcpscan_ai]: https://mcpscan.ai/
[link_mcpservers_org]: https://mcpservers.org/
[link_mcpserverscanner_com]: https://mcpserverscanner.com/
[link_pulsemcp_com]: https://www.pulsemcp.com/
