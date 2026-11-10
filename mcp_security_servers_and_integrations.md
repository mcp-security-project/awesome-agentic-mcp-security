# MCP security servers and integrations

MCP servers and integrations that connect agents to **external security products**, threat feeds, SOC platforms, identity systems, and assessment tooling. Each section separates **open source and community** projects from **commercial and vendor platform** integrations (paid product, licensed platform, or vendor-hosted MCP endpoint required unless noted).

For MCP-aware scanners, gateways, and hardening utilities that do not wrap a vendor product, see [MCP security tools](mcp_security_tools.md).

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

### Open source and community

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [semgrep/mcp][link_semgrep_mcp] | Run [Semgrep][link_semgrep_dev] scans on code from an MCP client | Requires Semgrep access/token policy; scope what paths the agent can read; full rule coverage may need Semgrep Teams/Enterprise | ![](https://badgen.net/github/last-commit/semgrep/mcp) |
| [StacklokLabs/osv-mcp][link_stacklok_osv_mcp] | Query [OSV][link_osv_dev] for package/CVE data | Egress to OSV APIs; pin versions and review tool outputs before acting on them | ![](https://badgen.net/github/last-commit/StacklokLabs/osv-mcp) |
| [safedep/vet MCP][link_safedep_vet_mcp] | Vet npm/PyPI-style packages for vulns and malicious patterns ([docs][link_safedep_vet_docs]) | Runs locally or via Docker; good for AI-suggested dependencies | ![](https://badgen.net/github/last-commit/safedep/vet) |
| [mcp-security-audit][link_qianniuspace_mcp_security_audit] | Audit npm dependencies via MCP (registry-backed checks) | Remote registry calls; validate lockfiles and CI usage | ![](https://badgen.net/github/last-commit/qianniuspace/mcp-security-audit) |
| [toan203/osv-ui][link_toan203_osv_ui] | CVE audit UI workflow (OSV-powered) from MCP hosts | Human-in-the-loop; browser opens for review—watch secret exposure in logs | ![](https://badgen.net/github/last-commit/toan203/osv-ui) |
| [agent-bom][link_msaad00_agent_bom] | SBOM, CVE mapping, and supply-chain style checks across MCP clients | Broad filesystem and metadata access; isolate scan targets | ![](https://badgen.net/github/last-commit/msaad00/agent-bom) |
| [addcontent/nuclei-mcp][link_addcontent_nuclei_mcp] | [Nuclei][link_projectdiscovery_nuclei]-driven scanning via MCP | **High risk** if pointed at non-owned targets; auth and rate limits mandatory; compare with [Bolt][link_cyberstrikeus_bolt] Nuclei path | ![](https://badgen.net/github/last-commit/addcontent/nuclei-mcp) |
| [elliotllliu/agent-shield][link_elliotllliu_agent_shield] | Pre-deployment scanning for agent skills, MCP servers, and plugins | Offline-focused static analysis for injection-style risks; still requires human review of findings | ![](https://badgen.net/github/last-commit/elliotllliu/agent-shield) |
| [prompt-security/clawsec][link_prompt_security_clawsec] | Audit pipeline for agent skills and MCP servers | Multi-stage analysis; validate where data/artefacts are stored and how reports are generated | ![](https://badgen.net/github/last-commit/prompt-security/clawsec) |
| [@tensorfeed/mcp-server][link_tensorfeed_mcp_server] | TensorFeed catalog MCP with `get_ai_supply_chain_iocs` (daily AI-filtered GHSA feed) | Pure data feed, no scanning or code execution; treat linked GHSA records as authoritative | ![](https://badgen.net/github/last-commit/RipperMercs/tensorfeed) |
| [aquasecurity/trivy-mcp][link_aquasecurity_trivy_mcp] | Official [Trivy][link_trivy_dev] plugin for container, IaC, and dependency scanning via MCP | Local-first; monitor plugin maintenance and upstream Trivy supply-chain advisories | ![](https://badgen.net/github/last-commit/aquasecurity/trivy-mcp) |
| [JordyZomer/codeql-mcp][link_jordyzomer_codeql_mcp] | Community CodeQL query/scan bridge for AI agents | Not an official GitHub MCP server; CodeQL DB setup and GHAS licensing apply for private repos | ![](https://badgen.net/github/last-commit/JordyZomer/codeql-mcp) |
| [shaikh-shahid/veracode-mcp-server][link_shaikh_shahid_veracode_mcp] | [Veracode][link_veracode] Pipeline Scan + Fix via Veracode CLI | Commercial Veracode credentials; Fix region limits per vendor; not an official Veracode MCP server | ![](https://badgen.net/github/last-commit/shaikh-shahid/veracode-mcp-server) |
| [jamiesonio/defectdojo-mcp][link_jamiesonio_defectdojo_mcp] | Experimental bridge to [DefectDojo][link_defectdojo] findings, products, and engagements | API token inherits that user's permissions; treat finding text as untrusted content | ![](https://badgen.net/github/last-commit/jamiesonio/defectdojo-mcp) |
| [awslabs/mcp][link_awslabs_security_agent_mcp] (Security Agent) | Official AWS Security Agent MCP for code scans, diff scans, threat-model review, and pentest orchestration | Same monorepo as [Security Hub][link_awslabs_mcp_security_hub]; pin a release with the CVE-2026-87913 S3 bucket-ownership fix (≥ 0.2.0, see [mcp_cve.md](mcp_cve.md)); **authorized testing only** | ![](https://badgen.net/github/last-commit/awslabs/mcp) |

### Commercial and vendor platforms

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [Snyk studio-mcp][link_snyk_studio_mcp] | Embeds Snyk engines in agentic dev workflows | Commercial Snyk account and token handling; least-privilege service users; also via `snyk mcp --experimental` | ![](https://badgen.net/github/last-commit/snyk/studio-mcp) |
| [SonarQube MCP][link_sonarsource_sonarqube_mcp_server] | Official MCP for [SonarQube][link_sonarsource_sonarqube_mcp_server] Cloud/Server quality and security | SonarQube license required; cloud-hosted MCP at [mcp.sonarqube.com][link_sonarsource_mcp_config_generator]; Docker image `sonarsource/sonarqube-mcp` | ![](https://badgen.net/github/last-commit/SonarSource/sonarqube-mcp-server) |
| [Checkmarx One MCP][link_checkmarx_mcp_docs] | SAST, SCA, IaC, and secrets via Checkmarx One REST APIs | Commercial Checkmarx One + SSO; marketplace install for Copilot/VS Code; read-only findings context for agent remediation | Vendor docs |
| [GitGuardian MCP][link_gitguardian_ggmcp] | Secrets detection, honeytokens, and incident workflows | Commercial GitGuardian SaaS or self-hosted; hosted MCP at `mcp.gitguardian.com` or self-host [ghcr.io/gitguardian/mcp-server][link_gitguardian_ggmcp] | ![](https://badgen.net/github/last-commit/GitGuardian/ggmcp) |
| [Datadog Code Security MCP][link_datadog_code_security_mcp] | Local SAST, SCA, IaC, secrets, and SBOM via Datadog security binaries | Preview; requires Datadog API/app keys and installed `datadog-static-analyzer` / SBOM / IaC CLIs | ![](https://badgen.net/github/last-commit/datadog-labs/datadog-code-security-mcp) |
| [Cycode MCP][link_cycodehq_cycode_cli] | ASPM-style SAST, SCA, secrets, and IaC via `cycode mcp` in the CLI | Commercial Cycode account; MCP embedded in [cycode-cli][link_cycodehq_cycode_cli] | ![](https://badgen.net/github/last-commit/cycodehq/cycode-cli) |
| [Contrast Security MCP][link_contrast_security_oss_mcp_contrast] | IAST findings, taint flows, and SARIF export from Contrast platform | Contrast enterprise license; avoid LLMs that train on submitted code per vendor guidance | ![](https://badgen.net/github/last-commit/Contrast-Security-OSS/mcp-contrast) |
| [StackHawk MCP][link_stackhawk_stackhawk_mcp] | DAST setup, YAML validation, scan runs, and finding triage | Beta; StackHawk Pro/Enterprise/Vibe subscription; **authorized targets only** | ![](https://badgen.net/github/last-commit/stackhawk/stackhawk-mcp) |
| [Endor Labs MCP][link_endorlabs_mcp_docs] | SAST, SCA, secrets, and diff-scoped `security_review` via `endorctl` | Commercial namespace for full platform; free Developer Edition MCP has limited scope | Vendor docs |
| [Aikido MCP][link_aikidosec_mcp] (`@aikidosec/mcp`) | Code and secrets scanning for AI-generated code | Commercial Aikido account; OAuth browser sign-in or `AIKIDO_API_KEY` for CI | npm package |
| [Black Duck Polaris MCP][link_black_duck_polaris_mcp] (`@black-duck/mcp-server`) | Read-only Polaris issue management and ContextAI remediation context | Commercial Synopsys Black Duck Polaris; no scan trigger via MCP | npm package |
| [Mend MCP][link_mend_mcp_docs] | Agentic SAST and SCA assistants (`mend-code-security-assistant`, `mend-dependencies-assistant`) | Commercial Mend platform; SAST+DAST correlation when both products are in use | Vendor docs |
| [JFrog MCP Server][link_jfrog_mcp_docs] | Remote MCP for Artifactory, Xray, Curation, Catalog, and platform admin toolsets | JFrog Cloud GA; admin must enable on JPD; Catalog/Curation need Unified/Ultimate Security tiers | Vendor docs |
| [Socket MCP][link_socket_mcp] | Official dependency risk scores for npm, PyPI, cargo, Maven, and other ecosystems (`https://mcp.socket.dev/` or local npm) | Hosted OAuth, or an API token for local stdio; scores are advisory—confirm before blocking installs | ![](https://badgen.net/github/last-commit/socketdev/socket-mcp) |
| [Harness Code Security MCP][link_harness_code_security_mcp] | SAST, SCA, data-flow triage, AutoFix, and package CVE lookup (`harness-code-security-mcp`) | Commercial Qwiet AI by Harness account; local `sl analyze` uploads results to the vendor | npm package |
| [ByteHide MCP][link_bytehide_mcp] | SAST, secrets, dependency checks, and a local AI-config audit | Commercial ByteHide account; `audit_ai_environment` stays local, other scans may leave the workstation | Vendor docs |
| [Chainguard MCP servers][link_chainguard_mcp] | Live image SBOMs, Wolfi packages, upstream EOL data, and read-only platform API | OAuth per endpoint (`cgr.dev`, `apk.cgr.dev`, `versions.cgr.dev`, console API); each token sees only what that account can read | Vendor docs |
| [ZeroPath MCP][link_zeropath_mcp_server] | Query and triage ZeroPath findings, scans, rules, and patches | Hosted OAuth at `https://zeropath.com/mcp`, or local stdio with an API token | ![](https://badgen.net/github/last-commit/ZeroPathAI/zeropath-mcp-server) |
| [ProjectDiscovery Neo MCP][link_projectdiscovery_neo_mcp] | Hosted Neo assessments (recon, code review, CVE triage, pentest) at `https://mcp.projectdiscovery.io/mcp` | `X-Api-Key` carries account permissions; **authorized targets only**; distinct from community [nuclei-mcp][link_addcontent_nuclei_mcp] | Vendor-hosted |

---

## Offensive tooling, reverse engineering, and mobile

### Open source and community

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [radareorg/radare2-mcp][link_radareorg_radare2_mcp] (r2mcp) | Radare2 disassembly / RE via MCP | Malware samples stay offline; sandbox hosts | ![](https://badgen.net/github/last-commit/radareorg/radare2-mcp) |
| [LaurieWired/GhidraMCP][link_lauriewired_ghidramcp] | Ghidra RE automation for LLMs | JVM + Ghidra install; untrusted binaries in isolated VMs | ![](https://badgen.net/github/last-commit/LaurieWired/GhidraMCP) |
| [13bm/GhidraMCP][link_13bm_ghidramcp] | Alternate Ghidra MCP bridge | Same as above; pick one maintained path per team | ![](https://badgen.net/github/last-commit/13bm/GhidraMCP) |
| [jtang613/GhidrAssistMCP][link_jtang613_ghidrassistmcp] | Ghidra-native MCP server with GUI options | Same isolation guidance | ![](https://badgen.net/github/last-commit/jtang613/GhidrAssistMCP) |
| [MCPPhalanx/binaryninja-mcp][link_mcpphalanx_binaryninja_mcp] | Binary Ninja MCP integration (community) | Compare with official/community options before standardizing | ![](https://badgen.net/github/last-commit/MCPPhalanx/binaryninja-mcp) |
| [morluto/rea][link_morluto_rea] | Local-first reverse-engineering CLI/MCP | Analyzes native binaries and shipped JavaScript, .NET, and browser targets; native engines are bring-your-own. Use only on authorized targets. | ![](https://badgen.net/github/last-commit/morluto/rea) |
| [zinja-coder/jadx-ai-mcp][link_zinja_jadx_ai_mcp] | JADX decompiler + MCP for Android RE | APKs may contain PII; storage and network egress policy | ![](https://badgen.net/github/last-commit/zinja-coder/jadx-ai-mcp) |
| [mobilehackinglab/jadx-mcp-plugin][link_mobilehackinglab_jadx_mcp_plugin] | JADX HTTP MCP plugin | Exposes decompiler over HTTP—TLS and auth required | ![](https://badgen.net/github/last-commit/mobilehackinglab/jadx-mcp-plugin) |
| [zinja-coder/apktool-mcp-server][link_zinja_apktool_mcp] | APKTool automation via MCP | Build pipeline integration only with reviewed APKs | ![](https://badgen.net/github/last-commit/zinja-coder/apktool-mcp-server) |
| [pullkitsan/mobsf-mcp-server][link_pullkitsan_mobsf_mcp] | [MobSF][link_mobsf] static/dynamic mobile analysis | Dynamic analysis can execute malware; dedicated lab networks | ![](https://badgen.net/github/last-commit/pullkitsan/mobsf-mcp-server) |
| [operantlabs/operant-mcp][link_operantlabs_operant_mcp] | Broad pentest / assessment tool surface via MCP | **Authorized testing only**; dangerous combined with autonomous agents | ![](https://badgen.net/github/last-commit/operantlabs/operant-mcp) |
| [securityfortech/secops-mcp][link_securityfortech_secops_mcp] | Toolbox-style MCP wrapping common open-source security tools | Same authorization and logging requirements as any pentest stack | ![](https://badgen.net/github/last-commit/securityfortech/secops-mcp) |
| [cyberstrikeus/bolt][link_cyberstrikeus_bolt] | Successor to [cyproxio/mcp-for-security][link_cyproxio_mcp_for_security] — Nmap, SQLMap, FFUF, Nuclei, Scout Suite, and more | Docker-first pentest MCP suite; **authorized testing only**; cyprox repo archived | ![](https://badgen.net/github/last-commit/cyberstrikeus/bolt) |
| [MorDavid/BloodHound-MCP-AI][link_mordavid_bloodhound_mcp_ai] | BloodHound AD attack-path analysis via MCP | AD recon output is sensitive; lab/engagement scope only | ![](https://badgen.net/github/last-commit/MorDavid/BloodHound-MCP-AI) |
| [atomicchonk/roadrecon_mcp_server][link_atomicchonk_roadrecon_mcp_server] | [ROADRecon][link_roadrecon] Azure AD mapping via MCP | Tenant recon data is highly sensitive; authorized assessments only | ![](https://badgen.net/github/last-commit/atomicchonk/roadrecon_mcp_server) |
| [eversinc33/TriageMCP][link_eversinc33_triagemcp] | Static triage of Portable Executable (PE) files | Malware samples in isolated VMs; output may contain exploit hints | ![](https://badgen.net/github/last-commit/eversinc33/TriageMCP) |
| [slouchd/cyberchef-api-mcp-server][link_slouchd_cyberchef_api_mcp_server] | CyberChef API operations via MCP (decode/transform/forensics helpers) | Treat as analyst workstation tooling; watch data classification | ![](https://badgen.net/github/last-commit/slouchd/cyberchef-api-mcp-server) |
| [girste/mcp-cybersec-watchdog][link_girste_mcp_cybersec_watchdog] | Linux host hardening / audit checks via MCP | Run on authorized hosts only; store reports securely | ![](https://badgen.net/github/last-commit/girste/mcp-cybersec-watchdog) |
| [ZAP MCP Integration][link_zaproxy_mcp] | Official [OWASP ZAP][link_owasp_zap] add-on: spider, active scan, alerts, and MCP import | Alpha; bind to localhost only—the server can read proxy history and start scans | ![](https://badgen.net/github/last-commit/zaproxy/zap-extensions) |
| [Gaffx/volatility-mcp][link_gaffx_volatility_mcp] | [Volatility 3][link_volatility3] memory-forensics bridge | Memory images hold credentials and PII; analyze in an isolated lab | ![](https://badgen.net/github/last-commit/Gaffx/volatility-mcp) |
| [0xKoda/WireMCP][link_0xkoda_wiremcp] | Wireshark `tshark` capture and packet analysis via MCP | Live traffic and pcaps are sensitive; authorized networks only | ![](https://badgen.net/github/last-commit/0xKoda/WireMCP) |
| [GH05TCREW/MetasploitMCP][link_gh05tcrew_metasploitmcp] | [Metasploit][link_metasploit] module search and session workflows via MCP | **Authorized testing only**; module execution can compromise hosts—lab scope and human approval | ![](https://badgen.net/github/last-commit/GH05TCREW/MetasploitMCP) |
| [xpn/mythic_mcp][link_xpn_mythic_mcp] | Proof-of-concept MCP for the [Mythic][link_mythic] C2 framework | **Authorized testing only**; lab PoC, not a production control plane | ![](https://badgen.net/github/last-commit/xpn/mythic_mcp) |

### Commercial and vendor platforms

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [PortSwigger/mcp-server][link_portswigger_mcp_server] | [Burp Suite][link_portswigger_burp] integration for web security testing | Commercial Burp license; **authorized engagements only**; secrets and session data in scope | ![](https://badgen.net/github/last-commit/PortSwigger/mcp-server) |
| [mrexodia/ida-pro-mcp][link_mrexodia_ida_pro_mcp] | IDA Pro plugin for binary analysis | Commercial IDA license; sensitive IP in IDB files | ![](https://badgen.net/github/last-commit/mrexodia/ida-pro-mcp) |
| [zboralski/ida-headless-mcp][link_zboralski_ida_headless_mcp] | Headless IDA orchestration (Go + Python workers) | Commercial IDA licensing; concurrency and strict path controls | ![](https://badgen.net/github/last-commit/zboralski/ida-headless-mcp) |
| [fosdickio/binary_ninja_mcp][link_fosdickio_binary_ninja_mcp] | [Binary Ninja][link_binary_ninja] plugin and bridge | Commercial BN license; malware handling same as Ghidra | ![](https://badgen.net/github/last-commit/fosdickio/binary_ninja_mcp) |

---

## Threat intelligence and OSINT APIs

### Open source and community

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [BurtTheCoder/mcp-shodan][link_burtthecoder_mcp_shodan] | [Shodan][link_shodan] API queries | API keys are high value; block accidental mass scanning | ![](https://badgen.net/github/last-commit/BurtTheCoder/mcp-shodan) |
| [BurtTheCoder/mcp-virustotal][link_burtthecoder_mcp_virustotal] | [VirusTotal][link_virustotal] file/URL/hash lookups | Quota, privacy (submissions per VT terms), and PII in samples | ![](https://badgen.net/github/last-commit/BurtTheCoder/mcp-virustotal) |
| [BurtTheCoder/mcp-dnstwist][link_burtthecoder_mcp_dnstwist] | [dnstwist][link_dnstwist] typosquat / phishing-style DNS fuzzing | Use for **defensive** brand monitoring by default | ![](https://badgen.net/github/last-commit/BurtTheCoder/mcp-dnstwist) |
| [BurtTheCoder/mcp-maigret][link_burtthecoder_mcp_maigret] | [Maigret][link_maigret] OSINT username / URL expansion | Respect platform ToS and local privacy law | ![](https://badgen.net/github/last-commit/BurtTheCoder/mcp-maigret) |
| [fr0gger/MCP_Security][link_fr0gger_mcp_security] | ORKL threat-intel style queries via MCP | API keys and intel classification handling | ![](https://badgen.net/github/last-commit/fr0gger/MCP_Security) |
| [roadwy/cve-search_mcp][link_roadwy_cve_search_mcp] | CVE-Search API queries (vendor/product/CVE details) | Validate upstream CVE-Search instance and rate limits | ![](https://badgen.net/github/last-commit/roadwy/cve-search_mcp) |
| [nickpending/mcp-recon][link_nickpending_mcp_recon] | Recon workflows (domain/ASN/certs/headers) via MCP | Prefer owned assets and authorized scopes; log and gate usage | ![](https://badgen.net/github/last-commit/nickpending/mcp-recon) |
| [ppcvote/misp-mcp-server][link_ppcvote_misp_mcp_server] | [MISP][link_misp] read-only access with prompt-injection defense | Federated feeds may contain adversarial payloads—`scanOutput()` before LLM exposure | ![](https://badgen.net/github/last-commit/ppcvote/misp-mcp-server) |
| [aplaceforallmystuff/mcp-threatintel][link_aplaceforallmystuff_mcp_threatintel] | Unified lookups across OTX, AbuseIPDB, GreyNoise, and abuse.ch | Optional API keys per source; respect feed ToS and quota | ![](https://badgen.net/github/last-commit/aplaceforallmystuff/mcp-threatintel) |
| [badchars/cve-mcp][link_badchars_cve_mcp] | Multi-source CVE and vuln intel (NVD, EPSS, KEV, GHSA, OSV, exploit signals) | `npx` server; optional paid source keys; bulk triage can exfiltrate sensitive asset context into model chats | ![](https://badgen.net/github/last-commit/badchars/cve-mcp) |
| [GreyNoise-Intelligence/greynoise-mcp-server][link_greynoise_mcp_server] | Official [GreyNoise][link_greynoise_io] Enterprise API MCP (`@greynoise/greynoise-mcp-server`) | Enterprise API key; client-side stdio—keys stay in local MCP config | ![](https://badgen.net/github/last-commit/GreyNoise-Intelligence/greynoise-mcp-server) |
| [thinkchainai/vulnerability-intelligence-mcp][link_thinkchainai_vulnerability_intelligence_mcp] | [MCP App][link_mcp_apps_overview] for NVD, CISA KEV, EPSS, stack profiles, and watchlists | Interactive briefing UI in supported hosts; treat stack/watchlist data as sensitive | ![](https://badgen.net/github/last-commit/thinkchainai/vulnerability-intelligence-mcp) |
| [darrenjrobinson/HIBP-MCP-Server][link_darrenjrobinson_hibp_mcp] | Community [Have I Been Pwned][link_hibp] breach, paste, and password-exposure lookups | API key required; email queries are PII; distinct from the official [HIBP MCP][link_hibp_mcp] | ![](https://badgen.net/github/last-commit/darrenjrobinson/HIBP-MCP-Server) |
| [mytechnotalent/MalwareBazaar_MCP][link_mytechnotalent_malwarebazaar_mcp] | [MalwareBazaar][link_malwarebazaar] sample metadata and threat-intel lookups | Keep this to metadata; do not pull live malware into an agent workspace | ![](https://badgen.net/github/last-commit/mytechnotalent/MalwareBazaar_MCP) |
| [stoyky/mitre-attack-mcp][link_stoyky_mitre_attack_mcp] | Query [MITRE ATT&CK][link_mitre_attack] techniques, groups, software, and Navigator layers | Read-only knowledge base; review how query results are cached in the client | ![](https://badgen.net/github/last-commit/stoyky/mitre-attack-mcp) |
| [zxzinn/opencti-mcp][link_zxzinn_opencti_mcp] | Community [OpenCTI][link_opencti] bridge for reports, indicators, malware, and threat actors | API token is tenant intel access; not the official [XTM One MCP][link_opencti_mcp_docs] | ![](https://badgen.net/github/last-commit/zxzinn/opencti-mcp) |
| [FiligranHQ/xtm-mcp][link_filigranhq_xtm_mcp] (OpenCTI) | Earlier Filigran GraphQL MCP for [OpenCTI][link_opencti] schema introspection and queries | Superseded by the native [XTM One MCP][link_opencti_mcp_docs]; if still used, prefer a read-only token—arbitrary GraphQL can change intel | ![](https://badgen.net/github/last-commit/FiligranHQ/xtm-mcp) |

### Commercial and vendor platforms

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [urlDNA MCP][link_urldna_mcp] | Phishing/URL scanning and threat-intel search on the [urlDNA][link_urldna_io] platform | Hosted SSE at `https://mcp.urldna.io/sse`; API key required; submissions leave your tenant boundary | ![](https://badgen.net/github/last-commit/urldna/mcp) |
| [HackerOne MCP][link_hackerone_mcp_docs] | Read-only HackerOne program, report, asset, and bounty data | Hosted OAuth at `https://hackerone.com/mcp`; use the OAuth `client_id` for your specific MCP host | Vendor docs |
| [Bugcrowd AI Connect][link_bugcrowd_ai_connect] | Real-time submission and program stream for authorized Bugcrowd programs | SSE at `https://stream.bugcrowd.com/mcp`; least-privilege API credentials; org boundary follows account access | Vendor docs |
| [Recorded Future MCP][link_recorded_future_mcp] | Intelligence Graph access (indicators, actors, vulns, alerts, lists) for MCP clients | Commercial RF platform; connector URLs vary by distribution partner—audit OAuth and data egress | Vendor docs |
| [OpenCTI MCP (XTM One)][link_opencti_mcp_docs] | Hosted [OpenCTI][link_opencti] MCP for STIX search, create, update, and markings | Served at `/mcp/opencti`; personal API key or OAuth; actions run as the calling user; this replaces the older [FiligranHQ/xtm-mcp][link_filigranhq_xtm_mcp] GraphQL server | Vendor docs |
| [VirusTotal MCP][link_virustotal_mcp] | Official VirusTotal / VTAI MCP for file, URL, domain, and IP reports, plus analysis submission | Hosted OAuth at `https://ai.virustotal.com/mcp` (free VTAI limits) or local `vt-mcp`; submissions leave your environment; distinct from community [mcp-virustotal][link_burtthecoder_mcp_virustotal] | ![](https://badgen.net/github/last-commit/VirusTotal/virustotal-mcp) |
| [VulnCheck MCP][link_vulncheck_mcp] | Official VulnCheck MCP for CVEs, exploits, advisories, packages, and threat indices | Commercial VulnCheck API token; exploit and C2 context is sensitive—scope which asset data the agent sends | ![](https://badgen.net/github/last-commit/vulncheck-oss/mcp) |
| [Censys Platform MCP][link_censys_mcp] | Hosted Censys Internet Map and Platform API MCP (`https://mcp.platform.censys.io/platform/mcp/`) | OAuth or personal access token; API calls spend Censys credits; host and attack-surface queries can be sensitive | Vendor-hosted |
| [Have I Been Pwned MCP][link_hibp_mcp] | Breach, paste, stealer-log, and Pwned Passwords lookups at `https://haveibeenpwned.com/mcp` | Public breach catalog needs no sign-in; account, domain, and stealer-log tools need OAuth and often a paid plan—email lookups are PII | Vendor-hosted |

---

## Cloud, identity, and zero-trust style access

### Open source and community

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [pomerium/pomerium][link_pomerium_pomerium] | Identity-aware proxy with MCP support | Pair with [mcp-app-demo][link_pomerium_mcp_app_demo] and [mcp-servers][link_pomerium_mcp_servers]; treat as prod identity path | ![](https://badgen.net/github/last-commit/pomerium/pomerium) |
| [hieuttmmo/entraid-mcp-server][link_hieuttmmo_entraid_mcp] | Microsoft Entra ID / Graph directory and security operations | Community server—not Microsoft official; highly privileged Graph scopes | ![](https://badgen.net/github/last-commit/hieuttmmo/entraid-mcp-server) |
| [takleb3rry/zitadel-mcp][link_takleb3rry_zitadel_mcp] | [Zitadel][link_zitadel] identity administration via MCP | Admin-plane access; separate service users from human admins | ![](https://badgen.net/github/last-commit/takleb3rry/zitadel-mcp) |
| [samvas-codes/dawshund_mcp][link_samvas_dawshund_mcp] | AWS IAM effective permissions and relationship views | Read-only IAM analysis preferred; validate AWS account scoping | ![](https://badgen.net/github/last-commit/samvas-codes/dawshund_mcp) |
| [groovyBugify/aws-security-mcp][link_groovybugify_aws_security_mcp] | Natural-language AWS security posture queries (GuardDuty, Security Hub, Access Analyzer, logs) | Highly privileged AWS read APIs; org-wide discovery—scope IAM and segregate accounts | ![](https://badgen.net/github/last-commit/groovyBugify/aws-security-mcp) |
| [awslabs/mcp][link_awslabs_mcp_security_hub] (Security Hub) | Official AWS Security Hub findings MCP (`get_findings` and related tools) | AWS credentials with Security Hub read scope; distinct from community [aws-security-mcp][link_groovybugify_aws_security_mcp] | ![](https://badgen.net/github/last-commit/awslabs/mcp) |
| [awslabs/mcp][link_awslabs_cloudtrail_mcp] (CloudTrail) | Official CloudTrail event lookup and CloudTrail Lake SQL for investigations | Read of account activity; Lake queries need `cloudtrail:StartQuery`; least-privilege IAM and result-size limits | ![](https://badgen.net/github/last-commit/awslabs/mcp) |
| [awslabs/mcp][link_awslabs_well_architected_security_mcp] (Well-Architected Security) | Official posture checks for GuardDuty, Security Hub, Inspector, and Access Analyzer against the Security Pillar | Read-only assessment role; distinct from community [aws-security-mcp][link_groovybugify_aws_security_mcp] and from [Security Hub MCP][link_awslabs_mcp_security_hub] | ![](https://badgen.net/github/last-commit/awslabs/mcp) |
| [hashicorp/vault-mcp-server][link_hashicorp_vault_mcp_server] | Official [HashiCorp Vault][link_hashicorp_vault] KV mount and secret operations | `VAULT_TOKEN` is full secrets-plane access; prefer read-only policies and localhost HTTP binding | ![](https://badgen.net/github/last-commit/hashicorp/vault-mcp-server) |
| [zscaler/zscaler-mcp-server][link_zscaler_mcp_server] | Official OSS MCP for ZIA, ZPA, ZDX, ZCC, and related Zscaler APIs | **Read-only by default**; write tools require explicit allowlists—see [configuration guide][link_zscaler_mcp_server_docs] | ![](https://badgen.net/github/last-commit/zscaler/zscaler-mcp-server) |
| [oidebrett/mcpauth][link_oidebrett_mcpauth] | OAuth2.1-style MCP gateway authentication component (research PoC) | Treat as architecture reference until hardened; see [SelfHostedMCP.com](https://selfhostedmcp.com) | ![](https://badgen.net/github/last-commit/oidebrett/mcpauth) |
| [icoretech/warden-mcp][link_icoretech_warden_mcp] | Bitwarden / Vaultwarden administration via MCP | Extremely sensitive secrets plane; avoid exposing vault contents to untrusted models | ![](https://badgen.net/github/last-commit/icoretech/warden-mcp) |
| [microsoft/agent-governance-toolkit][link_microsoft_agent_governance_toolkit] | Deterministic policy enforcement + audit logging for agent runtimes | Validate policy model and logging backend before production | ![](https://badgen.net/github/last-commit/microsoft/agent-governance-toolkit) |
| [okta/okta-mcp-server][link_okta_mcp_server] | Official Okta admin MCP (users, groups, apps, policies, system log), self-hosted or Okta-managed | Device authorization or private-key JWT; scope tools with `OKTA_SCOPES`; destructive calls need confirmation | ![](https://badgen.net/github/last-commit/okta/okta-mcp-server) |
| [auth0/auth0-mcp-server][link_auth0_mcp_server] | Official OSS MCP for the Auth0 Management API (apps, actions, and related admin operations) | Tenant management credentials; scope the Auth0 application to the smallest API surface | ![](https://badgen.net/github/last-commit/auth0/auth0-mcp-server) |
| [prowler-cloud/prowler][link_prowler_mcp] | Official [Prowler][link_prowler_mcp_docs] MCP for findings, inventory, scans, compliance, and attack paths | Hosted at `https://mcp.prowler.com/mcp` or local from the repo; the API key is cloud-security-plane access | ![](https://badgen.net/github/last-commit/prowler-cloud/prowler) |

### Commercial and vendor platforms

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [google/mcp-security][link_google_mcp_security] | Google SecOps, SOAR, Threat Intelligence, and Security Command Center MCP servers, plus a managed remote SecOps MCP | Google Cloud org credentials; least privilege, audit, and data residency review | ![](https://badgen.net/github/last-commit/google/mcp-security) |
| [sanyambassi/ciphertrust-manager-mcp-server][link_sanyambassi_ciphertrust_manager_mcp] | Thales CipherTrust Manager key and crypto ops | HSM/KM boundaries; dual control for production | ![](https://badgen.net/github/last-commit/sanyambassi/ciphertrust-manager-mcp-server) |
| [sanyambassi/thales-cdsp-cakm-mcp-server][link_sanyambassi_thales_cdsp_cakm_mcp] | Thales CDSP CAKM for SQL/Oracle key management | Database crypto keys—extreme sensitivity | ![](https://badgen.net/github/last-commit/sanyambassi/thales-cdsp-cakm-mcp-server) |
| [sanyambassi/thales-cdsp-crdp-mcp-server][link_sanyambassi_thales_cdsp_crdp_mcp] | CipherTrust REST data protection MCP surface | Same as above; network placement and mTLS | ![](https://badgen.net/github/last-commit/sanyambassi/thales-cdsp-crdp-mcp-server) |
| [alexgoller/illumio-mcp-server][link_alexgoller_illumio_mcp_server] | [Illumio][link_illumio] PCE workload, label, and traffic-flow operations | Commercial Illumio license; policy changes need change control | ![](https://badgen.net/github/last-commit/alexgoller/illumio-mcp-server) |
| [Teleport MCP access][link_goteleport_mcp_use_case] | Zero-trust identity, audit, and `tsh mcp connect` for MCP server access | Commercial Teleport platform; extends infrastructure identity to MCP workloads | Vendor docs |
| [1Password Environments MCP][link_1password_environments_mcp] | Official local MCP for 1Password Environments (names, mounts, and env files) | Desktop app required; the server does not return secret values to the agent; stdio clients only | Vendor docs |
| [BeyondTrust Pathfinder MCP][link_beyondtrust_pathfinder_mcp] | Read-only gateway across Identity Security Insights, Entitle, Password Safe, EPM, PRA, and Remote Support | Early access, US region; `https://mcp.beyondtrust.io/mcp`; the token inherits the user's Pathfinder rights—managed-account metadata is sensitive | Vendor docs |
| [Netskope MCP][link_netskope_mcp] | Netskope Management API MCP for events, alerts, DLP incidents, and policy context | Commercial Netskope tenant; extra API collections can be enabled—keep write and policy tools gated | Vendor docs |

---

## Hosting, gateways, and transport helpers

### Open source and community

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [StacklokLabs/toolhive][link_stacklok_toolhive] | Container-isolated MCP runtime, identity hooks, K8s operator, observability | Complements [osv-mcp][link_stacklok_osv_mcp]; review enterprise vs. OSS boundary | ![](https://badgen.net/github/last-commit/StacklokLabs/toolhive) |
| [cloudflare/workers-mcp][link_cloudflare_workers_mcp] | Bridge pattern: local MCP client ↔ Cloudflare Worker methods | Prefer current Cloudflare **remote MCP** guidance; secrets in Worker bindings only | ![](https://badgen.net/github/last-commit/cloudflare/workers-mcp) |
| [PolicyLayer/Intercept][link_policylayer_intercept] | MCP proxy enforcing YAML policies (rate limits, validation, audit) | Put policy at the transport boundary; treat policy bundles as code with review + CI | ![](https://badgen.net/github/last-commit/PolicyLayer/Intercept) |
| [Sentinel-Gate/Sentinelgate][link_sentinel_gate_sentinelgate] | MCP proxy with CEL policies + RBAC + audit trail | Strong fit for governed org deployments; validate authn/authz and log handling | ![](https://badgen.net/github/last-commit/Sentinel-Gate/Sentinelgate) |
| [luckyPipewrench/pipelock][link_luckypipewrench_pipelock] | “Firewall” wrapper for MCP servers (prompt-injection / leakage scanning) | Defense-in-depth only; validate false positives and bypass paths | ![](https://badgen.net/github/last-commit/luckyPipewrench/pipelock) |
| [wd041216-bit/ironclaw-agent-guard][link_wd041216_bit_ironclaw_agent_guard] | Agent-runtime guard (scan/redact/audit) with stdio + HTTP MCP servers | Ensure logs are tamper-evident and access-controlled | ![](https://badgen.net/github/last-commit/wd041216-bit/ironclaw-agent-guard) |
| [cordum-io/cordum][link_cordum_io_cordum] | Agent control plane with policy checks + output scanning + audit trail | Confirm policy evaluation order and what data leaves the runtime | ![](https://badgen.net/github/last-commit/cordum-io/cordum) |
| [trailofbits/mcp-context-protector][link_trailofbits_mcp_context_protector] | Security wrapper: TOFU config pinning, quarantine, response guardrails | Complements scanners; see [Trail of Bits blog][link_trailofbits_mcp_context_protector_blog] | ![](https://badgen.net/github/last-commit/trailofbits/mcp-context-protector) |
| [agentic-community/mcp-gateway-registry][link_agentic_community_mcp_gateway_registry] | Enterprise MCP gateway + registry (OAuth, tool discovery, audit) | K8s/ECS/Docker Compose; treat registry DB and IdP integration as security-critical | ![](https://badgen.net/github/last-commit/agentic-community/mcp-gateway-registry) |
| [PaloAltoNetworks/pan-mcp-relay][link_paloaltonetworks_pan_mcp_relay] | Prisma AIRS MCP relay/proxy for AI Runtime API intercept on MCP traffic | Requires Prisma AIRS API key and security profile from Strata Cloud Manager | ![](https://badgen.net/github/last-commit/PaloAltoNetworks/pan-mcp-relay) |

### Commercial and vendor platforms

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [Lasso MCP Gateway][link_lasso_security_mcp_gateway] | Enterprise MCP gateway: lifecycle, intercept, sanitize before load | Central control point for governed MCP connections; review data handling and SLA | ![](https://badgen.net/github/last-commit/lasso-security/mcp-gateway) |
| [Harmonic MCP Gateway][link_harmonic_mcp_gateway] | Local gateway: MCP client/server discovery, policy, and sensitive-data controls | Commercial Harmonic Connectors; complements IDE and web AI usage—not a substitute for server code review | Vendor docs |
| [Prisma AIRS MCP Server][link_prisma_airs_mcp_docs] | Runtime prompt/tool-invocation scanning via Prisma AI Runtime Security | Commercial Palo Alto Prisma AIRS; pair with [pan-mcp-relay][link_paloaltonetworks_pan_mcp_relay] or vendor deployment guides | Vendor docs |

---

## SIEM and security analytics

### Open source and community

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [gbrigandi/mcp-server-wazuh][link_gbrigandi_mcp_server_wazuh] | Bridge [Wazuh][link_wazuh] SIEM alerts and events into MCP clients | Real-time security telemetry; isolate agent from production SIEM where possible | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-wazuh) |
| [gbrigandi/mcp-server-thehive][link_gbrigandi_mcp_server_thehive] | [TheHive][link_thehive] case management via MCP | Incident and evidence data; role-based access and export controls | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-thehive) |
| [gbrigandi/mcp-server-cortex][link_gbrigandi_mcp_server_cortex] | [Cortex][link_cortex] security response automation via MCP | Automated actions need human gates in production | ![](https://badgen.net/github/last-commit/gbrigandi/mcp-server-cortex) |
| [splunk/splunk-mcp-server2][link_splunk_splunk_mcp_server2] | Unofficial Splunk SPL search and analysis MCP (Python/TypeScript) | Built-in query guardrails; Splunk admin role risks (see [mcp_cve.md](mcp_cve.md)); not Splunk-supported; distinct from the official [Splunk MCP Server][link_splunk_mcp_official] | ![](https://badgen.net/github/last-commit/splunk/splunk-mcp-server2) |
| [AndreuCrespo/elastic-security-mcp][link_andreucrespo_elastic_security_mcp] | Community MCP for Elasticsearch/Kibana Security, Fleet, and gated response actions | Not official Elastic; least-privilege Elastic service account; confirm action flags before enabling | ![](https://badgen.net/github/last-commit/AndreuCrespo/elastic-security-mcp) |
| [IBM/qradar-mcp][link_ibm_qradar_mcp] | Official read-only IBM QRadar SIEM MCP (offenses, reference data, assets, rules, QVM) | SEC/CSRF or authorized service token; also see sibling [IBM/qradar-mcp-server][link_ibm_qradar_mcp_server] | ![](https://badgen.net/github/last-commit/IBM/qradar-mcp) |
| [bhayanak/qualys-mcp-server][link_bhayanak_qualys_mcp_server] | Qualys VM/compliance workflows via natural language (`qualys-mcp-server` / PyPI `qualys-mcp`) | Commercial Qualys account; community-maintained—not Qualys official | ![](https://badgen.net/github/last-commit/bhayanak/qualys-mcp-server) |
| [shashwat-sec/lacework-mcp-server][link_lacework_mcp_shashwat] | Lacework API v2 alerts (list, search, investigate, comment, close) | Commercial Lacework tenant; community server—gate write tools in production | ![](https://badgen.net/github/last-commit/shashwat-sec/lacework-mcp-server) |
| [mikeclueby4/mcp-xdr][link_mikeclueby4_mcp_xdr] | Microsoft Defender advanced hunting + optional Sentinel KQL via Graph Security API | Delegated or app-only Graph permissions; replaces legacy Defender hunting endpoints | ![](https://badgen.net/github/last-commit/mikeclueby4/mcp-xdr) |
| [markolauren/ResponseMCP][link_markolauren_responsemcp] | Defender XDR response actions (isolate, AV scan, investigation packages) for agentic SOC | **High impact** write tools; Azure-hosted deployment—human approval gates mandatory | ![](https://badgen.net/github/last-commit/markolauren/ResponseMCP) |
| [vinayaklatthe/microsoft-security-agent-toolkit][link_vinayaklatthe_microsoft_security_agent_toolkit] | Multi-server kit: Sentinel, Defender XDR, Graph security, Purview audit MCP paths | Companion to Microsoft security agent skills; not a single unified Microsoft product MCP | ![](https://badgen.net/github/last-commit/vinayaklatthe/microsoft-security-agent-toolkit) |
| [tarhou/tenable-mcp-server][link_tarhou_tenable_mcp_server] | Community MCP for Tenable Vulnerability Management and Tenable One | Commercial Tenable credentials; not Tenable official; distinct from [Tenable.sc][link_tenable_sc_mcp] and hosted [Tenable Hexa AI][link_tenable_hexa_mcp]; gate scan launch and stop | ![](https://badgen.net/github/last-commit/tarhou/tenable-mcp-server) |
| [ReverseThrottle/cortex-mcp][link_reversethrottle_cortex_mcp] | Community MCP for Cortex XSIAM/XDR cases, endpoints, vulnerabilities, and XQL | Not the official [Cortex MCP server][link_paloalto_cortex_mcp]; API keys are highly privileged; endpoint isolate/unisolate needs change control | ![](https://badgen.net/github/last-commit/ReverseThrottle/cortex-mcp) |
| [socfortress/velociraptor-mcp-server][link_socfortress_velociraptor_mcp] | [Velociraptor][link_velociraptor] artifacts, VQL, hunts, and client lookup via MCP | DFIR API keys can collect from endpoints; HTTP mode requires `MCP_AUTH_TOKEN`; gate hunts and active collection | ![](https://badgen.net/github/last-commit/socfortress/velociraptor-mcp-server) |

### Commercial and vendor platforms

| Server / project | Role | Summary | Last updated |
| --- | --- | --- | --- |
| [panther-labs/mcp-panther][link_panther_labs_mcp_panther] | Official MCP for [Panther](https://panther.com/) SIEM: detections, queries, alerts | SOC data plane; least-privilege API roles and full audit of model-driven changes | ![](https://badgen.net/github/last-commit/panther-labs/mcp-panther) |
| [RunReveal MCP][link_runreveal_mcp_docs] | Vendor-documented MCP for [RunReveal](https://runreveal.com/) security log queries | Cloud log store access; confirm retention and query scopes | Vendor docs |
| [rad-security/mcp-server][link_rad_security_mcp_server] | Query RAD Security for K8s/cloud security findings and runtime context | Production cluster insights are sensitive; scope API tokens and separate environments | ![](https://badgen.net/github/last-commit/rad-security/mcp-server) |
| [CrowdStrike Falcon MCP][link_crowdstrike_falcon_mcp] | Self-hosted Falcon MCP ([docs][link_crowdstrike_falcon_mcp_docs]): detections, intel, NG-SIEM, policies, Shield, Fusion SOAR, and zero-trust assessment | Maintenance mode—new features ship in hosted CrowdStrike MCP inside Falcon (US-1, US-2, EU-1); this repo stays on security fixes; Falcon API credentials; audit agent-driven actions | ![](https://badgen.net/github/last-commit/CrowdStrike/falcon-mcp) |
| [Datadog MCP Server][link_datadog_mcp_server] (security toolset) | Remote MCP for logs, metrics, monitors, and security signals/findings | Enable `?toolsets=core,security` on `https://mcp.<DD_SITE>/v1/mcp`; distinct from [Code Security MCP][link_datadog_code_security_mcp] | Vendor-hosted |
| [Wiz MCP Server][link_wiz_mcp_blog] | CNAPP inventory, risk, and remediation context for MCP-compatible agents | Commercial Wiz preview/AWS Marketplace; OAuth service account; customer-gated hosted or container deploy | Vendor docs |
| [Microsoft Sentinel MCP][link_microsoft_sentinel_mcp_overview] | GA hosted MCP for Sentinel data lake exploration, incident and alert triage (including Defender XDR hunting), and Security Copilot agent creation | Entra auth; Security Reader minimum; triage tools at `https://sentinel.microsoft.com/mcp/triage`; **not** [Sentinel-Gate/Sentinelgate][link_sentinel_gate_sentinelgate] | Vendor-hosted |
| [elastic/example-mcp-app-security][link_elastic_example_mcp_app_security] | Reference [MCP App][link_mcp_apps_overview] for interactive Elastic Security SOC workflows | Requires Elastic Stack with Elastic Security license; sandboxed UI in MCP hosts | ![](https://badgen.net/github/last-commit/elastic/example-mcp-app-security) |
| [rapid7/rapid7-bulk-export-mcp][link_rapid7_rapid7_bulk_export_mcp] | Official OSS MCP + Agent Skill for Rapid7 Bulk Export data in local DuckDB | Rapid7 Command Platform account required; sandboxed SQL; on-demand export reuse | ![](https://badgen.net/github/last-commit/rapid7/rapid7-bulk-export-mcp) |
| [Sentinel-One/purple-mcp][link_sentinel_one_purple_mcp] | Read-only SentinelOne Purple AI, alerts, vulns, misconfigs, and inventory | Account/site service-user token (`PURPLEMCP_*`); transport has no built-in auth—protect HTTP/SSE exposure | ![](https://badgen.net/github/last-commit/Sentinel-One/purple-mcp) |
| [Orca Security MCP][link_orca_mcp_docs] | Hosted CNAPP MCP for risks, assets, attack paths, and remediation context | OAuth at `https://mcp.orcasecurity.io` or regional token URLs; see [orca-skills][link_orcasecurity_orca_skills] for client wiring | ![](https://badgen.net/github/last-commit/orcasecurity/orca-skills) |
| [Upwind MCP Server][link_upwind_mcp_docs] | Hosted runtime cloud security (inventory, detections, vulns, compliance, graph search) | OAuth remote MCP; scope tools to least-privilege Upwind roles | Vendor docs |
| [Sysdig Secure MCP][link_sysdig_secure_mcp_docs] | Vendor-hosted regional Secure MCP (`/mcp/secure`) for events, vulns, SysQL, posture | OAuth per region; distinct from [sysdiglabs/sysdig-mcp-server][link_sysdiglabs_sysdig_mcp_server] (Monitor-focused) | Vendor docs |
| [Tenable.sc MCP Server][link_tenable_sc_mcp] | Tenable Security Center vulnerability and asset queries via MCP | Commercial Tenable.sc API keys; Redis-backed caching in reference deployments; distinct from hosted [Tenable Hexa AI MCP][link_tenable_hexa_mcp] | Vendor docs |
| [Splunk MCP Server][link_splunk_mcp_official] | Official Splunk Cloud MCP for searches, alerts, and index discovery (preinstalled on Splunk Cloud 10.6) | Admin allowlists, safe-search command lists, and audit logs; distinct from unofficial [splunk-mcp-server2][link_splunk_splunk_mcp_server2] | Vendor docs |
| [Cortex MCP server][link_paloalto_cortex_mcp] | Palo Alto Cortex MCP for XSIAM and XDR cases, issues, and investigations | Downloadable tenant connector; commercial Cortex license; review AI-suggested actions before they run | Vendor docs |
| [Tenable Hexa AI MCP][link_tenable_hexa_mcp] | Hosted Tenable One exposure MCP (`https://cloud.tenable.com/mcp/`) for assets, vulnerabilities, tags, and scans | `X-ApiKeys` access and secret keys; scan launch is high impact—**authorized targets only**; distinct from [Tenable.sc MCP][link_tenable_sc_mcp] | Vendor-hosted |
| [Qualys MCP][link_qualys_cli_mcp] (`qualys-cli-mcp`) | Vendor package for Qualys VM, compliance, WAS, TotalCloud, containers, and CSAM | PyPI owner `qualys`; command allowlists and optional `QUALYS_MCP_DENY_WRITE`; distinct from community [qualys-mcp-server][link_bhayanak_qualys_mcp_server] | PyPI package |
| [Sumo Logic MCP][link_sumologic_mcp] | Vendor MCP for log search, Cloud SIEM insights, alerts, and dashboards | OAuth and role-scoped tools; not for bulk export—platform rate limits apply | Vendor docs |

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

[link_0xkoda_wiremcp]: https://github.com/0xKoda/WireMCP
[link_13bm_ghidramcp]: https://github.com/13bm/GhidraMCP
[link_1password_environments_mcp]: https://www.1password.dev/environments/mcp-server
[link_addcontent_nuclei_mcp]: https://github.com/addcontent/nuclei-mcp
[link_agentgraph_co_agentgraph]: https://github.com/agentgraph-co/agentgraph
[link_agentic_community_mcp_gateway_registry]: https://github.com/agentic-community/mcp-gateway-registry
[link_aikidosec_mcp]: https://www.npmjs.com/package/@aikidosec/mcp
[link_alexfleetcommander_agent_trust_stack_mcp]: https://github.com/alexfleetcommander/agent-trust-stack-mcp
[link_alexgoller_illumio_mcp_server]: https://github.com/alexgoller/illumio-mcp-server
[link_andreucrespo_elastic_security_mcp]: https://github.com/AndreuCrespo/elastic-security-mcp
[link_aplaceforallmystuff_mcp_threatintel]: https://github.com/aplaceforallmystuff/mcp-threatintel
[link_aquasecurity_trivy_mcp]: https://github.com/aquasecurity/trivy-mcp
[link_atomicchonk_roadrecon_mcp_server]: https://github.com/atomicchonk/roadrecon_mcp_server
[link_auth0_mcp_server]: https://github.com/auth0/auth0-mcp-server
[link_awslabs_cloudtrail_mcp]: https://github.com/awslabs/mcp/tree/main/src/cloudtrail-mcp-server
[link_awslabs_mcp_security_hub]: https://github.com/awslabs/mcp
[link_awslabs_security_agent_mcp]: https://github.com/awslabs/mcp/tree/main/src/security-agent-mcp-server
[link_awslabs_well_architected_security_mcp]: https://github.com/awslabs/mcp/tree/main/src/well-architected-security-mcp-server
[link_badchars_cve_mcp]: https://github.com/badchars/cve-mcp
[link_beyondtrust_pathfinder_mcp]: https://docs.beyondtrust.com/bt-docs/docs/welcome-to-pathfinder-mcp-gateway
[link_bhayanak_qualys_mcp_server]: https://github.com/bhayanak/qualys-mcp-server
[link_binary_ninja]: https://binary.ninja/
[link_black_duck_polaris_mcp]: https://www.blackduck.com/software-composition-analysis/polaris.html
[link_bugcrowd_ai_connect]: https://docs.bugcrowd.com/customers/ai-capabilities/ai-connect/
[link_burtthecoder_mcp_dnstwist]: https://github.com/BurtTheCoder/mcp-dnstwist
[link_burtthecoder_mcp_maigret]: https://github.com/BurtTheCoder/mcp-maigret
[link_burtthecoder_mcp_shodan]: https://github.com/BurtTheCoder/mcp-shodan
[link_burtthecoder_mcp_virustotal]: https://github.com/BurtTheCoder/mcp-virustotal
[link_bytehide_mcp]: https://docs.bytehide.com/products/ai/mcp/overview
[link_censys_mcp]: https://docs.censys.com/docs/platform-mcp-server
[link_chainguard_mcp]: https://www.chainguard.dev/docs/platform/mcp-servers
[link_checkmarx_mcp_docs]: https://docs.checkmarx.com/en/34965-659697-mcp-server---interacting-with-checkmarx-one-via-ai-assistant.html
[link_cloudflare_workers_mcp]: https://github.com/cloudflare/workers-mcp
[link_contrast_security_oss_mcp_contrast]: https://github.com/Contrast-Security-OSS/mcp-contrast
[link_cordum_io_cordum]: https://github.com/cordum-io/cordum
[link_cortex]: https://strangebee.com/cortex/
[link_crowdstrike_falcon_mcp]: https://github.com/CrowdStrike/falcon-mcp
[link_crowdstrike_falcon_mcp_docs]: https://developer.crowdstrike.com/falcon-mcp/overview/
[link_cyberstrikeus_bolt]: https://github.com/cyberstrikeus/bolt
[link_cycodehq_cycode_cli]: https://github.com/cycodehq/cycode-cli
[link_cyproxio_mcp_for_security]: https://github.com/cyproxio/mcp-for-security
[link_darrenjrobinson_hibp_mcp]: https://github.com/darrenjrobinson/HIBP-MCP-Server
[link_datadog_code_security_mcp]: https://github.com/datadog-labs/datadog-code-security-mcp
[link_datadog_mcp_server]: https://docs.datadoghq.com/mcp_server/
[link_defectdojo]: https://www.defectdojo.org/
[link_dnstwist]: https://github.com/elceef/dnstwist
[link_elastic_example_mcp_app_security]: https://github.com/elastic/example-mcp-app-security
[link_elliotllliu_agent_shield]: https://github.com/elliotllliu/agent-shield
[link_endorlabs_mcp_docs]: https://docs.endorlabs.com/setup-deployment/mcp
[link_eversinc33_triagemcp]: https://github.com/eversinc33/TriageMCP
[link_filigranhq_xtm_mcp]: https://github.com/FiligranHQ/xtm-mcp
[link_fosdickio_binary_ninja_mcp]: https://github.com/fosdickio/binary_ninja_mcp
[link_fr0gger_mcp_security]: https://github.com/fr0gger/MCP_Security
[link_gaffx_volatility_mcp]: https://github.com/Gaffx/volatility-mcp
[link_gbrigandi_mcp_server_cortex]: https://github.com/gbrigandi/mcp-server-cortex
[link_gbrigandi_mcp_server_thehive]: https://github.com/gbrigandi/mcp-server-thehive
[link_gbrigandi_mcp_server_wazuh]: https://github.com/gbrigandi/mcp-server-wazuh
[link_gh05tcrew_metasploitmcp]: https://github.com/GH05TCREW/MetasploitMCP
[link_girste_mcp_cybersec_watchdog]: https://github.com/girste/mcp-cybersec-watchdog
[link_gitguardian_ggmcp]: https://github.com/GitGuardian/ggmcp
[link_google_mcp_security]: https://github.com/google/mcp-security
[link_goteleport_mcp_use_case]: https://goteleport.com/use-cases/secure-model-context-protocol
[link_greynoise_io]: https://www.greynoise.io/
[link_greynoise_mcp_server]: https://github.com/GreyNoise-Intelligence/greynoise-mcp-server
[link_groovybugify_aws_security_mcp]: https://github.com/groovyBugify/aws-security-mcp
[link_hackerone_mcp_docs]: https://docs.hackerone.com/en/articles/16069077-hackerone-mcp-server-setup-tool-reference
[link_harmonic_mcp_gateway]: https://www.harmonic.security/solutions/ai-agent-security-mcp-gateway
[link_harness_code_security_mcp]: https://www.npmjs.com/package/harness-code-security-mcp
[link_hashicorp_vault]: https://www.hashicorp.com/products/vault
[link_hashicorp_vault_mcp_server]: https://github.com/hashicorp/vault-mcp-server
[link_hibp]: https://haveibeenpwned.com/
[link_hibp_mcp]: https://haveibeenpwned.com/Docs/MCP
[link_hieuttmmo_entraid_mcp]: https://github.com/hieuttmmo/entraid-mcp-server
[link_ibm_qradar_mcp]: https://github.com/IBM/qradar-mcp
[link_ibm_qradar_mcp_server]: https://github.com/IBM/qradar-mcp-server
[link_icoretech_warden_mcp]: https://github.com/icoretech/warden-mcp
[link_illumio]: https://www.illumio.com/
[link_jamiesonio_defectdojo_mcp]: https://github.com/jamiesonio/defectdojo-mcp
[link_jfrog_mcp_docs]: https://docs.jfrog.com/integrations/docs/jfrog-mcp-server
[link_jordyzomer_codeql_mcp]: https://github.com/JordyZomer/codeql-mcp
[link_jtang613_ghidrassistmcp]: https://github.com/jtang613/GhidrAssistMCP
[link_kovy_agentforge_trust_mcp]: https://github.com/KOVY/agentforge-trust-mcp
[link_lacework_mcp_shashwat]: https://github.com/shashwat-sec/lacework-mcp-server
[link_lasso_security_mcp_gateway]: https://github.com/lasso-security/mcp-gateway
[link_lauriewired_ghidramcp]: https://github.com/LaurieWired/GhidraMCP
[link_luckypipewrench_pipelock]: https://github.com/luckyPipewrench/pipelock
[link_maigret]: https://github.com/soxoj/maigret
[link_malwarebazaar]: https://bazaar.abuse.ch/
[link_markolauren_responsemcp]: https://github.com/markolauren/ResponseMCP
[link_mcp_apps_overview]: https://modelcontextprotocol.io/extensions/apps/overview
[link_mcpphalanx_binaryninja_mcp]: https://github.com/MCPPhalanx/binaryninja-mcp
[link_mend_mcp_docs]: https://docs.mend.io/
[link_metasploit]: https://github.com/rapid7/metasploit-framework
[link_microsoft_agent_governance_toolkit]: https://github.com/microsoft/agent-governance-toolkit
[link_microsoft_sentinel_mcp_overview]: https://learn.microsoft.com/en-us/azure/sentinel/datalake/sentinel-mcp-overview
[link_mikeclueby4_mcp_xdr]: https://github.com/mikeclueby4/mcp-xdr
[link_misp]: https://www.misp-project.org/
[link_mitre_attack]: https://attack.mitre.org/
[link_mobilehackinglab_jadx_mcp_plugin]: https://github.com/mobilehackinglab/jadx-mcp-plugin
[link_mobsf]: https://github.com/MobSF/Mobile-Security-Framework-MobSF
[link_mordavid_bloodhound_mcp_ai]: https://github.com/MorDavid/BloodHound-MCP-AI
[link_morluto_rea]: https://github.com/morluto/rea
[link_mrexodia_ida_pro_mcp]: https://github.com/mrexodia/ida-pro-mcp
[link_msaad00_agent_bom]: https://github.com/msaad00/agent-bom
[link_mytechnotalent_malwarebazaar_mcp]: https://github.com/mytechnotalent/MalwareBazaar_MCP
[link_mythic]: https://github.com/its-a-feature/Mythic
[link_netskope_mcp]: https://docs.netskope.com/en/netskope-copilot-for-mcp-server
[link_nickpending_mcp_recon]: https://github.com/nickpending/mcp-recon
[link_oidebrett_mcpauth]: https://github.com/oidebrett/mcpauth
[link_okta_mcp_server]: https://github.com/okta/okta-mcp-server
[link_opencti]: https://docs.opencti.io/
[link_opencti_mcp_docs]: https://docs.opencti.io/latest/deployment/mcp-server/
[link_operantlabs_operant_mcp]: https://github.com/operantlabs/operant-mcp
[link_orca_mcp_docs]: https://mcp-docs.orca.security/
[link_orcasecurity_orca_skills]: https://github.com/orcasecurity/orca-skills
[link_osv_dev]: https://osv.dev/
[link_owasp_zap]: https://www.zaproxy.org/
[link_paloalto_cortex_mcp]: https://cortex-docs.paloaltonetworks.com/cortex-xsiam/configure-cortex-xsiam/cortex-mcp-server
[link_paloaltonetworks_pan_mcp_relay]: https://github.com/PaloAltoNetworks/pan-mcp-relay
[link_panther_labs_mcp_panther]: https://github.com/panther-labs/mcp-panther
[link_policylayer_intercept]: https://github.com/PolicyLayer/Intercept
[link_pomerium_mcp_app_demo]: https://github.com/pomerium/mcp-app-demo
[link_pomerium_mcp_servers]: https://github.com/pomerium/mcp-servers
[link_pomerium_pomerium]: https://github.com/pomerium/pomerium
[link_portswigger_burp]: https://portswigger.net/burp
[link_portswigger_mcp_server]: https://github.com/PortSwigger/mcp-server
[link_ppcvote_misp_mcp_server]: https://github.com/ppcvote/misp-mcp-server
[link_prisma_airs_mcp_docs]: https://docs.paloaltonetworks.com/ai-runtime-security/activation-and-onboarding/prisma-airs-mcp-server-for-centralized-ai-agent-security/understanding-the-prisma-airs-mcp-server
[link_projectdiscovery_neo_mcp]: https://docs.neo.projectdiscovery.io/integrations/mcp
[link_projectdiscovery_nuclei]: https://github.com/projectdiscovery/nuclei
[link_prompt_security_clawsec]: https://github.com/prompt-security/clawsec
[link_prowler_mcp]: https://github.com/prowler-cloud/prowler
[link_prowler_mcp_docs]: https://docs.prowler.com/getting-started/products/prowler-mcp
[link_pullkitsan_mobsf_mcp]: https://github.com/pullkitsan/mobsf-mcp-server
[link_qianniuspace_mcp_security_audit]: https://github.com/qianniuspace/mcp-security-audit
[link_qualys_cli_mcp]: https://pypi.org/project/qualys-cli-mcp/
[link_rad_security_mcp_server]: https://github.com/rad-security/mcp-server
[link_radareorg_radare2_mcp]: https://github.com/radareorg/radare2-mcp
[link_rapid7_rapid7_bulk_export_mcp]: https://github.com/rapid7/rapid7-bulk-export-mcp
[link_recorded_future_mcp]: https://www.recordedfuture.com/platform/ai
[link_reversethrottle_cortex_mcp]: https://github.com/ReverseThrottle/cortex-mcp
[link_roadrecon]: https://github.com/dirkjanm/ROADtools
[link_roadwy_cve_search_mcp]: https://github.com/roadwy/cve-search_mcp
[link_runreveal_mcp_docs]: https://docs.runreveal.com/reference/model-context-protocol
[link_safedep_vet_docs]: https://github.com/safedep/vet/blob/main/docs/mcp.md
[link_safedep_vet_mcp]: https://github.com/safedep/vet
[link_samvas_dawshund_mcp]: https://github.com/samvas-codes/dawshund_mcp
[link_sanyambassi_ciphertrust_manager_mcp]: https://github.com/sanyambassi/ciphertrust-manager-mcp-server
[link_sanyambassi_thales_cdsp_cakm_mcp]: https://github.com/sanyambassi/thales-cdsp-cakm-mcp-server
[link_sanyambassi_thales_cdsp_crdp_mcp]: https://github.com/sanyambassi/thales-cdsp-crdp-mcp-server
[link_securityfortech_secops_mcp]: https://github.com/securityfortech/secops-mcp
[link_semgrep_dev]: https://semgrep.dev/
[link_semgrep_mcp]: https://github.com/semgrep/mcp
[link_sentinel_gate_sentinelgate]: https://github.com/Sentinel-Gate/Sentinelgate
[link_sentinel_one_purple_mcp]: https://github.com/Sentinel-One/purple-mcp
[link_shaikh_shahid_veracode_mcp]: https://github.com/shaikh-shahid/veracode-mcp-server
[link_shodan]: https://www.shodan.io/
[link_slouchd_cyberchef_api_mcp_server]: https://github.com/slouchd/cyberchef-api-mcp-server
[link_snyk_studio_mcp]: https://github.com/snyk/studio-mcp
[link_socfortress_velociraptor_mcp]: https://github.com/socfortress/velociraptor-mcp-server
[link_socket_mcp]: https://docs.socket.dev/docs/guide-to-socket-mcp
[link_sonarsource_mcp_config_generator]: https://mcp.sonarqube.com/config-generator.html
[link_sonarsource_sonarqube_mcp_server]: https://github.com/SonarSource/sonarqube-mcp-server
[link_splunk_mcp_official]: https://www.splunk.com/en_us/products/model-context-protocol.html
[link_splunk_splunk_mcp_server2]: https://github.com/splunk/splunk-mcp-server2
[link_stackhawk_stackhawk_mcp]: https://github.com/stackhawk/stackhawk-mcp
[link_stacklok_osv_mcp]: https://github.com/StacklokLabs/osv-mcp
[link_stacklok_toolhive]: https://github.com/StacklokLabs/toolhive
[link_stoyky_mitre_attack_mcp]: https://github.com/stoyky/mitre-attack-mcp
[link_sumologic_mcp]: https://www.sumologic.com/help/docs/api/mcp-server/
[link_sysdig_secure_mcp_docs]: https://docs.sysdig.com/en/sysdig-secure/secure-ai/sysdig-mcp-server/
[link_sysdiglabs_sysdig_mcp_server]: https://github.com/sysdiglabs/sysdig-mcp-server
[link_takleb3rry_zitadel_mcp]: https://github.com/takleb3rry/zitadel-mcp
[link_tarhou_tenable_mcp_server]: https://github.com/tarhou/tenable-mcp-server
[link_tenable_hexa_mcp]: https://docs.tenable.com/vulnerability-management/Content/getting-started/hexa-AI-MCP.htm
[link_tenable_sc_mcp]: https://exchange.tenable.com/mcp-servers/tenable-sc-mcp-server/
[link_tensorfeed_mcp_server]: https://github.com/RipperMercs/tensorfeed
[link_thehive]: https://strangebee.com/thehive/
[link_thinkchainai_vulnerability_intelligence_mcp]: https://github.com/thinkchainai/vulnerability-intelligence-mcp
[link_toan203_osv_ui]: https://github.com/toan203/osv-ui
[link_trailofbits_mcp_context_protector]: https://github.com/trailofbits/mcp-context-protector
[link_trailofbits_mcp_context_protector_blog]: https://blog.trailofbits.com/2025/07/28/we-built-the-security-layer-mcp-always-needed/
[link_trivy_dev]: https://trivy.dev/
[link_upwind_mcp_docs]: https://www.upwind.io/feed/introducing-the-upwind-mcp-server-for-runtime-cloud-security
[link_urldna_io]: https://urldna.io
[link_urldna_mcp]: https://github.com/urldna/mcp
[link_velociraptor]: https://docs.velociraptor.app/
[link_veracode]: https://www.veracode.com/
[link_vinayaklatthe_microsoft_security_agent_toolkit]: https://github.com/vinayaklatthe/microsoft-security-agent-toolkit
[link_vinaybhosle_agentstamp]: https://github.com/vinaybhosle/agentstamp
[link_virustotal]: https://www.virustotal.com/
[link_virustotal_mcp]: https://github.com/VirusTotal/virustotal-mcp
[link_volatility3]: https://github.com/volatilityfoundation/volatility3
[link_vulncheck_mcp]: https://github.com/vulncheck-oss/mcp
[link_wazuh]: https://wazuh.com/
[link_wd041216_bit_ironclaw_agent_guard]: https://github.com/wd041216-bit/ironclaw-agent-guard
[link_wiz_mcp_blog]: https://www.wiz.io/blog/introducing-mcp-server-for-wiz
[link_xpn_mythic_mcp]: https://github.com/xpn/mythic_mcp
[link_zaproxy_mcp]: https://www.zaproxy.org/docs/desktop/addons/mcp-integration/
[link_zboralski_ida_headless_mcp]: https://github.com/zboralski/ida-headless-mcp
[link_zeropath_mcp_server]: https://github.com/ZeroPathAI/zeropath-mcp-server
[link_zinja_apktool_mcp]: https://github.com/zinja-coder/apktool-mcp-server
[link_zinja_jadx_ai_mcp]: https://github.com/zinja-coder/jadx-ai-mcp
[link_zitadel]: https://zitadel.com/
[link_zscaler_mcp_server]: https://github.com/zscaler/zscaler-mcp-server
[link_zscaler_mcp_server_docs]: https://zscaler-mcp-server.readthedocs.io/en/latest/guides/configuration.html
[link_zxzinn_opencti_mcp]: https://github.com/zxzinn/opencti-mcp
