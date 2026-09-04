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
| **mcpguard** (four unrelated projects — pick by maintainer) — [loplop-h/mcpguard][link_github_com_loplop_h_mcpguard] (OWASP MCP Top 10 mapping, auto-fix, rug-pull alerts); [nbosa/mcpguard][link_github_com_nbosa_mcpguard] (Go scanner + stdio guard proxy, SARIF, entropy secret detection); [ardakocadoruu/mcpguard][link_github_com_ardakocadoruu_mcpguard] (Python npm-package static scanner, typosquat DB); [rohitguta2432/mcpguard][link_github_com_rohitguta2432_mcpguard] (deterministic manifest scanner, CI exit codes, eval suite). |
| **[mcp-shield][link_github_com_muhannad_hash_mcp_shield]** (npm `@muhannad-hash/mcp-shield`) | Pre-install npm/local MCP scanner — Exfiltration, code execution, obfuscation, prompt injection, supply-chain trust scoring; MCP server mode with `scan_package` / `scan_directory`; MIT. **Not** [MCPShield (mcpshield)][link_github_com_mcpshield_mcpshield] or other unrelated “MCP Shield” repos. |

---

## Guidance and checklists

| Resource | Category — Use for MCP |
| --- | --- |
| **[MCP Security Checklist (SlowMist)][link_github_com_slowmist_mcp_security_checklist]** | Community checklist — Design, deployment, and operations review items for MCP and agent integrations (process aid, not an automated scanner). |
| **[OWASP MCP Top 10][link_owasp_org_www_project_mcp_top_10]** | Community risk taxonomy — Ten MCP-specific risk categories (token mismanagement, tool poisoning, shadow servers, context oversharing, etc.); use to map scanner findings and control gaps. |
| **[MCP Azure Security Guide][link_github_com_microsoft_mcp_azure_security_guide]** ([published guide][link_microsoft_github_io_mcp_azure_security_guide]) | OSS reference — Maps each OWASP MCP Top 10 risk to Azure mitigations (Entra ID, managed identities, APIM, Key Vault, network isolation). |
| **[Invariant Guardrails docs][link_invariantlabs_ai_github_io_docs_mcp_scan]** ([Guardrails repo][link_github_com_invariantlabs_ai_invariant]) | Rule-based guardrails for MCP/LLM proxies — Tool-call restrictions, PII/secrets detection, custom policies; pairs with Snyk Agent Scan lineage and `mcp-scan proxy` runtime mode. |

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
| **[Bifrost][link_github_com_maximhq_bifrost]** | AI gateway — MCP support, request routing, guardrails, rate limits, access controls, and telemetry for governed model traffic. |
| **[shield (AperionAI)][link_github_com_aperionai_shield]** | Local guardrail proxy — TOFU tool-catalog pinning and rug-pull detection; wraps stdio or Streamable HTTP upstream servers. |
| **[sint-protocol][link_github_com_sint_ai_sint_protocol]** | Governance proxy + `sint-scan` CLI — Preflight tool-risk audits, capability tokens, approval tiers, tamper-evident receipts; Apache 2.0. |
| **[mcp-firewall][link_github_com_behrensd_mcp_firewall]** | Deterministic policy proxy — YAML policies (“iptables for MCP”), secret-leak scanning, no cloud dependency. |
| **[mcp-guardian][link_github_com_rudraneel93_mcp_guardian]** | Governance proxy — YAML policy, OAuth/OIDC RBAC, STRIDE threat model; distinct from [MCP Guardian (eqtylab)][link_github_com_eqtylab_mcp_guardian]. |
| **[PolicyLayer Intercept][link_github_com_policylayer_intercept]** | MCP proxy with YAML policies — Rate limits, validation, audit trail at the transport boundary. |
| **[Sentinelgate][link_github_com_sentinel_gate_sentinelgate]** | MCP proxy — CEL policies, RBAC, audit trail for governed deployments. |
| **[MCP Guardian (eqtylab)][link_github_com_eqtylab_mcp_guardian]** | Human-approval MCP proxy — Real-time approve/deny for tool calls, message logging, multi-config management; Apache 2.0. Distinct from [mcp-guardian (rudraneel93)][link_github_com_rudraneel93_mcp_guardian]. |
| **[MCPProxy Go][link_github_com_smart_mcp_proxy_mcpproxy_go]** | Local MCP proxy + dashboard — Security quarantine for new servers (TPA mitigation), BM25 tool discovery, Docker-isolated upstreams, sensitive-data detection in tool calls, full audit log; MIT. |

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

---

## Open-source observability

Open-source stacks for MCP audit telemetry, tool-call tracing, and security-adjacent log analytics. Pair with [OpenTelemetry MCP semantic conventions](#runtime-monitoring-tools) when instrumenting MCP servers.

| Tool | Summary |
| --- | --- |
| [OpenTelemetry Collector][link_opentelemetry_collector] | Vendor-neutral pipeline to receive, process, and export traces, metrics, and logs for unified observability. |
| [Grafana OSS stack][link_grafana_oss] | Dashboards and visualization; pair with [Tempo][link_grafana_tempo], [Loki][link_grafana_loki], and [Prometheus][link_prometheus] for full-stack observability. |
| [OpenSearch Security Analytics][link_opensearch_security_analytics] | Security Analytics plugin for OpenSearch; threat detection and correlating security findings. |
| [Graylog Open][link_graylog] | Open-source log management for aggregation, alerting, and dashboards (distinct from Graylog Enterprise). |


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
[link_github_com_maximhq_bifrost]: https://github.com/maximhq/bifrost
