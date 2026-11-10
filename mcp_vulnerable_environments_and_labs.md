# Vulnerable MCP Environments and Labs

Educational and research environments for MCP security testing. **Tables** summarize difficulty and defenses. Run all labs in isolated VMs or containers — never in production or on networks with real credentials.

**Last Update**: 2026-11-10

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
| [mcploitable][link_github_com_agilealligator_mcploitable] : agileAlligator | Seven Docker-isolated servers, three guided simulations, optional CTF harness | OWASP Top 10 for Agentic Applications (2026): goal hijack, tool misuse, privilege abuse, supply-chain plugins, unexpected code execution, memory poisoning, agent-to-agent abuse, cascading failures, human-trust exploitation, rogue agents | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |
| [IMCP (Insecure Model Context Protocol)][link_github_com_nav33n25_imcp] : nav33n25 | Enterprise business-scenario framework | 14 weaknesses: consent fatigue, compliance-scanner bypass, human-factor exploitation, progressive red-flag modules | ![](https://badgen.net/github/last-commit/nav33n25/imcp) |
| [vulnMCP][link_github_com_n0v1chok_vulnmcp] : N0V1CHOK | stdio server, terminal UI, gamified scoring | 8 progressive challenges: parameter injection, resource URI manipulation, context poisoning, prompt chains, sampling abuse, protocol injection | ![](https://badgen.net/github/last-commit/N0V1CHOK/vulnMCP) |
| [Vulnerable MCP Server (JoyGhoshs)][link_github_com_joyghoshs_vulnerable_mcp_server] : JoyGhoshs | stdio tools, Docker isolation | 14 vuln classes: OS command injection, path traversal, pickle RCE, arbitrary Python exec, SSRF, tool poisoning, rug pull, shadow backdoors | ![](https://badgen.net/github/last-commit/JoyGhoshs/vulnerable-mcp-server) |
| [MCP Poisoning PoC][link_github_com_gensecaihq_mcp_poisoning_poc] : GenSecAI | Tools, descriptions, agent workflows | Tool poisoning in real-world agent flows | ![](https://badgen.net/github/last-commit/gensecaihq/mcp-poisoning-poc) |
| [EVMCP][link_github_com_psiinon_evmcp] : Simon Bennetts | HTTP MCP endpoint, Docker, JSON-RPC tools, scanner target | OWASP VWAD-listed DAST target: SQLi, command injection, path traversal, SSRF, XXE, insecure deserialization, IDOR, weak auth, prompt injection | ![](https://badgen.net/github/last-commit/psiinon/evmcp) |
| [MCP Security Lab][link_github_com_anita_ani_mcp_security_lab] : Anita-ani | Vulnerable, secured, and exploit implementations per module | Five OWASP MCP Top 10 modules: token exposure, command injection, broken auth, shadow servers, context over-sharing | ![](https://badgen.net/github/last-commit/Anita-ani/mcp-security-lab) |
| [MCP CTF Challenge][link_github_com_aganita_mcp_ctf_challenge] : aganita | Python server, seven CTF challenges, Docker | Prompt injection, tool-description poisoning, file access, token exposure, shadowing, indirect injection, privilege escalation | ![](https://badgen.net/github/last-commit/aganita/mcp-ctf-challenge) |
| [evil-mcp-lab][link_github_com_rafsan_huseynov_evil_mcp_lab] : rafsan-huseynov | Deliberately malicious server, local collector, static/runtime governance fixtures | Eight confined attacks: poisoning, rug pull, shadowing, exfiltration, sensitive-file access, injection relay, schema mismatch, sandbox escape | ![](https://badgen.net/github/last-commit/rafsan-huseynov/evil-mcp-lab) |
| [MCP Agent Security Dojo][link_github_com_dgenio_mcp_agent_security_dojo] : dgenio | Local simulated tools, unsafe/governed modes, policy gates, audit traces | Prompt injection, tool poisoning, over-permissioning, privilege escalation, context controls, capability scoping | ![](https://badgen.net/github/last-commit/dgenio/mcp-agent-security-dojo) |
| [MCP Security Patterns][link_github_com_dnyandeobharambe_mcp_security_patterns] : dnyandeobharambe | Attack demos, defenses, tests, combined full-stack demo | Ten production-oriented security patterns mapped to all OWASP MCP Top 10 categories | ![](https://badgen.net/github/last-commit/dnyandeobharambe/mcp-security-patterns) |
| [Telekom MCP Security][link_github_com_telekom_mcp_security] : Deutsche Telekom | Interactive UI, real-time chat, sandboxed demo servers, slide deck | Safe baseline plus prompt injection, tool shadowing, Unicode tool poisoning, and data poisoning | ![](https://badgen.net/github/last-commit/telekom/mcp-security) |
| [MCP Security Lab (tal7aouy)][link_github_com_tal7aouy_mcp_security_lab] : tal7aouy | Podman pod, Streamable HTTP, attacker toolbox, MCP Inspector | 10 containerized challenges, 11 flags: tool poisoning, indirect injection, path traversal, command injection, eval RCE, token theft, fetch SSRF, rug pull, pickle deserialization, prefix-compare auth | ![](https://badgen.net/github/last-commit/tal7aouy/mcp-security-lab) |
| [EnumByte MCP Security Lab][link_github_com_sentinelbyte_enumbyte_mcp_security_lab] : SentinelByte | Docker Compose, vulnerable and hardened HTTP servers, pytest | Verification lab (not a guided CTF): missing, expired, wrong-audience, and under-scoped tokens; path traversal, SSRF, command injection, prompt injection, oversized input, credential leakage, excessive tool access | ![](https://badgen.net/github/last-commit/SentinelByte/enumbyte-mcp-security-lab) |
| [Hispalis MCP Lab][link_github_com_ezee_sg_mcp_security_lab] : ezee-sg | Four departmental servers, ungoverned shadow server, exfil listener, Ollama chat, Wazuh and Grafana on the hardened stack | Vulnerable and hardened pair per department; 10 scenarios, one per OWASP MCP Top 10 category | ![](https://badgen.net/github/last-commit/ezee-sg/mcp-security-lab) |
| [Vulnerable MCP Server (rahulsinghinfosec)][link_github_com_rahulsinghinfosec_damnvulnerablemcpserver] : rahulsinghinfosec | stdio, Streamable HTTP, SSE, Docker; one module per bug class | Missing authentication, default credentials, excessive filesystem tools, SSRF, SQL injection | ![](https://badgen.net/github/last-commit/rahulsinghinfosec/damnvulnerablemcpserver) |
| [VaultMCP][link_github_com_hardsoftsecurity_vulnerable_mcp_lab] : hardsoftsecurity | Streamable HTTP server with resources, resource templates, and tools | Three-part lab: protocol walkthrough, enumeration, then exploitation of the intentionally vulnerable server | ![](https://badgen.net/github/last-commit/hardsoftsecurity/vulnerable-mcp-lab) |
| [VEIL][link_github_com_het_p301204_veil] : het-P301204 | FastAPI and React command center, YAML scenarios, live protocol view | Tool poisoning, rug pulls, output injection, and sampling hijack across eight built-in scenarios | ![](https://badgen.net/github/last-commit/het-P301204/veil) |
| [MCP Security Lab (mariuslihet)][link_github_com_mariuslihet_mcp_security_lab] : mariuslihet | Vulnerable and hardened servers, policy proxy, conversational actors, HTML dashboard | Output poisoning and tool shadowing across seeds and transports; protocol checks run without a model | ![](https://badgen.net/github/last-commit/mariuslihet/mcp-security-lab) |
| [vuln-support-mcp][link_github_com_obotchris_vuln_support_mcp] : obotchris | Streamable HTTP support server, GHCR image, simulated webhook | Ticket-text injection, poisoned tool descriptions, private data plus an egress tool, and a least-privilege composite server | ![](https://badgen.net/github/last-commit/obotchris/vuln-support-mcp) |
| [MCP Servers and Security Workshop][link_github_com_avilewis_mcp_security_workshop] : AviLewis | Hand-built Python server, planted workspace, Claude Code, spoiler solutions | Build a server, expose it, then attack and harden it against planted flags and fake secrets | ![](https://badgen.net/github/last-commit/AviLewis/mcp-security-workshop) |
| [Quarkus Secure AI Agent Workshop][link_github_com_wjglerum_quarkus_secure_ai_agent_workshop_javazone_2026] : wjglerum | Quarkus and LangChain4j assistant, Keycloak, Postgres, Ollama, one branch per fix | Vulnerable baseline, then prompt injection, unauthenticated MCP confused deputy, excessive agency, sensitive disclosure, and unbounded consumption | ![](https://badgen.net/github/last-commit/wjglerum/quarkus-secure-ai-agent-workshop-javazone-2026) |
| [VulnAgent][link_github_com_s81207169_a11y_vulnagent] : s81207169-a11y | LLM chatbot, MCP server, autonomous agent, vibe-coded API, automated attack suite | Vulnerable and hardened twins; MCP pillar is tool-description poisoning plus an unrestricted file read | ![](https://badgen.net/github/last-commit/s81207169-a11y/Vulnagent) |
| [MCP Sentinel Research][link_github_com_piyerx_mcp_sentinel_research] : piyerx | Malicious weather server, benign baseline, sanitizing gateway | Eight tool-poisoning vectors (exfiltration, prompt injection, instruction hijacking, and related metadata attacks) with a zero-trust description gateway | ![](https://badgen.net/github/last-commit/piyerx/MCP-Sentinel-Research) |

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
| [mcploitable][link_github_com_agilealligator_mcploitable] | OWASP Top 10 for Agentic Applications (ASI01–ASI10) | Seven breakable servers (mail, analytics, account recovery, plugins, calculator, memory, multi-agent ops) plus three guided simulations; optional L0–L3 CTF harness. | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |
| [IMCP (Insecure Model Context Protocol)][link_github_com_nav33n25_imcp] | Enterprise scenarios across OWASP MCP themes | 14 critical weaknesses in business contexts: consent fatigue, compliance-scanner bypass, human-factor exploitation, progressive red-flag training modules. | ![](https://badgen.net/github/last-commit/nav33n25/imcp) |
| [MCP Attack & Def3nd][link_github_com_hello_urvesh_mcp_attack_def3nd] | 8 OWASP MCP Top 10 risks | Nullcon 2026 workshop pairs for credential leakage, mass assignment, code injection, prompt injection, auth bypass, audit gaps, SSRF, context sharing. | ![](https://badgen.net/github/last-commit/hello-urvesh/mcp-attack-def3nd) |
| [MCP Security Lab][link_github_com_anita_ani_mcp_security_lab] | 5 OWASP MCP Top 10 risks | Vulnerable server, secured implementation, and exploit for token exposure, command injection, broken auth, shadow servers, and context over-sharing. | ![](https://badgen.net/github/last-commit/Anita-ani/mcp-security-lab) |
| [MCP Security Patterns][link_github_com_dnyandeobharambe_mcp_security_patterns] | All 10 OWASP MCP Top 10 categories | Runnable attack demos, defense implementations, and tests for every category plus a combined full-stack example. | ![](https://badgen.net/github/last-commit/dnyandeobharambe/mcp-security-patterns) |
| [Hispalis MCP Lab][link_github_com_ezee_sg_mcp_security_lab] | All 10 OWASP MCP Top 10 categories | Fictional company with HR, finance, IT, and management servers in vulnerable and hardened Compose stacks, plus an ungoverned shadow server and per-category scenario notes. | ![](https://badgen.net/github/last-commit/ezee-sg/mcp-security-lab) |

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
| [MCP Security Lab][link_github_com_anita_ani_mcp_security_lab] | Vulnerable, secured, and exploit directories per module | Direct code comparison for five OWASP MCP risks with reproducible exploit examples | ![](https://badgen.net/github/last-commit/Anita-ani/mcp-security-lab) |
| [MCP Agent Security Dojo][link_github_com_dgenio_mcp_agent_security_dojo] | `run-unsafe` → `run-safe` scenarios | Compare ambient authority with policy gates, context firewalls, scoped capabilities, and audit traces | ![](https://badgen.net/github/last-commit/dgenio/mcp-agent-security-dojo) |
| [MCP Security Patterns][link_github_com_dnyandeobharambe_mcp_security_patterns] | Attack demo → defense implementation → regression test | Validate mitigations for all ten OWASP MCP risk categories | ![](https://badgen.net/github/last-commit/dnyandeobharambe/mcp-security-patterns) |
| [EnumByte MCP Security Lab][link_github_com_sentinelbyte_enumbyte_mcp_security_lab] | Same pytest attack against port 8000 (vulnerable) and port 8001 (hardened) | Confirm each flaw is reachable, then confirm the hardened server blocks it | ![](https://badgen.net/github/last-commit/SentinelByte/enumbyte-mcp-security-lab) |
| [Hispalis MCP Lab][link_github_com_ezee_sg_mcp_security_lab] | `docker-compose.vulnerable.yml` and `docker-compose.hardened.yml` | Walk one OWASP MCP Top 10 scenario, then repeat it against the hardened departmental servers | ![](https://badgen.net/github/last-commit/ezee-sg/mcp-security-lab) |
| [MCP Security Lab (mariuslihet)][link_github_com_mariuslihet_mcp_security_lab] | Same scenario on a vulnerable server and a hardened server behind a policy proxy | Compare attack success with task completion; protocol checks do not require a model | ![](https://badgen.net/github/last-commit/mariuslihet/mcp-security-lab) |
| [Quarkus Secure AI Agent Workshop][link_github_com_wjglerum_quarkus_secure_ai_agent_workshop_javazone_2026] | `main` is the vulnerable app; each later branch is one fix | Attack the conference assistant, then apply the reference diff for that step | ![](https://badgen.net/github/last-commit/wjglerum/quarkus-secure-ai-agent-workshop-javazone-2026) |
| [VulnAgent][link_github_com_s81207169_a11y_vulnagent] | Vulnerable pillar and hardened twin, graded by `python -m vulnagent.attacks` | Prove MCP tool poisoning and the agent-layer follow-on attacks, then confirm the hardened twin blocks them | ![](https://badgen.net/github/last-commit/s81207169-a11y/Vulnagent) |
| [agent-sec-lab][link_github_com_wstran118_agent_sec_lab] | Exploit directory and matching fix per scenario, with tests | Eight canary-secret scenarios, including an MCP-style rug pull stopped by tool pinning | ![](https://badgen.net/github/last-commit/wstran118/agent-sec-lab) |

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
| [MCP Agent Security Dojo][link_github_com_dgenio_mcp_agent_security_dojo] | Prompt injection in tool results | Unsafe flow exfiltrates simulated PII; governed flow applies context filtering, redaction, and policy denial. | ![](https://badgen.net/github/last-commit/dgenio/mcp-agent-security-dojo) |
| [Telekom MCP Security][link_github_com_telekom_mcp_security] | Prompt and data poisoning demos | Interactive sandbox shows injected instructions and corrupted data influencing an agent, with a safe baseline for comparison. | ![](https://badgen.net/github/last-commit/telekom/mcp-security) |
| [MCP Security Lab (tal7aouy)][link_github_com_tal7aouy_mcp_security_lab] | Challenge 02 indirect prompt injection | Poisoned tool data hijacks the agent; mapped to EchoLeak-class indirect injection. | ![](https://badgen.net/github/last-commit/tal7aouy/mcp-security-lab) |
| [vuln-support-mcp][link_github_com_obotchris_vuln_support_mcp] | Poisoned support ticket | `get_support_ticket` returns attacker-authored text; the same server also holds private customer data and a simulated webhook. | ![](https://badgen.net/github/last-commit/obotchris/vuln-support-mcp) |
| [MCP Context Poisoning Lab][link_github_com_connordev1337_mcp_context_poisoning_lab] | Untrusted browsing MCP | Measures whether an agent keeps user instructions separate from search results, page content, fake authority, DNS hijacking, and a malicious MCP server. Isolated `.test` hostnames only. | ![](https://badgen.net/github/last-commit/ConnorDev1337/mcp-context-poisoning-lab) |
| [MCP Security Lab (mariuslihet)][link_github_com_mariuslihet_mcp_security_lab] | Output poisoning | Compare how often poisoned tool output steers the agent on the vulnerable server versus the hardened server. | ![](https://badgen.net/github/last-commit/mariuslihet/mcp-security-lab) |
| [MCP Agent Security Lab (FCortez)][link_github_com_fcortezsecurity_mcp_security_lab] | Email injection against a local model | Repeated trials of indirect injection through email content, with a recipient allowlist as the measured defense. Fake data only. | ![](https://badgen.net/github/last-commit/FCortezSecurity/mcp-security-lab) |
| [prompt-injection-lab][link_github_com_danush_aries_prompt_injection_lab] | Levels 01–08, offline auto-grader | Progress from system-prompt leaks through RAG and tool hijacking to level 08, a poisoned MCP server. Each level has a guardrail that must block the exploit. | ![](https://badgen.net/github/last-commit/Danush-Aries/prompt-injection-lab) |
| [mcploitable][link_github_com_agilealligator_mcploitable] | ASI01 mail assistant | EchoLeak-class goal hijack: a planted email steers the agent into an image-URL exfiltration path. | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |

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
| [evil-mcp-lab][link_github_com_rafsan_huseynov_evil_mcp_lab] | Static/runtime safety-tool evaluation | Detect poisoning, metadata mutation, cross-tool shadowing, injection relay, and schema mismatch; verify blocking and audit records. | ![](https://badgen.net/github/last-commit/rafsan-huseynov/evil-mcp-lab) |
| [MCP CTF Challenge][link_github_com_aganita_mcp_ctf_challenge] | Beginner/intermediate CTF practice | Exploit tool-description poisoning, indirect injection, and dynamic tool-registration shadowing. | ![](https://badgen.net/github/last-commit/aganita/mcp-ctf-challenge) |
| [Telekom MCP Security][link_github_com_telekom_mcp_security] | Interactive visual demonstrations | Compare safe baseline behavior with Unicode-hidden poisoning and compromised-server tool shadowing. | ![](https://badgen.net/github/last-commit/telekom/mcp-security) |
| [MCP Security Lab (tal7aouy)][link_github_com_tal7aouy_mcp_security_lab] | Challenges 01 and 08 | Hidden instructions in a tool description, then a definition that mutates after approval. | ![](https://badgen.net/github/last-commit/tal7aouy/mcp-security-lab) |
| [VEIL][link_github_com_het_p301204_veil] | Four attack modules, eight YAML scenarios | Step through tool poisoning, rug pulls, injected tool output, and sampling hijack while watching protocol traffic. | ![](https://badgen.net/github/last-commit/het-P301204/veil) |
| [vuln-support-mcp][link_github_com_obotchris_vuln_support_mcp] | `reconcile_account` description | Hidden instructions in the tool description run before any call; pair with the least-privilege composite server. | ![](https://badgen.net/github/last-commit/obotchris/vuln-support-mcp) |
| [MCP Security Lab (mariuslihet)][link_github_com_mariuslihet_mcp_security_lab] | Tool shadowing | Measure shadowing across two seeds and both transports, then compare the hardened server and policy proxy. | ![](https://badgen.net/github/last-commit/mariuslihet/mcp-security-lab) |
| [VulnAgent][link_github_com_s81207169_a11y_vulnagent] | Attack A3 | Poisoned MCP tool description plus an unrestricted file read; the hardened twin scopes the read and keeps descriptions honest. | ![](https://badgen.net/github/last-commit/s81207169-a11y/Vulnagent) |
| [MCP Sentinel Research][link_github_com_piyerx_mcp_sentinel_research] | Malicious weather server | Eight metadata-poisoning tools against a benign baseline; the gateway rewrites suspicious descriptions before they reach the model. | ![](https://badgen.net/github/last-commit/piyerx/MCP-Sentinel-Research) |
| [DevKit-MCP][link_github_com_vibecodingnights_offensive_security] | Tool-description poisoning workshop | One of three workshop apps: a poisoned MCP tool description exfiltrates credentials through a boolean flag. | ![](https://badgen.net/github/last-commit/VibeCodingNights/offensive-security) |
| [prompt-injection-lab][link_github_com_danush_aries_prompt_injection_lab] | Level 08 MCP tool poisoning | Offline grader: a poisoned MCP server exfiltrates data with no extra user prompt, then the guardrail must stop it. | ![](https://badgen.net/github/last-commit/Danush-Aries/prompt-injection-lab) |
| [agent-sec-lab][link_github_com_wstran118_agent_sec_lab] | Scenario S4 rug pull | MCP-style tool mutation after trust; the fix pins the tool definition. Canary secrets only. | ![](https://badgen.net/github/last-commit/wstran118/agent-sec-lab) |
| [MCP Agent Security Lab (FCortez)][link_github_com_fcortezsecurity_mcp_security_lab] | Tool-poisoning trials | A malicious tool leaks data through its own arguments; a data-flow check on arguments is the measured defense. | ![](https://badgen.net/github/last-commit/FCortezSecurity/mcp-security-lab) |
| [mcploitable][link_github_com_agilealligator_mcploitable] | ASI04 plugin manager | A published plugin is adopted over the honest tool, then its output steers the agent into handing over workspace credentials. | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |

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
| [EVMCP][link_github_com_psiinon_evmcp] | HTTP DAST target | Fuzz JSON-RPC parameters for SQLi, command injection, path traversal, SSRF, XXE, insecure deserialization, and IDOR. | ![](https://badgen.net/github/last-commit/psiinon/evmcp) |
| [MCP CTF Challenge][link_github_com_aganita_mcp_ctf_challenge] | Excessive file access and privilege escalation | Practice unrestricted file access, token exposure, and chained escalation in a compact CTF server. | ![](https://badgen.net/github/last-commit/aganita/mcp-ctf-challenge) |
| [MCP Security Lab (tal7aouy)][link_github_com_tal7aouy_mcp_security_lab] | Challenges 03–05, 07, and 09 | Path traversal, shell concatenation, `eval()`, fetch SSRF including `file://`, and `pickle.loads` on caller-controlled bytes. | ![](https://badgen.net/github/last-commit/tal7aouy/mcp-security-lab) |
| [EnumByte MCP Security Lab][link_github_com_sentinelbyte_enumbyte_mcp_security_lab] | Path traversal, SSRF, command injection | Pytest asserts the vulnerable server is exploitable and the hardened server rejects the same calls. | ![](https://badgen.net/github/last-commit/SentinelByte/enumbyte-mcp-security-lab) |
| [Vulnerable MCP Server (rahulsinghinfosec)][link_github_com_rahulsinghinfosec_damnvulnerablemcpserver] | Filesystem, SSRF, and SQL tools | `read_file` / `write_file`, `fetch_url` / `import_feed` / `check_webhook`, and `search_user` / `login_user` / `get_order`. | ![](https://badgen.net/github/last-commit/rahulsinghinfosec/damnvulnerablemcpserver) |

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
| [MCP Security Lab][link_github_com_anita_ani_mcp_security_lab] | Shadow-server and context-sharing modules | Reproduce an exposed internal server and cross-session data leakage, then compare secured implementations. | ![](https://badgen.net/github/last-commit/Anita-ani/mcp-security-lab) |
| [evil-mcp-lab][link_github_com_rafsan_huseynov_evil_mcp_lab] | Schema mismatch, sandbox-escape attempts, hidden side effects | Evaluate whether static scanners and runtime gateways detect or block malicious-but-well-formed tools. | ![](https://badgen.net/github/last-commit/rafsan-huseynov/evil-mcp-lab) |
| [Hispalis MCP Lab][link_github_com_ezee_sg_mcp_security_lab] | `shadow-analytics` outside the Compose stacks | Ungoverned co-installed server next to the four departmental servers; hardened stack adds Wazuh and Grafana. | ![](https://badgen.net/github/last-commit/ezee-sg/mcp-security-lab) |
| [Vulnerable MCP Server (rahulsinghinfosec)][link_github_com_rahulsinghinfosec_damnvulnerablemcpserver] | Unauthenticated tools and default credentials | `read_notes`, `list_users`, and `system_info` need no auth; `admin_panel` and sensitive logs use default credentials. | ![](https://badgen.net/github/last-commit/rahulsinghinfosec/damnvulnerablemcpserver) |
| [VaultMCP][link_github_com_hardsoftsecurity_vulnerable_mcp_lab] | Streamable HTTP enumeration | Treat the server as directly callable JSON-RPC: list resources and tools before any model is attached. | ![](https://badgen.net/github/last-commit/hardsoftsecurity/vulnerable-mcp-lab) |

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
| [mcploitable][link_github_com_agilealligator_mcploitable] | ASI04 plugin manager | A lookalike plugin is adopted over the honest weather tool, then its output steers credential theft. Practice plugin provenance and tool-output distrust. | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |

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
| [MCP Auth Playground][link_github_com_gravitee_io_labs_mcp_auth_playground] | Interactive OAuth 2.1 flow | Step through protected-resource discovery, dynamic client registration, PKCE, authorization code exchange, tokens, and authenticated MCP calls. | ![](https://badgen.net/github/last-commit/gravitee-io-labs/MCP-Auth-Playground) |
| [Go MCP OAuth Workshop][link_github_com_go_training_mcp_workshop] | OAuth attacks and protocol defenses | Runnable labs for audience binding, authorization-server mix-up defense, JWKS/introspection, DCR, and client ID metadata documents. | ![](https://badgen.net/github/last-commit/go-training/mcp-workshop) |
| [MCP Security Lab (tal7aouy)][link_github_com_tal7aouy_mcp_security_lab] | Challenges 06 and 10 | Secrets leaked through tool output, environment, or logs; a prefix-compare token check on an exposed server. | ![](https://badgen.net/github/last-commit/tal7aouy/mcp-security-lab) |
| [EnumByte MCP Security Lab][link_github_com_sentinelbyte_enumbyte_mcp_security_lab] | Authn and authz pytest suite | Unauthenticated access, expired tokens, wrong audience, and insufficient scope, each proved on the vulnerable server and blocked on the hardened one. | ![](https://badgen.net/github/last-commit/SentinelByte/enumbyte-mcp-security-lab) |
| [Vulnerable MCP Server (rahulsinghinfosec)][link_github_com_rahulsinghinfosec_damnvulnerablemcpserver] | Missing auth and default credentials | Open tools on stdio, Streamable HTTP, and SSE; admin and log tools accept default credentials. | ![](https://badgen.net/github/last-commit/rahulsinghinfosec/damnvulnerablemcpserver) |
| [Quarkus Secure AI Agent Workshop][link_github_com_wjglerum_quarkus_secure_ai_agent_workshop_javazone_2026] | Step 02 token propagation | Unauthenticated MCP server with a confused-deputy flaw; the reference branch adds OIDC, forwarded caller tokens, and audit logging. | ![](https://badgen.net/github/last-commit/wjglerum/quarkus-secure-ai-agent-workshop-javazone-2026) |
| [vuln-support-mcp][link_github_com_obotchris_vuln_support_mcp] | Least-privilege composite server | A server that exposes only ticket and knowledge-base tools breaks the private-data plus egress path; gateway filters redact PII, with one format left to leak past a naive rule. | ![](https://badgen.net/github/last-commit/obotchris/vuln-support-mcp) |

---

## Agentic & multi-protocol labs

Broader agent platforms that include MCP-specific vulnerable servers alongside A2A and chat APIs.

| Resource | Protocols | MCP-relevant agents / labs | Last Update |
| --- | --- | --- | --- |
| [Damn Vulnerable AI Agent (DVAA)][link_github_com_opena2a_org_damn_vulnerable_ai_agent] | MCP, A2A, OpenAI-compatible chat | ToolBot (7010), DataBot (7011), PluginBot (7012), ProxyBot (7013); hardened reference on port 7001 | ![](https://badgen.net/github/last-commit/opena2a-org/damn-vulnerable-ai-agent) |
| [MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs] | MCP, A2A, RAG, memory | Lab 07 flagship kill chain crosses MCP→A2A trust boundary; Lab 03 automated red-team with PyRIT + Promptfoo | ![](https://badgen.net/github/last-commit/aminrj-labs/mcp-attack-labs) |
| [MCPGoat][link_github_com_sabyasachidhal_mcpgoat] | MCP Streamable HTTP | Victim-agent harness demonstrates real LLM agent exploitation impact beyond raw tool calls | ![](https://badgen.net/github/last-commit/SabyasachiDhal/MCPGoat) |
| [mcploitable][link_github_com_agilealligator_mcploitable] | MCP, multi-agent | Seven isolated servers plus ASI08–ASI10 simulations; optional CTF ladder from surface recon to an unwinnable control wall | ![](https://badgen.net/github/last-commit/agileAlligator/mcploitable) |
| [VulnAgent][link_github_com_s81207169_a11y_vulnagent] | LLM, MCP, agent, HTTP API | Eleven graded attacks across the chatbot, MCP server, autonomous agent, and vibe-coded API, each with a hardened twin | ![](https://badgen.net/github/last-commit/s81207169-a11y/Vulnagent) |
| [agent-sec-lab][link_github_com_wstran118_agent_sec_lab] | Tool-using agent, MCP-style tools | Eight scenarios from indirect injection and over-permissioned tools through rug pull, missing approval, and memory poisoning | ![](https://badgen.net/github/last-commit/wstran118/agent-sec-lab) |
| [Quarkus Secure AI Agent Workshop][link_github_com_wjglerum_quarkus_secure_ai_agent_workshop_javazone_2026] | LangChain4j agent, MCP, OIDC | Conference assistant whose MCP server starts unauthenticated; later steps add caller-token propagation and role-gated tools | ![](https://badgen.net/github/last-commit/wjglerum/quarkus-secure-ai-agent-workshop-javazone-2026) |

---

## Reference: CVE catalog & PoC repos

Use these to map CVEs and published incidents to hands-on labs above — not standalone exploit environments.

| Resource | Role | Summary | Last Update |
| --- | --- | --- | --- |
| [The Vulnerable MCP Project][link_vulnerablemcp_info] · [vineethsai/vulnerablemcp][link_github_com_vineethsai_vulnerablemcp] | CVE / advisory catalog | 50+ MCP CVEs, GHSA entries, and incident write-ups with severity, exploitability, and mitigation notes — reading map before lab reproduction. | ![](https://badgen.net/github/last-commit/vineethsai/vulnerablemcp) |
| [MCP Injection Experiments][link_github_com_invariantlabs_ai_mcp_injection_experiments] | Canonical poisoning PoCs | Original direct poisoning, tool shadowing, and WhatsApp rug-pull code from the Invariant Labs disclosure. | ![](https://badgen.net/github/last-commit/invariantlabs-ai/mcp-injection-experiments) |
| [MCPHammer][link_github_com_praetorian_inc_mcphammer] | Offensive testing framework | FastMCP-based framework for text injection, remote instance management, and C2-via-tool-argument demonstrations. | ![](https://badgen.net/github/last-commit/praetorian-inc/MCPHammer) |
| [mcp-ethical-hacking][link_github_com_cmpxchg16_mcp_ethical_hacking] | Educational abuse demos | “Legitimate” social/analysis MCP samples illustrating abuse potential — **authorized testing only**; lab isolation required. | ![](https://badgen.net/github/last-commit/cmpxchg16/mcp-ethical-hacking) |
| [Securing MCP Workshop][link_github_com_sammorrowdrums_mcp_security_workshop] | Workshop index and vulnerability catalog | Six-attack walkthrough against a fork of the GitHub MCP server, plus a 40-plus-entry vulnerability catalog and a trust-boundary diagram. Use it as a map, then reproduce attacks only in an isolated lab. | ![](https://badgen.net/github/last-commit/SamMorrowDrums/mcp-security-workshop) |


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
[link_github_com_aganita_mcp_ctf_challenge]: https://github.com/aganita/mcp-ctf-challenge
[link_github_com_anita_ani_mcp_security_lab]: https://github.com/Anita-ani/mcp-security-lab
[link_github_com_dgenio_mcp_agent_security_dojo]: https://github.com/dgenio/mcp-agent-security-dojo
[link_github_com_dnyandeobharambe_mcp_security_patterns]: https://github.com/dnyandeobharambe/mcp-security-patterns
[link_github_com_go_training_mcp_workshop]: https://github.com/go-training/mcp-workshop/tree/main/03-oauth-mcp
[link_github_com_gravitee_io_labs_mcp_auth_playground]: https://github.com/gravitee-io-labs/MCP-Auth-Playground
[link_github_com_psiinon_evmcp]: https://github.com/psiinon/evmcp
[link_github_com_rafsan_huseynov_evil_mcp_lab]: https://github.com/rafsan-huseynov/evil-mcp-lab
[link_github_com_telekom_mcp_security]: https://github.com/telekom/mcp-security
[link_github_com_avilewis_mcp_security_workshop]: https://github.com/AviLewis/mcp-security-workshop
[link_github_com_connordev1337_mcp_context_poisoning_lab]: https://github.com/ConnorDev1337/mcp-context-poisoning-lab
[link_github_com_danush_aries_prompt_injection_lab]: https://github.com/Danush-Aries/prompt-injection-lab
[link_github_com_ezee_sg_mcp_security_lab]: https://github.com/ezee-sg/mcp-security-lab
[link_github_com_fcortezsecurity_mcp_security_lab]: https://github.com/FCortezSecurity/mcp-security-lab
[link_github_com_hardsoftsecurity_vulnerable_mcp_lab]: https://github.com/hardsoftsecurity/vulnerable-mcp-lab
[link_github_com_het_p301204_veil]: https://github.com/het-P301204/veil
[link_github_com_mariuslihet_mcp_security_lab]: https://github.com/mariuslihet/mcp-security-lab
[link_github_com_obotchris_vuln_support_mcp]: https://github.com/obotchris/vuln-support-mcp
[link_github_com_piyerx_mcp_sentinel_research]: https://github.com/piyerx/MCP-Sentinel-Research
[link_github_com_rahulsinghinfosec_damnvulnerablemcpserver]: https://github.com/rahulsinghinfosec/damnvulnerablemcpserver
[link_github_com_s81207169_a11y_vulnagent]: https://github.com/s81207169-a11y/Vulnagent
[link_github_com_sammorrowdrums_mcp_security_workshop]: https://github.com/SamMorrowDrums/mcp-security-workshop
[link_github_com_sentinelbyte_enumbyte_mcp_security_lab]: https://github.com/SentinelByte/enumbyte-mcp-security-lab
[link_github_com_tal7aouy_mcp_security_lab]: https://github.com/tal7aouy/mcp-security-lab
[link_github_com_vibecodingnights_offensive_security]: https://github.com/VibeCodingNights/offensive-security
[link_github_com_wjglerum_quarkus_secure_ai_agent_workshop_javazone_2026]: https://github.com/wjglerum/quarkus-secure-ai-agent-workshop-javazone-2026
[link_github_com_wstran118_agent_sec_lab]: https://github.com/wstran118/agent-sec-lab
[link_vulnerablemcp_info]: https://vulnerablemcp.info/
[link_vulnerablemcp_info_vuln_cursor_jira_mcp_zero_click_html]: https://vulnerablemcp.info/vuln/cursor-jira-mcp-zero-click.html
[link_vulnerablemcp_info_vuln_github_mcp_exploit_html]: https://vulnerablemcp.info/vuln/github-mcp-exploit.html
[link_vulnerablemcp_info_vuln_markitdown_ssrf_html]: https://vulnerablemcp.info/vuln/microsoft-markitdown-mcp-ssrf.html
[link_vulnerablemcp_info_vuln_rug_pulls_silent_redefinition_html]: https://vulnerablemcp.info/vuln/rug-pulls-silent-redefinition.html
[link_vulnerablemcp_info_vuln_whatsapp_message_exfiltration_html]: https://vulnerablemcp.info/vuln/whatsapp-message-exfiltration.html
