# MCP security servers and integrations

---

## Contents

- [AppSec, SAST, dependencies, and supply chain](#appsec-sast-dependencies-and-supply-chain)
- [Offensive tooling, reverse engineering, and mobile](#offensive-tooling-reverse-engineering-and-mobile)
- [Threat intelligence and OSINT APIs](#threat-intelligence-and-osint-apis)
- [Cloud, identity, and zero-trust style access](#cloud-identity-and-zero-trust-style-access)
- [Hosting, gateways, and transport helpers](#hosting-gateways-and-transport-helpers)
- [SIEM and security analytics](#siem-and-security-analytics)
- [Trust markets, reputation, and agent infrastructure](#trust-markets-reputation-and-agent-infrastructure)

---

## AppSec, SAST, dependencies, and supply chain

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [semgrep/mcp][link_semgrep_mcp] | Run [Semgrep][link_semgrep_dev] scans on code from an MCP client | Requires Semgrep access/token policy; scope what paths the agent can read | ![](https://badgen.net/github/last-commit/semgrep/mcp) |
| [StacklokLabs/osv-mcp][link_stacklok_osv_mcp] | Query [OSV][link_osv_dev] for package/CVE data | Egress to OSV APIs; pin versions and review tool outputs before acting on them | ![](https://badgen.net/github/last-commit/StacklokLabs/osv-mcp) |
| [safedep/vet MCP][link_safedep_vet_mcp] | Vet npm/PyPI-style packages for vulns and malicious patterns ([docs][link_safedep_vet_docs]) | Runs locally or via Docker; good for AI-suggested dependencies | ![](https://badgen.net/github/last-commit/safedep/vet) |
| [mcp-security-audit][link_qianniuspace_mcp_security_audit] | Audit npm dependencies via MCP (registry-backed checks) | Remote registry calls; validate lockfiles and CI usage | ![](https://badgen.net/github/last-commit/qianniuspace/mcp-security-audit) |
| [toan203/osv-ui][link_toan203_osv_ui] | CVE audit UI workflow (OSV-powered) from MCP hosts | Human-in-the-loop; browser opens for review—watch secret exposure in logs | ![](https://badgen.net/github/last-commit/toan203/osv-ui) |
| [Snyk studio-mcp][link_snyk_studio_mcp] | Embeds Snyk engines in agentic dev workflows | Commercial Snyk account and token handling; least-privilege service users | ![](https://badgen.net/github/last-commit/snyk/studio-mcp) |
| [agent-bom][link_msaad00_agent_bom] | SBOM, CVE mapping, and supply-chain style checks across MCP clients | Broad filesystem and metadata access; isolate scan targets | ![](https://badgen.net/github/last-commit/msaad00/agent-bom) |
| [addcontent/nuclei-mcp][link_addcontent_nuclei_mcp] | [Nuclei][link_projectdiscovery_nuclei]-driven scanning via MCP | **High risk** if pointed at non-owned targets; auth and rate limits mandatory | ![](https://badgen.net/github/last-commit/addcontent/nuclei-mcp) |

---

## Offensive tooling, reverse engineering, and mobile

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [PortSwigger/mcp-server][link_portswigger_mcp_server] | Burp Suite integration for web security testing | Only on authorized engagements; secrets and session data in scope | ![](https://badgen.net/github/last-commit/PortSwigger/mcp-server) |
| [radareorg/radare2-mcp][link_radareorg_radare2_mcp] (r2mcp) | Radare2 disassembly / RE via MCP | Malware samples stay offline; sandbox hosts | ![](https://badgen.net/github/last-commit/radareorg/radare2-mcp) |
| [LaurieWired/GhidraMCP][link_lauriewired_ghidramcp] | Ghidra RE automation for LLMs | JVM + Ghidra install; untrusted binaries in isolated VMs | ![](https://badgen.net/github/last-commit/LaurieWired/GhidraMCP) |
| [13bm/GhidraMCP][link_13bm_ghidramcp] | Alternate Ghidra MCP bridge | Same as above; pick one maintained path per team | ![](https://badgen.net/github/last-commit/13bm/GhidraMCP) |
| [jtang613/GhidrAssistMCP][link_jtang613_ghidrassistmcp] | Ghidra-native MCP server with GUI options | Same isolation guidance | ![](https://badgen.net/github/last-commit/jtang613/GhidrAssistMCP) |
| [mrexodia/ida-pro-mcp][link_mrexodia_ida_pro_mcp] | IDA Pro plugin for binary analysis | Commercial IDA license; sensitive IP in IDB files | ![](https://badgen.net/github/last-commit/mrexodia/ida-pro-mcp) |
| [zboralski/ida-headless-mcp][link_zboralski_ida_headless_mcp] | Headless IDA orchestration (Go + Python workers) | Concurrency and licensing; strict path controls | ![](https://badgen.net/github/last-commit/zboralski/ida-headless-mcp) |
| [fosdickio/binary_ninja_mcp][link_fosdickio_binary_ninja_mcp] | [Binary Ninja][link_binary_ninja] plugin and bridge | Commercial BN license; malware handling same as Ghidra | ![](https://badgen.net/github/last-commit/fosdickio/binary_ninja_mcp) |
| [MCPPhalanx/binaryninja-mcp][link_mcpphalanx_binaryninja_mcp] | Binary Ninja MCP integration | Compare with official/community options before standardizing | ![](https://badgen.net/github/last-commit/MCPPhalanx/binaryninja-mcp) |
| [zinja-coder/jadx-ai-mcp][link_zinja_jadx_ai_mcp] | JADX decompiler + MCP for Android RE | APKs may contain PII; storage and network egress policy | ![](https://badgen.net/github/last-commit/zinja-coder/jadx-ai-mcp) |
| [mobilehackinglab/jadx-mcp-plugin][link_mobilehackinglab_jadx_mcp_plugin] | JADX HTTP MCP plugin | Exposes decompiler over HTTP—TLS and auth required | ![](https://badgen.net/github/last-commit/mobilehackinglab/jadx-mcp-plugin) |
| [zinja-coder/apktool-mcp-server][link_zinja_apktool_mcp] | APKTool automation via MCP | Build pipeline integration only with reviewed APKs | ![](https://badgen.net/github/last-commit/zinja-coder/apktool-mcp-server) |
| [pullkitsan/mobsf-mcp-server][link_pullkitsan_mobsf_mcp] | [MobSF][link_mobsf] static/dynamic mobile analysis | Dynamic analysis can execute malware; dedicated lab networks | ![](https://badgen.net/github/last-commit/pullkitsan/mobsf-mcp-server) |
| [operantlabs/operant-mcp][link_operantlabs_operant_mcp] | Broad pentest / assessment tool surface via MCP | **Authorized testing only**; dangerous combined with autonomous agents | ![](https://badgen.net/github/last-commit/operantlabs/operant-mcp) |
| [securityfortech/secops-mcp][link_securityfortech_secops_mcp] | Toolbox-style MCP wrapping common open-source security tools | Same authorization and logging requirements as any pentest stack | ![](https://badgen.net/github/last-commit/securityfortech/secops-mcp) |

---

## Threat intelligence and OSINT APIs

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [BurtTheCoder/mcp-shodan][link_burtthecoder_mcp_shodan] | [Shodan][link_shodan] API queries | API keys are high value; block accidental mass scanning | ![](https://badgen.net/github/last-commit/BurtTheCoder/mcp-shodan) |
| [BurtTheCoder/mcp-virustotal][link_burtthecoder_mcp_virustotal] | [VirusTotal][link_virustotal] file/URL/hash lookups | Quota, privacy (submissions become VT property per VT terms), and PII in samples | ![](https://badgen.net/github/last-commit/BurtTheCoder/mcp-virustotal) |
| [BurtTheCoder/mcp-dnstwist][link_burtthecoder_mcp_dnstwist] | [dnstwist][link_dnstwist] typosquat / phishing-style DNS fuzzing | Use for **defensive** brand monitoring by default | ![](https://badgen.net/github/last-commit/BurtTheCoder/mcp-dnstwist) |
| [BurtTheCoder/mcp-maigret][link_burtthecoder_mcp_maigret] | [Maigret][link_maigret] OSINT username / URL expansion | Respect platform ToS and local privacy law | ![](https://badgen.net/github/last-commit/BurtTheCoder/mcp-maigret) |
| [fr0gger/MCP_Security][link_fr0gger_mcp_security] | ORKL threat-intel style queries via MCP | API keys and intel classification handling | ![](https://badgen.net/github/last-commit/fr0gger/MCP_Security) |

---

## Cloud, identity, and zero-trust style access

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [google/mcp-security][link_google_mcp_security] | Google Security Operations / threat-intel style product access via MCP | Cloud org credentials; least privilege, audit, and data residency review | ![](https://badgen.net/github/last-commit/google/mcp-security) |
| [pomerium/pomerium][link_pomerium_pomerium] | Identity-aware proxy with MCP support | Pair with [mcp-app-demo][link_pomerium_mcp_app_demo] and [mcp-servers][link_pomerium_mcp_servers] examples; treat as prod identity path | ![](https://badgen.net/github/last-commit/pomerium/pomerium) |
| [hieuttmmo/entraid-mcp-server][link_hieuttmmo_entraid_mcp] | Microsoft Entra ID / Graph directory and security operations | Highly privileged Graph scopes; conditional access and audit logging | ![](https://badgen.net/github/last-commit/hieuttmmo/entraid-mcp-server) |
| [takleb3rry/zitadel-mcp][link_takleb3rry_zitadel_mcp] | [Zitadel][link_zitadel] identity administration via MCP | Admin-plane access; separate service users from human admins | ![](https://badgen.net/github/last-commit/takleb3rry/zitadel-mcp) |
| [sanyambassi/ciphertrust-manager-mcp-server][link_sanyambassi_ciphertrust_manager_mcp] | Thales CipherTrust Manager key and crypto ops | HSM/KM boundaries; dual control for production | ![](https://badgen.net/github/last-commit/sanyambassi/ciphertrust-manager-mcp-server) |
| [sanyambassi/thales-cdsp-cakm-mcp-server][link_sanyambassi_thales_cdsp_cakm_mcp] | Thales CDSP CAKM for SQL/Oracle key management | Database crypto keys—extreme sensitivity | ![](https://badgen.net/github/last-commit/sanyambassi/thales-cdsp-cakm-mcp-server) |
| [sanyambassi/thales-cdsp-crdp-mcp-server][link_sanyambassi_thales_cdsp_crdp_mcp] | CipherTrust REST data protection MCP surface | Same as above; network placement and mTLS | ![](https://badgen.net/github/last-commit/sanyambassi/thales-cdsp-crdp-mcp-server) |
| [samvas-codes/dawshund_mcp][link_samvas_dawshund_mcp] | AWS IAM effective permissions and relationship views | Read-only IAM analysis preferred; validate AWS account scoping | ![](https://badgen.net/github/last-commit/samvas-codes/dawshund_mcp) |
| [groovyBugify/aws-security-mcp][link_groovybugify_aws_security_mcp] | Natural-language AWS security posture queries (GuardDuty, Security Hub, Access Analyzer, logs) | Highly privileged AWS read APIs; org-wide discovery—scope IAM and segregate accounts | ![](https://badgen.net/github/last-commit/groovyBugify/aws-security-mcp) |
| [oidebrett/mcpauth][link_oidebrett_mcpauth] | OAuth2.1-style MCP gateway authentication component (research PoC; companion paper) | Treat as architecture reference until hardened for production; see [SelfHostedMCP.com](https://selfhostedmcp.com) | ![](https://badgen.net/github/last-commit/oidebrett/mcpauth) |

---

## Hosting, gateways, and transport helpers

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [StacklokLabs/toolhive][link_stacklok_toolhive] | Container-isolated MCP runtime, identity hooks, K8s operator, observability for self-hosted MCP | Complements [StacklokLabs/osv-mcp][link_stacklok_osv_mcp] (dependency intel)—different concern; review enterprise vs. OSS boundary | ![](https://badgen.net/github/last-commit/StacklokLabs/toolhive) |
| [cloudflare/workers-mcp][link_cloudflare_workers_mcp] | Bridge pattern: local MCP client ↔ Cloudflare Worker methods | Prefer current Cloudflare **remote MCP** guidance where applicable; secrets only in Worker bindings / secrets stores | ![](https://badgen.net/github/last-commit/cloudflare/workers-mcp) |

---

## SIEM and security analytics

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [panther-labs/mcp-panther][link_panther_labs_mcp_panther] | Official MCP server for [Panther](https://panther.com/) SIEM: detections, queries, alerts | SOC data plane; least-privilege API roles and full audit of model-driven changes | ![](https://badgen.net/github/last-commit/panther-labs/mcp-panther) |
| [gbrigandi/mcp-server-wazuh][link_gbrigandi_mcp_server_wazuh] | Bridge [Wazuh](https://wazuh.com/) SIEM alerts and events into MCP clients | Real-time security telemetry; isolate agent from production SIEM where possible | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-wazuh) |
| [gbrigandi/mcp-server-thehive][link_gbrigandi_mcp_server_thehive] | [TheHive](https://strangebee.com/thehive/) case management via MCP | Incident and evidence data; role-based access and export controls | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-thehive) |
| [gbrigandi/mcp-server-cortex][link_gbrigandi_mcp_server_cortex] | [Cortex](https://strangebee.com/cortex/) security response automation via MCP | Automated actions need human gates in production | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-cortex) |
| [RunReveal MCP][link_runreveal_mcp_docs] | Vendor-documented MCP for [RunReveal](https://runreveal.com/) security log queries | Cloud log store access; confirm retention and query scopes | May 6, 2026 |

---

## Trust markets, reputation, and agent infrastructure

These projects often combine **identity, scoring, payments (for example x402)**, and **MCP** for agent-to-agent commerce. They are relevant where teams assess **third-party MCP risk** or **automated trust signals**—not a substitute for code review and policy gates.

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [alexfleetcommander/agent-trust-stack-mcp][link_alexfleetcommander_agent_trust_stack_mcp] | Provenance, reputation scoring, and tamper-evident logging for agents | Cryptographic claims still need governance; review what is anchored vs. marketing | ![](https://badgen.net/github/last-commit/alexfleetcommander/agent-trust-stack-mcp) |
| [KOVY/agentforge-trust-mcp][link_kovy_agentforge_trust_mcp] | MCP trust scores and policy-style recommendations before connecting | Third-party scores are heuristics—do not bypass internal approval | ![](https://badgen.net/github/last-commit/KOVY/agentforge-trust-mcp) |
| [agentgraph-co/agentgraph][link_agentgraph_co_agentgraph] | Attestations and scanning posture signals for third-party MCP servers | Verify attestation roots and freshness | ![](https://badgen.net/github/last-commit/agentgraph-co/agentgraph) |
| [vinaybhosle/agentstamp][link_vinaybhosle_agentstamp] | Agent identity stamps and reputation registry | API and payment rails; watch data residency | ![](https://badgen.net/github/last-commit/vinaybhosle/agentstamp) |

---

[link_13bm_ghidramcp]: https://github.com/13bm/GhidraMCP
[link_addcontent_nuclei_mcp]: https://github.com/addcontent/nuclei-mcp
[link_agentgraph_co_agentgraph]: https://github.com/agentgraph-co/agentgraph
[link_alexfleetcommander_agent_trust_stack_mcp]: https://github.com/alexfleetcommander/agent-trust-stack-mcp
[link_binary_ninja]: https://binary.ninja/
[link_burtthecoder_mcp_dnstwist]: https://github.com/BurtTheCoder/mcp-dnstwist
[link_burtthecoder_mcp_maigret]: https://github.com/BurtTheCoder/mcp-maigret
[link_burtthecoder_mcp_shodan]: https://github.com/BurtTheCoder/mcp-shodan
[link_burtthecoder_mcp_virustotal]: https://github.com/BurtTheCoder/mcp-virustotal
[link_dnstwist]: https://github.com/elceef/dnstwist
[link_cloudflare_workers_mcp]: https://github.com/cloudflare/workers-mcp
[link_fr0gger_mcp_security]: https://github.com/fr0gger/MCP_Security
[link_groovybugify_aws_security_mcp]: https://github.com/groovyBugify/aws-security-mcp
[link_google_mcp_security]: https://github.com/google/mcp-security
[link_gbrigandi_mcp_server_cortex]: https://github.com/gbrigandi/mcp-server-cortex
[link_gbrigandi_mcp_server_thehive]: https://github.com/gbrigandi/mcp-server-thehive
[link_gbrigandi_mcp_server_wazuh]: https://github.com/gbrigandi/mcp-server-wazuh
[link_fosdickio_binary_ninja_mcp]: https://github.com/fosdickio/binary_ninja_mcp
[link_hieuttmmo_entraid_mcp]: https://github.com/hieuttmmo/entraid-mcp-server
[link_jtang613_ghidrassistmcp]: https://github.com/jtang613/GhidrAssistMCP
[link_kovy_agentforge_trust_mcp]: https://github.com/KOVY/agentforge-trust-mcp
[link_lauriewired_ghidramcp]: https://github.com/LaurieWired/GhidraMCP
[link_maigret]: https://github.com/soxoj/maigret
[link_mcpphalanx_binaryninja_mcp]: https://github.com/MCPPhalanx/binaryninja-mcp
[link_mobsf]: https://github.com/MobSF/Mobile-Security-Framework-MobSF
[link_mrexodia_ida_pro_mcp]: https://github.com/mrexodia/ida-pro-mcp
[link_msaad00_agent_bom]: https://github.com/msaad00/agent-bom
[link_oidebrett_mcpauth]: https://github.com/oidebrett/mcpauth
[link_operantlabs_operant_mcp]: https://github.com/operantlabs/operant-mcp
[link_panther_labs_mcp_panther]: https://github.com/panther-labs/mcp-panther
[link_osv_dev]: https://osv.dev/
[link_portswigger_mcp_server]: https://github.com/PortSwigger/mcp-server
[link_projectdiscovery_nuclei]: https://github.com/projectdiscovery/nuclei
[link_pullkitsan_mobsf_mcp]: https://github.com/pullkitsan/mobsf-mcp-server
[link_runreveal_mcp_docs]: https://docs.runreveal.com/reference/model-context-protocol
[link_pomerium_mcp_app_demo]: https://github.com/pomerium/mcp-app-demo
[link_pomerium_mcp_servers]: https://github.com/pomerium/mcp-servers
[link_pomerium_pomerium]: https://github.com/pomerium/pomerium
[link_qianniuspace_mcp_security_audit]: https://github.com/qianniuspace/mcp-security-audit
[link_radareorg_radare2_mcp]: https://github.com/radareorg/radare2-mcp
[link_safedep_vet_docs]: https://github.com/safedep/vet/blob/main/docs/mcp.md
[link_safedep_vet_mcp]: https://github.com/safedep/vet
[link_samvas_dawshund_mcp]: https://github.com/samvas-codes/dawshund_mcp
[link_sanyambassi_ciphertrust_manager_mcp]: https://github.com/sanyambassi/ciphertrust-manager-mcp-server
[link_sanyambassi_thales_cdsp_cakm_mcp]: https://github.com/sanyambassi/thales-cdsp-cakm-mcp-server
[link_sanyambassi_thales_cdsp_crdp_mcp]: https://github.com/sanyambassi/thales-cdsp-crdp-mcp-server
[link_securityfortech_secops_mcp]: https://github.com/securityfortech/secops-mcp
[link_semgrep_dev]: https://semgrep.dev/
[link_semgrep_mcp]: https://github.com/semgrep/mcp
[link_shodan]: https://www.shodan.io/
[link_snyk_studio_mcp]: https://github.com/snyk/studio-mcp
[link_stacklok_osv_mcp]: https://github.com/StacklokLabs/osv-mcp
[link_stacklok_toolhive]: https://github.com/StacklokLabs/toolhive
[link_takleb3rry_zitadel_mcp]: https://github.com/takleb3rry/zitadel-mcp
[link_toan203_osv_ui]: https://github.com/toan203/osv-ui
[link_vinaybhosle_agentstamp]: https://github.com/vinaybhosle/agentstamp
[link_virustotal]: https://www.virustotal.com/
[link_zboralski_ida_headless_mcp]: https://github.com/zboralski/ida-headless-mcp
[link_zinja_apktool_mcp]: https://github.com/zinja-coder/apktool-mcp-server
[link_zinja_jadx_ai_mcp]: https://github.com/zinja-coder/jadx-ai-mcp
[link_mobilehackinglab_jadx_mcp_plugin]: https://github.com/mobilehackinglab/jadx-mcp-plugin
[link_zitadel]: https://zitadel.com/
