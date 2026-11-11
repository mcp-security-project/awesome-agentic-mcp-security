# MCP Security Tools

For MCP servers that expose **external security products** (Semgrep, Burp, Shodan, cloud IAM, identity platforms, trust scores, and similar), see [MCP security servers and integrations](mcp_security_servers_and_integrations.md). This page focuses on **MCP-aware scanners, gateways, and general AppSec utilities** that harden or observe MCP and agent workflows.

**Scope:** free, open-source, or non-commercial tools only. Commercial SaaS scanners, paid-only platforms, and vendor SIEM/EDR products are excluded (see integrations page for MCP wrappers around commercial security products).

## Contents

- [MCP Scanners](#mcp-scanners)
- [Guidance and checklists](#guidance-and-checklists)
- [Runtime Monitoring Tools](#runtime-monitoring-tools)
- [MCP Policy Engines](#mcp-policy-engines)
- [Secrets and Dependency Scanners](#secrets-and-dependency-scanners)
- [Red Teaming Tools](#red-teaming-tools)
- [Open-source observability](#open-source-observability)

---

## MCP Scanners

| Tool & resources | Category — Use for / detects |
| --- | --- |
| **[Cisco AI Defense MCP Scanner][link_github_com_cisco_ai_defense_mcp_scanner]** | MCP scanner (multi-engine) — Servers, tools, prompts, resources, instructions, source, dependencies; **detects** malicious tools, prompt injection, vulnerable deps, suspicious code, malicious bundles. CLI or REST API (YARA, LLM-judge, Cisco API, pip-audit, optional VirusTotal, offline JSON); some features need API keys / data egress. |
| **[MSCC (MCP Security Command Center)][link_github_com_gensecaihq_mcpscc]** | MCP security scanner — Common MCP-specific issues; **detects** prompt injection, tool poisoning, secret exposure, other weaknesses. Dev / DevSecOps; validate maturity before enterprise. |
| **[Secure-Hulk][link_github_com_appiumtestdistribution_secure_hulk]** | MCP config & tool scanner — Config review, reports; **detects** prompt injection, tool poisoning, cross-origin escalation, exfiltration, toxic flows, privilege escalation, cross-resource risks. JSON/HTML reports; whitelist support; early-stage project. |
| **[AI-Infra-Guard][link_github_com_tencent_ai_infra_guard]** (A.I.G) | AI infra red-teaming platform — MCP server & agent-skills scanning, jailbreak eval, and related self-assessment flows; broader than MCP-only scanners (MCP-focused briefing PDFs also linked from [conference talks](mcp_conference_talks.md)). |
| **[SecureMCP][link_github_com_makalin_securemcp]** | MCP security audit — OAuth/token issues, prompt injection testing, auth & TLS checks, server integrity, reports. |
| **[mcp-watch][link_github_com_kapilduraphe_mcp_watch]** (npm: `mcp-watch`) | MCP server static/descriptor scanner — Credentials, tool poisoning, parameter injection, ANSI tricks, toxic flows, spoofing; **not** the same project as [mcpwatch][link_github_com_lazymac2x_mcpwatch] (separate maintainer). |
| **[mcp-audit][link_github_com_adudley78_mcp_audit]** | MCP config scanner (open source, privacy-first) — Scans MCP server JSON configs across 8+ supported clients; **detects** tool poisoning, plaintext credential exposure, transport misconfigs, supply chain / typosquatting, rug-pull description drift, toxic cross-server flows, and multi-hop attack paths. CLI + JSON + SARIF + HTML dashboard; GitHub Action; pre-commit hook; 89 bundled Semgrep SAST rules for MCP server source code; full OWASP MCP Top 10 mapping; runs fully offline by default; Apache 2.0. |
| **[Ant Group MCP-Security][link_github_com_antgroup_mcp_security]** | Static + dynamic MCP scanner — Auditing agent tools / plugins; **detects** malicious metadata (prompt injection), insecure tools, unsafe reads, code vulns. Semgrep-style taint + dynamic LLM eval; local or remote GitHub repos. |
| **[MCPServer Audit][link_github_com_modelcontextprotocol_security_mcpserver_audit]** | MCP server audit — Pre-use safety checks; publishing to audit/DB; output per audit workflow. Community initiative — verify maturity / evidence format. |
| **[MCPSafetyScanner][link_github_com_leidosinc_mcpsafetyscanner]** | Agentic MCP safety auditor — Adversarial samples from tools/resources; safety reports; **detects** unsafe tools, malicious execution, credential theft, unauthorized access. Research / academic; **safety:** isolated test env only. |
| **[Pluto AgentGuard][link_github_com_arpitha_dhanapathi_pluto_aguard]** | MCP config scanner + policy tester → Static analysis of MCP configs for dangerous servers, hardcoded secrets, missing auth, context safety gaps; **plus** policy coverage testing (22 attack scenarios), what-if risk simulation, OWASP-inspired control mapping, baseline drift detection, and launch evidence generation. Offline, no API keys; validated against 1,200 real GitHub MCP configs. |
| **[MCP-SandboxScan][link_github_com_wapiti08_mcp_sandboxscan]** | Runtime / sandbox analysis — Execute untrusted tools in WASM/WASI-style sandbox; **detects** env/file→prompt, filesystem violations, runtime-only issues. Research / experimental; advanced research & high-risk tool review. |
| **[MCP Inspector][link_github_com_modelcontextprotocol_inspector]** ([documentation][link_modelcontextprotocol_io_docs_tools_inspector]) | Dev test/debug (not a security scanner) — Manual inspection of servers, tools, prompts, resources, transport; observational only (no automated detection). For security review: validate tools/schemas before approval; **not** a replacement for automated scanning. |
| **[MCP Doctor][link_github_com_xlyoung_mcp_doctor]** | MCP server quality & security toolkit — 8 security checks (prompt injection, path traversal, credential leakage, SSRF, command injection, supply chain, excessive permissions, network exfiltration); automated 0-100 quality scoring; curated registry of 100+ servers; CI/CD integration. Python CLI; **pip install mcpdoctor**. |
| **[Snyk Agent Scan][link_github_com_snyk_agent_scan]** (PyPI `snyk-agent-scan`; legacy Invariant `mcp-scan`) | Agent/MCP/skills discovery scanner — Auto-discovers Claude, Cursor, Windsurf, Gemini configs; **detects** prompt injection, tool poisoning, tool shadowing, toxic flows, secrets, and skill malware patterns. Open-source CLI (Apache 2.0); analysis uses Snyk API by default — review data handling; `--dangerously-run-mcp-servers` for CI. |
| **[MCPShield][link_github_com_mcpshield_mcpshield]** (npm: `mcpshield`) | Supply-chain MCP scanner — Typosquat detection, dependency CVEs, hardcoded creds, dangerous permissions, transport security; HTTP endpoint + GitHub repo scans; JSON/SARIF; CI exit codes. **Not** the same as other unrelated “MCP Shield” repos. |
| **[MCPhound][link_github_com_tayler_id_mcphound]** (npm: `mcphound`) | Graph-based MCP config scanner — Models cross-server attack paths, rug-pull hashing, trust scoring, typosquats, CVEs, tool poisoning; JSON/SARIF; GitHub Action. Deterministic, no LLM required; `npx mcphound`. |
| **[mcpwatch][link_github_com_lazymac2x_mcpwatch]** (Go) | MCP server security scanner — Descriptor and config analysis in Go; distinct from [mcp-watch][link_github_com_kapilduraphe_mcp_watch] (Node). |
| **[MCTS][link_github_com_mcp_audit_mcts]** (Model Context Threat Scanner) | Static + live MCP scanner — Tool metadata, poisoning, shadowing, rug-pull baselines, source-aware SAST, optional YARA/LLM-judge; JSON/SARIF/HTML; OWASP LLM + MCP Top 10 mapping; alpha, local-first CI gates. |
| **[mcp-swiss-knife][link_github_com_nik1097_mcp_swiss_knife]** | Live MCP tool-poisoning detector — Pattern, semantic, and structural layers against running servers; tune thresholds for false positives. |
| **[MCPSec][link_github_com_mcp_shark_mcpsec]** | OWASP MCP + Agentic AI compliance audits — CLI or MCP server mode; SARIF output and CI gating; maps to FastMCP security baseline. **Not** the same project as [mcpsec (fuzzing)][link_github_com_manthanghasadiya_mcpsec]. |
| **[@piiiico/mcpaudit][link_github_com_piiiico_mcpaudit]** | MCP server SAST — Shell injection, path traversal, SSRF, SQLi, hardcoded secrets, missing auth across Node/Python/Rust/Go; `npx @piiiico/mcpaudit owner/repo`; validated against real MCP CVEs. |
| **[skill-audit-mcp][link_github_com_eltociear_skill_audit_mcp]** | Static scanner for MCP servers, agent skills, and plugins — 17 attack patterns; SARIF → GitHub Code Scanning; CLI, GitHub Action, Docker, and MCP server modes; official MCP Registry entry. |
| **[agent-bom][link_github_com_msaad00_agent_bom]** | Agent supply-chain scanner — CVEs, SBOMs, MCP client discovery, blast-radius mapping; OWASP LLM, MITRE ATLAS, NIST AI RMF crosswalks. |
| **[inkog-mcp][link_github_com_inkog_io_inkog_mcp]** | Pre-flight agent/MCP scanner — 20+ framework coverage; OWASP LLM Top 10 and EU AI Act theme mapping. |
| **[mcp-fence][link_github_com_daoyuanli2816_mcp_fence]** (PyPI `mcp-fence`) | Local-first scanner + fuzzer — Static config analysis, live stdio inspection, schema-aware fuzzing, Docker sandbox; JSON/SARIF/HTML; optional local LLM judge (Ollama); Apache 2.0. |
| **[MCPScan][link_github_com_sahiloj_mcpscan]** | Offensive MCP server auditor — Tool poisoning, credential leaks, RCE vectors, SSRF, session hijacking, supply chain across stdio/HTTP/SSE; SARIF with CVSS severities; MIT. |
| **[mcp-security-scanner][link_github_com_badchars_mcp_security_scanner]** | Agent-driven MCP audit MCP server — 55 local tools for runtime inspection, AST SAST, config audit, dependency checks, fuzzing, OWASP MCP Top 10 scoring; zero external API calls. |
| **[mcpsec][link_github_com_manthanghasadiya_mcpsec]** (PyPI `mcpsec`) | MCP protocol fuzzer + static audit — Command/path/SSRF/SQL injection payloads, auth audit, RAG-poisoning chains, description-vs-implementation mismatch; optional AI taint analysis. |
| **[Nova Proximity][link_github_com_nova_hunting_nova_proximity]** | MCP + agent-skills discovery scanner — Enumerates tools/prompts/resources; optional NOVA rule engine for prompt injection and jailbreak patterns; JSON/Markdown reports; GPL-3.0. |
| **[ClawGuard][link_github_com_joergmichno_clawguard]** | Regex-based agent/MCP scanner — 200+ patterns, 15 languages, sub-10ms; dedicated `mcp_scanner.py` for tool-description poisoning and permission abuse; MIT; no cloud LLM. |
| **[mcp-gateway-scan][link_github_com_willianpinho_mcp_gateway_scan]** | Read-only gateway readiness scorer — Seven security dimensions for MCP/agent-gateway configs; never executes scanned code. |
| **[mcpskills-server][link_github_com_bebravebekind_mcpskills_server]** | Pre-install trust gate — MCP servers, skills, and npm packages; `auto_gate` go/no-go; official MCP Registry entry. |
| **[agentscore-mcp-server][link_github_com_thezenmonster_agentscore_mcp_server]** | npm MCP package monitor — Install scripts, drift, publisher posture; GitHub Action policy gate. |
| **[mcp-audit (sovereign-shovels)][link_github_com_sovereign_shovels_mcp_audit]** | Static “npm audit for MCP” — Scans npm packages, GitHub repos, or local paths without executing code; JSON/SARIF. **Not** the same project as [mcp-audit (adudley78)][link_github_com_adudley78_mcp_audit]. |
| **[mcp-safeguard][link_github_com_syedanas01_mcp_safeguard]** | MCP source and server scanner — Checks prompt injection, credential exposure, SSRF, tool poisoning, and insecure credential handling; MIT; early-stage. |
| **[MCP Security Scanner (sidhpurwala-huzaifa)][link_github_com_sidhpurwala_huzaifa_mcp_security_scanner]** | Live MCP scanner — Tests HTTP, stdio, and SSE servers for auth, transport, tool, prompt, resource, rug-pull, permission, and token-leak issues; Apache 2.0. **Not** the same project as [badchars/mcp-security-scanner][link_github_com_badchars_mcp_security_scanner]. |
| **[MCPSec (pfrederiksen)][link_github_com_pfrederiksen_mcpsec]** | Evidence-based OWASP MCP Top 10 scanner — Config/source analysis, baseline drift, shadow-server discovery, and read-only remote enumeration; OCSF JSON and CI gates; Apache 2.0. Distinct from the other projects named MCPSec/mcpsec above. |
| **[mcp-verify][link_github_com_finktech_dev_mcp_verify]** | MCP security and protocol verifier — 61 security rules, schema-aware fuzzing, JSON-RPC/MCP compliance checks, gateway threat detection, and SARIF/HTML reports; AGPL-3.0. |
| **[MCP Tool Auditor][link_github_com_perparimmjeku_mcp_auditor]** (`mcp-tool-auditor`) | Live tool-schema auditor — Detects tool poisoning, ATPA behavior, shadowing, signed-baseline tampering, rug pulls, and cross-tool attack paths; MIT. |
| **[MCP Audit (AgentPostmortem)][link_github_com_agentpostmortem_mcp_audit]** | Offline deterministic linter — 18 rules for live stdio/HTTP servers or static manifests, with JSON/SARIF CI output; MIT. Distinct from the other `mcp-audit` projects listed here. |
| **mcpguard** (five unrelated projects — pick by maintainer) | [loplop-h/mcpguard][link_github_com_loplop_h_mcpguard] (OWASP MCP Top 10 mapping, auto-fix, rug-pull alerts); [nbosa/mcpguard][link_github_com_nbosa_mcpguard] (Go scanner + stdio guard proxy, SARIF, entropy secret detection); [ardakocadoruu/mcpguard][link_github_com_ardakocadoruu_mcpguard] (Python npm-package static scanner, typosquat DB); [rohitguta2432/mcpguard][link_github_com_rohitguta2432_mcpguard] (deterministic manifest scanner, CI exit codes, eval suite); [GT-Projects256/mcpguard][link_github_com_gt_projects256_mcpguard] (config scanner and runtime firewall, OWASP MCP Top 10, SARIF and audit logs; npm `@gtprojects/mcpguard`; MIT). |
| **[mcp-shield][link_github_com_muhannad_hash_mcp_shield]** (npm `@muhannad-hash/mcp-shield`) | Pre-install npm/local MCP scanner — Exfiltration, code execution, obfuscation, prompt injection, supply-chain trust scoring; MCP server mode with `scan_package` / `scan_directory`; MIT. **Not** [MCPShield (mcpshield)][link_github_com_mcpshield_mcpshield] or other unrelated “MCP Shield” repos. |
| **[Ramparts][link_github_com_highflame_ai_ramparts]** | MCP and agent-skill scanner — Multi-transport discovery, evasion-resistant YARA analysis, prompt/tool-poisoning detection, OSV dependency checks, OWASP mapping, and SARIF/JSON/Markdown reports; Apache 2.0. |
| **[APIsec MCP Audit][link_github_com_apisec_inc_mcp_audit]** | MCP configuration and source scanner — Discovers exposed secrets and shadow APIs, generates AI-BOMs, and detects MCP tool-input flows into unsafe shell execution; MIT. Distinct from the other `mcp-audit` projects listed here. |
| **[toolpoison][link_github_com_web3wikis_toolpoison]** | Local config and live-description scanner — Detects tool poisoning, hidden Unicode, cross-server shadowing, leaked credentials, and unpinned supply-chain dependencies across major MCP clients; MIT. |
| **[MCP Trust][link_github_com_stevemonsway_mcp_trust]** | Evidence-based MCP preflight scanner — Audits install commands, source, dependencies, metadata, and sandboxed live behavior; approve/block decisions plus SARIF/HTML reports; Apache 2.0. |
| **[mception][link_github_com_soufianetahiri_mception]** | Static MCP supply-chain auditor — Extracts MCP surfaces across Python, JavaScript/TypeScript, Go, Rust, and Ruby; checks poisoning, RCE, SSRF, credential exfiltration, dependencies, transport/auth, and cross-server composition; MIT. |
| **[MCPeek][link_github_com_iamakash_06_mcpeek]** | TypeScript/JavaScript MCP SAST — Recognizes MCP handlers and traces tool inputs into command/code execution, SQLi, path traversal, and SSRF sinks; SARIF includes taint paths; MIT. |
| **[MCPSense][link_github_com_fayzkk889_mcpsense]** | Multi-mode MCP scanner — Audits source, manifests, client configs, and live servers for tool poisoning, annotation deception, command injection, SSRF, environment leakage, and supply-chain risks; MIT. |
| **[MCP X-Ray][link_github_com_traceforce_mcp_xray]** | Unified MCP scanner and pentest utility — Config, SCA, SAST, secrets, TLS/OAuth, tool analysis, and active tests with SARIF output; local token analysis works offline, while cloud upload is optional. |
| **[MCPRadar][link_github_com_yatuk_mcpradar]** | MCP protocol, source, config, and supply-chain scanner — Tool poisoning, prompt injection, schema abuse, secret exposure, transport issues, cross-server paths, Python and JavaScript SAST, OSV checks, CycloneDX SBOM, and signed snapshot drift; optional Docker or Podman sandbox; JSON, SARIF, and CEF; MIT. |
| **[Agent Governance Toolkit `mcp-scan`][link_github_com_microsoft_agent_governance_toolkit]** ([CLI tutorial][link_microsoft_github_io_agt_mcp_scan]) | Local-first metadata scanner in Microsoft’s Agent Governance Toolkit — Hidden instructions, description injection, schema abuse, cross-server impersonation, and rug-pull fingerprint drift across stdio, Streamable HTTP, and HTTP+SSE; `--static-only` does not launch commands or connect to endpoints. MIT. Distinct from [Snyk Agent Scan][link_github_com_snyk_agent_scan] (legacy Invariant `mcp-scan`). |
| **[DefenseClaw][link_github_com_cisco_ai_defense_defenseclaw]** | Admission scanner — Reviews MCP servers, agent skills, plugins, and tool calls before use, then pairs with a runtime sidecar and audit export. Apache 2.0. Distinct from [Cisco AI Defense MCP Scanner][link_github_com_cisco_ai_defense_mcp_scanner]. |
| **[Aguara][link_github_com_garagon_aguara]** | Deterministic local scanner — MCP configs, skills, packages, and workflows for prompt injection and secrets; SARIF and CI. Apache 2.0. |
| **[Agent Audit Kit][link_github_com_sattyamjjain_agent_audit_kit]** | Static agent-pipeline scanner — MCP-connected workflows with SARIF output and compliance mappings; deterministic rules. Apache 2.0. |
| **[AgentShield (affaan-m)][link_github_com_affaan_m_agentshield]** (npm `ecc-agentshield`) | Agent-config auditor — Hardcoded secrets, permission misconfigs, hook injection, MCP server risk, and prompt injection; CLI, GitHub Action, and GitHub App. MIT. Distinct from other projects named AgentShield. |
| **[SkillSpector][link_github_com_nvidia_skillspector]** (NVIDIA) | Pre-install skill scanner — Vulnerabilities, prompt injection, exfiltration, and supply-chain risk in agent skills, including MCP skills. Apache 2.0. A skill-package scanner, separate from a live MCP protocol or config scanner. |
| **[Agent Security Scanner MCP][link_github_com_sinewaveai_agent_security_scanner_mcp]** | Scanner for MCP servers, prompts, generated code, dependencies, and agent actions. MIT. Review any cloud or LLM data handling before CI use. |
| **[MCP Scorecard][link_github_com_aak204_mcp_scorecard]** | CI scorecard — Launches a local stdio server and scores conformance, security, ergonomics, and metadata with deterministic rules. Apache 2.0. Treat the scan host as untrusted-code execution. |
| **[mcp-gateway (Niraven)][link_github_com_niraven_mcp_gateway]** (npm `@niraven/mcp-gateway`) | Config audit — Tool-description poisoning, supply-chain signals, and security misconfiguration, plus a live proxy mode. MIT; early-stage. |
| **[mcpsentry][link_github_com_roshan6335_mcpsentry]** (npm `@roshan6335/mcpsentry`) | Scanner and trust baseline — Tool poisoning and rug-pull drift against a saved baseline, with a proxy mode that inspects tool-call results. MIT. |
| **[Project Sentinel][link_github_com_sentinel_atl_project_sentinel]** | MCP trust scanner — Scores servers and issues signed trust certificates that a companion gateway can enforce. Apache 2.0. Review who signs certificates and what the score measures. |
| **[mcpwn (ressl)][link_github_com_ressl_mcpwn]** | Pre-deployment vulnerability scanner — Prompt injection, tool poisoning, exfiltration, SSRF, command injection, and exposed secrets. AGPL-3.0. Companion to [mcp-firewall (ressl)][link_github_com_ressl_mcp_firewall]. Distinct from [mcpwn (D0rs4n)][link_github_com_d0rs4n_mcpwn]. **Authorized targets only.** |
| **[KarmaDue][link_github_com_ashadow07_karmadue]** | Pre-install check for npm, PyPI and MCP servers — `check_install` returns block / ask / care, advisories and malicious-package reports, and tested setup fixes where a record exists. Hosted Streamable HTTP endpoint (no account for reads); the public MIT repository contains the guard, Claude Code hook, docs and seed records (hosted server code is not in the repository). Seed records are a founder-operated assessment, not independent. Official MCP Registry: `io.github.ashadow07/karmadue`. |

---

## Guidance and checklists

| Resource | Category — Use for MCP |
| --- | --- |
| **[MCP Security Checklist (SlowMist)][link_github_com_slowmist_mcp_security_checklist]** | Community checklist — Design, deployment, and operations review items for MCP and agent integrations (process aid, not an automated scanner). |
| **[OWASP MCP Top 10][link_owasp_org_www_project_mcp_top_10]** | Community risk taxonomy — Ten MCP-specific risk categories (token mismanagement, tool poisoning, shadow servers, context oversharing, etc.); use to map scanner findings and control gaps. |
| **[MCP Azure Security Guide][link_github_com_microsoft_mcp_azure_security_guide]** ([published guide][link_microsoft_github_io_mcp_azure_security_guide]) | OSS reference — Maps each OWASP MCP Top 10 risk to Azure mitigations (Entra ID, managed identities, APIM, Key Vault, network isolation). |
| **[Invariant Guardrails docs][link_invariantlabs_ai_github_io_docs_mcp_scan]** ([Guardrails repo][link_github_com_invariantlabs_ai_invariant]) | Rule-based guardrails for MCP/LLM proxies — Tool-call restrictions, PII/secrets detection, custom policies; pairs with Snyk Agent Scan lineage and `mcp-scan proxy` runtime mode. |
| **[MCP Server Security Standard (MSSS)][link_github_com_mcp_security_standard_mcp_server_security_standard]** | Open community standard — Tiered controls and evidence requirements for filesystem, execution, SSRF, authorization, validation, logging, supply chain, and deployment; includes machine-readable schemas. |
| **[Official MCP Security Best Practices][link_modelcontextprotocol_io_security_best_practices]** | Protocol guidance — Confused-deputy attacks, token passthrough, SSRF, OAuth state and audience validation, consent, and session security. |
| **[Pentesting MCP Servers Checklist][link_github_com_appsecco_pentesting_mcp_servers_checklist]** | CC BY 4.0 assessment checklist — Local and remote MCP testing across transport, authorization, tools, injection, context isolation, secrets, concurrency, and logging. |
| **[OWASP MCP Security Cheat Sheet][link_owasp_mcp_security_cheat_sheet]** | Cheat sheet — Least privilege, tool-schema integrity and pinning, sandboxing, human approval, transport security, and monitoring for MCP hosts, clients, and servers. |
| **[OWASP MCP Security Testing Guide][link_github_com_owasp_mcp_security_testing_guide]** | Community testing guide (MCPSTG) — Threat write-ups and tests for hosts, clients, servers, tools, transports, and gateways, modeled on the Web Security Testing Guide. GPL-3.0. The repository presents this as community guidance. **Authorized testing only.** |
| **[MCP Checklists][link_github_com_mcp_manager_mcp_checklists]** | Practitioner checklists — Screening items for poisoning, rug pulls, OAuth, metadata pinning, least privilege, and monitoring. AGPL-3.0. Published by MCP Manager; validate against current MCP and OWASP material. |

---

## Runtime Monitoring Tools

| Tool & resources | Category — Summary |
| --- | --- |
| **[Lasso MCP Gateway][link_github_com_lasso_security_mcp_gateway]** | MCP gateway — Centralize lifecycle, intercept, sanitize, scan before load; single control point for many servers. Enterprise / governed connections. |
| **[Agent Wall][link_github_com_agent_wall_agent_wall]** | MCP firewall / policy proxy — YAML policy on tool calls and responses; block dangerous reads, shell, exfiltration, risky chains. Client–server middle; local IDE workflows. |
| **[MCP Action Firewall][link_github_com_starskrime_mcp_action_firewall]** | Human-approval / transparent proxy — OTP approval for dangerous tool calls; circuit breaker for high-impact actions. Demos / local; validate before enterprise. |
| **[OpenTelemetry MCP semantic conventions][link_opentelemetry_io_docs_specs_semconv_gen_ai_mcp]** ([Grafana MCP observability guide][link_grafana_com_blog_ai_observability_mcp_servers]) | Observability / telemetry — Spans, latency, errors, health, audit metadata; baseline and detect abnormal tool patterns. Feeds Grafana, Tempo, Loki, Prometheus, OpenSearch, and other OSS backends. |
| **Egress proxies & network controls** (Smokescreen-style, corporate proxy, mesh egress, K8s NetworkPolicy) | Network runtime control — Block metadata SSRF, private IPs, paste sites, unexpected APIs; SSRF, exfiltration, untrusted remote fetch. Treat MCP servers as user-acting code; minimal explicit egress. |
| **[Armorer Guard][link_github_com_armorerlabs_armorer_guard]** | Local Rust scanner and MCP proxy — Wrap stdio MCP servers, inspect `tools/call` arguments, emit structured reasons, and block prompt injection, credential leakage, exfiltration, or dangerous tool-call risk before execution. |
| **[mcp-context-protector][link_github_com_trailofbits_mcp_context_protector]** (Trail of Bits) | MCP client wrapper / visibility layer — Surfaces malicious or deceptive server-provided context (e.g. description-driven exfiltration, “line jumping”); complements scanners and policy proxies. |
| **[MCP Audit (VS Code extension)][link_github_com_agentity_com_mcp_audit_extension]** ([Visual Studio Marketplace][link_marketplace_visualstudio_com_agentity_mcp_audit_extension]) | IDE-side audit logging — Intercepts and logs Copilot/MCP tool calls with optional SIEM/syslog forwarders; governance and troubleshooting, not a substitute for server-side controls. |
| **[MCP-Defender][link_github_com_mcp_defender_mcp_defender]** | Desktop proxy — Intercepts MCP traffic from supported clients, signature-style checks, user allow/block prompts; review AGPL terms and update channel before fleet rollout. |
| **[MCP-Dandan][link_github_com_82ch_mcp_dandan]** | Desktop monitoring — Real-time observation of MCP sessions with Electron UI; tune noise vs. signal for SOC handoff. |
| **[Pipelock][link_github_com_luckypipewrench_pipelock]** | Runtime MCP/HTTP proxy — Scans tool descriptions, call arguments, and responses on every message; DLP-style credential leak patterns and egress inspection; Apache 2.0. |
| **[shield (AperionAI)][link_github_com_aperionai_shield]** | Local guardrail proxy — TOFU tool-catalog pinning and rug-pull detection; wraps stdio or Streamable HTTP upstream servers. |
| **[sint-protocol][link_github_com_sint_ai_sint_protocol]** | Governance proxy + `sint-scan` CLI — Preflight tool-risk audits, capability tokens, approval tiers, tamper-evident receipts; Apache 2.0. |
| **[mcp-firewall][link_github_com_behrensd_mcp_firewall]** | Deterministic policy proxy — YAML policies (“iptables for MCP”), secret-leak scanning, no cloud dependency. |
| **[mcp-guardian][link_github_com_rudraneel93_mcp_guardian]** | Governance proxy — YAML policy, OAuth/OIDC RBAC, STRIDE threat model; distinct from [MCP Guardian (eqtylab)][link_github_com_eqtylab_mcp_guardian]. |
| **[PolicyLayer Intercept][link_github_com_policylayer_intercept]** | MCP proxy with YAML policies — Rate limits, validation, audit trail at the transport boundary. |
| **[Sentinelgate][link_github_com_sentinel_gate_sentinelgate]** | MCP proxy — CEL policies, RBAC, audit trail for governed deployments. |
| **[MCP Guardian (eqtylab)][link_github_com_eqtylab_mcp_guardian]** | Human-approval MCP proxy — Real-time approve/deny for tool calls, message logging, multi-config management; Apache 2.0. Distinct from [mcp-guardian (rudraneel93)][link_github_com_rudraneel93_mcp_guardian]. |
| **[MCPProxy Go][link_github_com_smart_mcp_proxy_mcpproxy_go]** | Local MCP proxy + dashboard — Security quarantine for new servers (TPA mitigation), BM25 tool discovery, Docker-isolated upstreams, sensitive-data detection in tool calls, full audit log; MIT. |
| **[mcpgate][link_github_com_maksym_mishchenko_mcpgate]** | Deny-by-default MCP proxy — YAML policy for tools/resources/prompts/sampling, human approval, poisoning heuristics, egress allowlists, and HMAC-verifiable SQLite audit logs; MIT; early-stage. |
| **[AgentGuard][link_github_com_tkingovr_agent_guard]** | Stdio/HTTP security proxy — YAML or OPA/Rego policy, default deny, approvals, secret scanning, rate limits, and a live audit dashboard; Apache 2.0; early-stage. |
| **[MCP Zero-Trust Proxy][link_github_com_keith_aykira_mcp_zero_trust_proxy]** | MCP-aware reverse proxy — OAuth 2.1 with PKCE, tool-level RBAC, filtered discovery, rate limiting, and JSONL/OCSF/CEF audit sinks; MIT; early-stage. |
| **[agentgateway][link_github_com_agentgateway_agentgateway]** | MCP/agent gateway — CEL-based per-tool authorization, JWT identity policy, denied-tool filtering, rate limits, guardrails, and OpenTelemetry telemetry; Apache 2.0. |
| **[Preloop][link_github_com_preloop_preloop]** | Self-hosted agent control plane — MCP firewall with YAML/CEL policy, human approvals, runtime session observability, budgets, and audit trails; Apache 2.0; pre-1.0. |
| **[mcp-fence (yjcho9317)][link_github_com_yjcho9317_mcp_fence]** | Bidirectional MCP security proxy — Request/response scanning, OPA or local policy, schema pinning, cross-server flow controls, JWT auth, and HMAC-protected audit logs; MIT. Distinct from the scanner/fuzzer named [mcp-fence][link_github_com_daoyuanli2816_mcp_fence]. |
| **[McpVanguard][link_github_com_provnai_mcpvanguard]** | MCP runtime firewall — Layered request and metadata inspection, auth/scope enforcement, capability-drift checks, signed provenance, and audit receipts across stdio and HTTP; MIT. |
| **[mcpproxy (hoophq)][link_github_com_hoophq_mcpproxy]** | MCP security gateway — Tool filtering, held-call approvals, session budgets, rug-pull detection, server-request gating, multi-plane auth, audit, Prometheus, and OTLP; MIT; early-stage. Distinct from MCPProxy Go above. |
| **[mcp-audit (P4ST4S)][link_github_com_p4st4s_mcp_audit]** | Transparent MCP audit proxy — Signed JSONL/SQLite evidence, redaction, tool policy, rate limits, dashboard, Prometheus, and OTLP export; Apache 2.0. Distinct from the scanner projects with the same name. |
| **[BlueRock OSS][link_github_com_bluerock_io_bluerock]** | Python MCP runtime sensor — Zero-code-change telemetry for tool/resource calls, sessions, transports, and module imports with SHA-256 evidence emitted as NDJSON; Apache 2.0; pre-1.0. |
| **[ToolHive][link_github_com_stacklok_toolhive]** | MCP runtime platform — Runs each server in an isolated container, enforces OIDC authentication and Cedar authorization, and emits audit logs and OpenTelemetry. Apache 2.0. Fleet RBAC compilation is a Stacklok Enterprise feature; Cedar policies are in the open-source gateway. |
| **[Kuadrant MCP Gateway][link_github_com_kuadrant_mcp_gateway]** | Envoy-based MCP gateway — Aggregates servers and attaches Istio/Kuadrant policy for authentication, per-tool and per-prompt authorization, rate limits, and token exchange. Apache 2.0. |
| **[GreenGateway][link_github_com_greenhat_security_greengateway]** | Self-hosted API and MCP gateway — JWT/OIDC, RBAC, deny-by-default firewall rules, shadow mode, egress allowlists, audit logs, and an admin UI. Apache 2.0; early-stage. |
| **[mcp-firewall (ressl)][link_github_com_ressl_mcp_firewall]** | MCP security gateway — YAML and per-agent RBAC, injection and chain detection, SSRF egress control, human approval, response scanning, and signed audit logs; includes a pre-deployment scan via [mcpwn (ressl)][link_github_com_ressl_mcpwn]. AGPL-3.0. Distinct from [behrensd/mcp-firewall][link_github_com_behrensd_mcp_firewall]. |
| **[DefenseClaw][link_github_com_cisco_ai_defense_defenseclaw]** | Runtime governance sidecar — Inspects MCP and agent tool-call traffic after admission scanning and exports audit evidence. Apache 2.0. |
| **[Agent Governance Toolkit MCP gateway][link_github_com_microsoft_agent_governance_toolkit]** | Runtime controls in the same toolkit as [`mcp-scan`][link_microsoft_github_io_agt_mcp_scan] — Poisoning detection, drift monitoring, typosquatting, and hidden-instruction scanning with policy evidence. MIT; community preview. Verify package provenance before deployment. |
| **[HOL Guard][link_github_com_hashgraph_online_hol_guard]** | Local-first agent runtime guard — Risky tools, secret access, prompt injection, packages, MCP servers, plugins, and skills. Apache 2.0. Review which checks stay on the machine. |
| **[Warden][link_github_com_parveshsaini_warden]** (npm `warden-gateway`) | Federating MCP gateway — Tool-poisoning and prompt-injection checks, YAML policy, rate limits, approval gates, JSONL audit, and OpenTelemetry. MIT. Distinct from the Bitwarden admin server `warden-mcp`. |
| **[ShieldMCP][link_github_com_saurabh_yergattikar_shieldmcp]** | Runtime MCP proxy — Inspects tool metadata, call arguments, and responses for poisoning, rug pulls, and indirect injection over stdio or legacy SSE; optional local classifiers. Apache 2.0. Response checks run after the tool executes. |
| **[SentinelMCP (Technosive)][link_github_com_technosiveuk_ui_sentinelmcp]** | MCP firewall — HTTP/SSE proxy or in-process Go SDK; YAML risk policies, PII and secret redaction, human approval, egress allowlists, and OpenTelemetry audit. Apache 2.0. Distinct from [Sentinelgate][link_github_com_sentinel_gate_sentinelgate]. |
| **[Flint][link_github_com_tejaaswini_flint]** | Local stdio session firewall — Default-deny RBAC and explicit deny rules on every `tools/call`. Behavioral checks for secret relay, cross-scope movement, and tool poisoning are scored and audited. MIT. No cloud dependency. |
| **[vex-mcp][link_github_com_mdombrov_33_vex_mcp]** | Transparent Rust gateway — Scans tool descriptions and schemas for injection, hidden Unicode, and definition drift. MIT. A legitimate description edit can look like drift; tune the policy before blocking. |
| **[mcpfw][link_github_com_kphatak001_mcpfw]** | Transparent MCP policy proxy — YAML per-call and session policy, tool-description rug-pull blocking, and response-injection scanning over stdio or HTTP. Apache 2.0; early-stage. |
| **[mcp-gateway (Niraven)][link_github_com_niraven_mcp_gateway]** | Live proxy — Argument checks, descriptor-drift detection, and secret redaction in front of upstream MCP servers. MIT; early-stage. |
| **[mcpsentry][link_github_com_roshan6335_mcpsentry]** | Live MCP proxy — Forwards client traffic and inspects tool-call results for injected instructions before they reach the agent. MIT. |
| **[Project Sentinel][link_github_com_sentinel_atl_project_sentinel]** | Trust-certificate gateway — Can refuse MCP traffic when a server certificate fails the configured trust check. Apache 2.0. |
| **[MCP Guardian (PawelKozy)][link_github_com_pawelkozy_mcp_guardian]** | Security proxy — Aggregates servers, enforces allow/block policy, fingerprints tools for rug pulls, and writes JSON audit logs. MIT; early-stage. Distinct from [MCP Guardian (eqtylab)][link_github_com_eqtylab_mcp_guardian] and [mcp-guardian (rudraneel93)][link_github_com_rudraneel93_mcp_guardian]. |

---

## MCP Policy Engines

| Tool & resources | Category — Use for MCP |
| --- | --- |
| **[Agent Wall][link_github_com_agent_wall_agent_wall]** | YAML policy on MCP traffic — Local/proxy tool + response enforcement; workstations, early governance. |
| **[Lasso MCP Gateway][link_github_com_lasso_security_mcp_gateway]** | Gateway policy & sanitization — Centralized policy, lifecycle, sensitive data; enterprise control point. |
| **[MCP Action Firewall][link_github_com_starskrime_mcp_action_firewall]** | Approval-based policy — Human confirmation for dangerous actions when allow/deny isn’t enough. |
| **[mcp-firewall][link_github_com_behrensd_mcp_firewall]** | YAML deny/allow on MCP traffic — Deterministic local proxy; secret-leak scanning built in. |
| **[mcp-guardian][link_github_com_rudraneel93_mcp_guardian]** | RBAC + YAML policy — OAuth/OIDC, STRIDE-aligned governance proxy. |
| **[sint-protocol][link_github_com_sint_ai_sint_protocol]** | Capability-token policy — Approval tiers and preflight `sint-scan` audits. |
| **[shield (AperionAI)][link_github_com_aperionai_shield]** | TOFU pinning policy — Blocks rug-pull tool-definition drift at the proxy. |
| **[Invariant Guardrails][link_github_com_invariantlabs_ai_invariant]** | Rule-based guardrails — Python-inspired policy language on MCP/LLM tool calls and responses; use via gateway or programmatic API. |
| **[MCP Guardian (eqtylab)][link_github_com_eqtylab_mcp_guardian]** | Human-approval policy — Per-tool-call approve/deny at the proxy; pairs with message logging for audit. |
| **[MCP Hangar][link_github_com_mcp_hangar_mcp_hangar]** | Deterministic policy gateway — Tool/argument policy, schema pinning, RBAC, approvals, and SIEM/OTLP audit export; MIT; early-stage. |
| **[MCP Visor][link_github_com_themayursinha_mcp_visor]** | Fail-closed policy proxy — Argument rules, approval, redaction, session taint, read-to-exfiltrate chain detection, and hash-linked audit logs; MIT; early-stage. |
| **[Deconvolute][link_github_com_deconvolute_labs_deconvolute]** | Client-side MCP firewall — CEL argument policies, default-deny enforcement, tool-definition hash baselines, origin validation, and JSONL audit; Apache 2.0. |
| **[MCP Zero Trust Layer (MCPZT)][link_github_com_686f6c61_mcp_zero_trust_layer]** | HTTP/stdio policy layer — Parameter controls, approvals, output redaction, tool-drift detection, hash-chained audit logs, and Prometheus metrics; Apache 2.0; early-stage. |
| **[PortcullisMCP][link_github_com_paclabsnet_portcullismcp]** | Identity-aware MCP policy gateway — Per-call authorization, policy-driven human escalation, OIDC/mTLS identity handling, argument-bound approval tokens, and centralized audit logs; Apache 2.0; early-stage. |
| **[ToolHive][link_github_com_stacklok_toolhive]** | Cedar authorization — Default deny in front of containerized MCP servers after OIDC authentication. |
| **[Kuadrant MCP Gateway][link_github_com_kuadrant_mcp_gateway]** | CEL AuthPolicy — Per-tool and per-prompt authorization, rate limits, and token exchange on an Envoy gateway. |
| **[GreenGateway][link_github_com_greenhat_security_greengateway]** | RBAC and firewall rules — JWT/OIDC, shadow mode, and egress controls for API and MCP traffic. |
| **[mcp-firewall (ressl)][link_github_com_ressl_mcp_firewall]** | YAML and per-agent RBAC — Injection, chain, and SSRF checks with human approval. Distinct from [behrensd/mcp-firewall][link_github_com_behrensd_mcp_firewall]. |
| **[Agent Governance Toolkit][link_github_com_microsoft_agent_governance_toolkit]** | Deterministic MCP policy — Scan evidence, drift checks, and gateway enforcement in one MIT toolkit. |
| **[Warden][link_github_com_parveshsaini_warden]** | YAML policy and approval gates — Quarantines poisoned tool definitions at the gateway. |
| **[ShieldMCP][link_github_com_saurabh_yergattikar_shieldmcp]** | Metadata, argument, and response checks — Schema pinning with heuristic or local-model detectors. |
| **[SentinelMCP (Technosive)][link_github_com_technosiveuk_ui_sentinelmcp]** | YAML risk policy — Allow, redact, block, or interrupt, with secret and PII redaction. |
| **[Flint][link_github_com_tejaaswini_flint]** | Default-deny RBAC — Explicit deny rules override allows on stdio tool calls. |
| **[vex-mcp][link_github_com_mdombrov_33_vex_mcp]** | Definition-drift policy — Blocks injection and hidden Unicode in tool schemas. |
| **[mcpfw][link_github_com_kphatak001_mcpfw]** | YAML call and session policy — Blocks tool-description changes after the first `tools/list`. |
| **[Project Sentinel][link_github_com_sentinel_atl_project_sentinel]** | Certificate gate — Routes MCP traffic only when the trust certificate passes. |
| **[MCP Guardian (PawelKozy)][link_github_com_pawelkozy_mcp_guardian]** | Allow/block policy — Argument conditions and rug-pull fingerprinting at the proxy. |

---

## Secrets and Dependency Scanners

| Tool & resources | Category — Use for MCP |
| --- | --- |
| **[Gitleaks][link_github_com_gitleaks_gitleaks]** | Secrets scanner — Keys/tokens in MCP repos, configs, examples, history; CI, pre-commit, `.env`, `mcp.json`, OAuth tokens, etc. |
| **[Trivy][link_trivy_dev]** | Vuln, misconfig, secret, SBOM, container, K8s, IaC — MCP containers, repos, K8s, cloud deployments; CI/CD, registries, platform eng. |
| **pip-audit, npm audit, OSV-Scanner** ([PyPA][link_pypa_io_pip_audit], [npm][link_docs_npmjs_com_cli_audit], [Google OSV][link_google_github_io_osv_scanner]) | Language/package scanners — Deps in Python/Node/Go/Java/Rust/container MCP servers; per-language CI; general OSS scanners, not MCP-native. |

---

## Red Teaming Tools

| Tool & resources | Category — Use for MCP | Attack vectors / notes |
| --- | --- | --- |
| **[Promptfoo MCP red team plugin][link_promptfoo_dev_docs_red_team_plugins_mcp]** | MCP red teaming — Function-call exploits, manipulation, prompt leakage, unauthorized discovery | Discovery, param injection, excessive calls, metadata injection, etc.; CI-style automation |
| **[Promptfoo][link_github_com_promptfoo_promptfoo]** | LLM eval & red team — Prompt injection, exfiltration, RAG, RBAC, BOLA/BFLA, SSRF, SQLi, tool boundaries | Regression tests for agents/guardrails |
| **[garak][link_github_com_nvidia_garak]** (NVIDIA) | LLM vuln scanner — Model/dialog layer around MCP workflows | Combine with MCP-specific tools |
| **[PyRIT][link_github_com_microsoft_pyrit]** (Microsoft) | AI red-team automation — Multi-turn adversarial scenarios, tool safety, chained workflows | Research, structured campaigns |
| **[mcp-ethical-hacking][link_github_com_cmpxchg16_mcp_ethical_hacking]** | Educational MCP examples — “Legitimate” social/analysis demos illustrating abuse potential | **Authorized use only**; respect platform ToS; lab isolation |
| **[Invariant MCP injection experiments][link_github_com_invariantlabs_ai_mcp_injection_experiments]** | Reproducible MCP attack samples — Tool poisoning, shadowing, and related PoCs for research and detection validation | Pair with scanners; lab isolation only |
| **[mcpnuke][link_github_com_babywyrm_mcpnuke]** | Active MCP security testing — Metadata analysis and behavioral probing over HTTP, SSE, stdio, and Kubernetes | Injection, SSRF, exfiltration, and attack-chain checks; **authorized labs only** |
| **[batesian][link_github_com_calbebop_batesian]** | MCP/A2A protocol security testing — Sends adversarial protocol traffic; 21 MCP-specific rules and SARIF output | OAuth audience/scope, sessions, callbacks, and authorization boundaries; **authorized use only** |
| **[mcpwn][link_github_com_d0rs4n_mcpwn]** | MCP reconnaissance and interaction CLI — Stdio/HTTP/SSE sessions, proxy support, and sqlmap-ready tool-call request generation | Offensive testing utility; **authorized labs only**. Distinct from [mcpwn (ressl)][link_github_com_ressl_mcpwn] |
| **[mcpwn (ressl)][link_github_com_ressl_mcpwn]** | Pre-deployment vulnerability scanner — Active checks for servers you are allowed to test; companion to [mcp-firewall (ressl)][link_github_com_ressl_mcp_firewall] | Prompt injection, tool poisoning, exfiltration, SSRF, command injection, and exposed secrets; AGPL-3.0; **authorized targets only** |
| **[mcp-redteam][link_github_com_aah20_mcp_redteam]** | Live MCP scenario tester — Incident-derived security checks | Rug pulls, destructive-tool annotations, unauthenticated exposure, token audiences, and tool-call authorization bypass; **authorized use only** |
| **[MCP Server Fuzzer][link_github_com_mcp_runtime_mcp_server_fuzzer]** | Schema-driven MCP protocol fuzzer over stdio, HTTP, SSE, and Streamable HTTP | Reproducible, severity-rated request/response evidence; **authorized targets only** |
| **[Vulnerable MCP Servers Lab][link_github_com_appsecco_vulnerable_mcp_servers_lab]** | Deliberately vulnerable local and remote MCP servers for defensive validation | Prompt injection, malicious tools, code execution, filesystem abuse, typosquatting, vulnerable dependencies, and secrets exposure; **isolated labs only** |
| **[MCP Attack Labs][link_github_com_aminrj_labs_mcp_attack_labs]** | Reproducible MCP exploit-and-defense labs | Tool poisoning, shadowing, cross-server abuse, and MCP-to-A2A kill chains with locally testable controls; **authorized labs only** |
| **[MCP Gauntlet][link_github_com_studiomeyer_io_mcp_gauntlet]** | Schema-aware MCP fuzzing and load testing | Hostile/boundary tool inputs, crash/hang/validation-gap detection, SARIF, and CI performance gates; **authorized targets only** |

---

## Open-source observability

Open-source stacks for MCP audit telemetry, tool-call tracing, and security-adjacent log analytics. Pair with [OpenTelemetry MCP semantic conventions](#runtime-monitoring-tools) when instrumenting MCP servers.

| Tool | Summary |
| --- | --- |
| [OpenTelemetry Collector][link_opentelemetry_collector] | Vendor-neutral pipeline to receive, process, and export traces, metrics, and logs for unified observability. |
| [Grafana OSS stack][link_grafana_oss] | Dashboards and visualization; pair with [Tempo][link_grafana_tempo], [Loki][link_grafana_loki], and [Prometheus][link_prometheus] for full-stack observability. |
| [OpenSearch Security Analytics][link_opensearch_security_analytics] | Security Analytics plugin for OpenSearch; threat detection and correlating security findings. |
| [Graylog Open][link_graylog] | Open-source log management for aggregation, alerting, and dashboards (distinct from Graylog Enterprise). |
| [mcp-otel][link_github_com_studiomeyer_io_mcp_otel] | MCP-native SEP-414 bridge that propagates W3C trace context through `_meta` and emits connected OpenTelemetry spans across hosts, servers, tools, and downstream calls. |
| [MCP Trace][link_github_com_ryux1_mcp_trace] | Security-first MCP observability gateway with sanitized recording/replay, Prometheus metrics, OpenTelemetry spans, trace propagation, and protocol/header mismatch detection. |


[link_github_com_agentity_com_mcp_audit_extension]: https://github.com/Agentity-com/mcp-audit-extension
[link_github_com_82ch_mcp_dandan]: https://github.com/82ch/MCP-Dandan
[link_github_com_armorerlabs_armorer_guard]: https://github.com/ArmorerLabs/Armorer-Guard
[link_github_com_cmpxchg16_mcp_ethical_hacking]: https://github.com/cmpxchg16/mcp-ethical-hacking
[link_github_com_kapilduraphe_mcp_watch]: https://github.com/kapilduraphe/mcp-watch
[link_github_com_lazymac2x_mcpwatch]: https://github.com/lazymac2x/mcpwatch
[link_github_com_makalin_securemcp]: https://github.com/makalin/SecureMCP
[link_github_com_mcp_defender_mcp_defender]: https://github.com/MCP-Defender/MCP-Defender
[link_github_com_slowmist_mcp_security_checklist]: https://github.com/slowmist/MCP-Security-Checklist
[link_github_com_tencent_ai_infra_guard]: https://github.com/Tencent/AI-Infra-Guard
[link_github_com_trailofbits_mcp_context_protector]: https://github.com/trailofbits/mcp-context-protector
[link_invariantlabs_ai_blog_introducing_mcp_scan]: https://invariantlabs.ai/blog/introducing-mcp-scan
[link_marketplace_visualstudio_com_agentity_mcp_audit_extension]: https://marketplace.visualstudio.com/items?itemName=Agentity.mcp-audit-extension
[link_github_com_adudley78_mcp_audit]: https://github.com/adudley78/mcp-audit
[link_github_com_agent_wall_agent_wall]: https://github.com/agent-wall/agent-wall
[link_github_com_antgroup_mcp_security]: https://github.com/antgroup/MCP-Security
[link_github_com_appiumtestdistribution_secure_hulk]: https://github.com/AppiumTestDistribution/secure-hulk
[link_github_com_cisco_ai_defense_mcp_scanner]: https://github.com/cisco-ai-defense/mcp-scanner
[link_github_com_gensecaihq_mcpscc]: https://github.com/gensecaihq/mcpscc
[link_github_com_gitleaks_gitleaks]: https://github.com/gitleaks/gitleaks
[link_github_com_invariantlabs_ai_invariant]: https://github.com/invariantlabs-ai/invariant
[link_github_com_invariantlabs_ai_mcp_injection_experiments]: https://github.com/invariantlabs-ai/mcp-injection-experiments
[link_github_com_lasso_security_mcp_gateway]: https://github.com/lasso-security/mcp-gateway
[link_github_com_leidosinc_mcpsafetyscanner]: https://github.com/leidosinc/McpSafetyScanner
[link_github_com_microsoft_pyrit]: https://github.com/microsoft/PyRIT
[link_github_com_modelcontextprotocol_inspector]: https://github.com/modelcontextprotocol/inspector
[link_github_com_modelcontextprotocol_security_mcpserver_audit]: https://github.com/ModelContextProtocol-Security/mcpserver-audit
[link_github_com_nvidia_garak]: https://github.com/NVIDIA/garak
[link_github_com_promptfoo_promptfoo]: https://github.com/promptfoo/promptfoo
[link_github_com_semgrep_semgrep]: https://github.com/semgrep/semgrep
[link_github_com_snyk_agent_scan]: https://github.com/snyk/agent-scan
[link_github_com_starskrime_mcp_action_firewall]: https://github.com/starskrime/mcp-action-firewall
[link_github_com_wapiti08_mcp_sandboxscan]: https://github.com/Wapiti08/MCP-SandboxScan
[link_grafana_com_blog_ai_observability_mcp_servers]: https://grafana.com/blog/ai-observability-MCP-servers/
[link_modelcontextprotocol_io_docs_tools_inspector]: https://modelcontextprotocol.io/docs/tools/inspector
[link_opentelemetry_io_docs_specs_semconv_gen_ai_mcp]: https://opentelemetry.io/docs/specs/semconv/gen-ai/mcp/
[link_promptfoo_dev_docs_red_team_plugins_mcp]: https://www.promptfoo.dev/docs/red-team/plugins/mcp/
[link_semgrep_dev_products_semgrep_supply_chain]: https://semgrep.dev/products/semgrep-supply-chain
[link_trivy_dev]: https://trivy.dev/
[link_pypa_io_pip_audit]: https://pypi.org/project/pip-audit/
[link_docs_npmjs_com_cli_audit]: https://docs.npmjs.com/cli/v10/commands/npm-audit
[link_google_github_io_osv_scanner]: https://google.github.io/osv-scanner/

<!-- Open-source observability links -->
[link_graylog]: https://graylog.org/products/open-source
[link_opensearch_security_analytics]: https://docs.opensearch.org/docs/latest/security-analytics/
[link_opentelemetry_collector]: https://opentelemetry.io/docs/collector/
[link_grafana_oss]: https://grafana.com/oss/
[link_grafana_tempo]: https://grafana.com/oss/tempo/
[link_grafana_loki]: https://grafana.com/oss/loki/
[link_prometheus]: https://prometheus.io/
[link_github_com_arpitha_dhanapathi_pluto_aguard]: https://github.com/arpitha-dhanapathi/pluto-aguard
[link_github_com_aperionai_shield]: https://github.com/AperionAI/shield
[link_github_com_badchars_mcp_security_scanner]: https://github.com/badchars/mcp-security-scanner
[link_github_com_bebravebekind_mcpskills_server]: https://github.com/BeBraveBeKind/mcpskills-server
[link_github_com_daoyuanli2816_mcp_fence]: https://github.com/DaoyuanLi2816/mcp-fence
[link_github_com_eltociear_skill_audit_mcp]: https://github.com/eltociear/skill-audit-mcp
[link_github_com_eqtylab_mcp_guardian]: https://github.com/eqtylab/mcp-guardian
[link_github_com_behrensd_mcp_firewall]: https://github.com/behrensd/mcp-firewall
[link_github_com_inkog_io_inkog_mcp]: https://github.com/inkog-io/inkog-mcp
[link_github_com_joergmichno_clawguard]: https://github.com/joergmichno/clawguard
[link_github_com_luckypipewrench_pipelock]: https://github.com/luckyPipewrench/pipelock
[link_github_com_manthanghasadiya_mcpsec]: https://github.com/manthanghasadiya/mcpsec
[link_github_com_mcp_audit_mcts]: https://github.com/MCP-Audit/MCTS
[link_github_com_mcp_shark_mcpsec]: https://github.com/mcp-shark/mcpsec
[link_github_com_mcpshield_mcpshield]: https://github.com/mcpshield/mcpshield
[link_github_com_microsoft_mcp_azure_security_guide]: https://github.com/microsoft/mcp-azure-security-guide
[link_github_com_msaad00_agent_bom]: https://github.com/msaad00/agent-bom
[link_github_com_nik1097_mcp_swiss_knife]: https://github.com/nik1097/mcp-swiss-knife
[link_github_com_nova_hunting_nova_proximity]: https://github.com/Nova-Hunting/nova-proximity
[link_github_com_piiiico_mcpaudit]: https://github.com/piiiico/mcpaudit
[link_github_com_policylayer_intercept]: https://github.com/PolicyLayer/Intercept
[link_github_com_rudraneel93_mcp_guardian]: https://github.com/rudraneel93/mcp-guardian
[link_github_com_sahiloj_mcpscan]: https://github.com/sahiloj/MCPScan
[link_github_com_sentinel_gate_sentinelgate]: https://github.com/Sentinel-Gate/Sentinelgate
[link_github_com_sint_ai_sint_protocol]: https://github.com/sint-ai/sint-protocol
[link_github_com_tayler_id_mcphound]: https://github.com/tayler-id/mcphound
[link_github_com_thezenmonster_agentscore_mcp_server]: https://github.com/Thezenmonster/agentscore-mcp-server
[link_github_com_willianpinho_mcp_gateway_scan]: https://github.com/willianpinho/mcp-gateway-scan
[link_github_com_xlyoung_mcp_doctor]: https://github.com/xlyoung/mcp-doctor
[link_github_com_loplop_h_mcpguard]: https://github.com/loplop-h/mcpguard
[link_github_com_muhannad_hash_mcp_shield]: https://github.com/muhannad-hash/mcp-shield
[link_github_com_nbosa_mcpguard]: https://github.com/nbosa/mcpguard
[link_github_com_ardakocadoruu_mcpguard]: https://github.com/ardakocadoruu/mcpguard
[link_github_com_rohitguta2432_mcpguard]: https://github.com/rohitguta2432/mcpguard
[link_github_com_sovereign_shovels_mcp_audit]: https://github.com/sovereign-shovels/mcp-audit
[link_github_com_smart_mcp_proxy_mcpproxy_go]: https://github.com/smart-mcp-proxy/mcpproxy-go
[link_invariantlabs_ai_github_io_docs_mcp_scan]: https://invariantlabs-ai.github.io/docs/mcp-scan/
[link_microsoft_github_io_mcp_azure_security_guide]: https://microsoft.github.io/mcp-azure-security-guide/
[link_owasp_org_www_project_mcp_top_10]: https://owasp.org/www-project-mcp-top-10/
[link_github_com_syedanas01_mcp_safeguard]: https://github.com/SyedAnas01/mcp-safeguard
[link_github_com_sidhpurwala_huzaifa_mcp_security_scanner]: https://github.com/sidhpurwala-huzaifa/mcp-security-scanner
[link_github_com_pfrederiksen_mcpsec]: https://github.com/pfrederiksen/mcpsec
[link_github_com_finktech_dev_mcp_verify]: https://github.com/finktech-dev/mcp-verify
[link_github_com_perparimmjeku_mcp_auditor]: https://github.com/perparimmjeku/mcp-auditor
[link_github_com_agentpostmortem_mcp_audit]: https://github.com/AgentPostmortem/MCP-audit
[link_github_com_babywyrm_mcpnuke]: https://github.com/babywyrm/mcpnuke
[link_github_com_calbebop_batesian]: https://github.com/calbebop/batesian
[link_github_com_d0rs4n_mcpwn]: https://github.com/D0rs4n/mcpwn
[link_github_com_aah20_mcp_redteam]: https://github.com/AAH20/mcp-redteam
[link_github_com_mcp_hangar_mcp_hangar]: https://github.com/mcp-hangar/mcp-hangar
[link_github_com_themayursinha_mcp_visor]: https://github.com/themayursinha/mcp-visor
[link_github_com_maksym_mishchenko_mcpgate]: https://github.com/maksym-mishchenko/mcpgate
[link_github_com_deconvolute_labs_deconvolute]: https://github.com/deconvolute-labs/deconvolute
[link_github_com_686f6c61_mcp_zero_trust_layer]: https://github.com/686f6c61/mcp-zero-trust-layer
[link_github_com_tkingovr_agent_guard]: https://github.com/tkingovr/agent-guard
[link_github_com_keith_aykira_mcp_zero_trust_proxy]: https://github.com/keith-aykira/mcp-zero-trust-proxy
[link_github_com_mcp_security_standard_mcp_server_security_standard]: https://github.com/mcp-security-standard/mcp-server-security-standard
[link_modelcontextprotocol_io_security_best_practices]: https://modelcontextprotocol.io/docs/2026-07-28/tutorials/security/security_best_practices
[link_github_com_highflame_ai_ramparts]: https://github.com/highflame-ai/ramparts
[link_github_com_apisec_inc_mcp_audit]: https://github.com/apisec-inc/mcp-audit
[link_github_com_web3wikis_toolpoison]: https://github.com/web3wikis/toolpoison
[link_github_com_stevemonsway_mcp_trust]: https://github.com/SteveMonsway/mcp-trust
[link_github_com_soufianetahiri_mception]: https://github.com/soufianetahiri/mception
[link_github_com_iamakash_06_mcpeek]: https://github.com/iamakash-06/MCPeek
[link_github_com_fayzkk889_mcpsense]: https://github.com/fayzkk889/MCPSense
[link_github_com_traceforce_mcp_xray]: https://github.com/traceforce/mcp-xray
[link_github_com_appsecco_pentesting_mcp_servers_checklist]: https://github.com/appsecco/pentesting-mcp-servers-checklist
[link_github_com_agentgateway_agentgateway]: https://github.com/agentgateway/agentgateway
[link_github_com_preloop_preloop]: https://github.com/preloop/preloop
[link_github_com_yjcho9317_mcp_fence]: https://github.com/yjcho9317/mcp-fence
[link_github_com_provnai_mcpvanguard]: https://github.com/provnai/McpVanguard
[link_github_com_hoophq_mcpproxy]: https://github.com/hoophq/mcpproxy
[link_github_com_p4st4s_mcp_audit]: https://github.com/P4ST4S/mcp-audit
[link_github_com_bluerock_io_bluerock]: https://github.com/bluerock-io/bluerock
[link_github_com_paclabsnet_portcullismcp]: https://github.com/paclabsnet/PortcullisMCP
[link_github_com_mcp_runtime_mcp_server_fuzzer]: https://github.com/mcp-runtime/mcp-server-fuzzer
[link_github_com_appsecco_vulnerable_mcp_servers_lab]: https://github.com/appsecco/vulnerable-mcp-servers-lab
[link_github_com_aminrj_labs_mcp_attack_labs]: https://github.com/aminrj-labs/mcp-attack-labs
[link_github_com_studiomeyer_io_mcp_gauntlet]: https://github.com/studiomeyer-io/mcp-gauntlet
[link_github_com_studiomeyer_io_mcp_otel]: https://github.com/studiomeyer-io/mcp-otel
[link_github_com_ryux1_mcp_trace]: https://github.com/ryux1/mcp-trace
[link_github_com_yatuk_mcpradar]: https://github.com/yatuk/mcpradar
[link_github_com_microsoft_agent_governance_toolkit]: https://github.com/microsoft/agent-governance-toolkit
[link_microsoft_github_io_agt_mcp_scan]: https://microsoft.github.io/agent-governance-toolkit/tutorials/27-mcp-scan-cli/
[link_github_com_cisco_ai_defense_defenseclaw]: https://github.com/cisco-ai-defense/defenseclaw
[link_github_com_garagon_aguara]: https://github.com/garagon/aguara
[link_github_com_sattyamjjain_agent_audit_kit]: https://github.com/sattyamjjain/agent-audit-kit
[link_github_com_affaan_m_agentshield]: https://github.com/affaan-m/agentshield
[link_github_com_nvidia_skillspector]: https://github.com/NVIDIA/SkillSpector
[link_github_com_sinewaveai_agent_security_scanner_mcp]: https://github.com/sinewaveai/agent-security-scanner-mcp
[link_github_com_aak204_mcp_scorecard]: https://github.com/aak204/MCP-Scorecard
[link_github_com_niraven_mcp_gateway]: https://github.com/Niraven/mcp-gateway
[link_github_com_roshan6335_mcpsentry]: https://github.com/Roshan6335/mcpsentry
[link_github_com_sentinel_atl_project_sentinel]: https://github.com/sentinel-atl/project-sentinel
[link_github_com_ressl_mcpwn]: https://github.com/ressl/mcpwn
[link_github_com_gt_projects256_mcpguard]: https://github.com/GT-Projects256/mcpguard
[link_owasp_mcp_security_cheat_sheet]: https://cheatsheetseries.owasp.org/cheatsheets/MCP_Security_Cheat_Sheet.html
[link_github_com_owasp_mcp_security_testing_guide]: https://github.com/OWASP/MCP-Security-Testing-Guide
[link_github_com_mcp_manager_mcp_checklists]: https://github.com/MCP-Manager/MCP-Checklists
[link_github_com_stacklok_toolhive]: https://github.com/stacklok/toolhive
[link_github_com_kuadrant_mcp_gateway]: https://github.com/Kuadrant/mcp-gateway
[link_github_com_greenhat_security_greengateway]: https://github.com/Greenhat-Security/GreenGateway
[link_github_com_ressl_mcp_firewall]: https://github.com/ressl/mcp-firewall
[link_github_com_hashgraph_online_hol_guard]: https://github.com/hashgraph-online/hol-guard
[link_github_com_parveshsaini_warden]: https://github.com/parveshsaini/warden
[link_github_com_saurabh_yergattikar_shieldmcp]: https://github.com/saurabh-yergattikar/ShieldMCP
[link_github_com_technosiveuk_ui_sentinelmcp]: https://github.com/technosiveuk-ui/SentinelMCP
[link_github_com_tejaaswini_flint]: https://github.com/Tejaaswini/flint
[link_github_com_mdombrov_33_vex_mcp]: https://github.com/mdombrov-33/vex-mcp
[link_github_com_kphatak001_mcpfw]: https://github.com/kphatak001/mcpfw
[link_github_com_pawelkozy_mcp_guardian]: https://github.com/PawelKozy/mcp-guardian
[link_github_com_ashadow07_karmadue]: https://github.com/ashadow07/karmadue
