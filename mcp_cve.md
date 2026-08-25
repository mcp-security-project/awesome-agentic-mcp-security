# MCP CVE catalogs

Repositories and pages that maintain **structured catalogs of published CVEs** affecting MCP servers, clients, SDKs, gateways, and related tooling — plus a curated index of published CVE IDs from public advisories (NVD, GitHub Security Advisories). For comprehensive coverage (111+ entries), use the external catalogs below.

## Contents

- [External catalogs](#external-catalogs)
- [Advisory sources](#advisory-sources)
- [Published CVEs](#published-cves)
  - [Official MCP SDKs and org repositories](#official-mcp-sdks-and-org-repositories)
  - [Third-party MCP servers and client libraries](#third-party-mcp-servers-and-client-libraries)
  - [MCP client platforms and STDIO configuration](#mcp-client-platforms-and-stdio-configuration)

---

## External catalogs

| Catalog | Description | Last updated |
| --- | --- | --- |
| [vermava/mcp-cve-project][link_vermava_mcp_cve_project] | Indexed list of **111+** MCP-related CVEs with per-CVE notes (`cves/`). | [![last commit](https://badgen.net/github/last-commit/vermava/mcp-cve-project)][link_vermava_mcp_cve_project_commits] |
| [vineethsai/vulnerablemcp][link_vineethsai_vulnerablemcp] | Searchable MCP vulnerability catalog (JSON); many entries map to CVE IDs by affected component. **Site:** [vulnerablemcp.info](https://vulnerablemcp.info) | [![last commit](https://badgen.net/github/last-commit/vineethsai/vulnerablemcp)][link_vineethsai_vulnerablemcp_commits] |

**Contributing:** Submit new catalog repositories via pull request. For **Last updated**, use `https://badgen.net/github/last-commit/{github-id}/{repo}`. Submit individual CVE records to the catalog that owns the advisory.

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

CVE IDs below are drawn from NVD and GitHub Security Advisories as of **catalog reviewed: 2026-08-25**. Fixed-version columns reflect vendor advisory text; verify against your deployment before relying on them for compliance.

### Official MCP SDKs and org repositories

| CVE | Affected component | Issue | Fixed in | Links |
| --- | --- | --- | --- | --- |
| CVE-2025-66414 | TypeScript SDK (`@modelcontextprotocol/sdk`) | DNS rebinding — unauthenticated localhost HTTP with `StreamableHTTPServerTransport` / `SSEServerTransport` | ≥ 1.24.0 | [NVD][link_nvd_cve_2025_66414] · [GHSA-w48q-cv73-mx4w][link_ghsa_w48q_cv73_mx4w] |
| CVE-2026-25536 | TypeScript SDK (`@modelcontextprotocol/sdk`) | Cross-client response data leak when reusing `McpServer` / transport across concurrent clients (stateless Streamable HTTP) | ≥ 1.26.0 | [NVD][link_nvd_cve_2026_25536] · [GHSA-345p-7cg4-v4c7][link_ghsa_345p_7cg4_v4c7] |
| CVE-2025-66416 | Python SDK (`mcp` on PyPI) | DNS rebinding — unauthenticated localhost HTTP with FastMCP streamable HTTP or SSE | ≥ 1.23.0 | [NVD][link_nvd_cve_2025_66416] · [GHSA-9h52-p55h-vw2f][link_ghsa_9h52_p55h_vw2f] |
| CVE-2026-52869 | Python SDK (`mcp` on PyPI) | SSE / stateful Streamable HTTP session routing by ID only — bearer-auth principal not verified (`SseServerTransport`, `StreamableHTTPSessionManager`) | ≥ 1.27.2 | [NVD][link_nvd_cve_2026_52869] · [GHSA-jpw9-pfvf-9f58][link_ghsa_jpw9_pfvf_9f58] |
| CVE-2026-52870 | Python SDK (`mcp` on PyPI) | Experimental task handlers — any client can list/get/cancel other clients' tasks when `enable_tasks()` is used | ≥ 1.27.2 | [NVD][link_nvd_cve_2026_52870] · [GHSA-hvrp-rf83-w775][link_ghsa_hvrp_rf83_w775] |
| CVE-2026-42559 | Rust SDK (`rmcp` crate) | Streamable HTTP server — missing `Host` header validation enables DNS rebinding to loopback/private MCP | ≥ 1.4.0 | [NVD][link_nvd_cve_2026_42559] |
| CVE-2026-27896 | Go SDK (`modelcontextprotocol/go-sdk`) | HTTP transport security weakness (session / routing class issue) | ≥ 1.4.1 | [NVD][link_nvd_cve_2026_27896] |
| CVE-2026-33252 | Go SDK (`modelcontextprotocol/go-sdk`) | HTTP transport security weakness | ≥ 1.4.1 | [NVD][link_nvd_cve_2026_33252] |
| CVE-2026-34237 | Java SDK (`modelcontextprotocol/java-sdk`) | HTTP transport / session security weakness | ≥ 1.0.0 | [NVD][link_nvd_cve_2026_34237] |
| CVE-2026-33946 | Ruby SDK (`mcp` gem) | Streamable HTTP — SSE session hijacking when attacker obtains valid session ID | ≥ 0.9.2 | [NVD][link_nvd_cve_2026_33946] |
| CVE-2026-63118 | Ruby SDK (`mcp` gem) | Streamable HTTP — lacks DNS-rebinding / Host / Origin protection | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_63118] |
| CVE-2026-63119 | Ruby SDK (`mcp` gem) | Streamable HTTP / stdio transport memory exhaustion (DoS) | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_63119] |
| CVE-2026-67430 | Ruby SDK (`mcp` gem) | Unbounded session retention in Streamable HTTP — memory exhaustion via initialize flood | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_67430] |
| CVE-2026-67431 | Ruby SDK (`mcp` gem) | SSE session poisoning — session ID not bound to session owner | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_67431] |
| CVE-2026-67432 | Ruby SDK (`mcp` gem) | Unbounded JSON-RPC POST body in Streamable HTTP — memory DoS | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_67432] |
| CVE-2025-49596 | MCP Inspector (`@modelcontextprotocol/inspector`) | Missing auth on Inspector proxy → RCE via unauthenticated stdio MCP launch (CSRF / DNS rebinding from malicious sites) | ≥ 0.14.1 | [NVD][link_nvd_cve_2025_49596] · [GHSA-7f8r-222p-6f5g][link_ghsa_7f8r_222p_6f5g] |
| CVE-2025-53109 | Reference server — filesystem (`@modelcontextprotocol/server-filesystem`) | Path validation bypass via symlinks within allowed directories | ≥ 2025.7.1 / 0.6.4 | [NVD][link_nvd_cve_2025_53109] |
| CVE-2025-53110 | Reference server — filesystem (`@modelcontextprotocol/server-filesystem`) | Path validation bypass via colliding directory prefix match | ≥ 2025.7.1 / 0.6.4 | [NVD][link_nvd_cve_2025_53110] · [GHSA-hc55-p739-j48w][link_ghsa_hc55_p739_j48w] |
| CVE-2026-27735 | Reference servers (`modelcontextprotocol/servers`) | Security issue in bundled reference server implementations | See NVD | [NVD][link_nvd_cve_2026_27735] |
| CVE-2026-44427 | MCP Registry (`modelcontextprotocol/registry`) | Registry security weakness | See NVD | [NVD][link_nvd_cve_2026_44427] |
| CVE-2026-44428 | MCP Registry (`modelcontextprotocol/registry`) | Registry security weakness | See NVD | [NVD][link_nvd_cve_2026_44428] |
| CVE-2026-44429 | MCP Registry (`modelcontextprotocol/registry`) | Registry security weakness | See NVD | [NVD][link_nvd_cve_2026_44429] |
| CVE-2026-44430 | MCP Registry (`modelcontextprotocol/registry`) | Registry security weakness | See NVD | [NVD][link_nvd_cve_2026_44430] |
| CVE-2026-45781 | MCP Registry (`modelcontextprotocol/registry`) | Registry information disclosure / low-severity issue | See NVD | [NVD][link_nvd_cve_2026_45781] |

### Third-party MCP servers and client libraries

| CVE | Affected component | Issue | Fixed in | Links |
| --- | --- | --- | --- | --- |
| CVE-2025-6514 | `mcp-remote` (npm) | OS command injection — malicious OAuth `authorization_endpoint` from untrusted MCP server | ≥ 0.1.16 | [NVD][link_nvd_cve_2025_6514] · [GHSA-6xpm-ggf7-wc3p][link_ghsa_6xpm_ggf7_wc3p] |
| CVE-2025-54073 | `mcp-package-docs` | Command injection — unsanitized input passed to `child_process.exec` | ≥ 0.1.28 | [NVD][link_nvd_cve_2025_54073] |
| CVE-2025-5277 | `aws-mcp-server` | Command injection — unsanitized AWS/shell commands in CLI executor | See NVD | [NVD][link_nvd_cve_2025_5277] |
| CVE-2026-61459 | `mcp-server-kubernetes` | Argument injection in structured kubectl tools — bearer token exfil via `--server` redirect | ≥ 3.9.0 | [NVD][link_nvd_cve_2026_61459] |
| CVE-2026-47250 | `mcp-server-kubernetes` | `kubectl_generic` — unrestricted flag passthrough enables bearer token exfiltration | ≥ 3.7.0 | [NVD][link_nvd_cve_2026_47250] · [GHSA-6mx4-4h42-r8vh][link_ghsa_6mx4_4h42_r8vh] |
| CVE-2026-46519 | `mcp-server-kubernetes` | Tool access controls enforced at `tools/list` only — bypass at `tools/call` | ≥ 3.6.0 | [NVD][link_nvd_cve_2026_46519] · [GHSA-CR22-WJX7-2W6M][link_ghsa_cr22_wjx7_2w6m] |
| CVE-2025-66404 | `mcp-server-kubernetes` | Command / argument injection in kubectl tooling | See NVD | [NVD][link_nvd_cve_2025_66404] |
| CVE-2025-65719 | `kubectl-mcp-server` | Command injection — unsanitized `namespace` with `subprocess` + `shell=True` | ≥ 1.2.0 | [NVD][link_nvd_cve_2025_65719] |
| CVE-2025-68143 | Git MCP server | Unrestricted `git_init` behavior | See NVD | [NVD][link_nvd_cve_2025_68143] |
| CVE-2025-68144 | Git MCP server | Argument injection in `git_diff` | See NVD | [NVD][link_nvd_cve_2025_68144] |
| CVE-2025-68145 | Git MCP server | Path validation bypass | See NVD | [NVD][link_nvd_cve_2025_68145] |
| CVE-2026-48529 | GitHub MCP Server (`github/github-mcp-server`) | Lockdown-mode HTTP — process-global cache binds to first user; later users checked under wrong identity | See advisory | [NVD][link_nvd_cve_2026_48529] · [GHSA-pjp5-fpmr-3349][link_ghsa_pjp5_fpmr_3349] |
| CVE-2026-47427 | GitHub MCP Server (`github/github-mcp-server`) | Nil pointer dereference — unauthenticated DoS | > 0.33.0 | [NVD][link_nvd_cve_2026_47427] |
| CVE-2025-67366 | `filesystem-mcp` (SylphxAI) | Path traversal — escape configured directory boundaries | See NVD | [NVD][link_nvd_cve_2025_67366] · [vulnerablemcp][link_vulnerablemcp_2025_67366] |
| CVE-2026-7400 | `filesystem-mcp-server` (geekgod382) | Path traversal in `read_file_tool` / `write_file_tool` | ≥ 1.1.0 | [NVD][link_nvd_cve_2026_7400] |

### MCP client platforms and STDIO configuration

Platforms that spawn MCP servers from user-supplied `command` / `args` in client config (`mcp.json`, IDE settings). STDIO transport itself executes configured binaries with no SDK-level allowlist — downstream apps must validate config sources ([OX Security advisory](https://www.ox.security/blog/mcp-supply-chain-advisory-rce-vulnerabilities-across-the-ai-ecosystem/), [CSA research note](https://labs.cloudsecurityalliance.org/research/csa-research-note-mcp-by-design-rce-ox-security-20260420-csa/)).

| CVE | Affected component | Issue | Fixed in | Links |
| --- | --- | --- | --- | --- |
| CVE-2026-30623 | LiteLLM | STDIO MCP config — arbitrary command execution via unsanitized `command` field | See NVD | [NVD][link_nvd_cve_2026_30623] |
| CVE-2026-30615 | Windsurf IDE | STDIO MCP config — command injection (zero-interaction variant in OX disclosure) | See NVD | [NVD][link_nvd_cve_2026_30615] |
| CVE-2026-30624 | Agent Zero | STDIO MCP config — command injection / RCE | See NVD | [NVD][link_nvd_cve_2026_30624] |
| CVE-2026-40933 | Flowise | STDIO custom MCP — server-side RCE on chatflow import | See NVD | [NVD][link_nvd_cve_2026_40933] |
| CVE-2026-26015 | DocsGPT | STDIO MCP config — command injection / RCE | See NVD | [NVD][link_nvd_cve_2026_26015] |
| CVE-2025-65720 | GPT Researcher | STDIO MCP config — command injection / RCE | See NVD | [NVD][link_nvd_cve_2025_65720] |
| CVE-2026-30616 | Jaaz | STDIO MCP config — command injection / RCE | See NVD | [NVD][link_nvd_cve_2026_30616] |
| CVE-2026-30617 | Langchain-Chatchat | STDIO MCP config — command injection / RCE | See NVD | [NVD][link_nvd_cve_2026_30617] |
| CVE-2026-33224 | Bisheng | STDIO MCP config — command injection / RCE | See NVD | [NVD][link_nvd_cve_2026_33224] |
| CVE-2026-30625 | Upsonic | STDIO MCP config — command injection / RCE | See NVD | [NVD][link_nvd_cve_2026_30625] |
| CVE-2026-22252 | LibreChat | STDIO MCP server registration — command injection / RCE | See NVD | [NVD][link_nvd_cve_2026_22252] |
| CVE-2026-22688 | WeKnora | STDIO MCP server registration — command injection / RCE | See NVD | [NVD][link_nvd_cve_2026_22688] |
| CVE-2025-54994 | `@akoskm/create-mcp-server-stdio` | STDIO scaffolding — command injection in generated / configured server spawn | See NVD | [NVD][link_nvd_cve_2025_54994] |
| CVE-2025-54136 | Cursor IDE (MCPoison) | MCP config trust persistence — malicious MCP config retained across sessions (related STDIO / config attack class) | See NVD | [NVD][link_nvd_cve_2025_54136] |

---

[link_vermava_mcp_cve_project]: https://github.com/vermava/mcp-cve-project
[link_vermava_mcp_cve_project_commits]: https://github.com/vermava/mcp-cve-project/commits/main/
[link_vineethsai_vulnerablemcp]: https://github.com/vineethsai/vulnerablemcp
[link_vineethsai_vulnerablemcp_commits]: https://github.com/vineethsai/vulnerablemcp/commits/main/
[link_opencve_modelcontextprotocol]: https://app.opencve.io/cve/?vendor=modelcontextprotocol
[link_github_advisories_mcp_search]: https://github.com/advisories?query=model+context+protocol
[link_mcp_python_sdk_advisories]: https://github.com/modelcontextprotocol/python-sdk/security/advisories
[link_mcp_typescript_sdk_advisories]: https://github.com/modelcontextprotocol/typescript-sdk/security/advisories
[link_mcp_inspector_advisories]: https://github.com/modelcontextprotocol/inspector/security/advisories
[link_pysec_mcp]: https://github.com/pypa/advisory-database/tree/main/vulns/mcp
[link_nvd_cve_2025_49596]: https://nvd.nist.gov/vuln/detail/CVE-2025-49596
[link_nvd_cve_2025_5277]: https://nvd.nist.gov/vuln/detail/CVE-2025-5277
[link_nvd_cve_2025_53109]: https://nvd.nist.gov/vuln/detail/CVE-2025-53109
[link_nvd_cve_2025_53110]: https://nvd.nist.gov/vuln/detail/CVE-2025-53110
[link_nvd_cve_2025_54073]: https://nvd.nist.gov/vuln/detail/CVE-2025-54073
[link_nvd_cve_2025_54136]: https://nvd.nist.gov/vuln/detail/CVE-2025-54136
[link_nvd_cve_2025_54994]: https://nvd.nist.gov/vuln/detail/CVE-2025-54994
[link_nvd_cve_2025_6514]: https://nvd.nist.gov/vuln/detail/CVE-2025-6514
[link_nvd_cve_2025_65719]: https://nvd.nist.gov/vuln/detail/CVE-2025-65719
[link_nvd_cve_2025_65720]: https://nvd.nist.gov/vuln/detail/CVE-2025-65720
[link_nvd_cve_2025_66404]: https://nvd.nist.gov/vuln/detail/CVE-2025-66404
[link_nvd_cve_2025_66414]: https://nvd.nist.gov/vuln/detail/CVE-2025-66414
[link_nvd_cve_2025_66416]: https://nvd.nist.gov/vuln/detail/CVE-2025-66416
[link_nvd_cve_2025_67366]: https://nvd.nist.gov/vuln/detail/CVE-2025-67366
[link_nvd_cve_2025_68143]: https://nvd.nist.gov/vuln/detail/CVE-2025-68143
[link_nvd_cve_2025_68144]: https://nvd.nist.gov/vuln/detail/CVE-2025-68144
[link_nvd_cve_2025_68145]: https://nvd.nist.gov/vuln/detail/CVE-2025-68145
[link_nvd_cve_2026_22252]: https://nvd.nist.gov/vuln/detail/CVE-2026-22252
[link_nvd_cve_2026_22688]: https://nvd.nist.gov/vuln/detail/CVE-2026-22688
[link_nvd_cve_2026_25536]: https://nvd.nist.gov/vuln/detail/CVE-2026-25536
[link_nvd_cve_2026_26015]: https://nvd.nist.gov/vuln/detail/CVE-2026-26015
[link_nvd_cve_2026_27735]: https://nvd.nist.gov/vuln/detail/CVE-2026-27735
[link_nvd_cve_2026_27896]: https://nvd.nist.gov/vuln/detail/CVE-2026-27896
[link_nvd_cve_2026_30615]: https://nvd.nist.gov/vuln/detail/CVE-2026-30615
[link_nvd_cve_2026_30616]: https://nvd.nist.gov/vuln/detail/CVE-2026-30616
[link_nvd_cve_2026_30617]: https://nvd.nist.gov/vuln/detail/CVE-2026-30617
[link_nvd_cve_2026_30623]: https://nvd.nist.gov/vuln/detail/CVE-2026-30623
[link_nvd_cve_2026_30624]: https://nvd.nist.gov/vuln/detail/CVE-2026-30624
[link_nvd_cve_2026_30625]: https://nvd.nist.gov/vuln/detail/CVE-2026-30625
[link_nvd_cve_2026_33224]: https://nvd.nist.gov/vuln/detail/CVE-2026-33224
[link_nvd_cve_2026_33252]: https://nvd.nist.gov/vuln/detail/CVE-2026-33252
[link_nvd_cve_2026_33946]: https://nvd.nist.gov/vuln/detail/CVE-2026-33946
[link_nvd_cve_2026_34237]: https://nvd.nist.gov/vuln/detail/CVE-2026-34237
[link_nvd_cve_2026_40933]: https://nvd.nist.gov/vuln/detail/CVE-2026-40933
[link_nvd_cve_2026_42559]: https://nvd.nist.gov/vuln/detail/CVE-2026-42559
[link_nvd_cve_2026_44427]: https://nvd.nist.gov/vuln/detail/CVE-2026-44427
[link_nvd_cve_2026_44428]: https://nvd.nist.gov/vuln/detail/CVE-2026-44428
[link_nvd_cve_2026_44429]: https://nvd.nist.gov/vuln/detail/CVE-2026-44429
[link_nvd_cve_2026_44430]: https://nvd.nist.gov/vuln/detail/CVE-2026-44430
[link_nvd_cve_2026_45781]: https://nvd.nist.gov/vuln/detail/CVE-2026-45781
[link_nvd_cve_2026_46519]: https://nvd.nist.gov/vuln/detail/CVE-2026-46519
[link_nvd_cve_2026_47250]: https://nvd.nist.gov/vuln/detail/CVE-2026-47250
[link_nvd_cve_2026_47427]: https://nvd.nist.gov/vuln/detail/CVE-2026-47427
[link_nvd_cve_2026_48529]: https://nvd.nist.gov/vuln/detail/CVE-2026-48529
[link_nvd_cve_2026_52869]: https://nvd.nist.gov/vuln/detail/CVE-2026-52869
[link_nvd_cve_2026_52870]: https://nvd.nist.gov/vuln/detail/CVE-2026-52870
[link_nvd_cve_2026_61459]: https://nvd.nist.gov/vuln/detail/CVE-2026-61459
[link_nvd_cve_2026_63118]: https://nvd.nist.gov/vuln/detail/CVE-2026-63118
[link_nvd_cve_2026_63119]: https://nvd.nist.gov/vuln/detail/CVE-2026-63119
[link_nvd_cve_2026_67430]: https://nvd.nist.gov/vuln/detail/CVE-2026-67430
[link_nvd_cve_2026_67431]: https://nvd.nist.gov/vuln/detail/CVE-2026-67431
[link_nvd_cve_2026_67432]: https://nvd.nist.gov/vuln/detail/CVE-2026-67432
[link_nvd_cve_2026_7400]: https://nvd.nist.gov/vuln/detail/CVE-2026-7400
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
[link_vulnerablemcp_2025_67366]: https://vulnerablemcp.info/vuln/cve-2025-67366-filesystem-mcp-path-traversal.html
