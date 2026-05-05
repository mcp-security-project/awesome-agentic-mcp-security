# MCP CVEs and Advisories

## Contents

- [Official advisory dashboards](#official-advisory-dashboards)
- [Official advisory snapshot](#official-advisory-snapshot)
  - [modelcontextprotocol/servers](#modelcontextprotocolservers)
  - [modelcontextprotocol/inspector](#modelcontextprotocolinspector)
  - [modelcontextprotocol/python-sdk](#modelcontextprotocolpython-sdk)
  - [modelcontextprotocol/typescript-sdk](#modelcontextprotocoltypescript-sdk)
  - [modelcontextprotocol/go-sdk](#modelcontextprotocolgo-sdk)
  - [modelcontextprotocol/java-sdk](#modelcontextprotocoljava-sdk)
- [Why This Page Matters](#why-this-page-matters)

---

## Official advisory dashboards

| Repository / component | Security dashboard | Snapshot |
| --- | --- | --- |
| `modelcontextprotocol/servers` | [Security][link_github_com_modelcontextprotocol_servers_security] | Published advisories for `server-filesystem` and `mcp-server-git` |
| `modelcontextprotocol/inspector` | [Security][link_github_com_modelcontextprotocol_inspector_security] | Published advisories present |
| `modelcontextprotocol/python-sdk` | [Security][link_github_com_modelcontextprotocol_python_sdk_security] | Published advisories present |
| `modelcontextprotocol/typescript-sdk` | [Security][link_github_com_modelcontextprotocol_typescript_sdk_security] | Published advisories present |
| `modelcontextprotocol/go-sdk` | [Security][link_github_com_modelcontextprotocol_go_sdk_security] | Published advisories present |
| `modelcontextprotocol/java-sdk` | [Security][link_github_com_modelcontextprotocol_java_sdk_security] | Published advisories present |
| `modelcontextprotocol/csharp-sdk` | [Security][link_github_com_modelcontextprotocol_csharp_sdk_security] | No published advisories listed on 2026-05-05 |
| `modelcontextprotocol/rust-sdk` | [Security][link_github_com_modelcontextprotocol_rust_sdk_security] | No published advisories listed on 2026-05-05 |

---

## Official advisory snapshot

### modelcontextprotocol/servers

- [GHSA-q66q-fx2p-7w4m / CVE-2025-53109][link_ghsa_q66q_fx2p_7w4m] — `@modelcontextprotocol/server-filesystem` path validation bypass via prefix matching and symlink handling. **High.** Published 2025-07-01. Patched in `2025.7.1`.
- [GHSA-hc55-p739-j48w / CVE-2025-53110][link_ghsa_hc55_p739_j48w] — `@modelcontextprotocol/server-filesystem` path validation bypass via colliding path prefix. **High.** Published 2025-07-01. Patched in `2025.7.1`.
- [GHSA-5cgr-j3jf-jw3v / CVE-2025-68143][link_ghsa_5cgr_j3jf_jw3v] — `mcp-server-git` allowed unrestricted `git_init` at arbitrary filesystem locations. **Moderate.** Published 2025-12-17. Patched in `2025.9.25`.
- [GHSA-9xwc-hfwc-8w59 / CVE-2025-68144][link_ghsa_9xwc_hfwc_8w59] — `mcp-server-git` argument injection in `git_diff` and `git_checkout` could overwrite local files. **Moderate.** Published 2025-12-17. Patched in `2025.12.18`.
- [GHSA-j22h-9j4x-23w5 / CVE-2025-68145][link_ghsa_j22h_9j4x_23w5] — `mcp-server-git` missing path validation when using `--repository`. **Moderate.** Published 2025-12-17. Patched in `2025.12.18`.
- [GHSA-vjqx-cfc4-9h6v / CVE-2026-27735][link_ghsa_vjqx_cfc4_9h6v] — `mcp-server-git` path traversal in `git_add` allowed staging files outside repository boundaries. **Moderate.** Published 2026-02-25. Patched in `2026.1.14`.

### modelcontextprotocol/inspector

- [GHSA-7f8r-222p-6f5g / CVE-2025-49596][link_ghsa_7f8r_222p_6f5g] — MCP Inspector proxy lacked authentication between the browser client and proxy, enabling remote code execution paths via unauthenticated stdio launches. **Critical.** Published 2025-06-13. Patched in `0.14.1`.
- [GHSA-g9hg-qhmf-q45m / CVE-2025-58444][link_ghsa_g9hg_qhmf_q45m] — Inspector XSS when rendering a redirect URL from an untrusted MCP server, with possible command execution on the developer machine through the built-in proxy. **High.** Published 2025-09-06. Patched in `0.16.6`.

### modelcontextprotocol/python-sdk

- [GHSA-3qhf-m339-9g5v][link_github_com_modelcontextprotocol_python_sdk_security] — FastMCP server validation error leading to denial of service. **High.** Published 2025-07-04.
- [GHSA-j975-95f5-7wqh][link_github_com_modelcontextprotocol_python_sdk_security] — unhandled exception in Streamable HTTP transport leading to denial of service. **High.** Published 2025-07-04.
- [GHSA-9h52-p55h-vw2f / CVE-2025-66416][link_ghsa_9h52_p55h_vw2f] — DNS rebinding protection disabled by default for localhost HTTP servers. **High.** Published 2025-12-02. Patched in `1.23.0`.

### modelcontextprotocol/typescript-sdk

- [GHSA-w48q-cv73-mx4w / CVE-2025-66414][link_ghsa_w48q_cv73_mx4w] — DNS rebinding protection disabled by default for localhost HTTP servers. **High.** Published 2025-12-02. Patched in `1.24.0`.
- [GHSA-cqwc-fm46-7fff / CVE-2026-0621][link_ghsa_cqwc_fm46_7fff] — `UriTemplate` ReDoS vulnerability that could hang MCP servers handling malicious resource URIs. **High.** Published 2026-01-07 in the security dashboard; patched in `1.25.2`.
- [GHSA-345p-7cg4-v4c7 / CVE-2026-25536][link_ghsa_345p_7cg4_v4c7] — cross-client data leak caused by shared server / transport instance reuse in HTTP deployments. **High.** Published 2026-02-04. Patched in `1.26.0`.

### modelcontextprotocol/go-sdk

- [GHSA-wvj2-96wp-fq3f][link_github_com_modelcontextprotocol_go_sdk_security] — improper handling of case sensitivity. **High.** Published 2026-02-25.
- [GHSA-89xv-2j6f-qhc8][link_github_com_modelcontextprotocol_go_sdk_security] — cross-site tool execution for HTTP servers without authorization. **High.** Published 2026-03-18.
- [GHSA-q382-vc8q-7jhj][link_github_com_modelcontextprotocol_go_sdk_security] — improper handling of null Unicode character when parsing JSON. **High.** Published 2026-03-18.
- [GHSA-xw59-hvm2-8pj6][link_github_com_modelcontextprotocol_go_sdk_security] — DNS rebinding protection disabled by default for localhost HTTP servers. **High.** Published 2026-03-30.

### modelcontextprotocol/java-sdk

- [GHSA-hv2w-8mjj-jw22][link_github_com_modelcontextprotocol_java_sdk_security] — hardcoded wildcard CORS (`Access-Control-Allow-Origin: *`). **Moderate.** Published 2026-03-30.
- [GHSA-8jxr-pr72-r468][link_github_com_modelcontextprotocol_java_sdk_security] — DNS rebinding vulnerability in the Java SDK. **High.** Published 2026-04-07.

---

## Why This Page Matters

- MCP security issues are no longer limited to prompt-injection research; there are now published advisories across **reference servers, SDKs, and developer tooling**.
- Several advisories cluster around a few recurring themes: **path validation**, **HTTP localhost exposure**, **cross-origin / rebinding risks**, **unsafe tool execution paths**, and **state leakage across clients**.
- If you maintain an MCP allowlist, golden image, or internal platform standard, these dashboard links are the fastest place to watch for new official advisories.


[link_github_com_modelcontextprotocol_csharp_sdk_security]: https://github.com/modelcontextprotocol/csharp-sdk/security
[link_github_com_modelcontextprotocol_go_sdk_security]: https://github.com/modelcontextprotocol/go-sdk/security
[link_github_com_modelcontextprotocol_inspector_security]: https://github.com/modelcontextprotocol/inspector/security
[link_github_com_modelcontextprotocol_java_sdk_security]: https://github.com/modelcontextprotocol/java-sdk/security
[link_github_com_modelcontextprotocol_python_sdk_security]: https://github.com/modelcontextprotocol/python-sdk/security
[link_github_com_modelcontextprotocol_rust_sdk_security]: https://github.com/modelcontextprotocol/rust-sdk/security
[link_github_com_modelcontextprotocol_servers]: https://github.com/modelcontextprotocol/servers
[link_github_com_modelcontextprotocol_servers_security]: https://github.com/modelcontextprotocol/servers/security
[link_github_com_modelcontextprotocol_typescript_sdk_security]: https://github.com/modelcontextprotocol/typescript-sdk/security
[link_ghsa_345p_7cg4_v4c7]: https://github.com/advisories/GHSA-345p-7cg4-v4c7
[link_ghsa_3qhf_m339_9g5v]: https://github.com/advisories/GHSA-3qhf-m339-9g5v
[link_ghsa_5cgr_j3jf_jw3v]: https://github.com/advisories/GHSA-5cgr-j3jf-jw3v
[link_ghsa_7f8r_222p_6f5g]: https://github.com/advisories/GHSA-7f8r-222p-6f5g
[link_ghsa_9h52_p55h_vw2f]: https://github.com/advisories/GHSA-9h52-p55h-vw2f
[link_ghsa_9xwc_hfwc_8w59]: https://github.com/advisories/GHSA-9xwc-hfwc-8w59
[link_ghsa_cqwc_fm46_7fff]: https://github.com/modelcontextprotocol/typescript-sdk/security/advisories/GHSA-cqwc-fm46-7fff
[link_ghsa_g9hg_qhmf_q45m]: https://github.com/advisories/GHSA-g9hg-qhmf-q45m
[link_ghsa_hc55_p739_j48w]: https://github.com/advisories/GHSA-hc55-p739-j48w
[link_ghsa_j22h_9j4x_23w5]: https://github.com/advisories/GHSA-j22h-9j4x-23w5
[link_ghsa_q66q_fx2p_7w4m]: https://github.com/advisories/GHSA-q66q-fx2p-7w4m
[link_ghsa_vjqx_cfc4_9h6v]: https://github.com/advisories/GHSA-vjqx-cfc4-9h6v
[link_ghsa_w48q_cv73_mx4w]: https://github.com/advisories/GHSA-w48q-cv73-mx4w
