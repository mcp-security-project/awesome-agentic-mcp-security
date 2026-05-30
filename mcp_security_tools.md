# MCP Security Tools

For MCP servers that expose **external security products** (Semgrep, Burp, Shodan, cloud IAM, identity platforms, trust scores, and similar), see [MCP security servers and integrations](mcp_security_servers_and_integrations.md). This page focuses on **MCP-aware scanners, gateways, and general AppSec utilities** that harden or observe MCP and agent workflows.

## Contents

- [MCP Scanners](#mcp-scanners)
- [Guidance and checklists](#guidance-and-checklists)
- [Runtime Monitoring Tools](#runtime-monitoring-tools)
- [MCP Policy Engines](#mcp-policy-engines)
- [Secrets and Dependency Scanners](#secrets-and-dependency-scanners)
- [Red Teaming Tools](#red-teaming-tools)
- [Blue Team and SOC Tools](#blue-team-and-soc-tools)
  - [SIEM and detection platforms](#siem-and-detection-platforms)
  - [Observability platforms](#observability-platforms)
  - [Representative EDR platforms](#representative-edr-platforms)

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
| **[MCP Server Scanner][link_mcpserverscanner_com]** | Web/SaaS-oriented MCP server discovery or assessment (verify methodology, data handling, and jurisdiction before uploading manifests). |
| **[MCPScan.ai][link_mcpscan_ai]** | Web scanner / assessment surface for MCP configs or servers (review terms, telemetry, and what leaves your network). |
| **[Ant Group MCP-Security][link_github_com_antgroup_mcp_security]** | Static + dynamic MCP scanner — Auditing agent tools / plugins; **detects** malicious metadata (prompt injection), insecure tools, unsafe reads, code vulns. Semgrep-style taint + dynamic LLM eval; local or remote GitHub repos. |
| **[MCPServer Audit][link_github_com_modelcontextprotocol_security_mcpserver_audit]** | MCP server audit — Pre-use safety checks; publishing to audit/DB; output per audit workflow. Community initiative — verify maturity / evidence format. |
| **[MCPSafetyScanner][link_github_com_leidosinc_mcpsafetyscanner]** | Agentic MCP safety auditor — Adversarial samples from tools/resources; safety reports; **detects** unsafe tools, malicious execution, credential theft, unauthorized access. Research / academic; **safety:** isolated test env only. |
| **[MCP-SandboxScan][link_github_com_wapiti08_mcp_sandboxscan]** | Runtime / sandbox analysis — Execute untrusted tools in WASM/WASI-style sandbox; **detects** env/file→prompt, filesystem violations, runtime-only issues. Research / experimental; advanced research & high-risk tool review. |
| **[MCP Inspector][link_github_com_modelcontextprotocol_inspector]** ([documentation][link_modelcontextprotocol_io_docs_tools_inspector]) | Dev test/debug (not a security scanner) — Manual inspection of servers, tools, prompts, resources, transport; observational only (no automated detection). For security review: validate tools/schemas before approval; **not** a replacement for automated scanning. |

---

## Guidance and checklists

| Resource | Category — Use for MCP |
| --- | --- |
| **[MCP Security Checklist (SlowMist)][link_github_com_slowmist_mcp_security_checklist]** | Community checklist — Design, deployment, and operations review items for MCP and agent integrations (process aid, not an automated scanner). |

---

## Runtime Monitoring Tools

| Tool & resources | Category — Summary |
| --- | --- |
| **[Lasso MCP Gateway][link_github_com_lasso_security_mcp_gateway]** | MCP gateway — Centralize lifecycle, intercept, sanitize, scan before load; single control point for many servers. Enterprise / governed connections. |
| **[Agent Wall][link_github_com_agent_wall_agent_wall]** | MCP firewall / policy proxy — YAML policy on tool calls and responses; block dangerous reads, shell, exfiltration, risky chains. Client–server middle; local IDE workflows. |
| **[MCP Action Firewall][link_github_com_starskrime_mcp_action_firewall]** | Human-approval / transparent proxy — OTP approval for dangerous tool calls; circuit breaker for high-impact actions. Demos / local; validate before enterprise. |
| **[OpenTelemetry MCP semantic conventions][link_opentelemetry_io_docs_specs_semconv_gen_ai_mcp]** ([Grafana MCP observability guide][link_grafana_com_blog_ai_observability_mcp_servers]) | Observability / telemetry — Spans, latency, errors, health, audit metadata; baseline and detect abnormal tool patterns. Feeds Grafana, Tempo, Datadog, etc. |
| **Egress proxies & network controls** (Smokescreen-style, corporate proxy, mesh egress, K8s NetworkPolicy) | Network runtime control — Block metadata SSRF, private IPs, paste sites, unexpected APIs; SSRF, exfiltration, untrusted remote fetch. Treat MCP servers as user-acting code; minimal explicit egress. |
| **[mcp-context-protector][link_github_com_trailofbits_mcp_context_protector]** (Trail of Bits) | MCP client wrapper / visibility layer — Surfaces malicious or deceptive server-provided context (e.g. description-driven exfiltration, “line jumping”); complements scanners and policy proxies. |
| **[MCP Audit (VS Code extension)][link_github_com_agentity_com_mcp_audit_extension]** ([Visual Studio Marketplace][link_marketplace_visualstudio_com_agentity_mcp_audit_extension]) | IDE-side audit logging — Intercepts and logs Copilot/MCP tool calls with optional SIEM/syslog forwarders; governance and troubleshooting, not a substitute for server-side controls. |
| **[MCP-Defender][link_github_com_mcp_defender_mcp_defender]** | Desktop proxy — Intercepts MCP traffic from supported clients, signature-style checks, user allow/block prompts; review AGPL terms and update channel before fleet rollout. |
| **[defenter-proxy][link_github_com_defenter_ai_defenter_proxy]** (Defenter) | Semantic policy broker — IDE/agent MCP and file/shell hooks with cloud policy decisions; validate data residency and cloud dependency. |
| **[MCP-Dandan][link_github_com_82ch_mcp_dandan]** | Desktop monitoring — Real-time observation of MCP sessions with Electron UI; tune noise vs. signal for SOC handoff. |

---

## MCP Policy Engines

| Tool & resources | Category — Use for MCP |
| --- | --- |
| **[Agent Wall][link_github_com_agent_wall_agent_wall]** | YAML policy on MCP traffic — Local/proxy tool + response enforcement; workstations, early governance. |
| **[Lasso MCP Gateway][link_github_com_lasso_security_mcp_gateway]** | Gateway policy & sanitization — Centralized policy, lifecycle, sensitive data; enterprise control point. |
| **[MCP Action Firewall][link_github_com_starskrime_mcp_action_firewall]** | Approval-based policy — Human confirmation for dangerous actions when allow/deny isn’t enough. |

---

## Secrets and Dependency Scanners

| Tool & resources | Category — Use for MCP |
| --- | --- |
| **[Gitleaks][link_github_com_gitleaks_gitleaks]** | Secrets scanner — Keys/tokens in MCP repos, configs, examples, history; CI, pre-commit, `.env`, `mcp.json`, OAuth tokens, etc. |
| **[Trivy][link_trivy_dev]** | Vuln, misconfig, secret, SBOM, container, K8s, IaC — MCP containers, repos, K8s, cloud deployments; CI/CD, registries, platform eng. |
| **pip-audit, npm audit, OSV-Scanner, Safety, Dependabot, Snyk Open Source** (various vendors) | Language/package scanners — Deps in Python/Node/Go/Java/Rust/container MCP servers; per-language CI; general scanners, not MCP-native. |

---

## Red Teaming Tools

| Tool & resources | Category — Use for MCP | Attack vectors / notes |
| --- | --- | --- |
| **[Promptfoo MCP red team plugin][link_promptfoo_dev_docs_red_team_plugins_mcp]** | MCP red teaming — Function-call exploits, manipulation, prompt leakage, unauthorized discovery | Discovery, param injection, excessive calls, metadata injection, etc.; CI-style automation |
| **[Promptfoo][link_github_com_promptfoo_promptfoo]** | LLM eval & red team — Prompt injection, exfiltration, RAG, RBAC, BOLA/BFLA, SSRF, SQLi, tool boundaries | Regression tests for agents/guardrails |
| **[garak][link_github_com_nvidia_garak]** (NVIDIA) | LLM vuln scanner — Model/dialog layer around MCP workflows | Combine with MCP-specific tools |
| **[PyRIT][link_github_com_microsoft_pyrit]** (Microsoft) | AI red-team automation — Multi-turn adversarial scenarios, tool safety, chained workflows | Research, structured campaigns |
| **[mcp-ethical-hacking][link_github_com_cmpxchg16_mcp_ethical_hacking]** | Educational MCP examples — “Legitimate” social/analysis demos illustrating abuse potential | **Authorized use only**; respect platform ToS; lab isolation |

---

## Blue Team and SOC Tools

### SIEM and detection platforms

| Tool | Summary |
| --- | --- |
| [Splunk][link_splunk] | Enterprise SIEM for search, correlation, detection content, and SOC investigations across logs and security data. |
| [Elastic Security][link_elastic_security] | SIEM and security analytics on the Elastic Stack; detection rules, case management, and endpoint telemetry integration. |
| [Microsoft Sentinel][link_microsoft_sentinel] | Cloud-native SIEM and SOAR on Azure; scalable ingestion, Microsoft-centric and multi-cloud connectors. |
| [Google Security Operations / Chronicle][link_google_security_operations] | Google’s security analytics platform for threat hunting and detection at cloud scale. |
| [Datadog Cloud SIEM][link_datadog_cloud_siem] | Cloud SIEM with detection rules and correlation on infrastructure and application telemetry. |
| [Sumo Logic][link_sumo_logic] | Cloud SIEM and log analytics for centralized visibility and compliance-oriented retention. |
| [Graylog][link_graylog] | Open-core log management and SIEM capabilities for aggregation, alerting, and dashboards. |
| [OpenSearch Security Analytics][link_opensearch_security_analytics] | Security Analytics plugin for OpenSearch; threat detection and correlating security findings. |

### Observability platforms

| Tool | Summary |
| --- | --- |
| [OpenTelemetry Collector][link_opentelemetry_collector] | Vendor-neutral pipeline to receive, process, and export traces, metrics, and logs for unified observability. |
| [Grafana OSS stack][link_grafana_oss] | Dashboards and visualization; pair with [Tempo][link_grafana_tempo], [Loki][link_grafana_loki], and [Prometheus][link_prometheus] for full-stack observability. |
| [Datadog APM + Cloud SIEM][link_datadog] | Unified monitoring, APM, and security signals for cloud and on-prem workloads. |
| [Elastic Observability][link_elastic_observability] | Full-stack observability on Elastic; APM, logs, metrics, and synthetic checks. |
| [Dynatrace][link_dynatrace] | AIOps-oriented observability with automatic dependency mapping and performance analytics. |
| [New Relic][link_new_relic] | Full-stack observability SaaS with APM, logs, infrastructure, and synthetic monitoring. |

### Representative EDR platforms

| Tool | Summary |
| --- | --- |
| [CrowdStrike Falcon][link_crowdstrike] | Cloud-delivered EDR/XDR with behavioral detection and threat hunting on endpoints. |
| [Microsoft Defender for Endpoint][link_microsoft_defender_endpoint] | Microsoft’s enterprise EDR integrated with Microsoft 365 Defender ecosystem. |
| [SentinelOne Singularity][link_sentinelone] | Autonomous EDR with rollback and storyline visualization for endpoint threats. |
| [VMware Carbon Black][link_carbon_black] | Endpoint protection platform with continuous recording and threat intelligence integrations. |
| [Sophos Intercept X][link_sophos_intercept_x] | Endpoint protection combining anti-exploit, ransomware defense, and EDR capabilities. |


[link_github_com_agentity_com_mcp_audit_extension]: https://github.com/Agentity-com/mcp-audit-extension
[link_github_com_82ch_mcp_dandan]: https://github.com/82ch/MCP-Dandan
[link_github_com_cmpxchg16_mcp_ethical_hacking]: https://github.com/cmpxchg16/mcp-ethical-hacking
[link_github_com_defenter_ai_defenter_proxy]: https://github.com/Defenter-AI/defenter-proxy
[link_github_com_kapilduraphe_mcp_watch]: https://github.com/kapilduraphe/mcp-watch
[link_github_com_lazymac2x_mcpwatch]: https://github.com/lazymac2x/mcpwatch
[link_github_com_makalin_securemcp]: https://github.com/makalin/SecureMCP
[link_github_com_mcp_defender_mcp_defender]: https://github.com/MCP-Defender/MCP-Defender
[link_github_com_slowmist_mcp_security_checklist]: https://github.com/slowmist/MCP-Security-Checklist
[link_github_com_tencent_ai_infra_guard]: https://github.com/Tencent/AI-Infra-Guard
[link_github_com_trailofbits_mcp_context_protector]: https://github.com/trailofbits/mcp-context-protector
[link_invariantlabs_ai_blog_introducing_mcp_scan]: https://invariantlabs.ai/blog/introducing-mcp-scan
[link_marketplace_visualstudio_com_agentity_mcp_audit_extension]: https://marketplace.visualstudio.com/items?itemName=Agentity.mcp-audit-extension
[link_mcpscan_ai]: https://mcpscan.ai/
[link_mcpserverscanner_com]: https://mcpserverscanner.com/
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

<!-- Blue Team / SOC platform links -->
[link_splunk]: https://www.splunk.com/
[link_elastic_security]: https://www.elastic.co/security
[link_microsoft_sentinel]: https://azure.microsoft.com/products/microsoft-sentinel
[link_google_security_operations]: https://cloud.google.com/chronicle
[link_datadog_cloud_siem]: https://www.datadoghq.com/product/cloud-siem/
[link_sumo_logic]: https://www.sumologic.com/
[link_graylog]: https://graylog.org/
[link_opensearch_security_analytics]: https://docs.opensearch.org/docs/latest/security-analytics/
[link_opentelemetry_collector]: https://opentelemetry.io/docs/collector/
[link_grafana_oss]: https://grafana.com/oss/
[link_grafana_tempo]: https://grafana.com/oss/tempo/
[link_grafana_loki]: https://grafana.com/oss/loki/
[link_prometheus]: https://prometheus.io/
[link_datadog]: https://www.datadoghq.com/
[link_elastic_observability]: https://www.elastic.co/observability
[link_dynatrace]: https://www.dynatrace.com/
[link_new_relic]: https://newrelic.com/
[link_crowdstrike]: https://www.crowdstrike.com/platform/
[link_microsoft_defender_endpoint]: https://www.microsoft.com/security/business/endpoint-security/microsoft-defender-endpoint
[link_sentinelone]: https://www.sentinelone.com/platform/singularity-xdr/
[link_carbon_black]: https://www.broadcom.com/products/cyber-security/endpoint
[link_sophos_intercept_x]: https://www.sophos.com/en-us/products/endpoint-antivirus
