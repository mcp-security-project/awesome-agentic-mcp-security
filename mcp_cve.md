# MCP CVE catalogs

Repositories and pages that maintain **structured catalogs of published CVEs** affecting MCP servers, clients, SDKs, gateways, and related tooling — plus a curated index synced from [mcp-cve-project](https://github.com/mcp-security-project/mcp-cve-project). For searchable JSON and per-CVE notes, also see [vulnerablemcp](https://vulnerablemcp.info).

## Contents

- [External catalogs](#external-catalogs)
- [Advisory sources](#advisory-sources)
- [Published CVEs](#published-cves)

---

## External catalogs

| Catalog | Description | Last updated |
| --- | --- | --- |
| [mcp-security-project/mcp-cve-project][link_vermava_mcp_cve_project] | Curated index of **313** MCP-related CVEs with per-CVE notes (`cves/`) and OWASP MCP Top 10 mapping. | [![last commit](https://badgen.net/github/last-commit/mcp-security-project/mcp-cve-project)][link_vermava_mcp_cve_project_commits] |
| [vineethsai/vulnerablemcp][link_vineethsai_vulnerablemcp] | Searchable MCP vulnerability catalog (JSON); many entries map to CVE IDs by affected component. **Site:** [vulnerablemcp.info](https://vulnerablemcp.info) | [![last commit](https://badgen.net/github/last-commit/vineethsai/vulnerablemcp)][link_vineethsai_vulnerablemcp_commits] |

**Contributing:** Submit new catalog repositories via pull request. Submit individual CVE records to [mcp-cve-project](https://github.com/mcp-security-project/mcp-cve-project).

---

## Advisory sources

| Source | Use for |
| --- | --- |
| [OpenCVE — modelcontextprotocol vendor][link_opencve_modelcontextprotocol] | CVE feed for official org packages |
| [GitHub Advisory Database — MCP search][link_github_advisories_mcp_search] | Cross-repo GHSAs mentioning MCP |
| [modelcontextprotocol/python-sdk/security/advisories][link_mcp_python_sdk_advisories] | Official Python SDK advisories |
| [modelcontextprotocol/typescript-sdk/security/advisories][link_mcp_typescript_sdk_advisories] | Official TypeScript SDK advisories |
| [modelcontextprotocol/inspector/security/advisories][link_mcp_inspector_advisories] | MCP Inspector advisories |
| [PYSEC — `mcp` (PyPI)][link_pysec_mcp] | Python package advisory database |

---

## Published CVEs

**313** indexed CVE IDs from [mcp-cve-project](https://github.com/mcp-security-project/mcp-cve-project) as of **catalog synced: 2026-08-25**. Sorted by CVE ID (newest first). Fixed-version column reflects vendor advisory text where known; verify against your deployment.

| CVE | Affected component | Issue (OWASP MCP Top 10 category) | Fixed in | Links |
| --- | --- | --- | --- | --- |
| CVE-2026-7738 | doc-tools-mcp | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7738] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7738] |
| CVE-2026-7730 | `privsim/mcp-test-runner` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7730] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7730] |
| CVE-2026-7729 | directus-mcp | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7729] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7729] |
| CVE-2026-7728 | mcp-rtfm | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7728] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7728] |
| CVE-2026-7715 | mcp-server-arangodb | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7715] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7715] |
| CVE-2026-7664 | IBM Langflow Streamable MCP authorization bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_7664] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7664] |
| CVE-2026-7663 | IBM Langflow Streamable MCP authorization bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_7663] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7663] |
| CVE-2026-7653 | mcp-server-rijksmuseum | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7653] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7653] |
| CVE-2026-7628 | mcp-code-review-server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7628] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7628] |
| CVE-2026-7627 | metatrader-4-mcp | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7627] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7627] |
| CVE-2026-7600 | mcp-server-yii2 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7600] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7600] |
| CVE-2026-7599 | terminalcraft | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7599] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7599] |
| CVE-2026-7594 | DungeonMind-MCP | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7594] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7594] |
| CVE-2026-7593 | command-executor-mcp-server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7593] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7593] |
| CVE-2026-7591 | `astro-mcp-server` (TimBroddin) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7591] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7591] |
| CVE-2026-7446 | mcp-server-semgrep | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7446] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7446] |
| CVE-2026-7443 | mcp-dnstwist | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7443] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7443] |
| CVE-2026-7417 | Algovate `xhs-mcp` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7417] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7417] |
| CVE-2026-7386 | mail-mcp-bridge | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7386] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7386] |
| CVE-2026-7272 | matlab-mcp-server | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7272] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7272] |
| CVE-2026-7237 | scaffold-mcp | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7237] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7237] |
| CVE-2026-7221 | TencentCloudBase CloudBase-MCP | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7221] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7221] |
| CVE-2026-7206 | sqlite-mcp | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7206] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7206] |
| CVE-2026-7205 | papers-mcp-server | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7205] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7205] |
| CVE-2026-7158 | dmitryglhf `mcp-url-downloader` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7158] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7158] |
| CVE-2026-7157 | disler `aider-mcp-server` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7157] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7157] |
| CVE-2026-7150 | dh1011 `auto-favicon` MCP server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7150] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7150] |
| CVE-2026-7147 | JoeCastrom `mcp-chat-studio` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7147] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7147] |
| CVE-2026-7146 | AlejandroArciniegas `mcp-data-vis` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7146] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7146] |
| CVE-2026-7061 | chatgpt-mcp-server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7061] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7061] |
| CVE-2026-6599 | Langflow | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_6599] · [mcp-cve-project][link_mcp_cve_project_cve_2026_6599] |
| CVE-2026-6494 | AAP MCP server log injection via toolsetroute | Lack of Audit and Telemetry | See NVD | [NVD][link_nvd_cve_2026_6494] · [mcp-cve-project][link_mcp_cve_project_cve_2026_6494] |
| CVE-2026-63119 | MCP Ruby SDK (`modelcontextprotocol/ruby-sdk`): stdio unbounded line buffer DoS | Insufficient Authentication & Authorization | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_63119] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63119] |
| CVE-2026-63118 | MCP Ruby SDK (`modelcontextprotocol/ruby-sdk`): Streamable HTTP DNS rebinding | Insufficient Authentication & Authorization | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_63118] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63118] |
| CVE-2026-61459 | `mcp-server-kubernetes` structured tools `--server` argument injection / bearer token exfiltration | Privilege Escalation via Scope Creep | ≥ 3.9.0 | [NVD][link_nvd_cve_2026_61459] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61459] |
| CVE-2026-6130 | Chatbox StdioClientTransport MCP config args/env code execution | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_6130] · [mcp-cve-project][link_mcp_cve_project_cve_2026_6130] |
| CVE-2026-6108 | MaxKB MCP node OS command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_6108] · [mcp-cve-project][link_mcp_cve_project_cve_2026_6108] |
| CVE-2026-59950 | MCP Python SDK (`mcp`): deprecated WebSocket transport Host/Origin validation gap | Insufficient Authentication & Authorization | ≥ 1.28.1 | [NVD][link_nvd_cve_2026_59950] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59950] |
| CVE-2026-58446 | Presenton bundled MCP server unauthenticated /mcp access | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_58446] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58446] |
| CVE-2026-5833 | mcp-server-taskwarrior | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5833] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5833] |
| CVE-2026-58171 | Vibe-Trading path traversal affecting MCP/agent workflow storage | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_58171] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58171] |
| CVE-2026-58168 | DeepTutor MCP tool authorization bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_58168] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58168] |
| CVE-2026-58057 | Flowise Custom MCP Windows env-var denylist bypass | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_58057] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58057] |
| CVE-2026-57922 | JetBrains YouTrack project settings disclosure via MCP | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_57922] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57922] |
| CVE-2026-57300 | Jenkins MCP Server Plugin missing permission check | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_57300] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57300] |
| CVE-2026-56274 | Flowise Custom MCP Server command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_56274] · [mcp-cve-project][link_mcp_cve_project_cve_2026_56274] |
| CVE-2026-5607 | imprvhub `mcp-browser-agent` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5607] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5607] |
| CVE-2026-55887 | Docker MCP Gateway (`github.com/docker/mcp-gateway`) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_55887] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55887] |
| CVE-2026-54842 | Royal MCP missing authorization | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_54842] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54842] |
| CVE-2026-5470 | Google-Research-MCP (SSRF in `extractContent`) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5470] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5470] |
| CVE-2026-54449 | LangBot | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_54449] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54449] |
| CVE-2026-54309 | @n8n/mcp-browser unauthenticated HTTP transport | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_54309] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54309] |
| CVE-2026-54030 | LibreChat MCP OAuth resource validation issue | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_54030] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54030] |
| CVE-2026-53840 | OpenClaw Streamable HTTP MCP custom-header leak on redirects | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_53840] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53840] |
| CVE-2026-53820 | OpenClaw bundled MCP exec denylist bypass | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_53820] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53820] |
| CVE-2026-53818 | OpenClaw MCP loopback owner-only policy bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_53818] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53818] |
| CVE-2026-53814 | OpenClaw hook-triggered MCP loopback privilege escalation | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_53814] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53814] |
| CVE-2026-53766 | chrome-devtools-mcp workspace path validation issue | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_53766] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53766] |
| CVE-2026-5323 | a11y-mcp | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5323] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5323] |
| CVE-2026-52870 | MCP Python SDK (`mcp`): experimental task handlers cross-client access | Insufficient Authentication & Authorization | ≥ 1.27.2 | [NVD][link_nvd_cve_2026_52870] · [mcp-cve-project][link_mcp_cve_project_cve_2026_52870] · [GHSA][link_ghsa_hvrp_rf83_w775] |
| CVE-2026-52869 | MCP Python SDK (`mcp`): HTTP session auth bypass (`SseServerTransport` / Streamable HTTP) | Insufficient Authentication & Authorization | ≥ 1.27.2 | [NVD][link_nvd_cve_2026_52869] · [mcp-cve-project][link_mcp_cve_project_cve_2026_52869] · [GHSA][link_ghsa_jpw9_pfvf_9f58] |
| CVE-2026-5059 | `aws-mcp` / aws-mcp-server (command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5059] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5059] |
| CVE-2026-5058 | `aws-mcp` / aws-mcp-server (unauthenticated command injection) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_5058] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5058] |
| CVE-2026-5029 | Code Runner MCP Server | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_5029] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5029] |
| CVE-2026-50287 | @agenticmail/mcp unauthenticated Streamable HTTP endpoint | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_50287] · [mcp-cve-project][link_mcp_cve_project_cve_2026_50287] |
| CVE-2026-5023 | `codebase-mcp` (OS command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5023] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5023] |
| CVE-2026-50143 | `@apify/actors-mcp-server` Actor `webServerMcpPath` authority injection / Apify token leak | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_50143] · [mcp-cve-project][link_mcp_cve_project_cve_2026_50143] |
| CVE-2026-5007 | `mcp-docs-rag` (OS command injection) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_5007] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5007] |
| CVE-2026-49357 | line-desktop-mcp unauthenticated HTTP mode chat access | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_49357] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49357] |
| CVE-2026-49291 | mcp-memory-service OAuth read-scope tools/call bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_49291] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49291] |
| CVE-2026-49257 | mcp-pinot unauthenticated 0.0.0.0 HTTP MCP server | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_49257] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49257] |
| CVE-2026-48989 | Windows-MCP unauthenticated HTTP control plane / PowerShell execution | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_48989] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48989] |
| CVE-2026-48814 | Network-AI MCP SSE unauthenticated tool invocation | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_48814] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48814] |
| CVE-2026-48787 | gin-vue-admin MCP management code-generation command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_48787] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48787] |
| CVE-2026-48774 | ProxySQL GenAI/MCP run_sql_readonly multi-statement bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_48774] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48774] |
| CVE-2026-48710 | Starlette / FastAPI-based MCP and AI gateways | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_48710] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48710] |
| CVE-2026-48529 | GitHub MCP Server HTTP lockdown-mode repo access cache issue | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_48529] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48529] · [GHSA][link_ghsa_pjp5_fpmr_3349] |
| CVE-2026-47751 | Anthropic Claude Code Action (`claude-code-action`) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_47751] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47751] |
| CVE-2026-47388 | NocoDB MCP token attachment ownership bypass / file read | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_47388] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47388] |
| CVE-2026-47250 | mcp-server-kubernetes kubectl_generic unsafe flags / token exfiltration | Privilege Escalation via Scope Creep | ≥ 3.7.0 | [NVD][link_nvd_cve_2026_47250] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47250] · [GHSA][link_ghsa_6mx4_4h42_r8vh] |
| CVE-2026-46549 | NocoDB MCP OAuth token scope bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_46549] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46549] |
| CVE-2026-46519 | mcp-server-kubernetes | Privilege Escalation via Scope Creep | ≥ 3.6.0 | [NVD][link_nvd_cve_2026_46519] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46519] · [GHSA][link_ghsa_cr22_wjx7_2w6m] |
| CVE-2026-46341 | @apify/actors-mcp-server | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_46341] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46341] |
| CVE-2026-46339 | 9router MCP routes | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_46339] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46339] |
| CVE-2026-45805 | @penpot/mcp | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_45805] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45805] |
| CVE-2026-45781 | MCP Registry | Privilege Escalation via Scope Creep | ≥ 1.7.9 | [NVD][link_nvd_cve_2026_45781] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45781] |
| CVE-2026-45707 | n8n-mcp multi-tenant HTTP transport authentication gap | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_45707] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45707] |
| CVE-2026-45609 | Spring AI mcp-security missing MCP-spec SSRF mitigations | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_45609] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45609] |
| CVE-2026-45582 | n8n-MCP (`czlonkowski/n8n-mcp`) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_45582] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45582] |
| CVE-2026-45555 | Roslyn CodeLens MCP Server arbitrary DiagnosticAnalyzer load | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_45555] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45555] |
| CVE-2026-45001 | OpenClaw | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_45001] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45001] |
| CVE-2026-44998 | OpenClaw | Tool Poisoning | See NVD | [NVD][link_nvd_cve_2026_44998] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44998] |
| CVE-2026-44995 | OpenClaw | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_44995] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44995] |
| CVE-2026-4496 | Git-MCP-Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_4496] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4496] |
| CVE-2026-44895 | GitLab MCP Server (HTTP transport without authentication) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_44895] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44895] |
| CVE-2026-44830 | Nocturne Memory MCP server (missing auth when token unset) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_44830] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44830] |
| CVE-2026-44717 | MCP Calculate Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_44717] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44717] |
| CVE-2026-44694 | `n8n-mcp` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_44694] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44694] |
| CVE-2026-44653 | LibreChat — `GET /api/mcp/servers` returns plaintext `apiKey.key` and `oauth.client_secret` to VIEW-only users | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_44653] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44653] |
| CVE-2026-44450 | Lumiverse (MCP server command allowlist bypass) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_44450] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44450] |
| CVE-2026-44430 | MCP Registry | Command Injection & Execution | ≥ 1.7.7 | [NVD][link_nvd_cve_2026_44430] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44430] |
| CVE-2026-44429 | MCP Registry | Command Injection & Execution | ≥ 1.7.7 | [NVD][link_nvd_cve_2026_44429] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44429] |
| CVE-2026-44428 | MCP Registry | Insufficient Authentication & Authorization | ≥ 1.7.6 | [NVD][link_nvd_cve_2026_44428] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44428] |
| CVE-2026-44427 | MCP Registry | Insufficient Authentication & Authorization | ≥ 1.7.5 | [NVD][link_nvd_cve_2026_44427] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44427] |
| CVE-2026-44336 | PraisonAI MCP tools/call path traversal to RCE via .pth injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_44336] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44336] |
| CVE-2026-44284 | FastGPT (MCP tool URL SSRF gap) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_44284] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44284] |
| CVE-2026-44118 | OpenClaw (loopback MCP owner-context spoofing) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_44118] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44118] |
| CVE-2026-43992 | JunoClaw | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_43992] · [mcp-cve-project][link_mcp_cve_project_cve_2026_43992] |
| CVE-2026-43901 | Wireshark MCP (`wireshark-mcp`) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_43901] · [mcp-cve-project][link_mcp_cve_project_cve_2026_43901] |
| CVE-2026-4339 | Mattermost Agents plugin MCP server internal/private IP validation issue | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_4339] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4339] |
| CVE-2026-4270 | AWS API MCP Server (`awslabs/mcp`):`awslabs.aws-api-mcp-server` (pip) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_4270] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4270] |
| CVE-2026-42559 | MCP Rust SDK (`rmcp` crate): Streamable HTTP server transport DNS rebinding | Insufficient Authentication & Authorization | ≥ 1.4.0 | [NVD][link_nvd_cve_2026_42559] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42559] |
| CVE-2026-42449 | `n8n-mcp` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_42449] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42449] |
| CVE-2026-42282 | `n8n-mcp` | Lack of Audit and Telemetry | See NVD | [NVD][link_nvd_cve_2026_42282] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42282] |
| CVE-2026-42271 | LiteLLM MCP server preview endpoints | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_42271] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42271] |
| CVE-2026-42260 | Open-WebSearch MCP server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_42260] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42260] |
| CVE-2026-42236 | `n8n` (MCP OAuth client registration DoS) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_42236] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42236] |
| CVE-2026-42230 | `n8n` (MCP OAuth open redirect) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_42230] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42230] |
| CVE-2026-42073 | OpenClaude MCP OAuth callback CSRF state bypass / DoS | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_42073] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42073] |
| CVE-2026-4198 | mcp-server-auto-commit | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_4198] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4198] |
| CVE-2026-41495 | `n8n-mcp` | Lack of Audit and Telemetry | See NVD | [NVD][link_nvd_cve_2026_41495] · [mcp-cve-project][link_mcp_cve_project_cve_2026_41495] |
| CVE-2026-40933 | Flowise (MCP adapter command injection via unsafe stdio serialization) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_40933] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40933] |
| CVE-2026-40775 | Royal MCP unauthenticated broken access control | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_40775] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40775] |
| CVE-2026-40608 | Next AI Draw.io embedded MCP HTTP sidecar | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_40608] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40608] |
| CVE-2026-40576 | `excel-mcp-server` (path traversal in remote file handlers) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_40576] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40576] |
| CVE-2026-40159 | PraisonAI MCP integration:`PraisonAI` (pip) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_40159] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40159] |
| CVE-2026-39987 | Marimo Python notebook server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39987] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39987] |
| CVE-2026-39974 | `n8n-mcp` (authenticated SSRF in multi-tenant HTTP mode) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39974] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39974] |
| CVE-2026-39885 | FrontMCP / `mcp-from-openapi` (OpenAPI `$ref` SSRF):`mcp-from-openapi` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39885] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39885] |
| CVE-2026-39884 | `mcp-server-kubernetes` (`port_forward` argument injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39884] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39884] |
| CVE-2026-39313 | `mcp-framework` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39313] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39313] |
| CVE-2026-35577 | Apollo MCP Server (`apollo-mcp-server`; Streamable HTTP Host validation) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_35577] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35577] |
| CVE-2026-35568 | MCP Java SDK (`io.modelcontextprotocol.sdk`):`io.modelcontextprotocol.sdk:mcp-core` (maven) | Insufficient Authentication & Authorization | ≥ 1.0.0 | [NVD][link_nvd_cve_2026_35568] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35568] |
| CVE-2026-35402 | mcp-neo4j-cypher | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_35402] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35402] |
| CVE-2026-35394 | @mobilenext/mobile-mcp arbitrary Android intent execution | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_35394] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35394] |
| CVE-2026-35228 | Oracle MCP Server Helper Tool (SQL injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_35228] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35228] |
| CVE-2026-34953 | PraisonAI MCP server authentication bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_34953] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34953] |
| CVE-2026-34742 | MCP Go SDK (`github.com/modelcontextprotocol/go-sdk`):`github.com/modelcontextprotocol/go-sdk` (go) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_34742] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34742] |
| CVE-2026-34476 | Apache SkyWalking MCP SSRF via SW-URL header | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_34476] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34476] |
| CVE-2026-34237 | MCP Java SDK (`io.modelcontextprotocol.sdk`) (wildcard CORS):`io.modelcontextprotocol.sdk:mcp-core` (maven) | Insufficient Authentication & Authorization | ≥ 0.83.0 / 1.0.1 / 1.1.1 | [NVD][link_nvd_cve_2026_34237] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34237] |
| CVE-2026-34200 | Nhost CLI MCP server (authentication bypass when network-exposed) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_34200] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34200] |
| CVE-2026-34163 | FastGPT (MCP tools endpoint auth gap) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_34163] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34163] |
| CVE-2026-33989 | @mobilenext/mobile-mcp | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_33989] · [mcp-cve-project][link_mcp_cve_project_cve_2026_33989] |
| CVE-2026-33980 | Azure Data Explorer MCP Server (KQL injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_33980] · [mcp-cve-project][link_mcp_cve_project_cve_2026_33980] |
| CVE-2026-33946 | MCP Ruby SDK (`modelcontextprotocol/ruby-sdk`) | Token Mismanagement & Secret Exposure | ≥ 0.9.2 | [NVD][link_nvd_cve_2026_33946] · [mcp-cve-project][link_mcp_cve_project_cve_2026_33946] |
| CVE-2026-33252 | MCP Go SDK (HTTP transport cross-site tool execution / CSRF class):`github.com/modelcontextprotocol/go-sdk` (go) | Insufficient Authentication & Authorization | ≥ 1.4.1 | [NVD][link_nvd_cve_2026_33252] · [mcp-cve-project][link_mcp_cve_project_cve_2026_33252] |
| CVE-2026-33224 | Bisheng (authenticated RCE via MCP stdio server configuration) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_33224] · [mcp-cve-project][link_mcp_cve_project_cve_2026_33224] |
| CVE-2026-33060 | CKAN MCP Server SSRF via base_url parameter | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_33060] · [mcp-cve-project][link_mcp_cve_project_cve_2026_33060] |
| CVE-2026-33032 | nginx-ui MCP integration:`github.com/0xJacky/Nginx-UI` (go) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_33032] · [mcp-cve-project][link_mcp_cve_project_cve_2026_33032] |
| CVE-2026-33010 | `mcp-memory-service` (cross-origin memory read/write/delete) | Context Injection & Over-Sharing | See NVD | [NVD][link_nvd_cve_2026_33010] · [mcp-cve-project][link_mcp_cve_project_cve_2026_33010] |
| CVE-2026-32871 | FastMCP OpenAPI Provider (SSRF + path traversal via unencoded path params) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_32871] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32871] |
| CVE-2026-32625 | LibreChat — MCP server URL `${VAR}` interpolation exfiltrates `JWT_SECRET`, `CREDS_KEY`, `CREDS_IV`, `MONGO_URI` | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_32625] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32625] |
| CVE-2026-32247 | Graphiti MCP server (`getzep/graphiti`) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_32247] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32247] |
| CVE-2026-32211 | Azure MCP Server | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_32211] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32211] |
| CVE-2026-32112 | `ha-mcp` (OAuth consent f-string injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_32112] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32112] |
| CVE-2026-32111 | ha-mcp OAuth consent ha_url SSRF | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_32111] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32111] |
| CVE-2026-31951 | LibreChat | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_31951] · [mcp-cve-project][link_mcp_cve_project_cve_2026_31951] |
| CVE-2026-31945 | LibreChat MCP server-side request forgery via DNS resolution | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_31945] · [mcp-cve-project][link_mcp_cve_project_cve_2026_31945] |
| CVE-2026-31944 | LibreChat (MCP OAuth callback account takeover) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_31944] · [mcp-cve-project][link_mcp_cve_project_cve_2026_31944] |
| CVE-2026-30861 | WeKnora | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_30861] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30861] |
| CVE-2026-30856 | WeKnora MCP tool execution hijacking via ambiguous naming | Tool Poisoning | See NVD | [NVD][link_nvd_cve_2026_30856] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30856] |
| CVE-2026-30635 | automagik-genie MCP Server (command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_30635] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30635] |
| CVE-2026-30625 | Upsonic (unauthenticated RCE via MCP server/task creation) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_30625] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30625] |
| CVE-2026-30624 | Agent Zero (RCE via external MCP stdio JSON configuration) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_30624] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30624] |
| CVE-2026-30623 | LiteLLM (authenticated RCE via MCP stdio server creation) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_30623] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30623] |
| CVE-2026-30618 | Fay Digital Human Framework (unauthenticated RCE via MCP adapter stdio) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_30618] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30618] |
| CVE-2026-30617 | LangChain-ChatChat (unauthenticated RCE via MCP STDIO server configuration) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_30617] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30617] |
| CVE-2026-30616 | Jaaz (RCE via MCP STDIO handling when network-exposed) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_30616] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30616] |
| CVE-2026-30615 | Windsurf (prompt injection leading to unauthorized MCP stdio registration / local RCE) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_30615] · [mcp-cve-project][link_mcp_cve_project_cve_2026_30615] |
| CVE-2026-29787 | `mcp-memory-service` (`/api/health/detailed` information disclosure) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_29787] · [mcp-cve-project][link_mcp_cve_project_cve_2026_29787] |
| CVE-2026-29783 | GitHub Copilot CLI | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_29783] · [mcp-cve-project][link_mcp_cve_project_cve_2026_29783] |
| CVE-2026-27896 | MCP Go SDK (case-sensitivity / JSON-RPC parsing inconsistency):`github.com/modelcontextprotocol/go-sdk` (go) | Software Supply Chain Attacks & Dependency Tampering | ≥ 1.3.1 | [NVD][link_nvd_cve_2026_27896] · [mcp-cve-project][link_mcp_cve_project_cve_2026_27896] |
| CVE-2026-27826 | MCP Atlassian (`mcp-atlassian`) (SSRF via unvalidated URL headers):`mcp-atlassian` (pip) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_27826] · [mcp-cve-project][link_mcp_cve_project_cve_2026_27826] |
| CVE-2026-27825 | MCP Atlassian (`mcp-atlassian`) (arbitrary file write / RCE) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_27825] · [mcp-cve-project][link_mcp_cve_project_cve_2026_27825] |
| CVE-2026-27735 | `mcp-server-git` (`git_add` path traversal; stage files outside repo) | Privilege Escalation via Scope Creep | ≥ 2026.1.14 | [NVD][link_nvd_cve_2026_27735] · [mcp-cve-project][link_mcp_cve_project_cve_2026_27735] |
| CVE-2026-27203 | eBay API MCP Server environment variable injection | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_27203] · [mcp-cve-project][link_mcp_cve_project_cve_2026_27203] |
| CVE-2026-27124 | FastMCP (`PrefectHQ/fastmcp`) (OAuth consent verification bypass / confused deputy) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_27124] · [mcp-cve-project][link_mcp_cve_project_cve_2026_27124] |
| CVE-2026-26118 | Azure MCP Server (`azure.mcp`) (SSRF):`Azure.Mcp` (nuget) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_26118] · [mcp-cve-project][link_mcp_cve_project_cve_2026_26118] |
| CVE-2026-26029 | `sf-mcp-server` (command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_26029] · [mcp-cve-project][link_mcp_cve_project_cve_2026_26029] |
| CVE-2026-26015 | DocsGPT (RCE via tampered MCP transport switching to hidden stdio configuration) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_26015] · [mcp-cve-project][link_mcp_cve_project_cve_2026_26015] |
| CVE-2026-25905 | mcp-run-python | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_25905] · [mcp-cve-project][link_mcp_cve_project_cve_2026_25905] |
| CVE-2026-25904 | mcp-run-python / Pydantic-AI MCP Run Python | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_25904] · [mcp-cve-project][link_mcp_cve_project_cve_2026_25904] |
| CVE-2026-25650 | MCP Salesforce Connector (`MCP-Salesforce` / `mcp-salesforce-connector`) (auth token disclosure):`mcp-salesforce-connector` (pip) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_25650] · [mcp-cve-project][link_mcp_cve_project_cve_2026_25650] |
| CVE-2026-25546 | Godot MCP | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_25546] · [mcp-cve-project][link_mcp_cve_project_cve_2026_25546] |
| CVE-2026-25536 | MCP TypeScript SDK (cross-client data leak via shared server/transport reuse) | Context Injection & Over-Sharing | ≥ 1.26.0 | [NVD][link_nvd_cve_2026_25536] · [mcp-cve-project][link_mcp_cve_project_cve_2026_25536] · [GHSA][link_ghsa_345p_7cg4_v4c7] |
| CVE-2026-23882 | Blinko MCP server creation function | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_23882] · [mcp-cve-project][link_mcp_cve_project_cve_2026_23882] |
| CVE-2026-23744 | MCPJam Inspector (unauthenticated RCE via exposed listener) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_23744] · [mcp-cve-project][link_mcp_cve_project_cve_2026_23744] |
| CVE-2026-23523 | Dive MCP Host Desktop Application | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_23523] · [mcp-cve-project][link_mcp_cve_project_cve_2026_23523] |
| CVE-2026-22793 | 5ire MCP client (ECharts option parsing → RCE) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_22793] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22793] |
| CVE-2026-22792 | 5ire Desktop MCP client (unsafe HTML rendering → arbitrary JS execution):`5ire` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_22792] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22792] |
| CVE-2026-22785 | `@orval/mcp` (Orval MCP server generation from OpenAPI) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_22785] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22785] |
| CVE-2026-22688 | WeKnora (untrusted MCP stdio input) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_22688] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22688] |
| CVE-2026-22252 | LibreChat (untrusted MCP stdio input; cross-referenced in OX advisory) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_22252] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22252] |
| CVE-2026-21852 | Claude Code (Anthropic agentic coding tool) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_21852] · [mcp-cve-project][link_mcp_cve_project_cve_2026_21852] |
| CVE-2026-2178 | `xcode-mcp-server` (command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_2178] · [mcp-cve-project][link_mcp_cve_project_cve_2026_2178] |
| CVE-2026-21518 | Microsoft Visual Studio Code and GitHub Copilot (`mcp.json` handling) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_21518] · [mcp-cve-project][link_mcp_cve_project_cve_2026_21518] |
| CVE-2026-20205 | Splunk MCP Server | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_20205] · [mcp-cve-project][link_mcp_cve_project_cve_2026_20205] |
| CVE-2026-1721 | Cloudflare `agents` SDK AI Playground OAuth callback | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_1721] · [mcp-cve-project][link_mcp_cve_project_cve_2026_1721] |
| CVE-2026-13524 | Cherry Studio MCP OAuth local callback issue | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_13524] · [mcp-cve-project][link_mcp_cve_project_cve_2026_13524] |
| CVE-2026-13489 | xiaozhi-esp32 MCP response handler validation issue | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_13489] · [mcp-cve-project][link_mcp_cve_project_cve_2026_13489] |
| CVE-2026-13341 | Kong Konnect MCP server (`mcp-konnect`) indirect prompt injection | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_13341] · [mcp-cve-project][link_mcp_cve_project_cve_2026_13341] |
| CVE-2026-12958 | Amazon Q Developer / Language Servers for AWS (symlink write outside workspace trust boundary) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_12958] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12958] |
| CVE-2026-12957 | Amazon Q Developer / Language Servers for AWS (`.amazonq/mcp.json` auto-execution) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_12957] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12957] |
| CVE-2026-12798 | LiteLLM OpenAPI-to-MCP generator SSRF | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_12798] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12798] |
| CVE-2026-12774 | LiteLLM MCP connection testing SSRF | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_12774] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12774] |
| CVE-2026-12773 | LiteLLM MCP Proxy improper authentication | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_12773] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12773] |
| CVE-2026-12537 | Google Gemini CLI / `run-gemini-cli` GitHub Action | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_12537] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12537] |
| CVE-2026-12112 | foreman-mcp-server session hijack via non-secret session IDs | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_12112] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12112] |
| CVE-2026-11719 | MCP Toolbox for Databases protocol-version scope bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_11719] · [mcp-cve-project][link_mcp_cve_project_cve_2026_11719] |
| CVE-2026-11624 | MCP Origin/Host validation gap for DNS rebinding controls | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_11624] · [mcp-cve-project][link_mcp_cve_project_cve_2026_11624] |
| CVE-2026-10789 | Autodesk Fusion Desktop MCP extension arbitrary code execution | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_10789] · [mcp-cve-project][link_mcp_cve_project_cve_2026_10789] |
| CVE-2026-10280 | mcpilot MCP API call endpoint SSRF via serverBaseUrl | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_10280] · [mcp-cve-project][link_mcp_cve_project_cve_2026_10280] |
| CVE-2026-10277 | mcp-google-workspace Gmail saveToDisk improper access controls | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_10277] · [mcp-cve-project][link_mcp_cve_project_cve_2026_10277] |
| CVE-2026-0758 | mcp-server-siri-shortcuts | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_0758] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0758] |
| CVE-2026-0757 | MCP Manager for Claude Desktop | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_0757] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0757] |
| CVE-2026-0756 | `github-kanban-mcp-server` (unauthenticated RCE / command injection) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_0756] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0756] |
| CVE-2026-0755 | `gemini-mcp-tool` (command injection via unsafe shell execution) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_0755] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0755] |
| CVE-2026-0621 | MCP TypeScript SDK (`UriTemplate` ReDoS) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_0621] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0621] |
| CVE-2025-9654 | mcp-ssh command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_9654] · [mcp-cve-project][link_mcp_cve_project_cve_2025_9654] |
| CVE-2025-9611 | Microsoft Playwright MCP Server (`@playwright/mcp`):`@playwright/mcp` (npm) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_9611] · [mcp-cve-project][link_mcp_cve_project_cve_2025_9611] |
| CVE-2025-8943 | Flowise Custom MCPs | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_8943] · [mcp-cve-project][link_mcp_cve_project_cve_2025_8943] |
| CVE-2025-8665 | agno MCPTools/MultiMCPTools command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_8665] · [mcp-cve-project][link_mcp_cve_project_cve_2025_8665] |
| CVE-2025-71336 | Flowise Custom MCP unsandboxed RCE | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_71336] · [mcp-cve-project][link_mcp_cve_project_cve_2025_71336] |
| CVE-2025-69443 | Archon (`coleam00/archon` research OS / UI) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_69443] · [mcp-cve-project][link_mcp_cve_project_cve_2025_69443] |
| CVE-2025-69256 | `@serverless/mcp` (command injection in Serverless Framework MCP feature) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_69256] · [mcp-cve-project][link_mcp_cve_project_cve_2025_69256] |
| CVE-2025-69196 | FastMCP (OAuth resource scope bypass) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_69196] · [mcp-cve-project][link_mcp_cve_project_cve_2025_69196] |
| CVE-2025-68669 | 5ire MCP client (Mermaid `securityLevel: loose` → RCE) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_68669] · [mcp-cve-project][link_mcp_cve_project_cve_2025_68669] |
| CVE-2025-68433 | Zed IDE malicious MCP settings.json arbitrary code execution | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2025_68433] · [mcp-cve-project][link_mcp_cve_project_cve_2025_68433] |
| CVE-2025-68145 | `mcp-server-git` (repository boundary bypass via `--repository`) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_68145] · [mcp-cve-project][link_mcp_cve_project_cve_2025_68145] |
| CVE-2025-68144 | `mcp-server-git` (argument injection in git operations) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_68144] · [mcp-cve-project][link_mcp_cve_project_cve_2025_68144] |
| CVE-2025-68143 | `mcp-server-git` (`git_init` arbitrary path) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_68143] · [mcp-cve-project][link_mcp_cve_project_cve_2025_68143] |
| CVE-2025-67366 | `@sylphxltd/filesystem-mcp` (path traversal / symlink bypass) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_67366] · [mcp-cve-project][link_mcp_cve_project_cve_2025_67366] |
| CVE-2025-66689 | Zen MCP Server (path traversal) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_66689] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66689] |
| CVE-2025-66580 | Dive MCP Host (Mermaid XSS → malicious MCP config / RCE) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2025_66580] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66580] |
| CVE-2025-66454 | Arcade MCP (`arcade-mcp`) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_66454] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66454] |
| CVE-2025-66416 | MCP Python SDK (`mcp`):`mcp` (pip) | Insufficient Authentication & Authorization | ≥ 1.23.0 | [NVD][link_nvd_cve_2025_66416] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66416] · [GHSA][link_ghsa_9h52_p55h_vw2f] |
| CVE-2025-66414 | MCP TypeScript SDK (`@modelcontextprotocol/sdk`):`@modelcontextprotocol/sdk` (npm) | Insufficient Authentication & Authorization | ≥ 1.24.0 | [NVD][link_nvd_cve_2025_66414] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66414] · [GHSA][link_ghsa_w48q_cv73_mx4w] |
| CVE-2025-66404 | `mcp-server-kubernetes` (`exec_in_pod` command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_66404] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66404] |
| CVE-2025-66401 | `mcp-watch` (command injection via `cloneRepo` URL) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_66401] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66401] |
| CVE-2025-66336 | Apache Doris MCP Server SQL injection in metadata query path | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_66336] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66336] |
| CVE-2025-66335 | Apache Doris MCP Server (`doris-mcp-server`; PyPI) (SQL injection via MCP query interface) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_66335] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66335] |
| CVE-2025-66222 | DeepChat (`deepchat`; Electron app) — Stored XSS in Mermaid renderer escalated to RCE via MCP server registration | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2025_66222] · [mcp-cve-project][link_mcp_cve_project_cve_2025_66222] |
| CVE-2025-65720 | GPT Researcher (unauthenticated RCE via malicious MCP stdio configuration) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2025_65720] · [mcp-cve-project][link_mcp_cve_project_cve_2025_65720] |
| CVE-2025-65719 | Open Source Kubectl MCP Server | Token Mismanagement & Secret Exposure | ≥ 1.2.0 | [NVD][link_nvd_cve_2025_65719] · [mcp-cve-project][link_mcp_cve_project_cve_2025_65719] |
| CVE-2025-65513 | `fetch-mcp` (MCP fetch / URL retrieval server; often referenced as MCP fetch server) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2025_65513] · [mcp-cve-project][link_mcp_cve_project_cve_2025_65513] |
| CVE-2025-6515 | `oatpp-mcp` (oatpp MCP SSE endpoint) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2025_6515] · [mcp-cve-project][link_mcp_cve_project_cve_2025_6515] |
| CVE-2025-6514 | `mcp-remote` (npm) | Token Mismanagement & Secret Exposure | ≥ 0.1.16 | [NVD][link_nvd_cve_2025_6514] · [mcp-cve-project][link_mcp_cve_project_cve_2025_6514] · [GHSA][link_ghsa_6xpm_ggf7_wc3p] |
| CVE-2025-64443 | Docker MCP Gateway:Docker MCP Plugin / Docker MCP Gateway:`github.com/docker/mcp-gateway` (go) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_64443] · [mcp-cve-project][link_mcp_cve_project_cve_2025_64443] |
| CVE-2025-64340 | FastMCP (`fastmcp` on PyPI): Windows `fastmcp install` command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_64340] · [mcp-cve-project][link_mcp_cve_project_cve_2025_64340] |
| CVE-2025-64132 | Jenkins MCP Server Plugin (missing permission checks in multiple tools) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_64132] · [mcp-cve-project][link_mcp_cve_project_cve_2025_64132] |
| CVE-2025-64109 | Cursor CLI Beta (command injection class) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_64109] · [mcp-cve-project][link_mcp_cve_project_cve_2025_64109] |
| CVE-2025-64106 | Cursor (MCP server install input validation) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_64106] · [mcp-cve-project][link_mcp_cve_project_cve_2025_64106] |
| CVE-2025-63604 | `mcp-server-aws-resources-python` (code injection / AWS credential exposure) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_63604] · [mcp-cve-project][link_mcp_cve_project_cve_2025_63604] |
| CVE-2025-63603 | MCP Data Science Server (`reading-plus-ai/mcp-server-data-exploration`) (unsafe `exec` / code execution) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_63603] · [mcp-cve-project][link_mcp_cve_project_cve_2025_63603] |
| CVE-2025-62801 | FastMCP (`install cursor` command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_62801] · [mcp-cve-project][link_mcp_cve_project_cve_2025_62801] |
| CVE-2025-62800 | FastMCP (reflected XSS in OAuth callback) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_62800] · [mcp-cve-project][link_mcp_cve_project_cve_2025_62800] |
| CVE-2025-61685 | `@mastra/mcp-docs-server` (directory listing / information exposure via path traversal logic flaw) | Context Injection & Over-Sharing | See NVD | [NVD][link_nvd_cve_2025_61685] · [mcp-cve-project][link_mcp_cve_project_cve_2025_61685] |
| CVE-2025-61591 | Cursor (MCP OAuth with untrusted MCP server) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_61591] · [mcp-cve-project][link_mcp_cve_project_cve_2025_61591] |
| CVE-2025-61590 | Cursor IDE | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_61590] · [mcp-cve-project][link_mcp_cve_project_cve_2025_61590] |
| CVE-2025-61260 | OpenAI Codex CLI | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_61260] · [mcp-cve-project][link_mcp_cve_project_cve_2025_61260] |
| CVE-2025-59956 | Coder `agentapi` (HTTP API for Claude Code, Goose, Aider, Gemini, Amp, Codex) | Context Injection & Over-Sharing | See NVD | [NVD][link_nvd_cve_2025_59956] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59956] |
| CVE-2025-59944 | Cursor IDE | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_59944] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59944] |
| CVE-2025-59834 | `adb-mcp` (command injection in ADB MCP Server) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_59834] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59834] |
| CVE-2025-59536 | Claude Code (Anthropic agentic coding tool) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_59536] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59536] |
| CVE-2025-59528 | Flowise CustomMCP node:`flowise` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_59528] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59528] |
| CVE-2025-59417 | Lobe Chat | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_59417] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59417] |
| CVE-2025-59377 | feiskyer `mcp-kubernetes-server` (distinct from `mcp-server-kubernetes`) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_59377] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59377] |
| CVE-2025-59333 | `@executeautomation/database-server` (read-only mode bypass) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_59333] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59333] |
| CVE-2025-59163 | SafeDep `vet` (MCP SSE server mode) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_59163] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59163] |
| CVE-2025-59155 | hackmd-mcp | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_59155] · [mcp-cve-project][link_mcp_cve_project_cve_2025_59155] |
| CVE-2025-58747 | Dify MCP OAuth component | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_58747] · [mcp-cve-project][link_mcp_cve_project_cve_2025_58747] |
| CVE-2025-58444 | MCP Inspector (`@modelcontextprotocol/inspector`) (XSS via untrusted redirect URL) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_58444] · [mcp-cve-project][link_mcp_cve_project_cve_2025_58444] |
| CVE-2025-58358 | Markdownify MCP server command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_58358] · [mcp-cve-project][link_mcp_cve_project_cve_2025_58358] |
| CVE-2025-58357 | 5ire MCP client (content injection via compromised MCP servers) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2025_58357] · [mcp-cve-project][link_mcp_cve_project_cve_2025_58357] |
| CVE-2025-58337 | Apache Doris MCP Server (`doris-mcp-server`; PyPI) (read-only mode bypass) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_58337] · [mcp-cve-project][link_mcp_cve_project_cve_2025_58337] |
| CVE-2025-58176 | Dive MCP Host Desktop Application | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_58176] · [mcp-cve-project][link_mcp_cve_project_cve_2025_58176] |
| CVE-2025-58062 | LSTM-Kirigaya `openmcp-client` VS Code plugin | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_58062] · [mcp-cve-project][link_mcp_cve_project_cve_2025_58062] |
| CVE-2025-56406 | `mcp-neo4j` (SSE sensitive information) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2025_56406] · [mcp-cve-project][link_mcp_cve_project_cve_2025_56406] |
| CVE-2025-54994 | `@akoskm/create-mcp-server-stdio` (`which-app-on-port` command injection via unsafe `exec`; also cited in OX supply-chain advisory) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_54994] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54994] |
| CVE-2025-54424 | 1Panel MCP Server | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_54424] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54424] |
| CVE-2025-54382 | Cherry Studio | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_54382] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54382] |
| CVE-2025-54136 | Cursor (MCP JSON / stdio exposure) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_54136] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54136] |
| CVE-2025-54135 | Cursor | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_54135] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54135] |
| CVE-2025-54074 | Cherry Studio | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_54074] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54074] |
| CVE-2025-54073 | `mcp-package-docs` (npm) | Command Injection & Execution | ≥ 0.1.28 | [NVD][link_nvd_cve_2025_54073] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54073] |
| CVE-2025-53967 | Framelink Figma MCP Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53967] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53967] |
| CVE-2025-53832 | Lara Translate MCP Server (`@translated/lara-mcp`) (npm) — command injection / RCE via `child_process.exec` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53832] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53832] |
| CVE-2025-53818 | GitHub Kanban MCP Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53818] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53818] |
| CVE-2025-53372 | `node-code-sandbox-mcp` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53372] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53372] |
| CVE-2025-53366 | MCP Python SDK (`mcp` on PyPI): validation error → unhandled exception / DoS | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_53366] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53366] |
| CVE-2025-53365 | MCP Python SDK (`mcp`) (DoS via unhandled exception in Streamable HTTP transport):`mcp` (pip) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_53365] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53365] |
| CVE-2025-53355 | `mcp-server-kubernetes` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53355] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53355] |
| CVE-2025-53110 | Filesystem MCP Server (`@modelcontextprotocol/server-filesystem`) (prefix/path collision bypass) | Privilege Escalation via Scope Creep | ≥ 2025.7.1 / 0.6.4 | [NVD][link_nvd_cve_2025_53110] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53110] · [GHSA][link_ghsa_hc55_p739_j48w] |
| CVE-2025-53109 | Filesystem MCP Server (`@modelcontextprotocol/server-filesystem`) (symlink containment bypass) | Privilege Escalation via Scope Creep | ≥ 2025.7.1 / 0.6.4 | [NVD][link_nvd_cve_2025_53109] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53109] |
| CVE-2025-53107 | `@cyanheads/git-mcp-server` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53107] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53107] |
| CVE-2025-53100 | RestDB Codehooks.io MCP Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53100] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53100] |
| CVE-2025-5277 | aws-mcp-server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_5277] · [mcp-cve-project][link_mcp_cve_project_cve_2025_5277] |
| CVE-2025-5276 | mcp-markdownify-server SSRF via Markdownify.get() | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_5276] · [mcp-cve-project][link_mcp_cve_project_cve_2025_5276] |
| CVE-2025-5273 | mcp-markdownify-server path traversal via get-markdown-file | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_5273] · [mcp-cve-project][link_mcp_cve_project_cve_2025_5273] |
| CVE-2025-52573 | iOS Simulator MCP Server (`ios-simulator-mcp`) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_52573] · [mcp-cve-project][link_mcp_cve_project_cve_2025_52573] |
| CVE-2025-49596 | MCP Inspector (`@modelcontextprotocol/inspector`) | Command Injection & Execution | ≥ 0.14.1 | [NVD][link_nvd_cve_2025_49596] · [mcp-cve-project][link_mcp_cve_project_cve_2025_49596] · [GHSA][link_ghsa_7f8r_222p_6f5g] |
| CVE-2025-47777 | 5ire MCP client (stored XSS → RCE) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_47777] · [mcp-cve-project][link_mcp_cve_project_cve_2025_47777] |
| CVE-2025-47274 | Stacklok ToolHive | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2025_47274] · [mcp-cve-project][link_mcp_cve_project_cve_2025_47274] |
| CVE-2025-4143 | Cloudflare `workers-mcp` (OAuth implementation flaw) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_4143] · [mcp-cve-project][link_mcp_cve_project_cve_2025_4143] |
| CVE-2025-35028 | HexStrike AI MCP server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_35028] · [mcp-cve-project][link_mcp_cve_project_cve_2025_35028] |
| CVE-2025-34072 | `@modelcontextprotocol/server-slack` (Slack link-unfurl data exfiltration) | Context Injection & Over-Sharing | See NVD | [NVD][link_nvd_cve_2025_34072] · [mcp-cve-project][link_mcp_cve_project_cve_2025_34072] |
| CVE-2025-20381 | Splunk MCP Server app | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_20381] · [mcp-cve-project][link_mcp_cve_project_cve_2025_20381] |
| CVE-2025-15063 | Ollama MCP Server (`execAsync` command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_15063] · [mcp-cve-project][link_mcp_cve_project_cve_2025_15063] |
| CVE-2025-15061 | Framelink Figma MCP Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_15061] · [mcp-cve-project][link_mcp_cve_project_cve_2025_15061] |
| CVE-2025-11445 | Kilo Code (AI agent IDE; `ClineProvider` / Prompt Handler) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2025_11445] · [mcp-cve-project][link_mcp_cve_project_cve_2025_11445] |
| CVE-2025-11286 | samanhappy MCPHub | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_11286] · [mcp-cve-project][link_mcp_cve_project_cve_2025_11286] |
| CVE-2025-10619 | sequa-ai `sequa-mcp` (OAuth redirect issue) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_10619] · [mcp-cve-project][link_mcp_cve_project_cve_2025_10619] |
| CVE-2025-10193 | Neo4j MCP Cypher server (`mcp-neo4j-cypher`) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_10193] · [mcp-cve-project][link_mcp_cve_project_cve_2025_10193] |
---

