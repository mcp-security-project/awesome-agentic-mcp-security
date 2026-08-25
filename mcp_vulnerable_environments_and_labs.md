# Vulnerable MCP Environments and Labs

Educational and research environments for MCP security testing. **Tables** summarize difficulty and defenses. Run all labs in isolated VMs or containers — never in production or on networks with real credentials.

**Last Update**: 2026-08-25

## Contents

- [MCP Goat–style projects (full detail)](#mcp-goatstyle-projects-full-detail)
- [Appsecco lab servers (per-scenario index)](#appsecco-lab-servers-per-scenario-index)
- [OWASP MCP Top 10 mapped labs](#owasp-mcp-top-10-mapped-labs)
- [Attack/defense paired labs](#attackdefense-paired-labs)
- [Prompt injection labs](#prompt-injection-labs)
- [Tool poisoning labs](#tool-poisoning-labs)
- [Code execution & classic injection labs](#code-execution--classic-injection-labs)
- [Shadow MCP and misconfiguration labs](#shadow-mcp-and-misconfiguration-labs)
- [Supply chain labs](#supply-chain-labs)
- [Authentication, OAuth & transport labs](#authentication-oauth--transport-labs)
- [Agentic & multi-protocol labs](#agentic--multi-protocol-labs)
- [Reference: CVE catalog & PoC repos](#reference-cve-catalog--poc-repos)

---

## MCP Goat–style projects (full detail)

| Project : Maintainer | MCP components | Vulnerabilities covered | Last Update |
| --- | --- | --- | --- |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] : SabyasachiDhal | Tools, resources, prompts, sampling, Streamable HTTP, victim-agent harness | 26 CTF challenges (78 flags): RCE, SSRF, SQLi, path traversal, tool poisoning, shadowing, rug pulls, indirect injection, sampling abuse | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [DVMCP / NovaTech (Kyze-Labs)][link_github_com_kyze_labs_damn_vulnerable_mcp_server] : Kyze-Labs | 6 departments, 28 tools, web UI, Docker | 38 challenges, 19 categories: prompt injection, tool poisoning, privilege escalation, exfiltration, confused deputy, SQLi, command injection, path traversal, supply chain, shadow tools, consent phishing | ![](https://badgen.net/github/last-commit/Kyze-Labs/damn-vulnerable-MCP-Server) |
| [Damn Vulnerable MCP Server (DVMCP)][link_github_com_harishsg993010_damn_vulnerable_mcp_server] : harishsg993010 | Server, tools, prompts, resources, SSE, client config | 10 tiered challenges: prompt injection, tool poisoning, excessive permissions, rug pull, shadowing, indirect injection, token theft, RCE, remote access, multi-vector chains | ![](https://badgen.net/github/last-commit/harishsg993010/damn-vulnerable-MCP-server) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] : Appsecco | Local/remote servers, filesystem, HTTP/SSE, tool output, client config | Nine standalone servers — path traversal, unsandboxed exec, indirect/remote injection, eval RCE, malicious tools, typosquatting, outdated pkgs, secrets/PII, untrusted content | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [IntegSec VulnerableMCP][link_github_com_integsec_vulnerablemcp] : IntegSec | stdio, HTTP/SSE, HTTPS/SSE, WebSocket, WSS transports | 20+ vulns, 16+ CTF flags: path traversal, command injection, missing auth, cleartext transport, JSON-RPC flaws, tool poisoning, rug pulls, resource exhaustion | ![](https://badgen.net/github/last-commit/integsec/VulnerableMCP) |
| [Vulnerable MCP Server (beejak)][link_github_com_beejak_vulnerable_mcp_server] : beejak | stdio, SSE, OAuth metadata, tools, agent chains | 18 CVE-mapped CTF flags: CVE-2025-6514 OAuth RCE, rug pull, shadowing, SSRF, deserialization, multi-vector chains; `show_fix` secure comparisons | ![](https://badgen.net/github/last-commit/beejak/Vulnerable-MCP-Server) |
| [bad-mcp][link_github_com_canack_bad_mcp] : canack | Tool descriptions, schemas, resources, sessions, cross-server | Full-schema poisoning, advanced poisoning, rug pulls, resource poisoning, cross-server shadowing, protocol attacks | ![](https://badgen.net/github/last-commit/canack/bad-mcp) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] : MCP Shark | MCP config, tools, resources, prompts, multi-server harness, Cursor config, YARA-style rules, auth fixtures | Toxic metadata, prompt injection, command injection patterns, oversharing, privilege abuse, bad URLs, env secrets, duplicate tools, bad args, weak authZ | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] : PawelKozy | Dockerized FastMCP servers, fixtures, pytest regressions | 10 real-incident/CVE scenarios with vulnerable + secure pairs; Cursor/Claude exploit walkthroughs | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| [MCP Security Summit Workshop (Sherpa)][link_github_com_azure_samples_sherpa] : Microsoft Azure Samples | Servers, Azure ID, OAuth, MI, Key Vault, gateway, private endpoints, content safety, logging, red/blue validation | Auth gaps, over-permissioned access, weak I/O, no monitoring, unsafe cloud patterns | ![](https://badgen.net/github/last-commit/Azure-Samples/sherpa) |
| [mcp-security-workshop][link_github_com_antoninbr_mcp_security_workshop] : antoninBr | Containerized stdio servers, Docker logs, VS Code sandbox demos | 5 CTF exercises: side-channel execution, secret exfiltration, supply chain poisoning, prompt injection, container poisoning | ![](https://badgen.net/github/last-commit/antoninBr/mcp-security-workshop) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] : aminrj-labs | Custom Python agent, local LLM (Ollama/LM Studio), offline MCP servers | 7 labs: tool poisoning, cross-server shadowing, RAG injection, agentic memory, DockerDash supply chain, MCP→A2A kill chain | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCP Attack & Def3nd][link_github_com_hello_urvesh_mcp_attack_def3nd] : hello-urvesh | Vulnerable + secured server pairs, Nullcon 2026 workshop | 8 OWASP MCP Top 10 risks with side-by-side SECURING.md comparisons | ![](https://badgen.net/github/last-commit/hello-urvesh/mcp-attack-def3nd) |
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] : opena2a-org | 19 agents, MCP + A2A + OpenAI-compatible APIs | MCP agents ToolBot/DataBot/PluginBot/ProxyBot: path traversal, SSRF, SQLi, tool registry poisoning, supply chain, tool MITM; plus agentic injection and memory labs | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |
| [MCP-Goat (OWASP)][link_github_com_satishpatnayak_mcp_goat] : satishpatnayak | CLI challenge runner, stdio MCP servers, Claude Desktop/Cursor configs | All 10 OWASP MCP Top 10 categories with guided exercises and solution write-ups | ![](https://badgen.net/github/last-commit/satishpatnayak/MCP-Goat) |
| [BrokenMCP][link_github_com_truststrikelabs_brokenmcp] : TrustStrike Labs | One server per OWASP MCP Top 10 risk, blog walkthroughs | Token mismanagement, scope creep, tool poisoning, supply chain, command injection, intent subversion, auth gaps, audit gaps, shadow servers, context over-sharing | ![](https://badgen.net/github/last-commit/truststrikelabs/BrokenMCP) |
| [mcploitable][link_github_com_agilealligator_mcploitable] : agileAlligator | Single vulnerable MCP server | OWASP Top 10 for Agentic Applications mapping — “Metasploitable for MCP” | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |
| [IMCP (Insecure Model Context Protocol)][link_github_com_nav33n25_imcp] : nav33n25 | Enterprise business-scenario framework | 14 weaknesses: consent fatigue, compliance-scanner bypass, human-factor exploitation, progressive red-flag modules | ![](https://badgen.net/github/last-commit/nav33n25/imcp) |
| [vulnMCP][link_github_com_n0v1chok_vulnmcp] : N0V1CHOK | stdio server, terminal UI, gamified scoring | 8 progressive challenges: parameter injection, resource URI manipulation, context poisoning, prompt chains, sampling abuse, protocol injection | ![](https://badgen.net/github/last-commit/N0V1CHOK/vulnMCP) |
| [Vulnerable MCP Server (JoyGhoshs)][link_github_com_joyghoshs_vulnerable_mcp_server] : JoyGhoshs | stdio tools, Docker isolation | 14 vuln classes: OS command injection, path traversal, pickle RCE, arbitrary Python exec, SSRF, tool poisoning, rug pull, shadow backdoors | ![](https://badgen.net/github/last-commit/JoyGhoshs/vulnerable-mcp-server) |
| [MCP Poisoning PoC][link_github_com_gensecaihq_mcp_poisoning_poc] : GenSecAI | Tools, descriptions, agent workflows | Tool poisoning in real-world agent flows | ![](https://badgen.net/github/last-commit/gensecaihq/mcp-poisoning-poc) |

---

## Appsecco lab servers (per-scenario index)

All nine servers live in [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab]. Each folder has its own README with run and attack steps. Listed on [OWASP VWAD](https://vwad.owasp.org/app/vulnerable-mcp-servers-lab/).

| Server folder | Vulnerability class | Summary | Last Update |
| --- | --- | --- | --- |
| `vulnerable-mcp-server-filesystem-workspace-actions` | Path traversal + code exec | Workspace read/write/list plus unsandboxed Python execution via naive path joining. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| `vulnerable-mcp-server-indirect-prompt-injection` | Local indirect prompt injection | Document retrieval returns verbatim content with embedded hidden instructions. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| `vulnerable-mcp-server-indirect-prompt-injection-remote-mcp` | Remote indirect prompt injection | HTTP+SSE server returns untrusted documents; models connecting to untrusted remote endpoints. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| `vulnerable-mcp-server-malicious-code-exec` | Eval-based RCE | “Quote of the day” tool with unsafe formatting that `eval()`s attacker-controlled JavaScript. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| `vulnerable-mcp-server-malicious-tools` | Instruction injection / fabricated output | Status tool injects misleading instructions and fabricates plausible incidents. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| `vulnerable-mcp-server-namespace-typosquatting` | Namespace typosquatting | Lookalike server name (`twittter-mcp`) mimics a legitimate package for supply-chain trust abuse. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| `vulnerable-mcp-server-outdated-pacakges` | Outdated dependencies | Read-only inspection tools demonstrating risk from deprecated/vulnerable dependency chains. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| `vulnerable-mcp-server-secrets-pii` | Secrets + PII exposure | Utility tools with embedded credentials in source and leakage via logs. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| `vulnerable-mcp-server-wikipedia-http-streamable` | Remote content injection | Wikipedia retrieval over Streamable HTTP without sanitization or instruction/data separation. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |

---

## OWASP MCP Top 10 mapped labs

| Project (linked) | Mapping | Summary | Last Update |
| --- | --- | --- | --- |
| [MCP-Goat (OWASP)][link_github_com_satishpatnayak_mcp_goat] | All 10 OWASP MCP Top 10 categories | CLI-driven WebGoat-style challenges (`mcp-goat list` / `run` / `exercise`) with guided exploit steps and LLM client config snippets for Claude Desktop/Cursor. | ![](https://badgen.net/github/last-commit/satishpatnayak/MCP-Goat) |
| [BrokenMCP][link_github_com_truststrikelabs_brokenmcp] | One lab per OWASP MCP Top 10 risk | Deliberately broken servers with blog walkthroughs for token mismanagement, scope creep, tool poisoning, supply chain, command injection, intent subversion, auth gaps, audit gaps, shadow servers, context over-sharing. | ![](https://badgen.net/github/last-commit/truststrikelabs/BrokenMCP) |
| [mcploitable][link_github_com_agilealligator_mcploitable] | OWASP Top 10 for Agentic Applications | "Metasploitable for MCP" — single vulnerable server mapped to agentic-application risk categories for red-team training. | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |
| [IMCP (Insecure Model Context Protocol)][link_github_com_nav33n25_imcp] | Enterprise scenarios across OWASP MCP themes | 14 critical weaknesses in business contexts: consent fatigue, compliance-scanner bypass, human-factor exploitation, progressive red-flag training modules. | ![](https://badgen.net/github/last-commit/nav33n25/imcp) |
| [MCP Attack & Def3nd][link_github_com_hello_urvesh_mcp_attack_def3nd] | 8 OWASP MCP Top 10 risks | Nullcon 2026 workshop pairs for credential leakage, mass assignment, code injection, prompt injection, auth bypass, audit gaps, SSRF, context sharing. | ![](https://badgen.net/github/last-commit/hello-urvesh/mcp-attack-def3nd) |

---

## Attack/defense paired labs

| Resource | Vulnerable → secure model | Best for | Last Update |
| --- | --- | --- | --- |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | Dockerized vulnerable + secure FastMCP pairs per challenge | Reproducing real CVE/incident flows in Cursor/Claude, then validating mitigations with pytest | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| [MCP Attack & Def3nd][link_github_com_hello_urvesh_mcp_attack_def3nd] | Side-by-side vulnerable + hardened servers + SECURING.md | Nullcon 2026 workshop; comparing attack vs. fix for eight OWASP MCP Top 10 risks | ![](https://badgen.net/github/last-commit/hello-urvesh/mcp-attack-def3nd) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | Easy / Moderate / Difficult + Secure reference level per challenge | Verifying every documented exploit fails at Secure level (`npm run attack -- … secure`) | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [Vulnerable MCP Server (beejak)][link_github_com_beejak_vulnerable_mcp_server] | `show_fix` mode per challenge | CVE-accurate before/after code comparisons for OAuth RCE, rug pull, shadowing, and chained attacks | ![](https://badgen.net/github/last-commit/beejak/Vulnerable-MCP-Server) |
| [DVMCP / NovaTech (Kyze-Labs)][link_github_com_kyze_labs_damn_vulnerable_mcp_server] | 38 challenges with remediation guidance per category | DVWA-style progression across 19 vulnerability classes in a fictional enterprise (NovaTech Solutions) | ![](https://badgen.net/github/last-commit/Kyze-Labs/damn-vulnerable-MCP-Server) |
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] | Hardened reference agent (port 7001) vs. vulnerable variants | Comparing ToolBot/PluginBot/ProxyBot MCP agents against AIM-protected counterparts | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |
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
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | Lab 04 RAG security | Knowledge-base poisoning, indirect prompt injection, cross-tenant data leakage in offline RAG agent. | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | Lab 05 agentic memory attacks | Persistent memory poisoning, cross-agent trust abuse, context-window overflow. | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | Indirect prompt injection challenges | Tiered CTF flags for injection via tools, resources, and sampling across Easy/Moderate/Difficult levels. | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] | ResearchBot / FlightBot indirect injection | Web-content injection during research/browsing; wallet exfiltration via poisoned fetch results. | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |
| [github-mcp-exploit][link_vulnerablemcp_info_vuln_github_mcp_exploit_html] | GitHub toxic agent flow | Malicious issue + broad GitHub token → private data exfil path; practice scoped tokens and approvals. | 2026-08-25 |
| [cursor-jira-mcp-zero-click][link_vulnerablemcp_info_vuln_cursor_jira_mcp_zero_click_html] | AgentFlayer / Jira toxic flow | Malicious Jira ticket + privileged local tools + outbound sink; practice toxic-flow analysis and scoped tool policies. | 2026-08-25 |
| [whatsapp-message-exfiltration][link_vulnerablemcp_info_vuln_whatsapp_message_exfiltration_html] | Messaging bridge exfiltration | Co-installed server alters behavior to read other server messages; practice cross-server isolation and change detection. | 2026-08-25 |
| [rug-pulls-silent-redefinition][link_vulnerablemcp_info_vuln_rug_pulls_silent_redefinition_html] | Rug pull via description mutation | Tool mutates after approval; practice description hashing, re-approval gates, and ETDI-style signing. | 2026-08-25 |

---

## Tool poisoning labs

| Resource | Best for | Exercise ideas (summary) | Last Update |
| --- | --- | --- | --- |
| [bad-mcp][link_github_com_canack_bad_mcp] | Protocol-level attacks, malicious server, tool/schema poisoning | Find hidden instructions; compare metadata pre/post approval; schema fields as instructions; client warnings on definition change | ![](https://badgen.net/github/last-commit/canack/bad-mcp) |
| [MCP Poisoning PoC][link_github_com_gensecaihq_mcp_poisoning_poc] | PoC poisoning in agent workflows | Run basic demo; mutate descriptions; add metadata scanner before/after | ![](https://badgen.net/github/last-commit/gensecaihq/mcp-poisoning-poc) |
| [MCP Injection Experiments][link_github_com_invariantlabs_ai_mcp_injection_experiments] | Canonical Invariant Labs PoCs | Reproduce direct poisoning, tool shadowing, and WhatsApp rug-pull/sleeper attacks in Cursor or Claude Desktop. | ![](https://badgen.net/github/last-commit/invariantlabs-ai/mcp-injection-experiments) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | Lab 01 tool poisoning | Offline Invariant-style poisoning with custom agent + LM Studio; includes `mcp-scan` detection guidance. | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | Lab 01b / 06 cross-server shadowing | One MCP server shadows or steers abuse of a second trusted server's tools. | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | Lab 07 MCP→A2A kill chain | Five-stage chain: tool poisoning → rogue A2A registration → routing hijack → lateral movement → persistence. | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | Repello.ai-style rug pull | Tool metadata mutates after approval to exfiltrate API keys; compare with secure metadata-pinning build. | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| Damn Vulnerable MCP Server (DVMCP) (see “MCP Goat–style projects” above) | CTF: poisoning, rug pulls, shadowing, permissions | Find malicious instruction in tool def; exploit shadowing; fix with stable metadata + approvals | ![](https://badgen.net/github/last-commit/harishsg993010/damn-vulnerable-MCP-server) |
| [DVMCP / NovaTech (Kyze-Labs)][link_github_com_kyze_labs_damn_vulnerable_mcp_server] | Shadow tool invocation, consent phishing | Hidden tools not in `tools/list`; hidden tool side effects after user approval fatigue. | ![](https://badgen.net/github/last-commit/Kyze-Labs/damn-vulnerable-MCP-Server) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | Tiered poisoning + shadowing CTF | Tool poisoning, rug pulls, and cross-server shadowing at three difficulty levels plus Secure reference. | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [MCP Shark Security Lab][link_github_com_mcp_shark_mcp_shark_security_lab] | Scanner / detection engineering | Toxic corpus, CI integration, YARA-style rules for poisoned metadata patterns | ![](https://badgen.net/github/last-commit/mcp-shark/mcp-shark-security-lab) |
| [MCPHammer][link_github_com_praetorian_inc_mcphammer] | Offensive testing framework | Text injection, remote management, init-tool download/execute, C2-via-tool-argument scanning demos | ![](https://badgen.net/github/last-commit/praetorian-inc/MCPHammer) |
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] | PluginBot tool registry poisoning | Supply-chain style tool registry tampering in multi-agent MCP setup. | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |

---

## Code execution & classic injection labs

| Resource | Scenario | Exercise focus | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Filesystem workspace + Python exec | Path traversal via naive joining; unsandboxed code execution in workspace tools. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab] | Eval-based RCE | JavaScript `eval()` in quote-formatting feature; never pass tool input to interpreters. | ![](https://badgen.net/github/last-commit/appsecco/vulnerable-mcp-servers-lab) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | RCE / SQLi / path traversal CTF | Classic web vulns resurfacing in MCP tool handlers across tiered challenges. | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [IntegSec VulnerableMCP][link_github_com_integsec_vulnerablemcp] | Command injection, SQLi, SSTI, path traversal | Classic web exploits plus MCP-specific variants; automated exploit tests included. | ![](https://badgen.net/github/last-commit/integsec/VulnerableMCP) |
| [DVMCP / NovaTech (Kyze-Labs)][link_github_com_kyze_labs_damn_vulnerable_mcp_server] | SQLi, command injection, path traversal (V12–V14) | Shell metacharacters, unsanitized SQL, directory escape in enterprise-simulation context. | ![](https://badgen.net/github/last-commit/Kyze-Labs/damn-vulnerable-MCP-Server) |
| [Vulnerable MCP Server (JoyGhoshs)][link_github_com_joyghoshs_vulnerable_mcp_server] | Pickle RCE, arbitrary Python exec | Deserialization and interpreter abuse over stdio MCP tools. | ![](https://badgen.net/github/last-commit/JoyGhoshs/vulnerable-mcp-server) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | Filesystem path traversal, git command injection | Real CVE/incident patterns; compare vulnerable vs. canonical-path / execFile secure builds. | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] | ToolBot / DataBot MCP agents | Path traversal, SSRF, command injection, SQL injection via MCP tool surface. | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |
| [beejak Vulnerable MCP Server][link_github_com_beejak_vulnerable_mcp_server] | Deserialization, MarkItDown SSRF | CVE-mapped advanced tiers including CWE-502 and unpatched fetch SSRF chains. | ![](https://badgen.net/github/last-commit/beejak/Vulnerable-MCP-Server) |

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
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] | ProxyBot tool MITM, no TLS pinning | MCP proxy misconfiguration enabling tool interception between agent and server. | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |

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
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | Lab 02 DockerDash | Prompt injection via Docker image labels → container destruction + inventory exfil. | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [DVMCP / NovaTech (Kyze-Labs)][link_github_com_kyze_labs_damn_vulnerable_mcp_server] | Compromised CI/CD (V15) | Supply-chain compromise patterns in fictional NovaTech deployment pipeline. | ![](https://badgen.net/github/last-commit/Kyze-Labs/damn-vulnerable-MCP-Server) |
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] | PluginBot supply chain | Tool registry poisoning and tampered plugin loading in agent ecosystem. | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |

---

## Authentication, OAuth & transport labs

| Resource | Scenario | Defense exercise | Last Update |
| --- | --- | --- | --- |
| [Vulnerable MCP Server (beejak)][link_github_com_beejak_vulnerable_mcp_server] | CVE-2025-6514 OAuth RCE via mcp-remote | Crafted `authorization_endpoint` in OAuth metadata → OS command injection on client; practice pinning and URL validation | ![](https://badgen.net/github/last-commit/beejak/Vulnerable-MCP-Server) |
| [IntegSec VulnerableMCP][link_github_com_integsec_vulnerablemcp] | Missing auth, cleartext HTTP/WS, no rate limiting | Enforce transport auth, TLS, session binding, and rate limits across stdio/HTTP/SSE/WS/WSS | ![](https://badgen.net/github/last-commit/integsec/VulnerableMCP) |
| [MCP Breach-to-Fix Labs][link_github_com_pawelkozy_mcp_breach_to_fix_labs] | CRM auth bypass, X-Forwarded-For trust, IDOR | Scope credentials per tenant; canonical path enforcement; reject spoofed client headers | ![](https://badgen.net/github/last-commit/PawelKozy/mcp-breach-to-fix-labs) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | Streamable HTTP transport, Origin allow-list bypass | Practice DNS rebinding and transport-layer auth gaps; validate Secure-level Origin enforcement | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [MCP Attack & Def3nd][link_github_com_hello_urvesh_mcp_attack_def3nd] | Auth bypass, SSRF, mass assignment | Side-by-side hardened builds for broken authentication and unsafe outbound fetch patterns | ![](https://badgen.net/github/last-commit/hello-urvesh/mcp-attack-def3nd) |
| [Sherpa MCP Security Workshop][link_github_com_azure_samples_sherpa] | OAuth 2.1, managed identity, private endpoints | Enterprise identity and network isolation before exposing remote MCP in Azure | ![](https://badgen.net/github/last-commit/Azure-Samples/sherpa) |
| [vulnMCP][link_github_com_n0v1chok_vulnmcp] | Sampling manipulation, protocol message injection | Validate MCP protocol messages and restrict sampling capability abuse | ![](https://badgen.net/github/last-commit/N0V1CHOK/vulnMCP) |
| [microsoft-markitdown-mcp-ssrf][link_vulnerablemcp_info_vuln_markitdown_ssrf_html] | MarkItDown MCP SSRF | Unpatched fetch SSRF to cloud metadata; pair with beejak ADVANCED-001 or advisory reading before reproduction. | 2026-08-25 |

---

## Agentic & multi-protocol labs

Broader agent platforms that include MCP-specific vulnerable servers alongside A2A and chat APIs.

| Resource | Protocols | MCP-relevant agents / labs | Last Update |
| --- | --- | --- | --- |
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] | MCP, A2A, OpenAI-compatible chat | ToolBot (70010), DataBot (7011), PluginBot (7012), ProxyBot (7013); hardened reference on port 7001 | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | MCP, A2A, RAG, memory | Lab 07 flagship kill chain crosses MCP→A2A trust boundary; Lab 03 automated red-team with PyRIT + Promptfoo | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | MCP Streamable HTTP | Victim-agent harness demonstrates real LLM agent exploitation impact beyond raw tool calls | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [mcploitable][link_github_com_agilealligator_mcploitable] | MCP | Single-server agentic risk mapping for scanner and red-team baseline testing | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |

---

## Reference: CVE catalog & PoC repos

Use these to map CVEs and published incidents to hands-on labs above — not standalone exploit environments.

| Resource | Role | Summary | Last Update |
| --- | --- | --- | --- |
| [The Vulnerable MCP Project][link_vulnerablemcp_info] · [vineethsai/vulnerablemcp][link_github_com_vineethsai_vulnerablemcp] | CVE / advisory catalog | 50+ MCP CVEs, GHSA entries, and incident write-ups with severity, exploitability, and mitigation notes — reading map before lab reproduction. | ![](https://badgen.net/github/last-commit/vineethsai/vulnerablemcp) |
| [MCP Injection Experiments][link_github_com_invariantlabs_ai_mcp_injection_experiments] | Canonical poisoning PoCs | Original direct poisoning, tool shadowing, and WhatsApp rug-pull code from the Invariant Labs disclosure. | ![](https://badgen.net/github/last-commit/invariantlabs-ai/mcp-injection-experiments) |
| [MCPHammer][link_github_com_praetorian_inc_mcphammer] | Offensive testing framework | FastMCP-based framework for text injection, remote instance management, and C2-via-tool-argument demonstrations. | ![](https://badgen.net/github/last-commit/praetorian-inc/MCPHammer) |
| [mcp-ethical-hacking][link_github_com_cmpxchg16_mcp_ethical_hacking] | Educational abuse demos | “Legitimate” social/analysis MCP samples illustrating abuse potential — **authorized testing only**; lab isolation required. | ![](https://badgen.net/github/last-commit/cmpxchg16/mcp-ethical-hacking) |


[link_github_com_agilealligator_mcploitable]: https://github.com/agileAlligator/mcploitable
[link_github_com_aminrj_labs_mcp_attack_labs]: https://github.com/aminrj-labs/mcp-attack-labs
[link_github_com_antoninbr_mcp_security_workshop]: https://github.com/antoninBr/mcp-security-workshop
[link_github_com_appsecco_vulnerable_mcp_servers_lab]: https://github.com/appsecco/vulnerable-mcp-servers-lab
[link_github_com_azure_samples_sherpa]: https://github.com/Azure-Samples/sherpa
[link_github_com_beejak_vulnerable_mcp_server]: https://github.com/beejak/Vulnerable-MCP-Server
[link_github_com_canack_bad_mcp]: https://github.com/canack/bad-mcp
[link_github_com_cmpxchg16_mcp_ethical_hacking]: https://github.com/cmpxchg16/mcp-ethical-hacking
[link_github_com_gensecaihq_mcp_poisoning_poc]: https://github.com/gensecaihq/mcp-poisoning-poc
[link_github_com_harishsg993010_damn_vulnerable_mcp_server]: https://github.com/harishsg993010/damn-vulnerable-MCP-server
[link_github_com_hello_urvesh_mcp_attack_def3nd]: https://github.com/hello-urvesh/mcp-attack-def3nd
[link_github_com_integsec_vulnerablemcp]: https://github.com/integsec/VulnerableMCP
[link_github_com_invariantlabs_ai_mcp_injection_experiments]: https://github.com/invariantlabs-ai/mcp-injection-experiments
[link_github_com_joyghoshs_vulnerable_mcp_server]: https://github.com/JoyGhoshs/vulnerable-mcp-server
[link_github_com_kyze_labs_damn_vulnerable_mcp_server]: https://github.com/Kyze-Labs/damn-vulnerable-MCP-Server
[link_github_com_mcp_shark_mcp_shark_security_lab]: https://github.com/mcp-shark/mcp-shark-security-lab
[link_github_com_n0v1chok_vulnmcp]: https://github.com/N0V1CHOK/vulnMCP
[link_github_com_nav33n25_imcp]: https://github.com/nav33n25/imcp
[link_github_com_opena2a_org_damn_vulnerable_ai_agent]: https://github.com/opena2a-org/damn-vulnerable-ai-agent
[link_github_com_pawelkozy_mcp_breach_to_fix_labs]: https://github.com/PawelKozy/mcp-breach-to-fix-labs
[link_github_com_praetorian_inc_mcphammer]: https://github.com/praetorian-inc/MCPHammer
[link_github_com_sabyasachidhal_mcpgoat]: https://github.com/SabyasachiDhal/MCPGoat
[link_github_com_satishpatnayak_mcp_goat]: https://github.com/satishpatnayak/MCP-Goat
[link_github_com_truststrikelabs_brokenmcp]: https://github.com/truststrikelabs/BrokenMCP
[link_github_com_vineethsai_vulnerablemcp]: https://github.com/vineethsai/vulnerablemcp
[link_vulnerablemcp_info]: https://vulnerablemcp.info/
[link_vulnerablemcp_info_vuln_cursor_jira_mcp_zero_click_html]: https://vulnerablemcp.info/vuln/cursor-jira-mcp-zero-click.html
[link_vulnerablemcp_info_vuln_github_mcp_exploit_html]: https://vulnerablemcp.info/vuln/github-mcp-exploit.html
[link_vulnerablemcp_info_vuln_markitdown_ssrf_html]: https://vulnerablemcp.info/vuln/microsoft-markitdown-mcp-ssrf.html
[link_vulnerablemcp_info_vuln_rug_pulls_silent_redefinition_html]: https://vulnerablemcp.info/vuln/rug-pulls-silent-redefinition.html
[link_vulnerablemcp_info_vuln_whatsapp_message_exfiltration_html]: https://vulnerablemcp.info/vuln/whatsapp-message-exfiltration.html
