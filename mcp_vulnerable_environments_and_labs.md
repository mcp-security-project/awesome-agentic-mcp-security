# Vulnerable MCP Environments and Labs

Educational and research environments for MCP security testing. **Tables** summarize difficulty and defenses. Run all labs in isolated VMs or containers — never in production or on networks with real credentials.

**Last Update**: 2026-08-25

## Contents

- [MCP Goat–style projects (full detail)](#mcp-goatstyle-projects-full-detail)
- [OWASP MCP Top 10 mapped labs](#owasp-mcp-top-10-mapped-labs)
- [Attack/defense paired labs](#attackdefense-paired-labs)
- [Prompt injection labs](#prompt-injection-labs)
- [Tool poisoning labs](#tool-poisoning-labs)
- [Shadow MCP and misconfiguration labs](#shadow-mcp-and-misconfiguration-labs)
- [Supply chain labs](#supply-chain-labs)
- [Authentication, OAuth & transport labs](#authentication-oauth--transport-labs)
- [Reference: CVE catalog & PoC repos](#reference-cve-catalog--poc-repos)

---

## MCP Goat–style projects (full detail)

| Project : Maintainer | MCP components | Vulnerabilities covered | Last Update |
| --- | --- | --- | --- |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] : SabyasachiDhal | Tools, resources, prompts, sampling, Streamable HTTP, victim-agent harness | 26 CTF challenges (78 flags): RCE, SSRF, SQLi, path traversal, tool poisoning, shadowing, rug pulls, indirect injection, sampling abuse | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [Damn Vulnerable MCP Server (DVMCP)][link_github_com_harishsg993010_damn_vulnerable_mcp_server] : harishsg993010 | Server, tools, prompts, resources, SSE, client config | Prompt injection, tool poisoning, excessive permissions, rug pull, shadowing, indirect injection, token theft | ![](https://badgen.net/github/last-commit/harishsg993010/damn-vulnerable-MCP-server) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] : Appsecco | Local/remote servers, filesystem, HTTP/SSE, tool output, client config | Path traversal, unsandboxed exec, indirect/remote injection, malicious tools, typosquatting, outdated pkgs, secrets/PII, untrusted content | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [IntegSec VulnerableMCP][link_github_com_integsec_vulnerablemcp] : IntegSec | stdio, HTTP/SSE, HTTPS/SSE, WebSocket, WSS transports | 20+ vulns, 16+ CTF flags: path traversal, command injection, missing auth, cleartext transport, JSON-RPC flaws, tool poisoning, rug pulls, resource exhaustion | ![](https://badgen.net/github/last-commit/integsec/VulnerableMCP) |
| [Vulnerable MCP Server (beejak)][link_github_com_beejak_vulnerable_mcp_server] : beejak | stdio, SSE, OAuth metadata, tools, agent chains | 18 CVE-mapped CTF flags: CVE-2025-6514 OAuth RCE, rug pull, shadowing, SSRF, deserialization, multi-vector chains; `show_fix` secure comparisons | ![](https://badgen.net/github/last-commit/beejak/vulnerable-mcp-server) |
| [bad-mcp][link_github_com_canack_bad_mcp] : canack | Tool descriptions, schemas, resources, sessions, cross-server | Full-schema poisoning, advanced poisoning, rug pulls, resource poisoning, cross-server shadowing, protocol attacks | ![](https://badgen.net/github/last-commit/canack/bad-mcp) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] : MCP Shark | MCP config, tools, resources, prompts, multi-server harness, Cursor config, YARA-style rules, auth fixtures | Toxic metadata, prompt injection, command injection patterns, oversharing, privilege abuse, bad URLs, env secrets, duplicate tools, bad args, weak authZ | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] : PawelKozy | Dockerized FastMCP servers, fixtures, pytest regressions | 10 real-incident/CVE scenarios with vulnerable + secure pairs; Cursor/Claude exploit walkthroughs | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| [MCP Security Summit Workshop (Sherpa)][link_github_com_azure_samples_sherpa] : Microsoft Azure Samples | Servers, Azure ID, OAuth, MI, Key Vault, gateway, private endpoints, content safety, logging, red/blue validation | Auth gaps, over-permissioned access, weak I/O, no monitoring, unsafe cloud patterns | ![](https://badgen.net/github/last-commit/Azure-Samples/sherpa) |
| [mcp-security-workshop][link_github_com_antoninbr_mcp_security_workshop] : antoninBr | Containerized stdio servers, Docker logs, VS Code sandbox demos | 5 CTF exercises: side-channel execution, secret exfiltration, supply chain poisoning, prompt injection, container poisoning | ![](https://badgen.net/github/last-commit/antoninBr/mcp-security-workshop) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] : aminrj-labs | Custom Python agent, local LLM (Ollama/LM Studio), offline MCP servers | Tool poisoning, cross-server shadowing, RAG injection, agentic memory attacks, MCP→A2A kill chain | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCP Attack & Def3nd][link_github_com_hello_urvesh_mcp_attack_def3nd] : hello-urvesh | Vulnerable + secured server pairs, Nullcon 2026 workshop | 8 OWASP MCP Top 10 risks with side-by-side SECURING.md comparisons | ![](https://badgen.net/github/last-commit/hello-urvesh/mcp-attack-def3nd) |
| [vulnMCP][link_github_com_n0v1chok_vulnmcp] : N0V1CHOK | stdio server, terminal UI, gamified scoring | 8 progressive challenges: parameter injection, resource URI manipulation, context poisoning, prompt chains, sampling abuse, protocol injection | ![](https://badgen.net/github/last-commit/N0V1CHOK/vulnMCP) |
| [Vulnerable MCP Server (JoyGhoshs)][link_github_com_joyghoshs_vulnerable_mcp_server] : JoyGhoshs | stdio tools, Docker isolation | 14 vuln classes: OS command injection, path traversal, pickle RCE, arbitrary Python exec, SSRF, tool poisoning, rug pull, shadow backdoors | ![](https://badgen.net/github/last-commit/JoyGhoshs/vulnerable-mcp-server) |
| [MCP Poisoning PoC][link_github_com_gensecaihq_mcp_poisoning_poc] : GenSecAI | Tools, descriptions, agent workflows | Tool poisoning in real-world agent flows | ![](https://badgen.net/github/last-commit/gensecaihq/mcp-poisoning-poc) |

---

## OWASP MCP Top 10 mapped labs

| Project (linked) | Mapping | Summary | Last Update |
| --- | --- | --- | --- |
| [MCP-Goat (OWASP)][link_github_com_satishpatnayak_mcp_goat] | All 10 OWASP MCP Top 10 categories | CLI-driven WebGoat-style challenges (`mcp-goat list` / `run` / `exercise`) with guided exploit steps and LLM client config snippets for Claude Desktop/Cursor. | ![](https://badgen.net/github/last-commit/satishpatnayak/MCP-Goat) |
| [BrokenMCP][link_github_com_truststrikelabs_brokenmcp] | One lab per OWASP MCP Top 10 risk | Deliberately broken servers with blog walkthroughs for token mismanagement, scope creep, tool poisoning, supply chain, command injection, intent subversion, auth gaps, audit gaps, shadow servers, context over-sharing. | ![](https://badgen.net/github/last-commit/truststrikelabs/BrokenMCP) |
| [mcploitable][link_github_com_agilealligator_mcploitable] | OWASP Top 10 for Agentic Applications | "Metasploitable for MCP" — single vulnerable server mapped to agentic-application risk categories for red-team training. | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |
| [IMCP (Insecure Model Context Protocol)][link_github_com_nav33n25_imcp] | Enterprise scenarios across OWASP MCP themes | 14 critical weaknesses in business contexts: consent fatigue, compliance-scanner bypass, human-factor exploitation, progressive red-flag training modules. | ![](https://badgen.net/github/last-commit/nav33n25/imcp) |

---

## Attack/defense paired labs

| Resource | Vulnerable → secure model | Best for | Last Update |
| --- | --- | --- | --- |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | Dockerized vulnerable + secure FastMCP pairs per challenge | Reproducing real CVE/incident flows in Cursor/Claude, then validating mitigations with pytest | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| [MCP Attack & Def3nd][link_github_com_hello_urvesh_mcp_attack_def3nd] | Side-by-side vulnerable + hardened servers + SECURING.md | Nullcon 2026 workshop; comparing attack vs. fix for eight OWASP MCP Top 10 risks | ![](https://badgen.net/github/last-commit/hello-urvesh/mcp-attack-def3nd) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | Easy / Moderate / Difficult + Secure reference level per challenge | Verifying every documented exploit fails at Secure level (`npm run attack -- … secure`) | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [Vulnerable MCP Server (beejak)][link_github_com_beejak_vulnerable_mcp_server] | `show_fix` mode per challenge | CVE-accurate before/after code comparisons for OAuth RCE, rug pull, shadowing, and chained attacks | ![](https://badgen.net/github/last-commit/beejak/vulnerable-mcp-server) |
| [Sherpa MCP Security Workshop][link_github_com_azure_samples_sherpa] | Base Camp → Summit progressive hardening + red/blue validation | Cloud/enterprise defense-in-depth: OAuth 2.1, MI, Key Vault, gateway, content safety, logging | ![](https://badgen.net/github/last-commit/Azure-Samples/sherpa) |

---

## Prompt injection labs

| Project (linked) | Lab / scenario | Summary | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Local indirect prompt injection | Local retrieval returns untrusted docs with hidden instructions; practice instruction/data separation and confirmation gates. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Remote indirect prompt injection | Remote HTTP/SSE content becomes instructions; practice origin trust, auth, isolation, and logging. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Malicious tools / fabricated output | Tool appears to return status data but injects misleading instructions and fabricates plausible incidents. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Wikipedia HTTP streamable | Public content returned without sanitization; practice remote-content prompt injection over Streamable HTTP. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | News prompt injection, GitHub public issue injection | Real-incident indirect injection via untrusted retrieved content and public issue text; compare with sanitized secure builds. | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | RAG injection, agentic memory attacks | Offline reproduction of injection via retrieval and persistent agent memory in a custom Python agent harness. | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | Indirect prompt injection challenges | Tiered CTF flags for injection via tools, resources, and sampling across Easy/Moderate/Difficult levels. | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [github-mcp-exploit][link_vulnerablemcp_info_vuln_github_mcp_exploit_html] | GitHub toxic agent flow | Malicious issue + broad GitHub token → private data exfil path; practice scoped tokens and approvals. | 2026-08-25 |
| [whatsapp-message-exfiltration][link_vulnerablemcp_info_vuln_whatsapp_message_exfiltration_html] | Messaging bridge exfiltration | Co-installed server alters behavior to read other server messages; practice cross-server isolation and change detection. | 2026-08-25 |
| [rug-pulls-silent-redefinition][link_vulnerablemcp_info_vuln_rug_pulls_silent_redefinition_html] | Rug pull via description mutation | Tool mutates after approval; practice description hashing, re-approval gates, and ETDI-style signing. | 2026-08-25 |

---

## Tool poisoning labs

| Resource | Best for | Exercise ideas (summary) | Last Update |
| --- | --- | --- | --- |
| [bad-mcp][link_github_com_canack_bad_mcp] | Protocol-level attacks, malicious server, tool/schema poisoning | Find hidden instructions; compare metadata pre/post approval; schema fields as instructions; client warnings on definition change | ![](https://badgen.net/github/last-commit/canack/bad-mcp) |
| [MCP Poisoning PoC][link_github_com_gensecaihq_mcp_poisoning_poc] | PoC poisoning in agent workflows | Run basic demo; mutate descriptions; add metadata scanner before/after | ![](https://badgen.net/github/last-commit/gensecaihq/mcp-poisoning-poc) |
| [MCP Injection Experiments][link_github_com_invariantlabs_ai_mcp_injection_experiments] | Canonical Invariant Labs PoCs | Reproduce direct poisoning, tool shadowing, and WhatsApp rug-pull/sleeper attacks in Cursor or Claude Desktop. | ![](https://badgen.net/github/last-commit/invariantlabs-ai/mcp-injection-experiments) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | Offline poisoning + shadowing reproduction | Lab 01: local Invariant-style poisoning with custom agent + LM Studio; includes `mcp-scan` detection guidance. | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | Repello.ai-style rug pull | Tool metadata mutates after approval to exfiltrate API keys; compare with secure metadata-pinning build. | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| Damn Vulnerable MCP Server (DVMCP) (see “MCP Goat–style projects” above) | CTF: poisoning, rug pulls, shadowing, permissions | Find malicious instruction in tool def; exploit shadowing; fix with stable metadata + approvals | ![](https://badgen.net/github/last-commit/harishsg993010/damn-vulnerable-MCP-server) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | Tiered poisoning + shadowing CTF | Tool poisoning, rug pulls, and cross-server shadowing at three difficulty levels plus Secure reference. | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] | Scanner / detection engineering | Toxic corpus, CI integration, YARA-style rules for poisoned metadata patterns | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |
| [MCPHammer][link_github_com_praetorian_inc_mcphammer] | Offensive testing framework | Text injection, remote management, init-tool download/execute, C2-via-tool-argument scanning demos | ![](https://badgen.net/github/last-commit/praetorian-inc/MCPHammer) |

---

## Shadow MCP and misconfiguration labs

| Resource | Relevant labs / focus | Misconfiguration lessons | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Remote HTTP/SSE, secrets/PII, filesystem actions | Network exposure, weak isolation, unsafe file access, untrusted output, secret leakage | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] | Multi-server config, duplicate tool names, bad URLs, env secrets, dangerous args | MCP config is attack surface — scan before use | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |
| [Sherpa MCP Security Workshop][link_github_com_azure_samples_sherpa] | OAuth, MI, gateway, private endpoints, content safety, logging | Defense-in-depth before exposing MCP in cloud/enterprise | ![](https://badgen.net/github/last-commit/Azure-Samples/sherpa) |
| [mcp-security-workshop][link_github_com_antoninbr_mcp_security_workshop] | Side-channel execution, secret exfiltration, container poisoning | Hidden malicious actions behind innocent tools; audit via Docker logs, network monitoring, filesystem inspection | ![](https://badgen.net/github/last-commit/antoninBr/mcp-security-workshop) |
| [BrokenMCP][link_github_com_truststrikelabs_brokenmcp] | MCP09 shadow servers, MCP08 audit gaps | Rogue co-installed servers and missing telemetry that hides cross-server abuse | ![](https://badgen.net/github/last-commit/truststrikelabs/BrokenMCP) |
| [MCP-Goat (OWASP)][link_github_com_satishpatnayak_mcp_goat] | MCP09 shadow servers, MCP08 data exfiltration | Rogue MCP server registration and insufficient logging/telemetry controls | ![](https://badgen.net/github/last-commit/satishpatnayak/MCP-Goat) |
| [IMCP][link_github_com_nav33n25_imcp] | Consent fatigue, compliance-scanner bypass | Human-factor misconfigurations that bypass approval-based security controls | ![](https://badgen.net/github/last-commit/nav33n25/imcp) |

---

## Supply chain labs

| Resource | Scenario | Defense exercise | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Namespace typosquatting — Lookalike server name mimics legitimate integration | Package allowlists, provenance, signed verification, registry policy | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Outdated packages — Server ships outdated/vulnerable dependencies | SCA, pin versions, update vulns, CI checks | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] | Supply chain patterns (config) — Risky commands, insecure URLs, env secrets, suspicious tool metadata | Policy-as-code on MCP configs; fail PRs on risky servers | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |
| [BrokenMCP][link_github_com_truststrikelabs_brokenmcp] | MCP04 supply chain & dependency tampering | Detect tampered dependencies and unsigned server packages before install | ![](https://badgen.net/github/last-commit/truststrikelabs/BrokenMCP) |
| [mcp-security-workshop][link_github_com_antoninbr_mcp_security_workshop] | Supply chain poisoning via malicious MCP server install | Pre-installation security checklist; VS Code MCP sandbox as mitigation | ![](https://badgen.net/github/last-commit/antoninBr/mcp-security-workshop) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | Git command injection (GHSA-3q26-f695-pp76) | Unsanitized repo names in `git init` helper; compare with execFile/allowlist secure build | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |

---

## Authentication, OAuth & transport labs

| Resource | Scenario | Defense exercise | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Server (beejak)][link_github_com_beejak_vulnerable_mcp_server] | CVE-2025-6514 OAuth RCE via mcp-remote | Crafted `authorization_endpoint` in OAuth metadata → OS command injection on client; practice pinning and URL validation | ![](https://badgen.net/github/last-commit/beejak/vulnerable-mcp-server) |
| [IntegSec VulnerableMCP][link_github_com_integsec_vulnerablemcp] | Missing auth, cleartext HTTP/WS, no rate limiting | Enforce transport auth, TLS, session binding, and rate limits across stdio/HTTP/SSE/WS/WSS | ![](https://badgen.net/github/last-commit/integsec/VulnerableMCP) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | CRM auth bypass, X-Forwarded-For trust, IDOR | Scope credentials per tenant; canonical path enforcement; reject spoofed client headers | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | Streamable HTTP transport, Origin allow-list bypass | Practice DNS rebinding and transport-layer auth gaps; validate Secure-level Origin enforcement | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [MCP Attack & Def3nd][link_github_com_hello_urvesh_mcp_attack_def3nd] | Auth bypass, SSRF, mass assignment | Side-by-side hardened builds for broken authentication and unsafe outbound fetch patterns | ![](https://badgen.net/github/last-commit/hello-urvesh/mcp-attack-def3nd) |
| [Sherpa MCP Security Workshop][link_github_com_azure_samples_sherpa] | OAuth 2.1, managed identity, private endpoints | Enterprise identity and network isolation before exposing remote MCP in Azure | ![](https://badgen.net/github/last-commit/Azure-Samples/sherpa) |
| [vulnMCP][link_github_com_n0v1chok_vulnmcp] | Sampling manipulation, protocol message injection | Validate MCP protocol messages and restrict sampling capability abuse | ![](https://badgen.net/github/last-commit/N0V1CHOK/vulnMCP) |

---

## Reference: CVE catalog & PoC repos

Use these to map CVEs and published incidents to hands-on labs above — not standalone exploit environments.

| Resource | Role | Summary | Last Update |
| --- | --- | --- | --- |
| [The Vulnerable MCP Project][link_vulnerablemcp_info] · [vineethsai/vulnerablemcp][link_github_com_vineethsai_vulnerablemcp] | CVE / advisory catalog | 50+ MCP CVEs, GHSA entries, and incident write-ups with severity, exploitability, and mitigation notes — reading map before lab reproduction. | ![](https://badgen.net/github/last-commit/vineethsai/vulnerablemcp) |
| [MCP Injection Experiments][link_github_com_invariantlabs_ai_mcp_injection_experiments] | Canonical poisoning PoCs | Original direct poisoning, tool shadowing, and WhatsApp rug-pull code from the Invariant Labs disclosure. | ![](https://badgen.net/github/last-commit/invariantlabs-ai/mcp-injection-experiments) |
| [MCPHammer][link_github_com_praetorian_inc_mcphammer] | Offensive testing framework | FastMCP-based framework for text injection, remote instance management, and C2-via-tool-argument demonstrations. | ![](https://badgen.net/github/last-commit/praetorian-inc/MCPHammer) |


[link_github_com_agilealligator_mcploitable]: https://github.com/agileAlligator/mcploitable
[link_github_com_aminrj_labs_mcp_attack_labs]: https://github.com/aminrj-labs/mcp-attack-labs
[link_github_com_antoninbr_mcp_security_workshop]: https://github.com/antoninBr/mcp-security-workshop
[link_github_com_appsecco_vulnerable_mcp_servers_lab]: https://github.com/appsecco/vulnerable-mcp-servers-lab
[link_github_com_azure_samples_sherpa]: https://github.com/Azure-Samples/sherpa
[link_github_com_beejak_vulnerable_mcp_server]: https://github.com/beejak/Vulnerable-MCP-Server
[link_github_com_canack_bad_mcp]: https://github.com/canack/bad-mcp
[link_github_com_gensecaihq_mcp_poisoning_poc]: https://github.com/gensecaihq/mcp-poisoning-poc
[link_github_com_harishsg993010_damn_vulnerable_mcp_server]: https://github.com/harishsg993010/damn-vulnerable-MCP-server
[link_github_com_hello_urvesh_mcp_attack_def3nd]: https://github.com/hello-urvesh/mcp-attack-def3nd
[link_github_com_integsec_vulnerablemcp]: https://github.com/integsec/VulnerableMCP
[link_github_com_invariantlabs_ai_mcp_injection_experiments]: https://github.com/invariantlabs-ai/mcp-injection-experiments
[link_github_com_joyghoshs_vulnerable_mcp_server]: https://github.com/JoyGhoshs/vulnerable-mcp-server
[link_github_com_mcp_shark_mcp_shark_security_lab]: https://github.com/mcp-shark/mcp-shark-security-lab
[link_github_com_n0v1chok_vulnmcp]: https://github.com/N0V1CHOK/vulnMCP
[link_github_com_nav33n25_imcp]: https://github.com/nav33n25/imcp
[link_github_com_pawelkozy_mcp_breach_to_fix_labs]: https://github.com/PawelKozy/mcp-breach-to-fix-labs
[link_github_com_praetorian_inc_mcphammer]: https://github.com/praetorian-inc/MCPHammer
[link_github_com_sabyasachidhal_mcpgoat]: https://github.com/SabyasachiDhal/MCPGoat
[link_github_com_satishpatnayak_mcp_goat]: https://github.com/satishpatnayak/MCP-Goat
[link_github_com_truststrikelabs_brokenmcp]: https://github.com/truststrikelabs/BrokenMCP
[link_github_com_vineethsai_vulnerablemcp]: https://github.com/vineethsai/vulnerablemcp
[link_vulnerablemcp_info]: https://vulnerablemcp.info/
[link_vulnerablemcp_info_vuln_github_mcp_exploit_html]: https://vulnerablemcp.info/vuln/github-mcp-exploit.html
[link_vulnerablemcp_info_vuln_rug_pulls_silent_redefinition_html]: https://vulnerablemcp.info/vuln/rug-pulls-silent-redefinition.html
[link_vulnerablemcp_info_vuln_whatsapp_message_exfiltration_html]: https://vulnerablemcp.info/vuln/whatsapp-message-exfiltration.html