[link_vermava_mcp_cve_project]: https://github.com/mcp-security-project/mcp-cve-project
[link_vermava_mcp_cve_project_commits]: https://github.com/mcp-security-project/mcp-cve-project/commits/main/
[link_vineethsai_vulnerablemcp]: https://github.com/vineethsai/vulnerablemcp
[link_vineethsai_vulnerablemcp_commits]: https://github.com/vineethsai/vulnerablemcp/commits/main/
[link_opencve_modelcontextprotocol]: https://app.opencve.io/cve/?vendor=modelcontextprotocol
[link_github_advisories_mcp_search]: https://github.com/advisories?query=model+context+protocol
[link_mcp_python_sdk_advisories]: https://github.com/modelcontextprotocol/python-sdk/security/advisories
[link_mcp_typescript_sdk_advisories]: https://github.com/modelcontextprotocol/typescript-sdk/security/advisories
[link_mcp_inspector_advisories]: https://github.com/modelcontextprotocol/inspector/security/advisories
[link_pysec_mcp]: https://github.com/pypa/advisory-database/tree/main/vulns/mcp

[link_nvd_cve_2026_7738]: https://nvd.nist.gov/vuln/detail/CVE-2026-7738
[link_nvd_cve_2026_7730]: https://nvd.nist.gov/vuln/detail/CVE-2026-7730
[link_nvd_cve_2026_7729]: https://nvd.nist.gov/vuln/detail/CVE-2026-7729
[link_nvd_cve_2026_7728]: https://nvd.nist.gov/vuln/detail/CVE-2026-7728
[link_nvd_cve_2026_7715]: https://nvd.nist.gov/vuln/detail/CVE-2026-7715
[link_nvd_cve_2026_7664]: https://nvd.nist.gov/vuln/detail/CVE-2026-7664
[link_nvd_cve_2026_7663]: https://nvd.nist.gov/vuln/detail/CVE-2026-7663
[link_nvd_cve_2026_7653]: https://nvd.nist.gov/vuln/detail/CVE-2026-7653
[link_nvd_cve_2026_7628]: https://nvd.nist.gov/vuln/detail/CVE-2026-7628
[link_nvd_cve_2026_7627]: https://nvd.nist.gov/vuln/detail/CVE-2026-7627
[link_nvd_cve_2026_7600]: https://nvd.nist.gov/vuln/detail/CVE-2026-7600
[link_nvd_cve_2026_7599]: https://nvd.nist.gov/vuln/detail/CVE-2026-7599
[link_nvd_cve_2026_7594]: https://nvd.nist.gov/vuln/detail/CVE-2026-7594
[link_nvd_cve_2026_7593]: https://nvd.nist.gov/vuln/detail/CVE-2026-7593
[link_nvd_cve_2026_7591]: https://nvd.nist.gov/vuln/detail/CVE-2026-7591
[link_nvd_cve_2026_7446]: https://nvd.nist.gov/vuln/detail/CVE-2026-7446
[link_nvd_cve_2026_7443]: https://nvd.nist.gov/vuln/detail/CVE-2026-7443
[link_nvd_cve_2026_7417]: https://nvd.nist.gov/vuln/detail/CVE-2026-7417
[link_nvd_cve_2026_7386]: https://nvd.nist.gov/vuln/detail/CVE-2026-7386
[link_nvd_cve_2026_7272]: https://nvd.nist.gov/vuln/detail/CVE-2026-7272
[link_nvd_cve_2026_7237]: https://nvd.nist.gov/vuln/detail/CVE-2026-7237
[link_nvd_cve_2026_7221]: https://nvd.nist.gov/vuln/detail/CVE-2026-7221
[link_nvd_cve_2026_7206]: https://nvd.nist.gov/vuln/detail/CVE-2026-7206
[link_nvd_cve_2026_7205]: https://nvd.nist.gov/vuln/detail/CVE-2026-7205
[link_nvd_cve_2026_7158]: https://nvd.nist.gov/vuln/detail/CVE-2026-7158
[link_nvd_cve_2026_7157]: https://nvd.nist.gov/vuln/detail/CVE-2026-7157
[link_nvd_cve_2026_7150]: https://nvd.nist.gov/vuln/detail/CVE-2026-7150
[link_nvd_cve_2026_7147]: https://nvd.nist.gov/vuln/detail/CVE-2026-7147
[link_nvd_cve_2026_7146]: https://nvd.nist.gov/vuln/detail/CVE-2026-7146
[link_nvd_cve_2026_7061]: https://nvd.nist.gov/vuln/detail/CVE-2026-7061
[link_nvd_cve_2026_6599]: https://nvd.nist.gov/vuln/detail/CVE-2026-6599
[link_nvd_cve_2026_6494]: https://nvd.nist.gov/vuln/detail/CVE-2026-6494
[link_nvd_cve_2026_63119]: https://nvd.nist.gov/vuln/detail/CVE-2026-63119
[link_nvd_cve_2026_63118]: https://nvd.nist.gov/vuln/detail/CVE-2026-63118
[link_nvd_cve_2026_61459]: https://nvd.nist.gov/vuln/detail/CVE-2026-61459
[link_nvd_cve_2026_6130]: https://nvd.nist.gov/vuln/detail/CVE-2026-6130
[link_nvd_cve_2026_6108]: https://nvd.nist.gov/vuln/detail/CVE-2026-6108
[link_nvd_cve_2026_59950]: https://nvd.nist.gov/vuln/detail/CVE-2026-59950
[link_nvd_cve_2026_58446]: https://nvd.nist.gov/vuln/detail/CVE-2026-58446
[link_nvd_cve_2026_5833]: https://nvd.nist.gov/vuln/detail/CVE-2026-5833
[link_nvd_cve_2026_58171]: https://nvd.nist.gov/vuln/detail/CVE-2026-58171
[link_nvd_cve_2026_58168]: https://nvd.nist.gov/vuln/detail/CVE-2026-58168
[link_nvd_cve_2026_58057]: https://nvd.nist.gov/vuln/detail/CVE-2026-58057
[link_nvd_cve_2026_57922]: https://nvd.nist.gov/vuln/detail/CVE-2026-57922
[link_nvd_cve_2026_57300]: https://nvd.nist.gov/vuln/detail/CVE-2026-57300
[link_nvd_cve_2026_56274]: https://nvd.nist.gov/vuln/detail/CVE-2026-56274
[link_nvd_cve_2026_5607]: https://nvd.nist.gov/vuln/detail/CVE-2026-5607
[link_nvd_cve_2026_55887]: https://nvd.nist.gov/vuln/detail/CVE-2026-55887
[link_nvd_cve_2026_54842]: https://nvd.nist.gov/vuln/detail/CVE-2026-54842
[link_nvd_cve_2026_5470]: https://nvd.nist.gov/vuln/detail/CVE-2026-5470
[link_nvd_cve_2026_54449]: https://nvd.nist.gov/vuln/detail/CVE-2026-54449
[link_nvd_cve_2026_54309]: https://nvd.nist.gov/vuln/detail/CVE-2026-54309
[link_nvd_cve_2026_54030]: https://nvd.nist.gov/vuln/detail/CVE-2026-54030
[link_nvd_cve_2026_53840]: https://nvd.nist.gov/vuln/detail/CVE-2026-53840
[link_nvd_cve_2026_53820]: https://nvd.nist.gov/vuln/detail/CVE-2026-53820
[link_nvd_cve_2026_53818]: https://nvd.nist.gov/vuln/detail/CVE-2026-53818
[link_nvd_cve_2026_53814]: https://nvd.nist.gov/vuln/detail/CVE-2026-53814
[link_nvd_cve_2026_53766]: https://nvd.nist.gov/vuln/detail/CVE-2026-53766
[link_nvd_cve_2026_5323]: https://nvd.nist.gov/vuln/detail/CVE-2026-5323
[link_nvd_cve_2026_52870]: https://nvd.nist.gov/vuln/detail/CVE-2026-52870
[link_nvd_cve_2026_52869]: https://nvd.nist.gov/vuln/detail/CVE-2026-52869
[link_nvd_cve_2026_5059]: https://nvd.nist.gov/vuln/detail/CVE-2026-5059
[link_nvd_cve_2026_5058]: https://nvd.nist.gov/vuln/detail/CVE-2026-5058
[link_nvd_cve_2026_5029]: https://nvd.nist.gov/vuln/detail/CVE-2026-5029
[link_nvd_cve_2026_50287]: https://nvd.nist.gov/vuln/detail/CVE-2026-50287
[link_nvd_cve_2026_5023]: https://nvd.nist.gov/vuln/detail/CVE-2026-5023
[link_nvd_cve_2026_50143]: https://nvd.nist.gov/vuln/detail/CVE-2026-50143
[link_nvd_cve_2026_5007]: https://nvd.nist.gov/vuln/detail/CVE-2026-5007
[link_nvd_cve_2026_49357]: https://nvd.nist.gov/vuln/detail/CVE-2026-49357
[link_nvd_cve_2026_49291]: https://nvd.nist.gov/vuln/detail/CVE-2026-49291
[link_nvd_cve_2026_49257]: https://nvd.nist.gov/vuln/detail/CVE-2026-49257
[link_nvd_cve_2026_48989]: https://nvd.nist.gov/vuln/detail/CVE-2026-48989
[link_nvd_cve_2026_48814]: https://nvd.nist.gov/vuln/detail/CVE-2026-48814
[link_nvd_cve_2026_48787]: https://nvd.nist.gov/vuln/detail/CVE-2026-48787
[link_nvd_cve_2026_48774]: https://nvd.nist.gov/vuln/detail/CVE-2026-48774
[link_nvd_cve_2026_48710]: https://nvd.nist.gov/vuln/detail/CVE-2026-48710
[link_nvd_cve_2026_48529]: https://nvd.nist.gov/vuln/detail/CVE-2026-48529
[link_nvd_cve_2026_47751]: https://nvd.nist.gov/vuln/detail/CVE-2026-47751
[link_nvd_cve_2026_47388]: https://nvd.nist.gov/vuln/detail/CVE-2026-47388
[link_nvd_cve_2026_47250]: https://nvd.nist.gov/vuln/detail/CVE-2026-47250
[link_nvd_cve_2026_46549]: https://nvd.nist.gov/vuln/detail/CVE-2026-46549
[link_nvd_cve_2026_46519]: https://nvd.nist.gov/vuln/detail/CVE-2026-46519
[link_nvd_cve_2026_46341]: https://nvd.nist.gov/vuln/detail/CVE-2026-46341
[link_nvd_cve_2026_46339]: https://nvd.nist.gov/vuln/detail/CVE-2026-46339
[link_nvd_cve_2026_45805]: https://nvd.nist.gov/vuln/detail/CVE-2026-45805
[link_nvd_cve_2026_45781]: https://nvd.nist.gov/vuln/detail/CVE-2026-45781
[link_nvd_cve_2026_45707]: https://nvd.nist.gov/vuln/detail/CVE-2026-45707
[link_nvd_cve_2026_45609]: https://nvd.nist.gov/vuln/detail/CVE-2026-45609
[link_nvd_cve_2026_45582]: https://nvd.nist.gov/vuln/detail/CVE-2026-45582
[link_nvd_cve_2026_45555]: https://nvd.nist.gov/vuln/detail/CVE-2026-45555
[link_nvd_cve_2026_45001]: https://nvd.nist.gov/vuln/detail/CVE-2026-45001
[link_nvd_cve_2026_44998]: https://nvd.nist.gov/vuln/detail/CVE-2026-44998
[link_nvd_cve_2026_44995]: https://nvd.nist.gov/vuln/detail/CVE-2026-44995
[link_nvd_cve_2026_4496]: https://nvd.nist.gov/vuln/detail/CVE-2026-4496
[link_nvd_cve_2026_44895]: https://nvd.nist.gov/vuln/detail/CVE-2026-44895
[link_nvd_cve_2026_44830]: https://nvd.nist.gov/vuln/detail/CVE-2026-44830
[link_nvd_cve_2026_44717]: https://nvd.nist.gov/vuln/detail/CVE-2026-44717
[link_nvd_cve_2026_44694]: https://nvd.nist.gov/vuln/detail/CVE-2026-44694
[link_nvd_cve_2026_44653]: https://nvd.nist.gov/vuln/detail/CVE-2026-44653
[link_nvd_cve_2026_44450]: https://nvd.nist.gov/vuln/detail/CVE-2026-44450
[link_nvd_cve_2026_44430]: https://nvd.nist.gov/vuln/detail/CVE-2026-44430
[link_nvd_cve_2026_44429]: https://nvd.nist.gov/vuln/detail/CVE-2026-44429
[link_nvd_cve_2026_44428]: https://nvd.nist.gov/vuln/detail/CVE-2026-44428
[link_nvd_cve_2026_44427]: https://nvd.nist.gov/vuln/detail/CVE-2026-44427
[link_nvd_cve_2026_44336]: https://nvd.nist.gov/vuln/detail/CVE-2026-44336
[link_nvd_cve_2026_44284]: https://nvd.nist.gov/vuln/detail/CVE-2026-44284
[link_nvd_cve_2026_44118]: https://nvd.nist.gov/vuln/detail/CVE-2026-44118
[link_nvd_cve_2026_43992]: https://nvd.nist.gov/vuln/detail/CVE-2026-43992
[link_nvd_cve_2026_43901]: https://nvd.nist.gov/vuln/detail/CVE-2026-43901
[link_nvd_cve_2026_4339]: https://nvd.nist.gov/vuln/detail/CVE-2026-4339
[link_nvd_cve_2026_4270]: https://nvd.nist.gov/vuln/detail/CVE-2026-4270
[link_nvd_cve_2026_42559]: https://nvd.nist.gov/vuln/detail/CVE-2026-42559
[link_nvd_cve_2026_42449]: https://nvd.nist.gov/vuln/detail/CVE-2026-42449
[link_nvd_cve_2026_42282]: https://nvd.nist.gov/vuln/detail/CVE-2026-42282
[link_nvd_cve_2026_42271]: https://nvd.nist.gov/vuln/detail/CVE-2026-42271
[link_nvd_cve_2026_42260]: https://nvd.nist.gov/vuln/detail/CVE-2026-42260
[link_nvd_cve_2026_42236]: https://nvd.nist.gov/vuln/detail/CVE-2026-42236
[link_nvd_cve_2026_42230]: https://nvd.nist.gov/vuln/detail/CVE-2026-42230
[link_nvd_cve_2026_42073]: https://nvd.nist.gov/vuln/detail/CVE-2026-42073
[link_nvd_cve_2026_4198]: https://nvd.nist.gov/vuln/detail/CVE-2026-4198
[link_nvd_cve_2026_41495]: https://nvd.nist.gov/vuln/detail/CVE-2026-41495
[link_nvd_cve_2026_40933]: https://nvd.nist.gov/vuln/detail/CVE-2026-40933
[link_nvd_cve_2026_40775]: https://nvd.nist.gov/vuln/detail/CVE-2026-40775
[link_nvd_cve_2026_40608]: https://nvd.nist.gov/vuln/detail/CVE-2026-40608
[link_nvd_cve_2026_40576]: https://nvd.nist.gov/vuln/detail/CVE-2026-40576
[link_nvd_cve_2026_40159]: https://nvd.nist.gov/vuln/detail/CVE-2026-40159
[link_nvd_cve_2026_39987]: https://nvd.nist.gov/vuln/detail/CVE-2026-39987
[link_nvd_cve_2026_39974]: https://nvd.nist.gov/vuln/detail/CVE-2026-39974
[link_nvd_cve_2026_39885]: https://nvd.nist.gov/vuln/detail/CVE-2026-39885
[link_nvd_cve_2026_39884]: https://nvd.nist.gov/vuln/detail/CVE-2026-39884
[link_nvd_cve_2026_39313]: https://nvd.nist.gov/vuln/detail/CVE-2026-39313
[link_nvd_cve_2026_35577]: https://nvd.nist.gov/vuln/detail/CVE-2026-35577
[link_nvd_cve_2026_35568]: https://nvd.nist.gov/vuln/detail/CVE-2026-35568
[link_nvd_cve_2026_35402]: https://nvd.nist.gov/vuln/detail/CVE-2026-35402
[link_nvd_cve_2026_35394]: https://nvd.nist.gov/vuln/detail/CVE-2026-35394
[link_nvd_cve_2026_35228]: https://nvd.nist.gov/vuln/detail/CVE-2026-35228
[link_nvd_cve_2026_34953]: https://nvd.nist.gov/vuln/detail/CVE-2026-34953
[link_nvd_cve_2026_34742]: https://nvd.nist.gov/vuln/detail/CVE-2026-34742
[link_nvd_cve_2026_34476]: https://nvd.nist.gov/vuln/detail/CVE-2026-34476
[link_nvd_cve_2026_34237]: https://nvd.nist.gov/vuln/detail/CVE-2026-34237
[link_nvd_cve_2026_34200]: https://nvd.nist.gov/vuln/detail/CVE-2026-34200
[link_nvd_cve_2026_34163]: https://nvd.nist.gov/vuln/detail/CVE-2026-34163
[link_nvd_cve_2026_33989]: https://nvd.nist.gov/vuln/detail/CVE-2026-33989
[link_nvd_cve_2026_33980]: https://nvd.nist.gov/vuln/detail/CVE-2026-33980
[link_nvd_cve_2026_33946]: https://nvd.nist.gov/vuln/detail/CVE-2026-33946
[link_nvd_cve_2026_33252]: https://nvd.nist.gov/vuln/detail/CVE-2026-33252
[link_nvd_cve_2026_33224]: https://nvd.nist.gov/vuln/detail/CVE-2026-33224
[link_nvd_cve_2026_33060]: https://nvd.nist.gov/vuln/detail/CVE-2026-33060
[link_nvd_cve_2026_33032]: https://nvd.nist.gov/vuln/detail/CVE-2026-33032
[link_nvd_cve_2026_33010]: https://nvd.nist.gov/vuln/detail/CVE-2026-33010
[link_nvd_cve_2026_32871]: https://nvd.nist.gov/vuln/detail/CVE-2026-32871
[link_nvd_cve_2026_32625]: https://nvd.nist.gov/vuln/detail/CVE-2026-32625
[link_nvd_cve_2026_32247]: https://nvd.nist.gov/vuln/detail/CVE-2026-32247
[link_nvd_cve_2026_32211]: https://nvd.nist.gov/vuln/detail/CVE-2026-32211
[link_nvd_cve_2026_32112]: https://nvd.nist.gov/vuln/detail/CVE-2026-32112
[link_nvd_cve_2026_32111]: https://nvd.nist.gov/vuln/detail/CVE-2026-32111
[link_nvd_cve_2026_31951]: https://nvd.nist.gov/vuln/detail/CVE-2026-31951
[link_nvd_cve_2026_31945]: https://nvd.nist.gov/vuln/detail/CVE-2026-31945
[link_nvd_cve_2026_31944]: https://nvd.nist.gov/vuln/detail/CVE-2026-31944
[link_nvd_cve_2026_30861]: https://nvd.nist.gov/vuln/detail/CVE-2026-30861
[link_nvd_cve_2026_30856]: https://nvd.nist.gov/vuln/detail/CVE-2026-30856
[link_nvd_cve_2026_30635]: https://nvd.nist.gov/vuln/detail/CVE-2026-30635
[link_nvd_cve_2026_30625]: https://nvd.nist.gov/vuln/detail/CVE-2026-30625
[link_nvd_cve_2026_30624]: https://nvd.nist.gov/vuln/detail/CVE-2026-30624
[link_nvd_cve_2026_30623]: https://nvd.nist.gov/vuln/detail/CVE-2026-30623
[link_nvd_cve_2026_30618]: https://nvd.nist.gov/vuln/detail/CVE-2026-30618
[link_nvd_cve_2026_30617]: https://nvd.nist.gov/vuln/detail/CVE-2026-30617
[link_nvd_cve_2026_30616]: https://nvd.nist.gov/vuln/detail/CVE-2026-30616
[link_nvd_cve_2026_30615]: https://nvd.nist.gov/vuln/detail/CVE-2026-30615
[link_nvd_cve_2026_29787]: https://nvd.nist.gov/vuln/detail/CVE-2026-29787
[link_nvd_cve_2026_29783]: https://nvd.nist.gov/vuln/detail/CVE-2026-29783
[link_nvd_cve_2026_27896]: https://nvd.nist.gov/vuln/detail/CVE-2026-27896
[link_nvd_cve_2026_27826]: https://nvd.nist.gov/vuln/detail/CVE-2026-27826
[link_nvd_cve_2026_27825]: https://nvd.nist.gov/vuln/detail/CVE-2026-27825
[link_nvd_cve_2026_27735]: https://nvd.nist.gov/vuln/detail/CVE-2026-27735
[link_nvd_cve_2026_27203]: https://nvd.nist.gov/vuln/detail/CVE-2026-27203
[link_nvd_cve_2026_27124]: https://nvd.nist.gov/vuln/detail/CVE-2026-27124
[link_nvd_cve_2026_26118]: https://nvd.nist.gov/vuln/detail/CVE-2026-26118
[link_nvd_cve_2026_26029]: https://nvd.nist.gov/vuln/detail/CVE-2026-26029
[link_nvd_cve_2026_26015]: https://nvd.nist.gov/vuln/detail/CVE-2026-26015
[link_nvd_cve_2026_25905]: https://nvd.nist.gov/vuln/detail/CVE-2026-25905
[link_nvd_cve_2026_25904]: https://nvd.nist.gov/vuln/detail/CVE-2026-25904
[link_nvd_cve_2026_25650]: https://nvd.nist.gov/vuln/detail/CVE-2026-25650
[link_nvd_cve_2026_25546]: https://nvd.nist.gov/vuln/detail/CVE-2026-25546
[link_nvd_cve_2026_25536]: https://nvd.nist.gov/vuln/detail/CVE-2026-25536
[link_nvd_cve_2026_23882]: https://nvd.nist.gov/vuln/detail/CVE-2026-23882
[link_nvd_cve_2026_23744]: https://nvd.nist.gov/vuln/detail/CVE-2026-23744
[link_nvd_cve_2026_23523]: https://nvd.nist.gov/vuln/detail/CVE-2026-23523
[link_nvd_cve_2026_22793]: https://nvd.nist.gov/vuln/detail/CVE-2026-22793
[link_nvd_cve_2026_22792]: https://nvd.nist.gov/vuln/detail/CVE-2026-22792
[link_nvd_cve_2026_22785]: https://nvd.nist.gov/vuln/detail/CVE-2026-22785
[link_nvd_cve_2026_22688]: https://nvd.nist.gov/vuln/detail/CVE-2026-22688
[link_nvd_cve_2026_22252]: https://nvd.nist.gov/vuln/detail/CVE-2026-22252
[link_nvd_cve_2026_21852]: https://nvd.nist.gov/vuln/detail/CVE-2026-21852
[link_nvd_cve_2026_2178]: https://nvd.nist.gov/vuln/detail/CVE-2026-2178
[link_nvd_cve_2026_21518]: https://nvd.nist.gov/vuln/detail/CVE-2026-21518
[link_nvd_cve_2026_20205]: https://nvd.nist.gov/vuln/detail/CVE-2026-20205
[link_nvd_cve_2026_1721]: https://nvd.nist.gov/vuln/detail/CVE-2026-1721
[link_nvd_cve_2026_13524]: https://nvd.nist.gov/vuln/detail/CVE-2026-13524
[link_nvd_cve_2026_13489]: https://nvd.nist.gov/vuln/detail/CVE-2026-13489
[link_nvd_cve_2026_13341]: https://nvd.nist.gov/vuln/detail/CVE-2026-13341
[link_nvd_cve_2026_12958]: https://nvd.nist.gov/vuln/detail/CVE-2026-12958
[link_nvd_cve_2026_12957]: https://nvd.nist.gov/vuln/detail/CVE-2026-12957
[link_nvd_cve_2026_12798]: https://nvd.nist.gov/vuln/detail/CVE-2026-12798
[link_nvd_cve_2026_12774]: https://nvd.nist.gov/vuln/detail/CVE-2026-12774
[link_nvd_cve_2026_12773]: https://nvd.nist.gov/vuln/detail/CVE-2026-12773
[link_nvd_cve_2026_12537]: https://nvd.nist.gov/vuln/detail/CVE-2026-12537
[link_nvd_cve_2026_12112]: https://nvd.nist.gov/vuln/detail/CVE-2026-12112
[link_nvd_cve_2026_11719]: https://nvd.nist.gov/vuln/detail/CVE-2026-11719
[link_nvd_cve_2026_11624]: https://nvd.nist.gov/vuln/detail/CVE-2026-11624
[link_nvd_cve_2026_10789]: https://nvd.nist.gov/vuln/detail/CVE-2026-10789
[link_nvd_cve_2026_10280]: https://nvd.nist.gov/vuln/detail/CVE-2026-10280
[link_nvd_cve_2026_10277]: https://nvd.nist.gov/vuln/detail/CVE-2026-10277
[link_nvd_cve_2026_0758]: https://nvd.nist.gov/vuln/detail/CVE-2026-0758
[link_nvd_cve_2026_0757]: https://nvd.nist.gov/vuln/detail/CVE-2026-0757
[link_nvd_cve_2026_0756]: https://nvd.nist.gov/vuln/detail/CVE-2026-0756
[link_nvd_cve_2026_0755]: https://nvd.nist.gov/vuln/detail/CVE-2026-0755
[link_nvd_cve_2026_0621]: https://nvd.nist.gov/vuln/detail/CVE-2026-0621
[link_nvd_cve_2025_9654]: https://nvd.nist.gov/vuln/detail/CVE-2025-9654
[link_nvd_cve_2025_9611]: https://nvd.nist.gov/vuln/detail/CVE-2025-9611
[link_nvd_cve_2025_8943]: https://nvd.nist.gov/vuln/detail/CVE-2025-8943
[link_nvd_cve_2025_8665]: https://nvd.nist.gov/vuln/detail/CVE-2025-8665
[link_nvd_cve_2025_71336]: https://nvd.nist.gov/vuln/detail/CVE-2025-71336
[link_nvd_cve_2025_69443]: https://nvd.nist.gov/vuln/detail/CVE-2025-69443
[link_nvd_cve_2025_69256]: https://nvd.nist.gov/vuln/detail/CVE-2025-69256
[link_nvd_cve_2025_69196]: https://nvd.nist.gov/vuln/detail/CVE-2025-69196
[link_nvd_cve_2025_68669]: https://nvd.nist.gov/vuln/detail/CVE-2025-68669
[link_nvd_cve_2025_68433]: https://nvd.nist.gov/vuln/detail/CVE-2025-68433
[link_nvd_cve_2025_68145]: https://nvd.nist.gov/vuln/detail/CVE-2025-68145
[link_nvd_cve_2025_68144]: https://nvd.nist.gov/vuln/detail/CVE-2025-68144
[link_nvd_cve_2025_68143]: https://nvd.nist.gov/vuln/detail/CVE-2025-68143
[link_nvd_cve_2025_67366]: https://nvd.nist.gov/vuln/detail/CVE-2025-67366
[link_nvd_cve_2025_66689]: https://nvd.nist.gov/vuln/detail/CVE-2025-66689
[link_nvd_cve_2025_66580]: https://nvd.nist.gov/vuln/detail/CVE-2025-66580
[link_nvd_cve_2025_66454]: https://nvd.nist.gov/vuln/detail/CVE-2025-66454
[link_nvd_cve_2025_66416]: https://nvd.nist.gov/vuln/detail/CVE-2025-66416
[link_nvd_cve_2025_66414]: https://nvd.nist.gov/vuln/detail/CVE-2025-66414
[link_nvd_cve_2025_66404]: https://nvd.nist.gov/vuln/detail/CVE-2025-66404
[link_nvd_cve_2025_66401]: https://nvd.nist.gov/vuln/detail/CVE-2025-66401
[link_nvd_cve_2025_66336]: https://nvd.nist.gov/vuln/detail/CVE-2025-66336
[link_nvd_cve_2025_66335]: https://nvd.nist.gov/vuln/detail/CVE-2025-66335
[link_nvd_cve_2025_66222]: https://nvd.nist.gov/vuln/detail/CVE-2025-66222
[link_nvd_cve_2025_65720]: https://nvd.nist.gov/vuln/detail/CVE-2025-65720
[link_nvd_cve_2025_65719]: https://nvd.nist.gov/vuln/detail/CVE-2025-65719
[link_nvd_cve_2025_65513]: https://nvd.nist.gov/vuln/detail/CVE-2025-65513
[link_nvd_cve_2025_6515]: https://nvd.nist.gov/vuln/detail/CVE-2025-6515
[link_nvd_cve_2025_6514]: https://nvd.nist.gov/vuln/detail/CVE-2025-6514
[link_nvd_cve_2025_64443]: https://nvd.nist.gov/vuln/detail/CVE-2025-64443
[link_nvd_cve_2025_64340]: https://nvd.nist.gov/vuln/detail/CVE-2025-64340
[link_nvd_cve_2025_64132]: https://nvd.nist.gov/vuln/detail/CVE-2025-64132
[link_nvd_cve_2025_64109]: https://nvd.nist.gov/vuln/detail/CVE-2025-64109
[link_nvd_cve_2025_64106]: https://nvd.nist.gov/vuln/detail/CVE-2025-64106
[link_nvd_cve_2025_63604]: https://nvd.nist.gov/vuln/detail/CVE-2025-63604
[link_nvd_cve_2025_63603]: https://nvd.nist.gov/vuln/detail/CVE-2025-63603
[link_nvd_cve_2025_62801]: https://nvd.nist.gov/vuln/detail/CVE-2025-62801
[link_nvd_cve_2025_62800]: https://nvd.nist.gov/vuln/detail/CVE-2025-62800
[link_nvd_cve_2025_61685]: https://nvd.nist.gov/vuln/detail/CVE-2025-61685
[link_nvd_cve_2025_61591]: https://nvd.nist.gov/vuln/detail/CVE-2025-61591
[link_nvd_cve_2025_61590]: https://nvd.nist.gov/vuln/detail/CVE-2025-61590
[link_nvd_cve_2025_61260]: https://nvd.nist.gov/vuln/detail/CVE-2025-61260
[link_nvd_cve_2025_59956]: https://nvd.nist.gov/vuln/detail/CVE-2025-59956
[link_nvd_cve_2025_59944]: https://nvd.nist.gov/vuln/detail/CVE-2025-59944
[link_nvd_cve_2025_59834]: https://nvd.nist.gov/vuln/detail/CVE-2025-59834
[link_nvd_cve_2025_59536]: https://nvd.nist.gov/vuln/detail/CVE-2025-59536
[link_nvd_cve_2025_59528]: https://nvd.nist.gov/vuln/detail/CVE-2025-59528
[link_nvd_cve_2025_59417]: https://nvd.nist.gov/vuln/detail/CVE-2025-59417
[link_nvd_cve_2025_59377]: https://nvd.nist.gov/vuln/detail/CVE-2025-59377
[link_nvd_cve_2025_59333]: https://nvd.nist.gov/vuln/detail/CVE-2025-59333
[link_nvd_cve_2025_59163]: https://nvd.nist.gov/vuln/detail/CVE-2025-59163
[link_nvd_cve_2025_59155]: https://nvd.nist.gov/vuln/detail/CVE-2025-59155
[link_nvd_cve_2025_58747]: https://nvd.nist.gov/vuln/detail/CVE-2025-58747
[link_nvd_cve_2025_58444]: https://nvd.nist.gov/vuln/detail/CVE-2025-58444
[link_nvd_cve_2025_58358]: https://nvd.nist.gov/vuln/detail/CVE-2025-58358
[link_nvd_cve_2025_58357]: https://nvd.nist.gov/vuln/detail/CVE-2025-58357
[link_nvd_cve_2025_58337]: https://nvd.nist.gov/vuln/detail/CVE-2025-58337
[link_nvd_cve_2025_58176]: https://nvd.nist.gov/vuln/detail/CVE-2025-58176
[link_nvd_cve_2025_58062]: https://nvd.nist.gov/vuln/detail/CVE-2025-58062
[link_nvd_cve_2025_56406]: https://nvd.nist.gov/vuln/detail/CVE-2025-56406
[link_nvd_cve_2025_54994]: https://nvd.nist.gov/vuln/detail/CVE-2025-54994
[link_nvd_cve_2025_54424]: https://nvd.nist.gov/vuln/detail/CVE-2025-54424
[link_nvd_cve_2025_54382]: https://nvd.nist.gov/vuln/detail/CVE-2025-54382
[link_nvd_cve_2025_54136]: https://nvd.nist.gov/vuln/detail/CVE-2025-54136
[link_nvd_cve_2025_54135]: https://nvd.nist.gov/vuln/detail/CVE-2025-54135
[link_nvd_cve_2025_54074]: https://nvd.nist.gov/vuln/detail/CVE-2025-54074
[link_nvd_cve_2025_54073]: https://nvd.nist.gov/vuln/detail/CVE-2025-54073
[link_nvd_cve_2025_53967]: https://nvd.nist.gov/vuln/detail/CVE-2025-53967
[link_nvd_cve_2025_53832]: https://nvd.nist.gov/vuln/detail/CVE-2025-53832
[link_nvd_cve_2025_53818]: https://nvd.nist.gov/vuln/detail/CVE-2025-53818
[link_nvd_cve_2025_53372]: https://nvd.nist.gov/vuln/detail/CVE-2025-53372
[link_nvd_cve_2025_53366]: https://nvd.nist.gov/vuln/detail/CVE-2025-53366
[link_nvd_cve_2025_53365]: https://nvd.nist.gov/vuln/detail/CVE-2025-53365
[link_nvd_cve_2025_53355]: https://nvd.nist.gov/vuln/detail/CVE-2025-53355
[link_nvd_cve_2025_53110]: https://nvd.nist.gov/vuln/detail/CVE-2025-53110
[link_nvd_cve_2025_53109]: https://nvd.nist.gov/vuln/detail/CVE-2025-53109
[link_nvd_cve_2025_53107]: https://nvd.nist.gov/vuln/detail/CVE-2025-53107
[link_nvd_cve_2025_53100]: https://nvd.nist.gov/vuln/detail/CVE-2025-53100
[link_nvd_cve_2025_5277]: https://nvd.nist.gov/vuln/detail/CVE-2025-5277
[link_nvd_cve_2025_5276]: https://nvd.nist.gov/vuln/detail/CVE-2025-5276
[link_nvd_cve_2025_5273]: https://nvd.nist.gov/vuln/detail/CVE-2025-5273
[link_nvd_cve_2025_52573]: https://nvd.nist.gov/vuln/detail/CVE-2025-52573
[link_nvd_cve_2025_49596]: https://nvd.nist.gov/vuln/detail/CVE-2025-49596
[link_nvd_cve_2025_47777]: https://nvd.nist.gov/vuln/detail/CVE-2025-47777
[link_nvd_cve_2025_47274]: https://nvd.nist.gov/vuln/detail/CVE-2025-47274
[link_nvd_cve_2025_4143]: https://nvd.nist.gov/vuln/detail/CVE-2025-4143
[link_nvd_cve_2025_35028]: https://nvd.nist.gov/vuln/detail/CVE-2025-35028
[link_nvd_cve_2025_34072]: https://nvd.nist.gov/vuln/detail/CVE-2025-34072
[link_nvd_cve_2025_20381]: https://nvd.nist.gov/vuln/detail/CVE-2025-20381
[link_nvd_cve_2025_15063]: https://nvd.nist.gov/vuln/detail/CVE-2025-15063
[link_nvd_cve_2025_15061]: https://nvd.nist.gov/vuln/detail/CVE-2025-15061
[link_nvd_cve_2025_11445]: https://nvd.nist.gov/vuln/detail/CVE-2025-11445
[link_nvd_cve_2025_11286]: https://nvd.nist.gov/vuln/detail/CVE-2025-11286
[link_nvd_cve_2025_10619]: https://nvd.nist.gov/vuln/detail/CVE-2025-10619
[link_nvd_cve_2025_10193]: https://nvd.nist.gov/vuln/detail/CVE-2025-10193
[link_mcp_cve_project_cve_2026_7738]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7738.md
[link_mcp_cve_project_cve_2026_7730]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7730.md
[link_mcp_cve_project_cve_2026_7729]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7729.md
[link_mcp_cve_project_cve_2026_7728]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7728.md
[link_mcp_cve_project_cve_2026_7715]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7715.md
[link_mcp_cve_project_cve_2026_7664]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7664.md
[link_mcp_cve_project_cve_2026_7663]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7663.md
[link_mcp_cve_project_cve_2026_7653]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7653.md
[link_mcp_cve_project_cve_2026_7628]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7628.md
[link_mcp_cve_project_cve_2026_7627]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7627.md
[link_mcp_cve_project_cve_2026_7600]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7600.md
[link_mcp_cve_project_cve_2026_7599]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7599.md
[link_mcp_cve_project_cve_2026_7594]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7594.md
[link_mcp_cve_project_cve_2026_7593]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7593.md
[link_mcp_cve_project_cve_2026_7591]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7591.md
[link_mcp_cve_project_cve_2026_7446]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7446.md
[link_mcp_cve_project_cve_2026_7443]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7443.md
[link_mcp_cve_project_cve_2026_7417]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7417.md
[link_mcp_cve_project_cve_2026_7386]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7386.md
[link_mcp_cve_project_cve_2026_7272]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7272.md
[link_mcp_cve_project_cve_2026_7237]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7237.md
[link_mcp_cve_project_cve_2026_7221]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7221.md
[link_mcp_cve_project_cve_2026_7206]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7206.md
[link_mcp_cve_project_cve_2026_7205]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7205.md
[link_mcp_cve_project_cve_2026_7158]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7158.md
[link_mcp_cve_project_cve_2026_7157]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7157.md
[link_mcp_cve_project_cve_2026_7150]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7150.md
[link_mcp_cve_project_cve_2026_7147]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7147.md
[link_mcp_cve_project_cve_2026_7146]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7146.md
[link_mcp_cve_project_cve_2026_7061]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7061.md
[link_mcp_cve_project_cve_2026_6599]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-6599.md
[link_mcp_cve_project_cve_2026_6494]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-6494.md
[link_mcp_cve_project_cve_2026_63119]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63119.md
[link_mcp_cve_project_cve_2026_63118]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63118.md
[link_mcp_cve_project_cve_2026_61459]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61459.md
[link_mcp_cve_project_cve_2026_6130]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-6130.md
[link_mcp_cve_project_cve_2026_6108]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-6108.md
[link_mcp_cve_project_cve_2026_59950]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59950.md
[link_mcp_cve_project_cve_2026_58446]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58446.md
[link_mcp_cve_project_cve_2026_5833]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5833.md
[link_mcp_cve_project_cve_2026_58171]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58171.md
[link_mcp_cve_project_cve_2026_58168]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58168.md
[link_mcp_cve_project_cve_2026_58057]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58057.md
[link_mcp_cve_project_cve_2026_57922]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57922.md
[link_mcp_cve_project_cve_2026_57300]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57300.md
[link_mcp_cve_project_cve_2026_56274]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-56274.md
[link_mcp_cve_project_cve_2026_5607]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5607.md
[link_mcp_cve_project_cve_2026_55887]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55887.md
[link_mcp_cve_project_cve_2026_54842]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54842.md
[link_mcp_cve_project_cve_2026_5470]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5470.md
[link_mcp_cve_project_cve_2026_54449]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54449.md
[link_mcp_cve_project_cve_2026_54309]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54309.md
[link_mcp_cve_project_cve_2026_54030]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54030.md
[link_mcp_cve_project_cve_2026_53840]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53840.md
[link_mcp_cve_project_cve_2026_53820]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53820.md
[link_mcp_cve_project_cve_2026_53818]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53818.md
[link_mcp_cve_project_cve_2026_53814]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53814.md
[link_mcp_cve_project_cve_2026_53766]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53766.md
[link_mcp_cve_project_cve_2026_5323]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5323.md
[link_mcp_cve_project_cve_2026_52870]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-52870.md
[link_mcp_cve_project_cve_2026_52869]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-52869.md
[link_mcp_cve_project_cve_2026_5059]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5059.md
[link_mcp_cve_project_cve_2026_5058]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5058.md
[link_mcp_cve_project_cve_2026_5029]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5029.md
[link_mcp_cve_project_cve_2026_50287]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-50287.md
[link_mcp_cve_project_cve_2026_5023]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5023.md
[link_mcp_cve_project_cve_2026_50143]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-50143.md
[link_mcp_cve_project_cve_2026_5007]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5007.md
[link_mcp_cve_project_cve_2026_49357]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49357.md
[link_mcp_cve_project_cve_2026_49291]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49291.md
[link_mcp_cve_project_cve_2026_49257]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49257.md
[link_mcp_cve_project_cve_2026_48989]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48989.md
[link_mcp_cve_project_cve_2026_48814]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48814.md
[link_mcp_cve_project_cve_2026_48787]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48787.md
[link_mcp_cve_project_cve_2026_48774]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48774.md
[link_mcp_cve_project_cve_2026_48710]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48710.md
[link_mcp_cve_project_cve_2026_48529]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48529.md
[link_mcp_cve_project_cve_2026_47751]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47751.md
[link_mcp_cve_project_cve_2026_47388]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47388.md
[link_mcp_cve_project_cve_2026_47250]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47250.md
[link_mcp_cve_project_cve_2026_46549]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46549.md
[link_mcp_cve_project_cve_2026_46519]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46519.md
[link_mcp_cve_project_cve_2026_46341]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46341.md
[link_mcp_cve_project_cve_2026_46339]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46339.md
[link_mcp_cve_project_cve_2026_45805]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45805.md
[link_mcp_cve_project_cve_2026_45781]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45781.md
[link_mcp_cve_project_cve_2026_45707]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45707.md
[link_mcp_cve_project_cve_2026_45609]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45609.md
[link_mcp_cve_project_cve_2026_45582]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45582.md
[link_mcp_cve_project_cve_2026_45555]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45555.md
[link_mcp_cve_project_cve_2026_45001]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45001.md
[link_mcp_cve_project_cve_2026_44998]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44998.md
[link_mcp_cve_project_cve_2026_44995]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44995.md
[link_mcp_cve_project_cve_2026_4496]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4496.md
[link_mcp_cve_project_cve_2026_44895]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44895.md
[link_mcp_cve_project_cve_2026_44830]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44830.md
[link_mcp_cve_project_cve_2026_44717]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44717.md
[link_mcp_cve_project_cve_2026_44694]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44694.md
[link_mcp_cve_project_cve_2026_44653]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44653.md
[link_mcp_cve_project_cve_2026_44450]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44450.md
[link_mcp_cve_project_cve_2026_44430]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44430.md
[link_mcp_cve_project_cve_2026_44429]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44429.md
[link_mcp_cve_project_cve_2026_44428]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44428.md
[link_mcp_cve_project_cve_2026_44427]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44427.md
[link_mcp_cve_project_cve_2026_44336]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44336.md
[link_mcp_cve_project_cve_2026_44284]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44284.md
[link_mcp_cve_project_cve_2026_44118]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44118.md
[link_mcp_cve_project_cve_2026_43992]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-43992.md
[link_mcp_cve_project_cve_2026_43901]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-43901.md
[link_mcp_cve_project_cve_2026_4339]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4339.md
[link_mcp_cve_project_cve_2026_4270]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4270.md
[link_mcp_cve_project_cve_2026_42559]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42559.md
[link_mcp_cve_project_cve_2026_42449]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42449.md
[link_mcp_cve_project_cve_2026_42282]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42282.md
[link_mcp_cve_project_cve_2026_42271]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42271.md
[link_mcp_cve_project_cve_2026_42260]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42260.md
[link_mcp_cve_project_cve_2026_42236]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42236.md
[link_mcp_cve_project_cve_2026_42230]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42230.md
[link_mcp_cve_project_cve_2026_42073]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42073.md
[link_mcp_cve_project_cve_2026_4198]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4198.md
[link_mcp_cve_project_cve_2026_41495]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-41495.md
[link_mcp_cve_project_cve_2026_40933]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40933.md
[link_mcp_cve_project_cve_2026_40775]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40775.md
[link_mcp_cve_project_cve_2026_40608]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40608.md
[link_mcp_cve_project_cve_2026_40576]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40576.md
[link_mcp_cve_project_cve_2026_40159]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40159.md
[link_mcp_cve_project_cve_2026_39987]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39987.md
[link_mcp_cve_project_cve_2026_39974]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39974.md
[link_mcp_cve_project_cve_2026_39885]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39885.md
[link_mcp_cve_project_cve_2026_39884]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39884.md
[link_mcp_cve_project_cve_2026_39313]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39313.md
[link_mcp_cve_project_cve_2026_35577]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35577.md
[link_mcp_cve_project_cve_2026_35568]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35568.md
[link_mcp_cve_project_cve_2026_35402]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35402.md
[link_mcp_cve_project_cve_2026_35394]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35394.md
[link_mcp_cve_project_cve_2026_35228]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35228.md
[link_mcp_cve_project_cve_2026_34953]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34953.md
[link_mcp_cve_project_cve_2026_34742]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34742.md
[link_mcp_cve_project_cve_2026_34476]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34476.md
[link_mcp_cve_project_cve_2026_34237]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34237.md
[link_mcp_cve_project_cve_2026_34200]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34200.md
[link_mcp_cve_project_cve_2026_34163]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34163.md
[link_mcp_cve_project_cve_2026_33989]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-33989.md
[link_mcp_cve_project_cve_2026_33980]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-33980.md
[link_mcp_cve_project_cve_2026_33946]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-33946.md
[link_mcp_cve_project_cve_2026_33252]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-33252.md
[link_mcp_cve_project_cve_2026_33224]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-33224.md
[link_mcp_cve_project_cve_2026_33060]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-33060.md
[link_mcp_cve_project_cve_2026_33032]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-33032.md
[link_mcp_cve_project_cve_2026_33010]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-33010.md
[link_mcp_cve_project_cve_2026_32871]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32871.md
[link_mcp_cve_project_cve_2026_32625]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32625.md
[link_mcp_cve_project_cve_2026_32247]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32247.md
[link_mcp_cve_project_cve_2026_32211]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32211.md
[link_mcp_cve_project_cve_2026_32112]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32112.md
[link_mcp_cve_project_cve_2026_32111]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32111.md
[link_mcp_cve_project_cve_2026_31951]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-31951.md
[link_mcp_cve_project_cve_2026_31945]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-31945.md
[link_mcp_cve_project_cve_2026_31944]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-31944.md
[link_mcp_cve_project_cve_2026_30861]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30861.md
[link_mcp_cve_project_cve_2026_30856]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30856.md
[link_mcp_cve_project_cve_2026_30635]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30635.md
[link_mcp_cve_project_cve_2026_30625]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30625.md
[link_mcp_cve_project_cve_2026_30624]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30624.md
[link_mcp_cve_project_cve_2026_30623]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30623.md
[link_mcp_cve_project_cve_2026_30618]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30618.md
[link_mcp_cve_project_cve_2026_30617]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30617.md
[link_mcp_cve_project_cve_2026_30616]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30616.md
[link_mcp_cve_project_cve_2026_30615]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-30615.md
[link_mcp_cve_project_cve_2026_29787]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-29787.md
[link_mcp_cve_project_cve_2026_29783]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-29783.md
[link_mcp_cve_project_cve_2026_27896]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-27896.md
[link_mcp_cve_project_cve_2026_27826]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-27826.md
[link_mcp_cve_project_cve_2026_27825]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-27825.md
[link_mcp_cve_project_cve_2026_27735]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-27735.md
[link_mcp_cve_project_cve_2026_27203]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-27203.md
[link_mcp_cve_project_cve_2026_27124]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-27124.md
[link_mcp_cve_project_cve_2026_26118]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-26118.md
[link_mcp_cve_project_cve_2026_26029]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-26029.md
[link_mcp_cve_project_cve_2026_26015]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-26015.md
[link_mcp_cve_project_cve_2026_25905]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-25905.md
[link_mcp_cve_project_cve_2026_25904]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-25904.md
[link_mcp_cve_project_cve_2026_25650]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-25650.md
[link_mcp_cve_project_cve_2026_25546]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-25546.md
[link_mcp_cve_project_cve_2026_25536]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-25536.md
[link_mcp_cve_project_cve_2026_23882]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-23882.md
[link_mcp_cve_project_cve_2026_23744]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-23744.md
[link_mcp_cve_project_cve_2026_23523]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-23523.md
[link_mcp_cve_project_cve_2026_22793]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22793.md
[link_mcp_cve_project_cve_2026_22792]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22792.md
[link_mcp_cve_project_cve_2026_22785]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22785.md
[link_mcp_cve_project_cve_2026_22688]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22688.md
[link_mcp_cve_project_cve_2026_22252]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22252.md
[link_mcp_cve_project_cve_2026_21852]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-21852.md
[link_mcp_cve_project_cve_2026_2178]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-2178.md
[link_mcp_cve_project_cve_2026_21518]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-21518.md
[link_mcp_cve_project_cve_2026_20205]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-20205.md
[link_mcp_cve_project_cve_2026_1721]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-1721.md
[link_mcp_cve_project_cve_2026_13524]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-13524.md
[link_mcp_cve_project_cve_2026_13489]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-13489.md
[link_mcp_cve_project_cve_2026_13341]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-13341.md
[link_mcp_cve_project_cve_2026_12958]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12958.md
[link_mcp_cve_project_cve_2026_12957]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12957.md
[link_mcp_cve_project_cve_2026_12798]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12798.md
[link_mcp_cve_project_cve_2026_12774]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12774.md
[link_mcp_cve_project_cve_2026_12773]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12773.md
[link_mcp_cve_project_cve_2026_12537]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12537.md
[link_mcp_cve_project_cve_2026_12112]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12112.md
[link_mcp_cve_project_cve_2026_11719]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-11719.md
[link_mcp_cve_project_cve_2026_11624]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-11624.md
[link_mcp_cve_project_cve_2026_10789]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-10789.md
[link_mcp_cve_project_cve_2026_10280]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-10280.md
[link_mcp_cve_project_cve_2026_10277]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-10277.md
[link_mcp_cve_project_cve_2026_0758]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0758.md
[link_mcp_cve_project_cve_2026_0757]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0757.md
[link_mcp_cve_project_cve_2026_0756]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0756.md
[link_mcp_cve_project_cve_2026_0755]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0755.md
[link_mcp_cve_project_cve_2026_0621]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0621.md
[link_mcp_cve_project_cve_2025_9654]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-9654.md
[link_mcp_cve_project_cve_2025_9611]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-9611.md
[link_mcp_cve_project_cve_2025_8943]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-8943.md
[link_mcp_cve_project_cve_2025_8665]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-8665.md
[link_mcp_cve_project_cve_2025_71336]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-71336.md
[link_mcp_cve_project_cve_2025_69443]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-69443.md
[link_mcp_cve_project_cve_2025_69256]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-69256.md
[link_mcp_cve_project_cve_2025_69196]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-69196.md
[link_mcp_cve_project_cve_2025_68669]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-68669.md
[link_mcp_cve_project_cve_2025_68433]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-68433.md
[link_mcp_cve_project_cve_2025_68145]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-68145.md
[link_mcp_cve_project_cve_2025_68144]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-68144.md
[link_mcp_cve_project_cve_2025_68143]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-68143.md
[link_mcp_cve_project_cve_2025_67366]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-67366.md
[link_mcp_cve_project_cve_2025_66689]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66689.md
[link_mcp_cve_project_cve_2025_66580]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66580.md
[link_mcp_cve_project_cve_2025_66454]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66454.md
[link_mcp_cve_project_cve_2025_66416]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66416.md
[link_mcp_cve_project_cve_2025_66414]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66414.md
[link_mcp_cve_project_cve_2025_66404]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66404.md
[link_mcp_cve_project_cve_2025_66401]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66401.md
[link_mcp_cve_project_cve_2025_66336]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66336.md
[link_mcp_cve_project_cve_2025_66335]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66335.md
[link_mcp_cve_project_cve_2025_66222]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-66222.md
[link_mcp_cve_project_cve_2025_65720]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-65720.md
[link_mcp_cve_project_cve_2025_65719]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-65719.md
[link_mcp_cve_project_cve_2025_65513]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-65513.md
[link_mcp_cve_project_cve_2025_6515]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-6515.md
[link_mcp_cve_project_cve_2025_6514]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-6514.md
[link_mcp_cve_project_cve_2025_64443]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-64443.md
[link_mcp_cve_project_cve_2025_64340]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-64340.md
[link_mcp_cve_project_cve_2025_64132]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-64132.md
[link_mcp_cve_project_cve_2025_64109]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-64109.md
[link_mcp_cve_project_cve_2025_64106]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-64106.md
[link_mcp_cve_project_cve_2025_63604]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-63604.md
[link_mcp_cve_project_cve_2025_63603]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-63603.md
[link_mcp_cve_project_cve_2025_62801]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-62801.md
[link_mcp_cve_project_cve_2025_62800]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-62800.md
[link_mcp_cve_project_cve_2025_61685]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-61685.md
[link_mcp_cve_project_cve_2025_61591]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-61591.md
[link_mcp_cve_project_cve_2025_61590]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-61590.md
[link_mcp_cve_project_cve_2025_61260]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-61260.md
[link_mcp_cve_project_cve_2025_59956]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59956.md
[link_mcp_cve_project_cve_2025_59944]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59944.md
[link_mcp_cve_project_cve_2025_59834]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59834.md
[link_mcp_cve_project_cve_2025_59536]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59536.md
[link_mcp_cve_project_cve_2025_59528]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59528.md
[link_mcp_cve_project_cve_2025_59417]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59417.md
[link_mcp_cve_project_cve_2025_59377]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59377.md
[link_mcp_cve_project_cve_2025_59333]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59333.md
[link_mcp_cve_project_cve_2025_59163]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59163.md
[link_mcp_cve_project_cve_2025_59155]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-59155.md
[link_mcp_cve_project_cve_2025_58747]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-58747.md
[link_mcp_cve_project_cve_2025_58444]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-58444.md
[link_mcp_cve_project_cve_2025_58358]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-58358.md
[link_mcp_cve_project_cve_2025_58357]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-58357.md
[link_mcp_cve_project_cve_2025_58337]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-58337.md
[link_mcp_cve_project_cve_2025_58176]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-58176.md
[link_mcp_cve_project_cve_2025_58062]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-58062.md
[link_mcp_cve_project_cve_2025_56406]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-56406.md
[link_mcp_cve_project_cve_2025_54994]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-54994.md
[link_mcp_cve_project_cve_2025_54424]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-54424.md
[link_mcp_cve_project_cve_2025_54382]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-54382.md
[link_mcp_cve_project_cve_2025_54136]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-54136.md
[link_mcp_cve_project_cve_2025_54135]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-54135.md
[link_mcp_cve_project_cve_2025_54074]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-54074.md
[link_mcp_cve_project_cve_2025_54073]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-54073.md
[link_mcp_cve_project_cve_2025_53967]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53967.md
[link_mcp_cve_project_cve_2025_53832]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53832.md
[link_mcp_cve_project_cve_2025_53818]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53818.md
[link_mcp_cve_project_cve_2025_53372]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53372.md
[link_mcp_cve_project_cve_2025_53366]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53366.md
[link_mcp_cve_project_cve_2025_53365]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53365.md
[link_mcp_cve_project_cve_2025_53355]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53355.md
[link_mcp_cve_project_cve_2025_53110]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53110.md
[link_mcp_cve_project_cve_2025_53109]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53109.md
[link_mcp_cve_project_cve_2025_53107]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53107.md
[link_mcp_cve_project_cve_2025_53100]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53100.md
[link_mcp_cve_project_cve_2025_5277]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-5277.md
[link_mcp_cve_project_cve_2025_5276]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-5276.md
[link_mcp_cve_project_cve_2025_5273]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-5273.md
[link_mcp_cve_project_cve_2025_52573]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-52573.md
[link_mcp_cve_project_cve_2025_49596]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-49596.md
[link_mcp_cve_project_cve_2025_47777]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-47777.md
[link_mcp_cve_project_cve_2025_47274]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-47274.md
[link_mcp_cve_project_cve_2025_4143]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-4143.md
[link_mcp_cve_project_cve_2025_35028]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-35028.md
[link_mcp_cve_project_cve_2025_34072]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-34072.md
[link_mcp_cve_project_cve_2025_20381]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-20381.md
[link_mcp_cve_project_cve_2025_15063]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-15063.md
[link_mcp_cve_project_cve_2025_15061]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-15061.md
[link_mcp_cve_project_cve_2025_11445]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-11445.md
[link_mcp_cve_project_cve_2025_11286]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-11286.md
[link_mcp_cve_project_cve_2025_10619]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-10619.md
[link_mcp_cve_project_cve_2025_10193]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-10193.md
[link_ghsa_345p_7cg4_v4c7]: https://github.com/advisories/GHSA-345p-7cg4-v4c7
[link_ghsa_6mx4_4h42_r8vh]: https://github.com/advisories/GHSA-6mx4-4h42-r8vh
[link_ghsa_6xpm_ggf7_wc3p]: https://github.com/advisories/GHSA-6xpm-ggf7-wc3p
[link_ghsa_7f8r_222p_6f5g]: https://github.com/advisories/GHSA-7f8r-222p-6f5g
[link_ghsa_9h52_p55h_vw2f]: https://github.com/advisories/GHSA-9h52-p55h-vw2f
[link_ghsa_cr22_wjx7_2w6m]: https://github.com/advisories/GHSA-CR22-WJX7-2W6M
[link_ghsa_hc55_p739_j48w]: https://github.com/advisories/GHSA-hc55-p739-j48w
[link_ghsa_hvrp_rf83_w775]: https://github.com/advisories/GHSA-hvrp-rf83-w775
[link_ghsa_jpw9_pfvf_9f58]: https://github.com/advisories/GHSA-jpw9-pfvf-9f58
[link_ghsa_pjp5_fpmr_3349]: https://github.com/advisories/GHSA-pjp5-fpmr-3349
[link_ghsa_w48q_cv73_mx4w]: https://github.com/advisories/GHSA-W48Q-CV73-MX4W
