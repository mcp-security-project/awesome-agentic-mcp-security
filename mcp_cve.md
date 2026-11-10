# MCP CVE catalogs

Repositories and pages that maintain **structured catalogs of published CVEs** affecting MCP servers, clients, SDKs, gateways, and related tooling — plus a curated index synced from [mcp-cve-project](https://github.com/mcp-security-project/mcp-cve-project). For searchable JSON and per-CVE notes, also see [vulnerablemcp](https://vulnerablemcp.info).

## Contents

- [External catalogs](#external-catalogs)
- [Advisory sources](#advisory-sources)
- [Published CVEs](#published-cves)
- [GitHub advisories without a CVE](#github-advisories-without-a-cve)

---

## External catalogs

| Catalog | Description | Last updated |
| --- | --- | --- |
| [mcp-security-project/mcp-cve-project][link_mcp_cve_project] | Curated index of **765** MCP-related CVEs (802 advisories, including GHSA-only notes) with per-CVE notes (`cves/`) and OWASP MCP Top 10 mapping. | [![last commit](https://badgen.net/github/last-commit/mcp-security-project/mcp-cve-project)][link_mcp_cve_project_commits] |

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

**765** indexed CVE IDs from [mcp-cve-project](https://github.com/mcp-security-project/mcp-cve-project) as of **catalog synced: 2026-11-10**, plus **26** added after checking NVD and GitHub advisories for Model Context Protocol, MCP server, SDK transport, DNS rebinding, command injection, path traversal, stdio RCE, and MCP-config code execution (including CVE-2026-22708). Sorted by CVE ID (newest first). Fixed-version column reflects vendor advisory text where known; verify against your deployment.

| CVE | Affected component | Issue (OWASP MCP Top 10 category) | Fixed in | Links |
| --- | --- | --- | --- | --- |
| CVE-2026-124503 | sooperset mcp-atlassian through 0.24.0: `validate_safe_path` in `src/mcp_atlassian/utils/io.py` accepts a `path` argument that escapes the intended directory (path traversal). | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_124503] |
| CVE-2026-123812 | Dynatrace MCP Server before 1.8.7: `create_dynatrace_notebook` writes a document without the human-approval gate used by the server's other write tools. | Insufficient Authentication & Authorization | ≥ 1.8.7 | [NVD][link_nvd_cve_2026_123812] · [GHSA][link_ghsa_pc2w_4mq8_32qw] |
| CVE-2026-123811 | Dynatrace MCP Server before 2.0.0 started with `--http` accepts `tools/call` without authentication, session checks, or Host/Origin protections, and runs the call with the server's Dynatrace credentials. | Insufficient Authentication & Authorization | ≥ 2.0.0 | [NVD][link_nvd_cve_2026_123811] · [GHSA][link_ghsa_p7w7_4929_vpj5] |
| CVE-2026-123810 | Dynatrace MCP Server before 2.1.1 interpolates caller-controlled values into DQL in several read tools without sufficient validation or escaping. | Command Injection & Execution | ≥ 2.1.1 | [NVD][link_nvd_cve_2026_123810] · [GHSA][link_ghsa_pqh8_p93p_2rx7] |
| CVE-2026-123809 | Dynatrace MCP Server before 2.0.0 inserts caller-controlled `teamName`, `problemType`, and `channel` values into a workflow template without neutralizing Jinja2 expressions. | Command Injection & Execution | ≥ 2.0.0 | [NVD][link_nvd_cve_2026_123809] · [GHSA][link_ghsa_xrmj_5g4g_8987] |
| CVE-2026-123272 | Mark3labs mcp-go before v1.2.1 contains an improper validation vulnerability in OAuthHandler.fetchServerMetadata that allows malicious MCP servers to obtain tokens for other resources by declaring arbitrary resources in well-known metadata. | Insufficient Authentication & Authorization | ≥ 1.2.1 | [NVD][link_nvd_cve_2026_123272] · [mcp-cve-project][link_mcp_cve_project_cve_2026_123272] · [GHSA][link_ghsa_xf6j_693p_wqxx] |
| CVE-2026-123271 | ChatCLI before v1.215.2 contains an improper validation vulnerability in the MCP OAuth login flow that uses server-supplied Protected Resource Metadata as the resource indicator without checking it matches the configured server URL. | Token Mismanagement & Secret Exposure | ≥ 1.215.2 | [NVD][link_nvd_cve_2026_123271] · [mcp-cve-project][link_mcp_cve_project_cve_2026_123271] · [GHSA][link_ghsa_95vg_3r9c_2v5q] |
| CVE-2026-123022 | AgentScope through 2.0.11 passes the caller-controlled `command` argument of the MCP workspace API to `subprocess.Popen` in `src/agentscope/mcp/_config.py` (OS command injection). No fixed release was listed when this row was added. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_123022] |
| CVE-2026-122140 | Trawl 1.5.0 before 1.10.0 contains a server-side request forgery vulnerability that allows unauthenticated attackers to bypass the MCP outbound URL policy using IPv4-mapped IPv6 addresses. | Command Injection & Execution | ≥ 1.10.0 | [NVD][link_nvd_cve_2026_122140] · [mcp-cve-project][link_mcp_cve_project_cve_2026_122140] · [GHSA][link_ghsa_mj45_84p2_v77q] |
| CVE-2026-121576 | AtlasAiDev MCP Server for WordPress (`ai-workflow-automation-ai-agent-hub`) through 2.0.1 assigns privileges incorrectly, so a low-privilege signed-in user can escalate to administrator. | Insufficient Authentication & Authorization | ≥ 2.0.2 | [NVD][link_nvd_cve_2026_121576] · [Patchstack][link_patchstack_cve_2026_121576] |
| CVE-2026-121458 | Instatic before 0.0.21: AI/MCP content read tools (`content_get_document`, `content_list_documents`) check a capability but not object ownership, so a low-privilege user can read another user's rows. | Insufficient Authentication & Authorization | ≥ 0.0.21 | [NVD][link_nvd_cve_2026_121458] · [GHSA][link_ghsa_x5cc_8486_8qqx] |
| CVE-2026-121419 | SurrealDB 3.1.0 before 3.3.0 builds the MCP session fingerprint from the access-method name instead of the user, so another holder of that access method who knows `mcp-session-id` can reuse the victim's roles. | Insufficient Authentication & Authorization | ≥ 3.3.0 | [NVD][link_nvd_cve_2026_121419] · [GHSA][link_ghsa_pgh9_49q4_hqcx] |
| CVE-2026-120492 | Chainlit 2.12.0 contains a server-side request forgery vulnerability that allows unauthenticated attackers to bypass path-scoped MCP allowed_urls entries because validate_mcp_url does not reject the semicolon character. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_120492] · [mcp-cve-project][link_mcp_cve_project_cve_2026_120492] · [GHSA][link_ghsa_hvfh_5mj3_5f3j] |
| CVE-2026-120450 | LaraDashboard 1.4.0 before 1.4.9 lets a user with read-only `email_template.view` mint an MCP token and send arbitrary email through the `send-email` tool. | Insufficient Authentication & Authorization | ≥ 1.4.9 | [NVD][link_nvd_cve_2026_120450] · [GHSA][link_ghsa_gjfv_h634_pxpv] |
| CVE-2026-120338 | From prefab-ui 0.14.0 through 0.20.2 the launcher starts Deno with unrestricted --allow-read, --allow-write, and --allow-net, and the runner leaves the Deno API on the JavaScript global object. | Command Injection & Execution | ≥ 0.21.0 | [NVD][link_nvd_cve_2026_120338] · [mcp-cve-project][link_mcp_cve_project_cve_2026_120338] · [GHSA][link_ghsa_595q_jv4r_q7j9] |
| CVE-2026-119613 | ash_ai before 1.5.1 returns internal error details, including module names and data values, to the caller of a failed AshAi tool call. | Insufficient Authentication & Authorization | ≥ 1.5.1 | [NVD][link_nvd_cve_2026_119613] · [GHSA][link_ghsa_vhmw_fwrr_r6c6] |
| CVE-2026-119025 | open 7.2.0 before 11.0.0 contains an OS command injection vulnerability that allows attackers to execute PowerShell code by supplying crafted URLs on Windows and WSL. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_119025] · [mcp-cve-project][link_mcp_cve_project_cve_2026_119025] · [GHSA][link_ghsa_q978_78c7_phqw] |
| CVE-2026-117573 | hagent through commit 761eec6 contains an OS command injection vulnerability that allows MCP clients to execute shell commands by injecting metacharacters into the args parameter of the hagent_arduino and hagent_esp32 tools. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_117573] · [mcp-cve-project][link_mcp_cve_project_cve_2026_117573] |
| CVE-2026-117569 | Kali-GPT through commit a608c74 contains an OS command injection vulnerability in execute_tool() in kali_gpt/tools/mcp_server.py that allows MCP clients to run commands via unsanitized scanner parameters. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_117569] · [mcp-cve-project][link_mcp_cve_project_cve_2026_117569] |
| CVE-2026-117568 | mcp-ffmpeg through 1.0.5 contains an OS command injection vulnerability that allows attackers to run shell commands by supplying crafted videoPath or outputDir values to the resize-video, extract-audio and get-video-info tools. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_117568] · [mcp-cve-project][link_mcp_cve_project_cve_2026_117568] |
| CVE-2026-117567 | esp-mcp through commit 28afddf contains an OS command injection vulnerability that allows attackers to run arbitrary commands by supplying shell metacharacters in MCP tool parameters. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_117567] · [mcp-cve-project][link_mcp_cve_project_cve_2026_117567] |
| CVE-2026-117561 | Codefriar sf-mcp through 1.3.2 contains an OS command injection vulnerability that allows attackers to execute shell commands by supplying crafted Salesforce CLI tool flag values. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_117561] · [mcp-cve-project][link_mcp_cve_project_cve_2026_117561] |
| CVE-2026-117558 | The ai-sdlc plugin MCP server through 0.31.2 contains an OS command injection vulnerability that allows attackers to execute commands by supplying shell metacharacters in the repo argument. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_117558] · [mcp-cve-project][link_mcp_cve_project_cve_2026_117558] |
| CVE-2026-116686 | From 1.10.0 until 1.30.0 and 2.2.0, ClientSession, ClientSessionGroup, and Client tool calls validate server-declared outputSchema documents with jsonschema's default resolver, causing an unresolved $ref value to fetch an HTTP, HTTPS, or file URL from the client's network and filesystem context. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_116686] · [mcp-cve-project][link_mcp_cve_project_cve_2026_116686] · [GHSA][link_ghsa_rwrf_2pqf_9j8j] |
| CVE-2026-116685 | From 1.8.0 until 1.30.0 and 2.2.0, streamable_http_client, streamablehttp_client, sse_client, ClientSessionGroup, OAuth, and create_mcp_http_client client paths enable follow_redirects and follow redirects to a different origin, forwarding caller-supplied custom credential headers and, for 307 or 308 responses, the request body. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_116685] · [mcp-cve-project][link_mcp_cve_project_cve_2026_116685] · [GHSA][link_ghsa_5h93_6whr_6q8j] |
| CVE-2026-116684 | From 1.10.0 until 1.30.0 and 2.2.0, server-side bearer authentication configured through AuthSettings with token_verifier accepts a valid token issued for another service when the authorization server serves multiple resources and the TokenVerifier does not independently validate the aud audience. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_116684] · [mcp-cve-project][link_mcp_cve_project_cve_2026_116684] · [GHSA][link_ghsa_w4fh_qvv9_3v23] |
| CVE-2026-116635 | Improper limitation of a pathname to a restricted directory in the deployment status component of the AWS Serverless MCP Server (aws-serverless-mcp-server) before v0.2.1 might allow an actor who can influence the MCP agent to read the contents of JSON files outside the intended deployment status directory. | Privilege Escalation via Scope Creep | ≥ 0.2.1 | [NVD][link_nvd_cve_2026_116635] · [mcp-cve-project][link_mcp_cve_project_cve_2026_116635] · [GHSA][link_ghsa_r6mm_377j_qg8m] |
| CVE-2026-116109 | continuedev Continue MCP Server Transport ConfigHandler.ts MCPManagerSingleton.setConnections os command injec | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_116109] · [mcp-cve-project][link_mcp_cve_project_cve_2026_116109] |
| CVE-2026-115845 | An incomplete list of disallowed inputs in the Python code validator of the run_script tool in AWS MCP Server might allow an authenticated remote user to execute arbitrary code within their own isolated session environment via a crafted script. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_115845] · [mcp-cve-project][link_mcp_cve_project_cve_2026_115845] |
| CVE-2026-115751 | Agentfront mcp-from-openapi from 2.2.0 before 2.9.0 contains a server-side request forgery vulnerability that allows attackers to bypass the ssrf.blockedHosts denylist using trailing-dot hostnames. | Command Injection & Execution | ≥ 2.9.0 | [NVD][link_nvd_cve_2026_115751] · [mcp-cve-project][link_mcp_cve_project_cve_2026_115751] · [GHSA][link_ghsa_ff5q_5r4v_fw4v] |
| CVE-2026-115563 | In affected versions, the SDK's OAuth client support (`mcp.client.auth`) let the MCP server a client connected to decide where the client's OAuth credentials were sent. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_115563] · [mcp-cve-project][link_mcp_cve_project_cve_2026_115563] · [GHSA][link_ghsa_qx49_fqc8_xw99] |
| CVE-2026-115478 | From 1.0.1 until 1.31.4, `create_entity`, `link_entities`, `rename_entity`, `unlink_entities` and `delete_entity` regenerate memory notes from SQLite at the computed `memory/<type>/<name>.md` path without reliably preserving note ownership or the consistency of a failed lifecycle operation. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_115478] · [mcp-cve-project][link_mcp_cve_project_cve_2026_115478] · [GHSA][link_ghsa_r3g7_r4hr_m258] |
| CVE-2026-115477 | From 1.13.0 until 1.31.4, on a Streamable HTTP deployment with `auth.jwtSecret` configured and a 2026-07-28-era client declaring `elicitation.form` support, a dispatch-gated tool call offered an `inputRequired` confirmation could still complete after the human declined or cancelled, or the elicitation response was omitted or malformed, provided the client | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_115477] · [mcp-cve-project][link_mcp_cve_project_cve_2026_115477] · [GHSA][link_ghsa_737x_cwfr_5vvc] |
| CVE-2026-115413 | Missing token audience validation in the OAuth authentication mode of AWS API MCP Server before version 1.6.0 might allow local users to run AWS operations with the server's configured AWS credentials via an access token issued to another application by the same identity provider. | Token Mismanagement & Secret Exposure | ≥ 1.6.0 | [NVD][link_nvd_cve_2026_115413] · [mcp-cve-project][link_mcp_cve_project_cve_2026_115413] · [GHSA][link_ghsa_4prq_p2x5_w9fh] |
| CVE-2026-114612 | From 1.87.0 until 1.100.4, 1.101.3, 1.102.2, 1.103.1, and 1.104.0-rc.2, the proxy reuses one cryptographic context for at-rest secrets and session tokens, allowing an authenticated internal user to have crafted metadata containing a forged administrator credential encrypted and returned by the API-key flow. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_114612] · [mcp-cve-project][link_mcp_cve_project_cve_2026_114612] · [GHSA][link_ghsa_7hp6_4w63_5g45] |
| CVE-2026-114123 | With API_KEY unset or empty, src/middleware/apiKeyAuth.ts passes requests through without authentication, while src/index.ts binds the HTTP listener to 0.0.0.0 by default. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_114123] · [mcp-cve-project][link_mcp_cve_project_cve_2026_114123] · [GHSA][link_ghsa_8764_fh3m_wf7g] |
| CVE-2026-114090 | Trigger.dev cli-v3 from 3.0.0 before 4.5.4 contains a missing authentication vulnerability in the trigger dev --mcp server, which binds all network interfaces and exposes the /sse and /messages endpoints. | Token Mismanagement & Secret Exposure | ≥ 4.5.4 | [NVD][link_nvd_cve_2026_114090] · [mcp-cve-project][link_mcp_cve_project_cve_2026_114090] · [GHSA][link_ghsa_pqmg_rq46_vm4m] |
| CVE-2026-113731 | From 0.9.0 until 1.0.10, 1.1.7, 1.2.4, and 1.3.0rc8, the find_handlers_for_template MCP tool in python/djust/mcp/server.py accepts an existing absolute template_path and reads it without restricting the resolved path to the project or configured template directories. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_113731] · [mcp-cve-project][link_mcp_cve_project_cve_2026_113731] · [GHSA][link_ghsa_r57g_mc79_8hj2] |
| CVE-2026-113378 | The manipulation of the argument fileType results in os command injection. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_113378] · [mcp-cve-project][link_mcp_cve_project_cve_2026_113378] |
| CVE-2026-111771 | From 1.6.0 until 1.32.0 in @modelcontextprotocol/sdk, from 2.0.0 until 2.3.0 in @modelcontextprotocol/server, from 2.0.0 until 2.0.2 in @modelcontextprotocol/express, and from 2.0.0 until 2.3.1 in @modelcontextprotocol/server-legacy, server-side bearer authentication could accept a valid access token issued for a different service because the SDK did not | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_111771] · [mcp-cve-project][link_mcp_cve_project_cve_2026_111771] · [GHSA][link_ghsa_rvq5_wwqv_78pq] |
| CVE-2026-111770 | Cross-client delivery exposes one client's responses and notifications to another client. | Context Injection & Over-Sharing | See NVD | [NVD][link_nvd_cve_2026_111770] · [mcp-cve-project][link_mcp_cve_project_cve_2026_111770] · [GHSA][link_ghsa_jm63_cq47_j5jp] |
| CVE-2026-111769 | Prior to 1.32.0 in @modelcontextprotocol/sdk and from 2.0.0 until 2.3.0 in @modelcontextprotocol/client, the HTTP client transports and OAuth client requests followed redirects to a different origin while retaining custom request headers and, for HTTP 307 or 308 responses, request bodies. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_111769] · [mcp-cve-project][link_mcp_cve_project_cve_2026_111769] · [GHSA][link_ghsa_6prh_2h8m_c8cw] |
| CVE-2026-111768 | Tools accepting arrays or records carry the greatest risk. stdio-only servers do not expose the HTTP request path. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_111768] · [mcp-cve-project][link_mcp_cve_project_cve_2026_111768] · [GHSA][link_ghsa_46jr_4wx8_v453] |
| CVE-2026-111767 | From version 1.24.0 to before version 1.32.0, the experimental tasks feature (taskStore) did not check which session created a task. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_111767] · [mcp-cve-project][link_mcp_cve_project_cve_2026_111767] · [GHSA][link_ghsa_22jm_h49p_29qw] |
| CVE-2026-111091 | In JetBrains Junie CLI before 26.8.3 code execution was possible via an untrusted project's MCP server configuration | Command Injection & Execution | ≥ 26.8.3 | [NVD][link_nvd_cve_2026_111091] · [mcp-cve-project][link_mcp_cve_project_cve_2026_111091] |
| CVE-2026-110842 | n8n before 2.41.4 and 2.42.x before 2.42.1 contains a prototype pollution vulnerability in the MCP workflow-validation tool, whose interpreter evaluates caller-supplied code in the main process, reads inherited properties, and permits assignment onto shared prototypes. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_110842] · [mcp-cve-project][link_mcp_cve_project_cve_2026_110842] · [GHSA][link_ghsa_5jr4_xmvf_frmj] |
| CVE-2026-110616 | NullHub through 2026.5.29 contains a missing authentication vulnerability that allows unauthenticated attackers to access the /api/* management API because the auth_token field defaults to null and is never assigned. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_110616] · [mcp-cve-project][link_mcp_cve_project_cve_2026_110616] |
| CVE-2026-109527 | In mcp versions before 1.29.1 and from 2.0.0a1 through 2.0.1, the Streamable HTTP session manager, SSE message endpoint, and OAuth authorization-server routes buffer complete HTTP request bodies without enforcing a maximum size. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_109527] · [mcp-cve-project][link_mcp_cve_project_cve_2026_109527] · [GHSA][link_ghsa_fmmv_w9g8_j3gc] |
| CVE-2026-109402 | conductor-oss conductor MCP Service MCPService.java MCPService.listTools server-side request forgery | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_109402] · [mcp-cve-project][link_mcp_cve_project_cve_2026_109402] |
| CVE-2026-109332 | Network-AI (npm network-ai) before 5.15.2 contains an origin validation error in McpSseServer._handleRequest in lib/mcp-transport-sse.ts that reflects localhost Origins into Access-Control-Allow-Origin regardless of bind interface. | Insufficient Authentication & Authorization | ≥ 5.15.2 | [NVD][link_nvd_cve_2026_109332] · [mcp-cve-project][link_mcp_cve_project_cve_2026_109332] · [GHSA][link_ghsa_4pvg_m42h_c3x2] |
| CVE-2026-108953 | mac-shell-mcp before 2.0.0 contains an OS command injection vulnerability that allows MCP clients to bypass the command whitelist by injecting shell metacharacters into execute_command arguments. | Command Injection & Execution | ≥ 2.0.0 | [NVD][link_nvd_cve_2026_108953] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108953] |
| CVE-2026-108865 | AmoyLab Unla through 0.10.0 contains an authentication bypass vulnerability that allows unauthenticated attackers to obtain valid access tokens because the OAuth2 server never authenticates a resource owner. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_108865] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108865] |
| CVE-2026-108859 | mcp-go through 1.2.1 contains a denial of service vulnerability in StreamableHTTPServer.ServeHTTP that allows remote unauthenticated attackers to exhaust memory by sending oversized POST bodies. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_108859] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108859] |
| CVE-2026-108856 | UnicomAI Wanwu through 0.6.5 contains an authorization bypass vulnerability that allows authenticated users to mint AppKeys bound to other users' MCP servers via POST /v1/appspace/app/key. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_108856] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108856] |
| CVE-2026-108851 | phpMyFAQ through 4.1.10 contains a missing authorization vulnerability in the MCP server faq_search tool that allows MCP clients to read restricted FAQs because Search::searchDatabase() never applies user or group permission checks. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_108851] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108851] |
| CVE-2026-108714 | MCP Kotlin SDK through 0.15.0 contains an uncontrolled memory allocation vulnerability that allows remote clients to exhaust server memory because Application.mcpWebSocket installs Ktor WebSockets without a maxFrameSize limit. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_108714] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108714] |
| CVE-2026-108671 | JeecgBoot through 3.9.5 contains a missing authorization vulnerability that allows any authenticated user to read MCP server configurations because the queryById permission check is commented out. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_108671] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108671] |
| CVE-2026-108591 | InnoShop 0.9.2 contains a local file disclosure vulnerability that allows authenticated administrators with files_create permission to read server files by abusing the AI Core MCP file_upload tool's source argument. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_108591] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108591] |
| CVE-2026-108586 | 1MCP Agent (@1mcp/agent) 0.20.0 through 0.39.0 contains an incorrect authorization vulnerability that allows authenticated clients to bypass OAuth tag-scope enforcement using negated advanced tag-filter expressions. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_108586] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108586] |
| CVE-2026-108585 | argocd-mcp (Argo CD MCP Server) through 0.9.0 contains a path traversal vulnerability in the delete_application tool that allows MCP clients to reach unintended API endpoints via unvalidated applicationName values. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_108585] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108585] |
| CVE-2026-108582 | GenOffice through 0.11.505 contains an incorrect permissions vulnerability in its HTTP MCP server file store that allows local unprivileged users to read uploaded and generated documents. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_108582] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108582] |
| CVE-2026-108542 | Affected by this vulnerability is an unknown functionality of the file src/mcp/index.ts of the component MCP Request Handler. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_108542] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108542] |
| CVE-2026-108395 | From version 0.8.0 through 0.12.0 in the io.modelcontextprotocol.sdk:mcp artifact, from 0.13.0 through 0.18.3 and 1.0.0 through 1.1.3 in io.modelcontextprotocol.sdk:mcp-core, and from mcp-core 2.0.0-M1 through 2.0.0, the Servlet-based SSE, Streamable HTTP, and Stateless server transports read an HTTP request body into memory without enforcing a maximum size. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_108395] · [mcp-cve-project][link_mcp_cve_project_cve_2026_108395] · [GHSA][link_ghsa_4x8c_5vv7_973f] |
| CVE-2026-107824 | Prior to 1.1, x64dbg-MCP Server exposes all MCP debugger tools over HTTP and SSE without authentication while listening on 0.0.0.0 by default. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_107824] · [mcp-cve-project][link_mcp_cve_project_cve_2026_107824] · [GHSA][link_ghsa_4478_h5jv_647m] |
| CVE-2026-107820 | Prior to 1.2, src/core/mcp_server.zig parses an unbounded Content-Length value in parseContentLength() and uses it in unchecked usize addition in wsRecv() before token authentication. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_107820] · [mcp-cve-project][link_mcp_cve_project_cve_2026_107820] · [GHSA][link_ghsa_jgj3_97w2_9v9r] |
| CVE-2026-107745 | The AI Engine – The Chatbot, AI Framework & MCP for WordPress plugin for WordPress is vulnerable to limited media file deletion due to insufficient file path validation in the upload_file function in all versions up to, and including, 3.8.4 This makes it possible for authenticated attackers, with subscriber-level access and above, to delete arbitrary media | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_107745] · [mcp-cve-project][link_mcp_cve_project_cve_2026_107745] |
| CVE-2026-105761 | Prior to 1.16.0, the PUT /console/api/apps/&lt;app_id&gt;/server endpoint in api/controllers/console/app/mcp_server.py used AppMCPServerController.put() to retrieve an AppMCPServer by the client-supplied server ID without verifying that the server belonged to the requested application and tenant. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_105761] · [mcp-cve-project][link_mcp_cve_project_cve_2026_105761] · [GHSA][link_ghsa_ccrj_frp2_c945] |
| CVE-2026-105741 | From 1.5.0 until 1.10.3, an IP spoofing vulnerability in the Model Context Protocol (MCP) configuration installation endpoint (POST /api/v1/mcp/project/{project_id}/install) allowed authenticated remote attackers to bypass the "local-only" access restriction. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_105741] · [mcp-cve-project][link_mcp_cve_project_cve_2026_105741] · [GHSA][link_ghsa_4f6c_2vvp_gw82] |
| CVE-2026-105740 | Prior to 1.9.0, any authenticated Langflow user can achieve Remote Code Execution (RCE) on the server by adding an MCP server with the "Stdio" transport. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_105740] · [mcp-cve-project][link_mcp_cve_project_cve_2026_105740] · [GHSA][link_ghsa_7w94_79vh_5mr2] |
| CVE-2026-105697 | Before Langflow 1.10.3, the MCP stdio transport launched whatever command / args a user put in an MCP server configuration, with no allowlist and (before 1.10.3) wrapped in bash -c "exec {command} ...". | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_105697] · [mcp-cve-project][link_mcp_cve_project_cve_2026_105697] · [GHSA][link_ghsa_w794_rj3p_xv45] |
| CVE-2026-104850 | Starting in version 1.12.0 and prior to versions 1.31.0 and 2.2.0, the SDK's OAuth client support let the MCP server a client connected to decide which authorization server received the client's OAuth credentials. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_104850] · [mcp-cve-project][link_mcp_cve_project_cve_2026_104850] · [GHSA][link_ghsa_6qxp_vccf_f47h] |
| CVE-2026-104634 | Incorrect Type Conversion or Cast vulnerability in BeamMCP.Server in ScriptKittyOS beam_mcp allows an MCP client's JSON true, false and null tool arguments to reach the host's dispatch function as the strings "true", "false" and "nil". | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_104634] · [mcp-cve-project][link_mcp_cve_project_cve_2026_104634] · [GHSA][link_ghsa_wv7p_j6qh_3hj4] |
| CVE-2026-104120 | A security vulnerability has been detected in modelcontextprotocol mcp-server-fetch and mcp-server-everything up to 2026.6.4. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_104120] · [mcp-cve-project][link_mcp_cve_project_cve_2026_104120] |
| CVE-2026-103758 | Obot 0.21.1 through 0.24.1 contains an authorization bypass vulnerability that allows authenticated users to reach MCP servers because the checkUI deny list omits the /mcp-connect-composite/ route. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_103758] · [mcp-cve-project][link_mcp_cve_project_cve_2026_103758] · [GHSA][link_ghsa_6fwv_3h4c_37j9] |
| CVE-2026-102943 | Dagu before 2.11.0: the MCP `dagu_read` operation with target `dag_spec` loads a DAG specification without the path restriction added for CVE-2026-33344, so a resolved path can leave the configured DAG directory. | Privilege Escalation via Scope Creep | ≥ 2.11.0 | [NVD][link_nvd_cve_2026_102943] · [GHSA][link_ghsa_5m6c_38r8_5w76] |
| CVE-2026-102878 | mcp-chrome-bridge through 1.0.31 contains an origin validation error in the native-server HTTP API that allows attackers to bypass CORS restrictions. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_102878] · [mcp-cve-project][link_mcp_cve_project_cve_2026_102878] |
| CVE-2026-102610 | Prior to 0.7.21, fast-agent serve uses HTTP transport bound to 0.0.0.0 on port 8000 without authentication, allowing any network client that can reach the /mcp endpoint to invoke the exposed agent tool. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_102610] · [mcp-cve-project][link_mcp_cve_project_cve_2026_102610] · [GHSA][link_ghsa_9vhv_g5hf_m7m7] |
| CVE-2026-102503 | Missing Authentication for Critical Function (CWE-306) and Missing Authorization (CWE-862) in the /libp2p-http ingress server (StartIngressServer in cmd/sam-node/node.go) in Google OSS Agent Mesh (SAM) versions 0.1.0-alpha.1 through 0.1.0-alpha.2 allow an unauthenticated remote libp2p peer to bypass Biscuit capability policy enforcement and invoke arbitrary | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_102503] · [mcp-cve-project][link_mcp_cve_project_cve_2026_102503] · [GHSA][link_ghsa_r6hp_67wp_c7jx] |
| CVE-2026-101084 | obot versions before v0.21.1 fail to enforce Access Control Rules on the /mcp-connect endpoint, allowing any authenticated user to connect to restricted MCP servers if they possess the server ID. | Token Mismanagement & Secret Exposure | ≥ 0.21.1 | [NVD][link_nvd_cve_2026_101084] · [mcp-cve-project][link_mcp_cve_project_cve_2026_101084] · [GHSA][link_ghsa_vw82_7fv8_r6gp] |
| CVE-2026-101065 | In all versions up to and including commit d7e6970, the Docker quickstart command documented in the README starts the container listening on 0.0.0.0:8080 with authentication disabled by default. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_101065] · [mcp-cve-project][link_mcp_cve_project_cve_2026_101065] · [GHSA][link_ghsa_jj4w_pfgv_4mrm] |
| CVE-2026-101064 | Obot before v0.23.0 contains a server-side request forgery vulnerability in remote MCP server registration that allows privileged users to specify arbitrary URLs without destination validation. | Command Injection & Execution | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_101064] · [mcp-cve-project][link_mcp_cve_project_cve_2026_101064] · [GHSA][link_ghsa_jgh3_fggc_mcpm] |
| CVE-2026-101063 | Obot versions before v0.23.0 fail to enforce authentication on MCP Registry endpoints under /v0.1/* when registry authentication is enabled. | Insufficient Authentication & Authorization | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_101063] · [mcp-cve-project][link_mcp_cve_project_cve_2026_101063] · [GHSA][link_ghsa_pr6h_vr44_xq8j] |
| CVE-2026-101062 | Obot before v0.23.0 (affected versions <= v0.22.1) running with OBOT_SERVER_ENABLE_AUTHENTICATION=true exposes OAuth dynamic client registration without authentication and without any restriction on the redirect URIs a client may register. | Token Mismanagement & Secret Exposure | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_101062] · [mcp-cve-project][link_mcp_cve_project_cve_2026_101062] · [GHSA][link_ghsa_xwmw_prc4_v3cr] |
| CVE-2026-101057 | utcp-mcp (the MCP plugin of python-utcp) through 1.1.2 connects to the HTTP and WebSocket MCP server URLs given in a call template's mcpServers configuration without the ensure_secure_url validation that the HTTP-family plugins apply, so the HTTPS/WSS-or-loopback rule is not enforced. | Command Injection & Execution | ≥ 1.1.3 | [NVD][link_nvd_cve_2026_101057] · [mcp-cve-project][link_mcp_cve_project_cve_2026_101057] · [GHSA][link_ghsa_qwr9_cj2c_v3fv] |
| CVE-2026-100868 | Penpot before 2.18.0 binds the MCP server plugin WebSocket bridge to all network interfaces without authentication in single-user mode. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_100868] · [mcp-cve-project][link_mcp_cve_project_cve_2026_100868] · [GHSA][link_ghsa_ch2q_6x56_qg5r] |
| CVE-2026-100633 | In versions 3.8.0 through 3.8.3, the MCP file tool's sensitive-path guard (util.IsForbiddenAbsPath(), invoked from resolvePath()) is applied only to the allowed root of recursive operations and not to each resolved descendant path — an incomplete fix for GHSA-c8r8-95hg-mp34. | Privilege Escalation via Scope Creep | ≥ 3.8.4 | [NVD][link_nvd_cve_2026_100633] · [mcp-cve-project][link_mcp_cve_project_cve_2026_100633] · [GHSA][link_ghsa_9g6v_r3xf_673q] |
| CVE-2026-96620 | Prior to 0.2.121, the resume option is passed to the Claude CLI as a separate token without validation, so a dash-leading value is parsed as an independent CLI flag. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_96620] · [mcp-cve-project][link_mcp_cve_project_cve_2026_96620] · [GHSA][link_ghsa_h4mw_j7qp_8mwm] |
| CVE-2026-96561 | The AI Engine – The Chatbot, AI Framework & MCP for WordPress plugin for WordPress is vulnerable to Stored Cross-Site Scripting in versions up to, and including, 3.8.0 This is due to a chain of missing input neutralization and output escaping across the /mwai-ui/v1/chats/submit REST endpoint, the PHP error-log parser (MeowKit_MWAI_Helpers::php_error_logs), | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_96561] · [mcp-cve-project][link_mcp_cve_project_cve_2026_96561] |
| CVE-2026-96526 | The MCP Server for WordPress WordPress plugin before 1.8.2 does not perform an object-level authorization check on one of its workflow REST routes, allowing users with the Contributor role to disclose the title and publication status of any post, page or custom post type, including other users' private, draft, pending and scheduled content. | Insufficient Authentication & Authorization | ≥ 1.8.2 | [NVD][link_nvd_cve_2026_96526] · [mcp-cve-project][link_mcp_cve_project_cve_2026_96526] |
| CVE-2026-96525 | The MCP Server for WordPress WordPress plugin before 1.8.2 does not perform an ownership or sufficient capability check on its workflow create, update and delete REST routes, allowing users with the Contributor role to modify, delete and create site-wide workflow configuration, including workflows created by administrators. | Insufficient Authentication & Authorization | ≥ 1.8.2 | [NVD][link_nvd_cve_2026_96525] · [mcp-cve-project][link_mcp_cve_project_cve_2026_96525] |
| CVE-2026-96524 | The MCP Server for WordPress WordPress plugin before 1.8.2 does not correctly verify the WordPress REST API nonce for cookie-authenticated requests when a condition an attacker can influence is present, allowing unauthenticated attackers to perform administrator-only actions, including creating a new administrator account, by tricking a logged-in | Token Mismanagement & Secret Exposure | ≥ 1.8.2 | [NVD][link_nvd_cve_2026_96524] · [mcp-cve-project][link_mcp_cve_project_cve_2026_96524] |
| CVE-2026-94486 | From 16.0.0 until 16.3.8, the next dev development server exposes a Model Context Protocol endpoint without reliably restricting cross-site requests. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_94486] · [mcp-cve-project][link_mcp_cve_project_cve_2026_94486] · [GHSA][link_ghsa_39w2_rjm5_chcv] |
| CVE-2026-94485 | From 16.0.0 until 16.3.8, the `next dev` development server exposes a Model Context Protocol endpoint without reliably restricting cross-site requests. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_94485] · [mcp-cve-project][link_mcp_cve_project_cve_2026_94485] · [GHSA][link_ghsa_f87g_xv8r_7p7x] |
| CVE-2026-94046 | ACE-MCP through 4.10.8: `get_file_snippet` accepts `projectRootPath` and `filePath` values that leave the intended project (path traversal). | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_94046] |
| CVE-2026-94044 | 03-lovepreetSingh MCP through commit f95d035: `create_file` in `app/api/mcp/route.ts` accepts `filePath` and `content` values that write outside the intended directory. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_94044] |
| CVE-2026-94037 | mcp-file-analyzer through commit 8474085: the `analyze_csv_data` tool passes `filename` into `ControlFlowNode` without confining it to an allowed directory. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_94037] |
| CVE-2026-93982 | OpenPanel through 2.3.0 writes Model Context Protocol authentication tokens from URL query parameters to plaintext application logs without redaction. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_93982] · [mcp-cve-project][link_mcp_cve_project_cve_2026_93982] · [GHSA][link_ghsa_8wx6_g25r_2943] |
| CVE-2026-93965 | aiyiyi121 SxDevOps MCP STDIO Server Management services.py subprocess.Popen command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_93965] · [mcp-cve-project][link_mcp_cve_project_cve_2026_93965] |
| CVE-2026-91988 | atomic-agents-stack before 1.1.0 accepts cleartext HTTP schemes in the HTTP MCP server-registry backend factory, allowing network man-in-the-middle attackers to rewrite catalog responses. | Command Injection & Execution | ≥ 1.1.0 | [NVD][link_nvd_cve_2026_91988] · [mcp-cve-project][link_mcp_cve_project_cve_2026_91988] · [GHSA][link_ghsa_xhcr_cqfr_m3hv] |
| CVE-2026-91932 | Flowise before 3.1.4 contains a validation bypass vulnerability in MCP server configuration allowing authenticated attackers remote code execution through an unvalidated cwd parameter. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_91932] · [mcp-cve-project][link_mcp_cve_project_cve_2026_91932] · [GHSA][link_ghsa_x7x8_95gh_42xm] |
| CVE-2026-91931 | Flowise before 3.1.4 contains a remote code execution vulnerability in the Custom MCP node that allows authenticated attackers to execute arbitrary code by supplying npx package names in the mcpServerConfig parameter. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_91931] · [mcp-cve-project][link_mcp_cve_project_cve_2026_91931] · [GHSA][link_ghsa_vcwp_f9rq_3887] |
| CVE-2026-90474 | MCPHub before 1.0.32 contains an authentication bypass vulnerability in its embedded OAuth 2.0 authorization server where client authentication is disabled by default and PKCE enforcement is optional. | Token Mismanagement & Secret Exposure | ≥ 1.0.32 | [NVD][link_nvd_cve_2026_90474] · [mcp-cve-project][link_mcp_cve_project_cve_2026_90474] · [GHSA][link_ghsa_3m7m_37xf_xp9x] |
| CVE-2026-89039 | A caller who can invoke the convert_playwright_script prompt in mcp-k6 can pass a bare file path as the playwright_script argument and receive the contents of any file readable by the user running the server, including SSH keys and cloud credentials in that user's home directory (path traversal). | Privilege Escalation via Scope Creep | ≥ 0.7.0 | [NVD][link_nvd_cve_2026_89039] · [mcp-cve-project][link_mcp_cve_project_cve_2026_89039] |
| CVE-2026-88938 | knowns through 0.33.0 does not confine the `path` argument of the `code.find` MCP tool to the project root, so an agent session can read files elsewhere on the host. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_88938] · [GHSA][link_ghsa_5cj9_fcqq_g2h7] |
| CVE-2026-88755 | Z.ai ZCode v3.11.2.6792 was discovered to automatically establish connections with MCP servers declared inside a repository's workspace configuration, possibly allowing attackers to execute arbitrary code via opening a crafted repository. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_88755] · [mcp-cve-project][link_mcp_cve_project_cve_2026_88755] |
| CVE-2026-88257 | Improper Input Validation vulnerability in BeamMCP.Schema in ScriptKittyOS beam_mcp allows an MCP client to reach a tool's dispatch function with arguments that violate the input schema the server advertised. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_88257] · [mcp-cve-project][link_mcp_cve_project_cve_2026_88257] · [GHSA][link_ghsa_mrg2_4747_fmpw] |
| CVE-2026-87913 | A missing S3 bucket ownership verification in the AWS Security Agent MCP server before 0.2.0 version might allow remote attackers to obtain the private source archive of a scanned workspace, including credentials and infrastructure state contained in that archive, via a pre-registered storage bucket whose name is derived from a publicly known account | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_87913] · [mcp-cve-project][link_mcp_cve_project_cve_2026_87913] · [GHSA][link_ghsa_3jxw_vj8m_8x77] |
| CVE-2026-87911 | An OS command injection weakness in the read-only enforcement of the SQL validation component in Amazon awslabs postgres-mcp-server before 1.1.7 might allow an unauthenticated actor to execute operating system commands on the host of a self-managed PostgreSQL server by placing a crafted COPY ... | Command Injection & Execution | ≥ 1.1.7 | [NVD][link_nvd_cve_2026_87911] · [mcp-cve-project][link_mcp_cve_project_cve_2026_87911] · [GHSA][link_ghsa_fph8_pg5w_78fv] |
| CVE-2026-86439 | knowns versions before 0.30.0 fail to validate filesystem paths in MCP tool arguments, allowing attackers to read, create, overwrite and delete files outside the project directory. | Privilege Escalation via Scope Creep | ≥ 0.30.0 | [NVD][link_nvd_cve_2026_86439] · [mcp-cve-project][link_mcp_cve_project_cve_2026_86439] · [GHSA][link_ghsa_9gfj_28hw_jchp] |
| CVE-2026-86122 | Rowboat through 0.9.1 fails to validate custom MCP server and webhook URLs, allowing authenticated users to configure arbitrary destinations. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_86122] · [mcp-cve-project][link_mcp_cve_project_cve_2026_86122] |
| CVE-2026-85787 | An incomplete list of disallowed inputs in the SQL validation component in Amazon awslabs postgres-mcp-server before version 1.1.7 might allow an unauthenticated actor to modify data beyond the read-only scope by placing | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_85787] · [mcp-cve-project][link_mcp_cve_project_cve_2026_85787] |
| CVE-2026-85666 | OGX (formerly Llama Stack, affected at commit fbe8e0f) contains an unauthenticated server-side request forgery vulnerability in the OpenAI-compatible POST /v1/responses endpoint. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_85666] · [mcp-cve-project][link_mcp_cve_project_cve_2026_85666] |
| CVE-2026-85620 | Postgres MCP Pro 0.3.0 contains a restricted-mode bypass vulnerability where function-name validation is not applied to RangeFunction nodes in FROM clauses. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_85620] · [mcp-cve-project][link_mcp_cve_project_cve_2026_85620] |
| CVE-2026-85580 | SiYuan versions before v3.8.2 contain a path guard bypass vulnerability in the MCP file-access handler that uses case-sensitive matching on Linux filesystems. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_85580] · [mcp-cve-project][link_mcp_cve_project_cve_2026_85580] |
| CVE-2026-85306 | Missing Authorization vulnerability in Cascadia Web Services MountDev AI MCP Connector for WordPress allows Exploiting Incorrectly Configured Access Control Security Levels. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_85306] · [mcp-cve-project][link_mcp_cve_project_cve_2026_85306] |
| CVE-2026-85166 | n8n before 2.35.4 and 2.36.x before 2.36.2 does not validate credential references in the inline workflow JSON of nodes that execute an inline sub-workflow (e.g., the Workflow Tool node). | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_85166] · [mcp-cve-project][link_mcp_cve_project_cve_2026_85166] |
| CVE-2026-84779 | Subscriber Broken Access Control in Agentimus – AI SEO, llms.txt & MCP for AI Agents <= 1.51.0 versions. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_84779] · [mcp-cve-project][link_mcp_cve_project_cve_2026_84779] |
| CVE-2026-84360 | Prior to 2.4.1, the HTTP configuration mutation routes require RequireSecureSession, but /mcp and /mcp_message require only ordinary authentication before exposing nginx_config_add and nginx_config_modify. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_84360] · [mcp-cve-project][link_mcp_cve_project_cve_2026_84360] · [GHSA][link_ghsa_vc32_4gwf_77xp] |
| CVE-2026-84319 | However, the MCP configuration interface allows a secondary authenticated user to write and apply equivalent restricted configuration content. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_84319] · [mcp-cve-project][link_mcp_cve_project_cve_2026_84319] · [GHSA][link_ghsa_5r62_gj48_897x] |
| CVE-2026-84318 | From 2.0.0-rc.6 until 2.4.1, the MCP tool nginx_config_add writes nginx configuration files to disk and triggers an nginx reload without calling config.ValidateConfigFile. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_84318] · [mcp-cve-project][link_mcp_cve_project_cve_2026_84318] · [GHSA][link_ghsa_9jww_cxg5_rj9m] |
| CVE-2026-84317 | An authenticated MCP caller (or an MCP agent induced via prompt injection) can therefore inject exactly the directives the control is meant to block, leading to nginx code execution on deployments where the njs/perl module is available (e.g. the official Docker image). | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_84317] · [mcp-cve-project][link_mcp_cve_project_cve_2026_84317] · [GHSA][link_ghsa_76pm_mq2q_9gcr] |
| CVE-2026-84289 | NousResearch hermes-agent up to 0.18.2. This vulnerability affects the function list_tools of the file tools/mcp_tool.py of the component MCP Tool. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_84289] · [mcp-cve-project][link_mcp_cve_project_cve_2026_84289] |
| CVE-2026-82905 | sdcb chats up to 1.12.0. This affects the function McpController of the file src/BE/web/Controllers/Users/Mcps/McpController.cs of the component fetch-tools Endpoint. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_82905] · [mcp-cve-project][link_mcp_cve_project_cve_2026_82905] |
| CVE-2026-82456 | argocd-mcp 0.8.0 binds its HTTP transport to every network interface and accepts MCP sessions without requiring caller credentials when ARGOCD_API_TOKEN is configured. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_82456] · [mcp-cve-project][link_mcp_cve_project_cve_2026_82456] |
| CVE-2026-82233 | SiYuan before v3.8.1 contains a path traversal vulnerability in the asset.upload MCP tool that accepts arbitrary absolute file paths without workspace boundary validation. | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_82233] · [mcp-cve-project][link_mcp_cve_project_cve_2026_82233] |
| CVE-2026-82021 | Hermes Agent 0.18.2 prior to 0.19.0 contains a supply chain vulnerability in its bundled MCP catalog that allows a remote attacker to execute arbitrary code by compromising a third-party upstream repository referenced vi | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_82021] · [mcp-cve-project][link_mcp_cve_project_cve_2026_82021] |
| CVE-2026-81941 | IBM Langflow OSS 1.0.0 through 1.11.5 allows an authenticated non-administrative user could execute arbitrary operating system commands on the server at the privilege level of the application process by constructing a flow with an MCP Tools component configured to use a local stdio subprocess transport. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_81941] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81941] |
| CVE-2026-81846 | An authorization bypass in the runZero Platform MCP service has been resolved in version 5.1.260826.0. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_81846] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81846] |
| CVE-2026-81845 | arben-adm mcp-sequential-thinking up to 0.5.0. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_81845] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81845] |
| CVE-2026-81835 | RooCodeInc Roo-Code up to 3.51.1. This affects the function fetch_instructions of the file malicious_mcp_server.py of the component MCP Integration Trust Model. | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_81835] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81835] |
| CVE-2026-81735 | startServer.ts in the mcp-http-server package of UI-TARS-desktop defaulted its listen address to '::' when no host was given, so startSseAndStreamableHttpMcpServer bound the Streamable HTTP and SSE MCP transports to ever | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_81735] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81735] |
| CVE-2026-81486 | bsmi021 mcp-file-context-server 1.0.0. Affected by this issue is the function read_context of the file src/index.ts of the component Path Resolution. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_81486] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81486] |
| CVE-2026-81315 | ash_ai MCP HTTP transport DNS rebinding / `X-Forwarded-Proto` origin bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_81315] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81315] |
| CVE-2026-81102 | The Dash MCP server bound its listener to the loopback address but never checked the host a request named. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_81102] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81102] |
| CVE-2026-81101 | The configure command accepted any endpoint URL and stored it beside the user's access token. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_81101] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81101] |
| CVE-2026-81100 | tiger-gh-mcp-server started its MCP HTTP transport without enabling the host allow-list the underlying SDK provides. | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_81100] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81100] |
| CVE-2026-81099 | tiger-slack started its MCP HTTP transport without enabling the host allow-list the underlying SDK provides. | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_81099] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81099] |
| CVE-2026-81098 | The Telnyx MCP server exposed its HTTP transport on every interface and did not require a caller credential. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_81098] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81098] |
| CVE-2026-81097 | The execute_ruby tool is documented as a read-only Ruby sandbox and is enforced by a pattern denylist together with replacements for the process-spawning methods on Kernel. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_81097] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81097] |
| CVE-2026-81096 | ToolUniverse ran caller-supplied Python inside a sandbox that could be escaped, on a server that required no authentication. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_81096] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81096] |
| CVE-2026-81095 | pg-aiguide started its MCP HTTP transport without enabling the host allow-list the underlying SDK provides. | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_81095] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81095] |
| CVE-2026-81094 | The mcp-router CLI served its MCP aggregator on every interface and enforced authentication only when the operator asked for it. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_81094] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81094] |
| CVE-2026-81093 | The get-html-skeleton tool fetched a URL the caller supplied after checking only its syntax. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_81093] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81093] |
| CVE-2026-81092 | mcp-go (`mark3labs/mcp-go`): StreamableHTTP / SSE DNS rebinding via missing Host validation | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_81092] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81092] |
| CVE-2026-81091 | The proxy middleware in mcp-use's inspector forwards requests to a destination the caller names. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_81091] · [mcp-cve-project][link_mcp_cve_project_cve_2026_81091] |
| CVE-2026-80347 | mcp-fetch checks a fetch target against its SSRF guard without removing the brackets that surround an IPv6 literal. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_80347] · [mcp-cve-project][link_mcp_cve_project_cve_2026_80347] |
| CVE-2026-79786 | Coroot's unauthenticated MCP OAuth dynamic client registration endpoint accepts any syntactically valid redirect URI without validation, allowing attackers to register clients pointing to attacker-controlled hosts. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_79786] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79786] |
| CVE-2026-79750 | MCPHub is a unified hub for centrally managing and dynamically orchestrating multiple MCP servers/APIs into separate endpoints with flexible routing strategies. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_79750] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79750] |
| CVE-2026-79749 | MCPHub is a unified hub for centrally managing and dynamically orchestrating multiple MCP servers/APIs into separate endpoints with flexible routing strategies. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_79749] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79749] |
| CVE-2026-79748 | MCPHub (`samanhappy/mcphub`): STDIO MCP server create/update authorization gap | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_79748] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79748] |
| CVE-2026-79747 | MCPHub is a unified hub for centrally managing and dynamically orchestrating multiple MCP servers/APIs into separate endpoints with flexible routing strategies. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_79747] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79747] |
| CVE-2026-79746 | MCPHub is a unified hub for centrally managing and dynamically orchestrating multiple MCP servers/APIs into separate endpoints with flexible routing strategies. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_79746] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79746] |
| CVE-2026-79745 | MCPHub is a unified hub for centrally managing and dynamically orchestrating multiple MCP servers/APIs into separate endpoints with flexible routing strategies. | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_79745] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79745] |
| CVE-2026-79744 | MCPHub is a unified hub for centrally managing and dynamically orchestrating multiple MCP servers/APIs into separate endpoints with flexible routing strategies. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_79744] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79744] |
| CVE-2026-79743 | MCPHub is a unified hub for centrally managing and dynamically orchestrating multiple MCP servers/APIs into separate endpoints with flexible routing strategies. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_79743] · [mcp-cve-project][link_mcp_cve_project_cve_2026_79743] |
| CVE-2026-79534 | mark3labs mcp-filesystem-server 0.11.1: `validatePath` treats a dangling symlink as safe when `EvalSymlinks` reports the target missing, so `write_file` and related tools can follow that link outside the allowed root. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_79534] |
| CVE-2026-78575 | IBM Langflow OSS 1.0.0 through 1.11.5 could allow a remote authenticated attacker to execute arbitrary commands due to improper validation of command-line arguments in the MCP stdio server configuration. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_78575] · [mcp-cve-project][link_mcp_cve_project_cve_2026_78575] |
| CVE-2026-78430 | A vulnerability was detected in sworddut mcp-ffmpeg-helper 0.1.0/0.1.1/0.2.1 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_78430] · [mcp-cve-project][link_mcp_cve_project_cve_2026_78430] |
| CVE-2026-77825 | IBM ContextForge MCP Gateway 1.0.0 through 1.0.8: `GET /v1/admin/logs/file` checks the log path with `str.startswith`, so an authenticated admin can read `.log`, `.jsonl`, and `.json` files outside `LOG_FOLDER`. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77825] |
| CVE-2026-77822 | IBM ContextForge MCP Gateway (`mcp-contextforge-gateway`): A2A invoke DNS rebinding SSRF | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77822] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77822] |
| CVE-2026-77604 | Prior to 0.0.345, the MCPToolsRegistry.read_file implementation in codebase_rag/mcp/tools.py joins attacker-controlled file_path input to project_root without resolving and verifying containment when offset or limit selects the paginated branch. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77604] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77604] · [GHSA][link_ghsa_vvr2_h2jp_838m] |
| CVE-2026-77518 | In 2.10.2-lts and earlier, a normal workspace user who knows another user's active MCP tool_id in the same workspace can retrieve the hidden tool through the tool-detail route because it does not apply the per-resource authorization used by the list route. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77518] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77518] · [GHSA][link_ghsa_x65c_w438_c58f] |
| CVE-2026-77366 | Prior to 1.3.1, tool dispatch does not compare the caller-controlled input.vault value with the vault bound to the caller, the JSON Web Token (JWT) has no vault claim, and the folder access-control list is shared globally. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_77366] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77366] · [GHSA][link_ghsa_84c9_qqpq_2pq5] |
| CVE-2026-77364 | Prior to 1.3.1, undefined readPaths and writePaths settings allow all paths, strictReadDefault does not protect direct requests, and the .obsidian, .git, and .trash control directories are excluded only during enumeration. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77364] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77364] · [GHSA][link_ghsa_cvp8_vvgf_69q4] |
| CVE-2026-77363 | Prior to 1.3.1, the Streamable HTTP transport does not validate the Host or Origin header or enable DNS-rebinding protection. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77363] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77363] · [GHSA][link_ghsa_pqh8_4pj7_32xx] |
| CVE-2026-77362 | The tasks_filter tool exposes group counts derived from denied notes, makemd_query passes unfiltered sibling result fields through, and list_templates exposes template paths and parsed user-function bodies without a read-whitelist check. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77362] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77362] · [GHSA][link_ghsa_43r2_c7g8_prc8] |
| CVE-2026-77361 | An in-vault symlink under an allowed glob that resolves into a denied folder can therefore bypass the read ACL and expose files in the denied folder. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77361] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77361] · [GHSA][link_ghsa_c5xx_h28h_f682] |
| CVE-2026-77339 | Process Compose before 1.120.0: the MCP SSE listener accepts browser-origin requests to `/sse` and the message endpoint without checking Host or Origin and without authenticating the caller. | Insufficient Authentication & Authorization | ≥ 1.120.0 | [NVD][link_nvd_cve_2026_77339] · [GHSA][link_ghsa_5gm3_9crp_6g3v] |
| CVE-2026-77321 | Prior to 3.3.0, the get_trip_summary tool in server/src/mcp/tools/trips.ts is registered for scoped OAuth MCP tokens without requiring trips:read and returns core trip summary data regardless of the delegated scopes. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_77321] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77321] · [GHSA][link_ghsa_qvw8_w937_vcmq] |
| CVE-2026-77274 | Prior to 0.22.0, validate_url_for_ssrf has a backslash authority confusion because it interprets the authority differently from the Requests connection layer in the header-based Jira and Confluence URL authentication flow. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_77274] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77274] · [GHSA][link_ghsa_hgcf_4mq8_5266] |
| CVE-2026-77272 | Prior to 0.22.0, the OAuth error query parameter is passed to CallbackHandler._send_response in oauth_setup.py and interpolated into an HTML page without escaping. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_77272] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77272] · [GHSA][link_ghsa_g2r2_3j32_j27x] |
| CVE-2026-77271 | Prior to 0.22.0, validate_safe_path defaults its base directory to os.getcwd(), and affected Confluence attachment call sites omit base_dir, allowing attacker-selected writes within the working directory. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_77271] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77271] · [GHSA][link_ghsa_6vmq_24h2_pj7j] |
| CVE-2026-77270 | The advisory traces the vulnerable input and processing flow through confluence_upload_attachment, jira_upload_attachment, file_path, and open(file_path, "rb"), which identify the affected entry points, controls, and code paths. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77270] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77270] · [GHSA][link_ghsa_f26r_j276_ggg4] |
| CVE-2026-77269 | The advisory traces the vulnerable input and processing flow through upload_attachment, file_path, and CVE-2026-27825, which identify the affected entry points, controls, and code paths. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77269] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77269] · [GHSA][link_ghsa_h7wj_5v37_59r2] |
| CVE-2026-77268 | Prior to 0.22.0, the OAuth fallback token directory and JSON file are created without explicit owner-only modes. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_77268] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77268] · [GHSA][link_ghsa_4596_2p6p_28cv] |
| CVE-2026-77267 | Prior to 0.22.0, the X-Atlassian-Jira-Url and X-Atlassian-Confluence-Url headers are processed by _process_authentication_headers and used to construct Atlassian fetchers without calling validate_url_for_ssrf. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_77267] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77267] · [GHSA][link_ghsa_5wf4_jqxh_8gm3] |
| CVE-2026-77266 | Prior to 0.22.0, upload_attachment accepts absolute paths and traversal sequences without constraining the resolved path to the server workspace. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77266] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77266] · [GHSA][link_ghsa_mfv2_4wvm_9pgp] |
| CVE-2026-77265 | The advisory traces the vulnerable input and processing flow through X-Atlassian-Jira-Url, X-Atlassian-Confluence-Url, validate_url_for_ssrf, and DNS rebinding, which identify the affected entry points, controls, and code paths. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_77265] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77265] · [GHSA][link_ghsa_49xv_9743_pw8w] |
| CVE-2026-77262 | Prior to 0.22.0, confluence_upload_attachment accepts an attacker-controlled file_path and does not apply the path restriction added for the earlier download vulnerability. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77262] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77262] · [GHSA][link_ghsa_p6hp_93wp_fh6p] |
| CVE-2026-77261 | Prior to 0.22.0, _make_ssrf_safe_hook is omitted from JiraFetcher and ConfluenceFetcher sessions created through the basic-auth and oauth_pat branches. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_77261] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77261] · [GHSA][link_ghsa_6529_c226_h328] |
| CVE-2026-77260 | MCP Atlassian arbitrary local-file read | Privilege Escalation via Scope Creep | ≥ 0.22.0 | [NVD][link_nvd_cve_2026_77260] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77260] · [GHSA][link_ghsa_f4p7_qx46_wc5j] |
| CVE-2026-77259 | Prior to 0.22.0, confluence_upload_attachment opens a caller-selected server-local file without checking that the resolved path remains in the workspace. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77259] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77259] · [GHSA][link_ghsa_6cr4_ccf3_x7h4] |
| CVE-2026-77258 | Prior to 0.22.0, upload_attachment in src/mcp_atlassian/confluence/attachments.py accepts a caller-controlled file_path and opens the selected server-local file without restricting it to the workspace. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77258] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77258] · [GHSA][link_ghsa_93xw_j965_9mx3] |
| CVE-2026-77257 | MCP Atlassian HTTP upload path traversal | Privilege Escalation via Scope Creep | ≥ 0.22.0 | [NVD][link_nvd_cve_2026_77257] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77257] · [GHSA][link_ghsa_mrq8_fv7v_hhjg] |
| CVE-2026-77256 | Prior to 0.22.0, the plaintext OAuth fallback file containing refresh and access tokens is written with permissions inherited from the process umask. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_77256] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77256] · [GHSA][link_ghsa_76pr_5669_3xf5] |
| CVE-2026-77255 | Prior to 0.22.0, the Jira update_issue attachments argument is converted into local paths and routed to the attachment upload implementation without workspace validation. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77255] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77255] · [GHSA][link_ghsa_2xj6_xx86_cwwc] |
| CVE-2026-77254 | Prior to 0.22.0, requests to the HTTP MCP endpoint without a per-user identity are allowed to reach tool handlers, which then use globally configured Jira or Confluence credentials. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77254] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77254] · [GHSA][link_ghsa_vc8m_84rp_53hx] |
| CVE-2026-77253 | MCP Atlassian attachment upload local-file disclosure | Privilege Escalation via Scope Creep | ≥ 0.22.0 | [NVD][link_nvd_cve_2026_77253] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77253] · [GHSA][link_ghsa_vc25_24vv_fxxm] |
| CVE-2026-77252 | Prior to 0.22.0, caller-supplied projects_filter and spaces_filter arguments can replace administrator-configured allowlists, and caller-provided project or space clauses can suppress the configured restriction. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77252] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77252] · [GHSA][link_ghsa_rqwg_9346_fjjv] |
| CVE-2026-77251 | MCP Atlassian project and space filter bypass | Privilege Escalation via Scope Creep | ≥ 0.22.0 | [NVD][link_nvd_cve_2026_77251] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77251] · [GHSA][link_ghsa_w66g_j6c4_hcfc] |
| CVE-2026-77250 | Prior to 0.22.0, OAuthConfig writes a plaintext fallback file containing access and refresh tokens under the user's .mcp-atlassian directory using process-default permissions. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_77250] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77250] · [GHSA][link_ghsa_g5xv_mhgm_v5f6] |
| CVE-2026-77249 | MCP Atlassian redirect-based SSRF | Command Injection & Execution | ≥ 0.22.0 | [NVD][link_nvd_cve_2026_77249] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77249] · [GHSA][link_ghsa_v9m3_wfh8_5646] |
| CVE-2026-77248 | Prior to 0.22.0, the streamable HTTP transport accepts requests without a user identity and falls back to operator credentials, while upload_attachment accepts an unrestricted file_path. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77248] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77248] · [GHSA][link_ghsa_cc5h_2pwp_pvcc] |
| CVE-2026-77247 | The advisory traces the vulnerable input and processing flow through AttachmentsMixin.upload_attachment, AttachmentsMixin.upload_attachments, file_path, file_paths, and jira update_issue, which identify the affected entry points, controls, and code paths. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77247] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77247] · [GHSA][link_ghsa_f6pj_qv47_g96w] |
| CVE-2026-77246 | Prior to 0.22.0, an HTTP transport deployment with READ_ONLY_MODE=false accepts a request without an Authorization identity and permits attacker-controlled Atlassian service headers, including X-Atlassian-Confluence-Url, to select a public attacker hostname or one allowed by MCP_ALLOWED_URL_DOMAINS. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_77246] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77246] · [GHSA][link_ghsa_wv8v_v4c5_v75j] |
| CVE-2026-77244 | MCP Atlassian HTTP authentication bypass | Insufficient Authentication & Authorization | ≥ 0.22.0 | [NVD][link_nvd_cve_2026_77244] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77244] · [GHSA][link_ghsa_wrhw_j3f9_8vc6] |
| CVE-2026-77243 | MCP Atlassian tool authorization bypass | Privilege Escalation via Scope Creep | ≥ 0.22.0 | [NVD][link_nvd_cve_2026_77243] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77243] · [GHSA][link_ghsa_3r68_hf9h_887v] |
| CVE-2026-77242 | MCP Atlassian DNS-rebinding SSRF | Command Injection & Execution | ≥ 0.22.0 | [NVD][link_nvd_cve_2026_77242] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77242] · [GHSA][link_ghsa_72fm_whvq_jghf] |
| CVE-2026-77073 | n8n versions before 2.34.1 contain a credential validation bypass in the MCP create_workflow_from_code tool when authentication type is set to an expr | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_77073] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77073] |
| CVE-2026-77068 | n8n before 2.33.4 and 2.34.x before 2.34.1 contain a remote code execution vulnerability in the @n8n/workflow-sdk node-schema loader used for MCP node | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_77068] · [mcp-cve-project][link_mcp_cve_project_cve_2026_77068] |
| CVE-2026-76894 | Prior to 0.4.112, the DataStore table UI in src/resources/datastore-table-ui.ts accepts window message events without validating event.origin and sends JSON-RPC messages through postMessage with a wildcard target origin. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_76894] · [mcp-cve-project][link_mcp_cve_project_cve_2026_76894] · [GHSA][link_ghsa_vqff_r82h_9crc] |
| CVE-2026-76893 | An unauthenticated client that sends the first initialize request without an mcp-session-id claims the shared transport state, causing later independent clients to receive Server already initialized and preventing them from establishing sessions until the process restarts. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_76893] · [mcp-cve-project][link_mcp_cve_project_cve_2026_76893] · [GHSA][link_ghsa_h7c4_q426_7jh9] |
| CVE-2026-76404 | In Splunk MCP Server app versions below 1.2.1, a user who holds the "admin" Splunk role could execute arbitrary commands on the underlying operating s | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_76404] · [mcp-cve-project][link_mcp_cve_project_cve_2026_76404] |
| CVE-2026-76286 | In Splunk MCP Server versions below 1.2.1, Splunk MCP Server could send the Splunk platform authentication token of a user who runs a custom Application Programming Interface (API) tool to the URL configured for that tool. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_76286] · [mcp-cve-project][link_mcp_cve_project_cve_2026_76286] |
| CVE-2026-75858 | CodeWhale (packages codewhale / codewhale-tui) versions >= 0.8.41 and < 0.8.64 contain a remote code execution vulnerability in the rlm_eval tool | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_75858] · [mcp-cve-project][link_mcp_cve_project_cve_2026_75858] |
| CVE-2026-75857 | CodeWhale versions >= 0.8.41 and < 0.8.64 contain a vulnerability in the exec_shell_interact (alias exec_interact) tool, whose approval_requirement re | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_75857] · [mcp-cve-project][link_mcp_cve_project_cve_2026_75857] |
| CVE-2026-75845 | ArcadeDB versions 26.4.2 through 26.7.3 contain an authorization bypass vulnerability in the set_server_setting MCP server-level tool | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_75845] · [mcp-cve-project][link_mcp_cve_project_cve_2026_75845] |
| CVE-2026-75149 | marimo before 0.23.15 contains a code injection vulnerability in the notebook configuration handler that allows attackers to execute arbitrary command | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_75149] · [mcp-cve-project][link_mcp_cve_project_cve_2026_75149] |
| CVE-2026-75130 | Context7 through 2.1.2 contains a prompt injection vulnerability that allows attackers to execute malicious instructions in connected AI coding agents | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_75130] · [mcp-cve-project][link_mcp_cve_project_cve_2026_75130] |
| CVE-2026-75062 | Google langfun (`langfun`): default `lf.query` eval injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_75062] · [mcp-cve-project][link_mcp_cve_project_cve_2026_75062] |
| CVE-2026-75060 | In JetBrains PyCharm before 2026.2.1 code execution was possible via unauthenticated Jupyter MCP tools | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_75060] · [mcp-cve-project][link_mcp_cve_project_cve_2026_75060] |
| CVE-2026-74798 | SiYuan kernel before v3.7.4 contains a path traversal vulnerability in the database_clean MCP tool | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_74798] · [mcp-cve-project][link_mcp_cve_project_cve_2026_74798] |
| CVE-2026-73846 | CKAN MCP Server is a tool for querying CKAN open data portals | Lack of Audit and Telemetry | See NVD | [NVD][link_nvd_cve_2026_73846] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73846] |
| CVE-2026-73845 | CKAN MCP Server is a tool for querying CKAN open data portals | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_73845] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73845] |
| CVE-2026-73844 | CKAN MCP Server is a tool for querying CKAN open data portals | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_73844] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73844] |
| CVE-2026-73601 | Flowise versions before 3.1.3 contain a remote code execution vulnerability in the Custom MCP node when CUSTOM_MCP_PROTOCOL is set to stdio, allowing | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_73601] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73601] |
| CVE-2026-73498 | MCP Atlassian (`mcp-atlassian`): `confluence_upload_attachment` path traversal / arbitrary file read | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_73498] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73498] |
| CVE-2026-73497 | From 0.17.0 until 0.22.0, validate_url_for_ssrf resolves the attacker-controlled X-Atlassian-Jira-Url and X-Atlassian-Confluence-Url header host once at middleware time, but the outbound request is built with the raw hostname and resolves it again at connection time with no IP pinning. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_73497] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73497] · [GHSA][link_ghsa_489g_7rxv_6c8q] |
| CVE-2026-73496 | Prior to 0.22.0, the confluence_upload_attachment and confluence_upload_attachments tools pass a client-controlled file_path through src/mcp_atlassian/confluence/attachments.py upload_attachment, and the jira_update_issue attachments parameter reaches src/mcp_atlassian/jira/attachments.py upload_attachment, without confining either path to an approved | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_73496] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73496] · [GHSA][link_ghsa_wm45_qh3g_v83f] |
| CVE-2026-73296 | Microsoft UFO open-source framework for intelligent automation across devices and platforms | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_73296] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73296] |
| CVE-2026-73037 | Next AI Draw.io 0.2.1 through 0.4.16 contains a reflected cross-site scripting vulnerability in the mcp query parameter that is interpolated without e | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_73037] · [mcp-cve-project][link_mcp_cve_project_cve_2026_73037] |
| CVE-2026-72846 | Lightdash stores the webhook URL supplied with a scheduled delivery and later posts to it from sendWebhook in packages/backend/src/clients/GoogleChat/ | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_72846] · [mcp-cve-project][link_mcp_cve_project_cve_2026_72846] |
| CVE-2026-72768 | n8n versions before 2.32.1 contain a server-side request forgery protection bypass vulnerability in the MCP Client node that allows authenticated user | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_72768] · [mcp-cve-project][link_mcp_cve_project_cve_2026_72768] |
| CVE-2026-71424 | Onyx is an open-source AI platform | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_71424] · [mcp-cve-project][link_mcp_cve_project_cve_2026_71424] |
| CVE-2026-69263 | Flowise is a drag & drop user interface to build a customized large language model flow | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_69263] · [mcp-cve-project][link_mcp_cve_project_cve_2026_69263] |
| CVE-2026-69257 | Flowise is a drag & drop user interface to build a customized large language model flow | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_69257] · [mcp-cve-project][link_mcp_cve_project_cve_2026_69257] |
| CVE-2026-68578 | ArcadeDB versions before 26.7.3 fail to bind the authenticated principal in the MCP HTTP transport, causing all engine permission checks to silently p | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_68578] · [mcp-cve-project][link_mcp_cve_project_cve_2026_68578] |
| CVE-2026-67531 | FrontMCP is a TypeScript-first framework for the Model Context Protocol (MCP) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_67531] · [mcp-cve-project][link_mcp_cve_project_cve_2026_67531] |
| CVE-2026-67432 | MCP Ruby SDK (`modelcontextprotocol/ruby-sdk`): Streamable HTTP unbounded JSON-RPC body DoS | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_67432] · [mcp-cve-project][link_mcp_cve_project_cve_2026_67432] |
| CVE-2026-67431 | MCP Ruby SDK (`modelcontextprotocol/ruby-sdk`): Streamable HTTP session poisoning / missing session owner binding | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_67431] · [mcp-cve-project][link_mcp_cve_project_cve_2026_67431] |
| CVE-2026-67430 | MCP Ruby SDK (`modelcontextprotocol/ruby-sdk`): Streamable HTTP unbounded session retention DoS | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_67430] · [mcp-cve-project][link_mcp_cve_project_cve_2026_67430] |
| CVE-2026-67357 | ArcadeDB versions before 26.7.3 contain an information disclosure vulnerability in the MCP get_server_settings tool that leaks the arcadedb.ha.cluster | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_67357] · [mcp-cve-project][link_mcp_cve_project_cve_2026_67357] |
| CVE-2026-67336 | better-auth versions before 1.6.11 contain insecure cryptographic defaults in the oidcProvider and mcp plugins that advertise the none algorithm and a | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_67336] · [mcp-cve-project][link_mcp_cve_project_cve_2026_67336] |
| CVE-2026-67333 | better-auth before 1.6.13 (and pre-release builds 1.7.0-beta.0 through 1.7.0-beta.3) fail to validate the scheme of redirect_uris registered via the d | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_67333] · [mcp-cve-project][link_mcp_cve_project_cve_2026_67333] |
| CVE-2026-66065 | Ouroboros is a local-first runtime for AI coding agents that records their actions and applies user-defined policies to constrain behavior | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_66065] · [mcp-cve-project][link_mcp_cve_project_cve_2026_66065] |
| CVE-2026-66012 | SiYuan before v3.7.2 contains a missing authorization vulnerability in the POST /mcp kernel endpoint, which is gated only by a general auth check (mod | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_66012] · [mcp-cve-project][link_mcp_cve_project_cve_2026_66012] |
| CVE-2026-66005 | Jan through 0.8.4, fixed in commit 3e1c1e7, contains a CORS misconfiguration vulnerability in its local API server that allows network-adjacent attack | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_66005] · [mcp-cve-project][link_mcp_cve_project_cve_2026_66005] |
| CVE-2026-65594 | n8n before 2.29.8 and 2.30.x before 2.30.1 (affected from 2.27.0, when the OAuth 2.1 consent and token-issuance flow was introduced) does not verify t | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_65594] · [mcp-cve-project][link_mcp_cve_project_cve_2026_65594] |
| CVE-2026-65056 | mcp-webresearch 0.1.7 contains a server-side request forgery vulnerability that allows attackers to access internal network services by supplying loop | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_65056] · [mcp-cve-project][link_mcp_cve_project_cve_2026_65056] |
| CVE-2026-64684 | RMCP custom headers leak across redirects | Token Mismanagement & Secret Exposure | ≥ 2.1.0 | [NVD][link_nvd_cve_2026_64684] · [mcp-cve-project][link_mcp_cve_project_cve_2026_64684] · [GHSA][link_ghsa_9g45_5xwm_f3wc] |
| CVE-2026-63732 | 9router 0.4.59 (fixed in 0.4.60) contains a chain of vulnerabilities: a hardcoded default password (123456) that authenticates any fresh installation, | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_63732] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63732] |
| CVE-2026-63658 | Unauthenticated Remote Denial of Service in MCP Kotlin SDK Streamable HTTP transport (request body size limit bypass) | Insufficient Authentication & Authorization | ≥ 0.14.0 | [NVD][link_nvd_cve_2026_63658] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63658] · [GHSA][link_ghsa_f47c_p7wj_q7gx] |
| CVE-2026-63657 | Unbounded memory growth in `StreamableHttpClientTransport` when parsing inline Server-Sent Events on HTTP POST responses | Insufficient Authentication & Authorization | ≥ 0.14.0 | [NVD][link_nvd_cve_2026_63657] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63657] · [GHSA][link_ghsa_4x39_xh35_w96w] |
| CVE-2026-63128 | RMCP unauthenticated session-table exhaustion | Insufficient Authentication & Authorization | ≥ 2.0.0 | [NVD][link_nvd_cve_2026_63128] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63128] · [GHSA][link_ghsa_9pj6_vhgr_3mwh] |
| CVE-2026-63127 | RMCP OAuth resource validation failure | Token Mismanagement & Secret Exposure | ≥ 2.0.0 | [NVD][link_nvd_cve_2026_63127] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63127] · [GHSA][link_ghsa_33f5_2c5q_wgwj] |
| CVE-2026-63119 | MCP Ruby SDK (`modelcontextprotocol/ruby-sdk`): stdio unbounded line buffer DoS | Insufficient Authentication & Authorization | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_63119] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63119] |
| CVE-2026-63118 | MCP Ruby SDK (`modelcontextprotocol/ruby-sdk`): Streamable HTTP DNS rebinding | Insufficient Authentication & Authorization | ≥ 0.23.0 | [NVD][link_nvd_cve_2026_63118] · [mcp-cve-project][link_mcp_cve_project_cve_2026_63118] |
| CVE-2026-62863 | Prior to 0.5.0, when MoLing runs in SSE mode using `-l`, its `/sse` and `/message` HTTP endpoints do not authenticate requests and the `mcp-go` dependency sets `Access-Control-Allow-Origin: *`. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_62863] · [mcp-cve-project][link_mcp_cve_project_cve_2026_62863] · [GHSA][link_ghsa_qpgh_hp5g_4vwp] |
| CVE-2026-62674 | Omnigent is an open-source AI agent framework and meta-harness for orchestrating coding agents | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_62674] · [mcp-cve-project][link_mcp_cve_project_cve_2026_62674] |
| CVE-2026-62312 | 9Router is an AI router & token saver | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_62312] · [mcp-cve-project][link_mcp_cve_project_cve_2026_62312] |
| CVE-2026-62264 | In versions 2.2.0 and later prior to 3.0.1, when `MCP_TRANSPORT=http` enables the opt-in HTTP server, `@sylphx/pdf-reader-mcp` reads `MCP_API_KEY` and logs that `X-API-Key` authentication is enabled but never validates the `X-API-Key` header on incoming requests. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_62264] · [mcp-cve-project][link_mcp_cve_project_cve_2026_62264] · [GHSA][link_ghsa_q344_5v34_gm84] |
| CVE-2026-62208 | OpenClaw before 2026.6.5 could forward Authorization headers during MCP SSE redirects | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_62208] · [mcp-cve-project][link_mcp_cve_project_cve_2026_62208] |
| CVE-2026-62195 | OpenClaw versions 2026.5.20 before 2026.6.6 contain an authorization bypass vulnerability in the MCP loopback feature that allows lower-trust callers | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_62195] · [mcp-cve-project][link_mcp_cve_project_cve_2026_62195] |
| CVE-2026-61789 | Prior to 0.22.6, read-only SQL validation can be bypassed on the MySQL and MariaDB connectors. | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_61789] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61789] · [GHSA][link_ghsa_j656_3hf2_fvjc] |
| CVE-2026-61788 | Prior to version 0.22.6, setting `readonly = true` on the `execute_sql` tool does not make the connection read-only. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_61788] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61788] · [GHSA][link_ghsa_mwwr_p57h_56pf] |
| CVE-2026-61742 | Versions prior to 0.22.5 expose an unauthenticated HTTP MCP endpoint when started with the documented HTTP transport mode, for example `--transport http --port 8080`. | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_61742] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61742] · [GHSA][link_ghsa_fm8p_53ww_hf6w] |
| CVE-2026-61647 | Versions 1.6.0 through 2.0.2 contain a path traversal vulnerability in the `POST /batch-to-vault` endpoint, also exposed through the `batch_to_vault` MCP tool beginning in version 1.7.0, because attacker-controlled `vault_dir` and `slug_prefix` values can cause Markdown and JSON files to be written outside the intended vault directory to any location | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_61647] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61647] · [GHSA][link_ghsa_jjhp_8crj_mppq] |
| CVE-2026-61612 | CKAN MCP DNS-based SSRF bypass | Command Injection & Execution | ≥ 0.4.108 | [NVD][link_nvd_cve_2026_61612] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61612] · [GHSA][link_ghsa_798p_78g2_v556] |
| CVE-2026-61568 | GitLab MCP Streamable HTTP DNS rebinding | Insufficient Authentication & Authorization | ≥ 2.1.30 | [NVD][link_nvd_cve_2026_61568] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61568] · [GHSA][link_ghsa_vmp7_252j_cwp7] |
| CVE-2026-61560 | Prior to version 2.1.27, the SSE transport mode (`SSE=true`) exposes all MCP tools without any authentication. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_61560] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61560] · [GHSA][link_ghsa_cv3r_c5h8_f4g5] |
| CVE-2026-61559 | Starting in version 0.0.1 and prior to version 2.1.27, when the environment variable `ENABLE_DYNAMIC_API_URL=true` is set, the server reads the `X-GitLab-API-URL` HTTP request header and uses it as the base URL for all outbound GitLab API calls made within that request. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_61559] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61559] · [GHSA][link_ghsa_2h44_8472_frjj] |
| CVE-2026-61546 | Prior to version 0.21.0, `anki_mcp_server/mcp_server.py` globally disables FastMCP DNS-rebinding protection through `TransportSecuritySettings` with `enable_dns_rebinding_protection=False`, including for the default local Streamable HTTP listener. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_61546] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61546] · [GHSA][link_ghsa_j9xx_59ph_wmr6] |
| CVE-2026-61542 | Gearsystem, the affected component, has an optional `--mcp-http` mode that accepts unauthenticated MCP requests from any reachable network peer despite localhost-only documentation and logging. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_61542] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61542] · [GHSA][link_ghsa_fmvx_487g_mrww] |
| CVE-2026-61462 | mcp-gitlab contains a path traversal vulnerability in the job_id parameter of build/index.js that allows attackers to redirect GitLab API requests to | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_61462] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61462] |
| CVE-2026-61459 | `mcp-server-kubernetes` structured tools `--server` argument injection / bearer token exfiltration | Privilege Escalation via Scope Creep | ≥ 3.9.0 | [NVD][link_nvd_cve_2026_61459] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61459] |
| CVE-2026-61427 | PraisonAI before 4.6.78 exposes the MCP HTTP-stream transport without authentication by default: the CLI --api-key option defaults to None, and the se | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_61427] · [mcp-cve-project][link_mcp_cve_project_cve_2026_61427] |
| CVE-2026-60083 | SiYuan versions before v3.8.0 contain an incomplete path blocklist in the MCP file tool that fails to restrict access to sensitive workspace files pro | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_60083] · [mcp-cve-project][link_mcp_cve_project_cve_2026_60083] |
| CVE-2026-59973 | The external $ref guard checks parsed hostname strings without resolving addresses, pinning validated addresses, revalidating redirect targets, or normalizing IPv4-mapped IPv6. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_59973] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59973] · [GHSA][link_ghsa_65h7_9wrw_629c] |
| CVE-2026-59971 | MySQL MCP Server unauthenticated SQL execution | Insufficient Authentication & Authorization | ≥ 0.4.2 | [NVD][link_nvd_cve_2026_59971] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59971] · [GHSA][link_ghsa_rqfv_2mw9_78g2] |
| CVE-2026-59951 | From 1.8.0 until 1.30.0 and 2.2.0, stateful Streamable HTTP servers, including FastMCP, MCPServer, Server.streamable_http_app(), and StreamableHTTPSessionManager, retain session entries without an idle expiration or aggregate session-count limit. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_59951] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59951] · [GHSA][link_ghsa_84m7_p3x7_pcfv] |
| CVE-2026-59950 | MCP Python SDK (`mcp`): deprecated WebSocket transport Host/Origin validation gap | Insufficient Authentication & Authorization | ≥ 1.28.1 | [NVD][link_nvd_cve_2026_59950] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59950] |
| CVE-2026-59822 | LiteLLM is a proxy server (AI Gateway) to call LLM APIs in OpenAI (or native) format | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_59822] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59822] |
| CVE-2026-59809 | SiYuan before v3.8.0 interpolates secret placeholders into the destination URL parameter of the http_request MCP tool, allowing attackers to exfiltrat | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_59809] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59809] |
| CVE-2026-59726 | Ruflo is an agent meta-harness for Claude Code and Codex | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_59726] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59726] |
| CVE-2026-59723 | Cline is an autonomous coding agent as an SDK, IDE extension, or CLI assistant | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_59723] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59723] |
| CVE-2026-59563 | Zscaler MCP Server versions 0.7.0 and 0.7.1 has an issue where HMAC confirmation tokens were not bound to the target resource identifier, allowing an MCP client or agent to replay a token generated for one resource to affect another resource of the same type. | Token Mismanagement & Secret Exposure | ≥ 0.7.2 | [NVD][link_nvd_cve_2026_59563] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59563] |
| CVE-2026-59279 | The MCP Streamable HTTP server transport (WebFlux and WebMvc variants) does not place any limit on the number of sessions it retains, and by default d | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_59279] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59279] |
| CVE-2026-59207 | n8n is an open source workflow automation platform | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_59207] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59207] |
| CVE-2026-59176 | Package-alias syntaxes such as `file:`, `npm:`, URLs, or paths can cause an arbitrary local or remote package to be installed as functype. | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_59176] · [mcp-cve-project][link_mcp_cve_project_cve_2026_59176] · [GHSA][link_ghsa_wcjj_9m6g_2fr2] |
| CVE-2026-58500 | MCP Appium is an MCP server that provides AI assistants with tools to automate mobile app testing on Android and iOS | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_58500] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58500] |
| CVE-2026-58497 | Prior to version 0.225.2, Uni-CLI exposed the legacy JSON-RPC-over-HTTP MCP transport on loopback without validating browser Origin headers before routing requests. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_58497] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58497] · [GHSA][link_ghsa_v3f4_w7r7_v3hm] |
| CVE-2026-58485 | Prior to 1.7.1, web_url_read receives its caller-controlled URL through src/index.ts and validates only the literal hostname in assertUrlAllowed() within src/url-reader.ts before undiciFetch() performs operating-system DNS resolution. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_58485] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58485] · [GHSA][link_ghsa_mrvx_jmjw_vggc] |
| CVE-2026-58483 | Prior to 1.7.1, web_url_read in src/index.ts passes a caller-supplied URL to readUrlContent() in src/url-reader.ts, where checkContentLength() treats a missing Content-Length header as an inconclusive preflight and the normal and error paths then consume the complete body with response.text(). | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_58483] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58483] · [GHSA][link_ghsa_xcqx_9jf5_w339] |
| CVE-2026-58446 | Presenton bundled MCP server unauthenticated /mcp access | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_58446] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58446] |
| CVE-2026-58201 | A specially crafted path can alter URL authority parsing and cause an Azure Resource Manager bearer token to be sent to an unintended host. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_58201] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58201] · [GHSA][link_ghsa_g2gw_q38m_vjfc] |
| CVE-2026-58197 | Prior to ToolHive CLI 0.30.1 and ToolHive Studio 0.38.0, locally run MCP server containers use the default network permission profile without network isolation, permitting access to host.docker.internal while ToolHive API and MCP proxy endpoints are reachable without authentication. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_58197] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58197] · [GHSA][link_ghsa_qg2g_g9w3_m5h8] |
| CVE-2026-58196 | Prior to 0.31.0, remote.Handler.Authenticate in pkg/auth/remote/handler.go invokes discovery.DetectAuthenticationFromServer in pkg/auth/discovery/discovery.go, whose host-side HTTP clients trust remote-server-controlled authentication discovery destinations, follow redirects without host or scheme restrictions, and do not consistently block private | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_58196] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58196] · [GHSA][link_ghsa_pr64_jmmf_jp54] |
| CVE-2026-58195 | Agentic-Flow is an AI agent orchestration platform | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_58195] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58195] |
| CVE-2026-58171 | Vibe-Trading path traversal affecting MCP/agent workflow storage | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_58171] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58171] |
| CVE-2026-58168 | DeepTutor MCP tool authorization bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_58168] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58168] |
| CVE-2026-58057 | Flowise Custom MCP Windows env-var denylist bypass | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_58057] · [mcp-cve-project][link_mcp_cve_project_cve_2026_58057] |
| CVE-2026-57922 | JetBrains YouTrack project settings disclosure via MCP | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_57922] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57922] |
| CVE-2026-57860 | ForgeCode (tailcallhq/forgecode), an AI pair-programming CLI, automatically loads and executes the MCP servers defined in a repository's .mcp.json fil | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_57860] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57860] |
| CVE-2026-57496 | Prior to 0.1.8, netlicensing_get_product passes the caller-controlled product_number to src/netlicensing_mcp/tools/products.py, which interpolates it into a REST path consumed by nl_get() in src/netlicensing_mcp/client.py without path-segment validation. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_57496] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57496] · [GHSA][link_ghsa_hxpf_9xvq_wph8] |
| CVE-2026-57495 | AgenticMail gives AI agents real email addresses and phone numbers | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_57495] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57495] |
| CVE-2026-57442 | Prior to 0.11.5, PathFilter in src/pathfilter.ts uses root-anchored deny-list patterns, so nested .git, .obsidian, and node_modules path segments do not match the restriction and pass both isAllowed() and isAllowedForListing(). | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_57442] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57442] · [GHSA][link_ghsa_9c83_rr99_vfwj] |
| CVE-2026-57441 | Prior to 0.11.4, PathFilter in src/pathfilter.ts compiles restricted-directory patterns case-sensitively and compares paths without canonicalizing filesystem-equivalent segment names. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_57441] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57441] · [GHSA][link_ghsa_j99q_93c9_h869] |
| CVE-2026-57300 | Jenkins MCP Server Plugin missing permission check | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_57300] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57300] |
| CVE-2026-57207 | Prior to version 1.2.1, when running with TRANSPORT=http, the MCP server has no authentication on the HTTP endpoint. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_57207] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57207] · [GHSA][link_ghsa_5qg7_j8mr_9477] |
| CVE-2026-57139 | npm PraisonAI MCPServer exposes unauthenticated HTTP tools/call | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_57139] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57139] |
| CVE-2026-57112 | PraisonAI ToolsMCPServer legacy SSE transport lacks Host/Origin validation and authentication | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_57112] · [mcp-cve-project][link_mcp_cve_project_cve_2026_57112] |
| CVE-2026-56274 | Flowise Custom MCP Server command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_56274] · [mcp-cve-project][link_mcp_cve_project_cve_2026_56274] |
| CVE-2026-55887 | Docker MCP Gateway (`github.com/docker/mcp-gateway`) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_55887] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55887] |
| CVE-2026-55837 | Prior to 1.20.0, the local OAuth helper in src/dbt_mcp/oauth/fastapi_app.py exposes GET /dbt_platform_context without authentication or Host validation after a user completes the dbt Platform OAuth flow. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55837] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55837] · [GHSA][link_ghsa_jr33_mw75_7j8f] |
| CVE-2026-55786 | flyto-core: unauthenticated command execution via HTTP MCP execute_module | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_55786] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55786] |
| CVE-2026-55640 | Nextcloud MCP Server is a production-ready MCP server that connects AI assistants to a Nextcloud instance | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55640] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55640] |
| CVE-2026-55637 | genieacs-mcp: Streamable HTTP DNS rebinding on localhost listener | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_55637] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55637] |
| CVE-2026-55609 | sublinear-time-solver is a Rust and WebAssembly library for solving asymmetric diagonally dominant systems in sublinear time. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_55609] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55609] |
| CVE-2026-55608 | n8n-MCP is an MCP server that provides AI assistants access to n8n node documentation, properties, and operations | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_55608] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55608] |
| CVE-2026-55605 | DeepSeek MCP Server is an MCP server for DeepSeek V4 | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55605] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55605] |
| CVE-2026-55604 | DeepSeek MCP Server is an MCP server for DeepSeek V4 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_55604] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55604] |
| CVE-2026-55582 | mcp-shell is an MCP server for running shell commands securely, auditably, and on demand | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_55582] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55582] |
| CVE-2026-55581 | mcp-shell is an MCP server for running shell commands securely, auditably, and on demand | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55581] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55581] |
| CVE-2026-55580 | mcp-shell is an MCP server for running shell commands securely, auditably, and on demand | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_55580] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55580] |
| CVE-2026-55557 | browse-mcp is a Playwright-based headless-browser MCP server for MCP-capable agents. | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_55557] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55557] |
| CVE-2026-55550 | NextCRM is open-source customer relationship management (CRM) software | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55550] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55550] |
| CVE-2026-55546 | QWED-MCP is a deterministic verification gateway for MCP | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55546] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55546] |
| CVE-2026-55544 | NextCRM is open-source customer relationship management (CRM) software | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55544] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55544] |
| CVE-2026-55532 | PraisonAI is a multi-agent teams system | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55532] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55532] |
| CVE-2026-55531 | PraisonAI is a multi-agent teams system | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_55531] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55531] |
| CVE-2026-55529 | PraisonAI is a multi-agent teams system | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_55529] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55529] |
| CVE-2026-55157 | Token Optimizer MCP: OS command injection in smart_user via username | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_55157] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55157] |
| CVE-2026-55156 | Token Optimizer MCP dashboard path traversal | Privilege Escalation via Scope Creep | ≥ 5.1.0 | [NVD][link_nvd_cve_2026_55156] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55156] · [GHSA][link_ghsa_76pc_mqxp_3rq5] |
| CVE-2026-55096 | Downloads are guarded by _validate_url_security, an SSRF denylist that checks the URL's literal hostname string but never resolves DNS. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_55096] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55096] · [GHSA][link_ghsa_xr72_j7vj_vp7g] |
| CVE-2026-55071 | MCP-for-Stata: command injection via unsanitized package in ado_package_install | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_55071] · [mcp-cve-project][link_mcp_cve_project_cve_2026_55071] |
| CVE-2026-54842 | Royal MCP missing authorization | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_54842] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54842] |
| CVE-2026-54785 | gemini-bridge is a lightweight MCP server bridging AI agents to Google's Gemini AI via the official CLI | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_54785] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54785] |
| CVE-2026-54689 | Prior to 1.2.0, the web_url_read URL policy in src/url-reader.ts can be bypassed while MCP_HTTP_HARDEN is enabled and MCP_HTTP_ALLOW_PRIVATE_URLS is not enabled because redirect targets are not revalidated, 0.0.0.0 is not classified as an internal address, and IPv4-mapped IPv6 literals canonicalized to hexadecimal form are not recognized. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_54689] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54689] · [GHSA][link_ghsa_wppf_h75h_6pm6] |
| CVE-2026-54688 | Prior to 1.2.0, web_url_read passes a caller-supplied URL to the server-side fetch path while assertUrlAllowed() in src/url-reader.ts runs only when MCP_HTTP_HARDEN is enabled, even though MCP_HTTP_HARDEN is disabled by default in src/http-security.ts. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_54688] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54688] · [GHSA][link_ghsa_q87f_qc2r_2gw4] |
| CVE-2026-54618 | Prior to 0.2.0, /oauth/authorize issues an authorization code without a login, consent, or session check, and /oauth/token can exchange that code for the static VAULT_MCP_TOKEN without authenticating a client. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_54618] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54618] · [GHSA][link_ghsa_hwhg_mrjc_8g43] |
| CVE-2026-54561 | mcp-memory-keeper: arbitrary local file read in context_import via unvalidated filePath | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_54561] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54561] |
| CVE-2026-54549 | Prior to version 1.0.115, the upload_ad_image tool in meta_ads_mcp/core/ads.py passes an attacker-controlled image_url to try_multiple_download_methods() in meta_ads_mcp/core/utils.py, where httpx.AsyncClient uses follow_redirects=True and performs HTTP requests without validating the scheme, host, or resolved IP address. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_54549] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54549] · [GHSA][link_ghsa_45gf_fjxp_cjpq] |
| CVE-2026-54547 | Prior to version 1.0.115, AuthInjectionMiddleware in meta_ads_mcp/core/http_auth_integration.py rejects HTTP MCP requests only when both auth_token and pipeboard_token are absent, while extract_token_from_headers() does not recognize X-Pipeboard-Token as a primary credential. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_54547] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54547] · [GHSA][link_ghsa_2v2f_mvfg_ph56] |
| CVE-2026-54504 | @andrea9293/mcp-documentation-server: Web UI/API binds to all interfaces by default without authentication | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_54504] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54504] |
| CVE-2026-54450 | Prior to 0.29.1, networking.IsPrivateIP in pkg/networking/utilities.go omits the IPv6 NAT64 prefixes 64:ff9b::/96 and 64:ff9b:1::/48, so NAT64 addresses embedding private, loopback, or link-local IPv4 targets are classified as public and allowed. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_54450] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54450] · [GHSA][link_ghsa_pph6_vfjv_vpjw] |
| CVE-2026-54449 | LangBot | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_54449] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54449] |
| CVE-2026-54446 | Prior to 0.1.6, network-reachable HTTP transport requests to /mcp that omit x-netlicensing-api-key, Authorization: Bearer, and the apikey query parameter pass through ApiKeyMiddleware in src/netlicensing_mcp/server.py without authentication. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_54446] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54446] · [GHSA][link_ghsa_x9vc_9ffq_p3gj] |
| CVE-2026-54309 | @n8n/mcp-browser unauthenticated HTTP transport | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_54309] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54309] |
| CVE-2026-54149 | MaxKB is an open-source AI assistant for enterprise | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_54149] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54149] |
| CVE-2026-54140 | Before 0.57.13, OpenHuman places names, descriptions, titles, and parameter definitions returned by configured external MCP servers into the agent model context without neutralizing instructions or bounding the descriptive fields. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_54140] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54140] · [GHSA][link_ghsa_g6j9_89xv_v752] |
| CVE-2026-54052 | n8n-MCP is an MCP server that provides AI assistants access to n8n node documentation, properties, and operations | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_54052] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54052] |
| CVE-2026-54030 | LibreChat MCP OAuth resource validation issue | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_54030] · [mcp-cve-project][link_mcp_cve_project_cve_2026_54030] |
| CVE-2026-53965 | MCP PHP SDK (`modelcontextprotocol/php-sdk`): `HttpTransport` unbounded SSE buffer DoS | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_53965] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53965] |
| CVE-2026-53957 | Prior to @contentful/mcp-server 1.7.19 and @contentful/mcp-tools 0.4.5, export_space and import_space in packages/mcp-tools/src/tools/jobs/space-to-space-migration/exportSpace.ts and packages/mcp-tools/src/tools/jobs/space-to-space-migration/importSpace.ts expose host, proxy, rawProxy, and insecure network options to LLM-controlled tool arguments and | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_53957] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53957] · [GHSA][link_ghsa_2xhg_73j7_rrgx] |
| CVE-2026-53937 | A peer that streams bytes without ever sending a newline causes the internal buffer to grow indefinitely until the JVM (or the surrounding host process) is OOM-killed. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_53937] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53937] · [GHSA][link_ghsa_74gp_qhv5_v493] |
| CVE-2026-53840 | OpenClaw Streamable HTTP MCP custom-header leak on redirects | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_53840] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53840] |
| CVE-2026-53820 | OpenClaw bundled MCP exec denylist bypass | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_53820] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53820] |
| CVE-2026-53818 | OpenClaw MCP loopback owner-only policy bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_53818] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53818] |
| CVE-2026-53814 | OpenClaw hook-triggered MCP loopback privilege escalation | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_53814] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53814] |
| CVE-2026-53766 | chrome-devtools-mcp workspace path validation issue | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_53766] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53766] |
| CVE-2026-53710 | Prior to 1.0.2, the python_sandbox_server in mcp-servers/python/python_sandbox_server/src/python_sandbox_server/server_fastmcp.py exposes raw getattr through safe_builtins, omits a required _getattr_ guard, and relies on validate_code checks for literal dangerous dunder strings. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_53710] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53710] · [GHSA][link_ghsa_xm98_3vcf_fph7] |
| CVE-2026-53708 | ContextForge before 1.0.3: `/admin/gateways/test` checks a caller-supplied gateway URL for private, loopback, link-local, and cloud-metadata addresses, and that check can be bypassed by DNS rebinding. | Insufficient Authentication & Authorization | ≥ 1.0.3 | [NVD][link_nvd_cve_2026_53708] · [GHSA][link_ghsa_9hgc_g3w5_67cm] |
| CVE-2026-53518 | Better Auth is an authentication and authorization library for TypeScript | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_53518] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53518] |
| CVE-2026-53512 | Better Auth is an authentication and authorization library for TypeScript | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_53512] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53512] |
| CVE-2026-53509 | CKAN MCP Server is a tool for querying CKAN open data portals | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_53509] · [mcp-cve-project][link_mcp_cve_project_cve_2026_53509] |
| CVE-2026-52870 | MCP Python SDK (`mcp`): experimental task handlers cross-client access | Insufficient Authentication & Authorization | ≥ 1.27.2 | [NVD][link_nvd_cve_2026_52870] · [mcp-cve-project][link_mcp_cve_project_cve_2026_52870] · [GHSA][link_ghsa_hvrp_rf83_w775] |
| CVE-2026-52869 | MCP Python SDK (`mcp`): HTTP session auth bypass (`SseServerTransport` / Streamable HTTP) | Insufficient Authentication & Authorization | ≥ 1.27.2 | [NVD][link_nvd_cve_2026_52869] · [mcp-cve-project][link_mcp_cve_project_cve_2026_52869] · [GHSA][link_ghsa_jpw9_pfvf_9f58] |
| CVE-2026-52830 | fast-mcp-telegram is a Telegram MCP Server | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_52830] · [mcp-cve-project][link_mcp_cve_project_cve_2026_52830] |
| CVE-2026-51994 | mcp-remote versions 0.1.32 through 0.1.38 are vulnerable to Server-Side Request Forgery (SSRF) via the resource_metadata URL extracted from a remote MCP server's WWW-Authenticate header | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_51994] · [mcp-cve-project][link_mcp_cve_project_cve_2026_51994] |
| CVE-2026-50758 | Cross Site Scripting vulnerability in DayuanJiang next-ai-draw-io 0.4.13 allows a remote attacker to execute arbitrary code via the mcp parameter | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_50758] · [mcp-cve-project][link_mcp_cve_project_cve_2026_50758] |
| CVE-2026-50287 | @agenticmail/mcp unauthenticated Streamable HTTP endpoint | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_50287] · [mcp-cve-project][link_mcp_cve_project_cve_2026_50287] |
| CVE-2026-50158 | Prior to 0.10.9, the caption-download MCP tool accepts a caller-controlled file parameter through cmd/caption/download.go and passes it to Caption.Download() in pkg/caption/caption.go, where os.Create() creates or truncates that path without using the pkg.Root confinement boundary backed by YUTU_ROOT. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_50158] · [mcp-cve-project][link_mcp_cve_project_cve_2026_50158] · [GHSA][link_ghsa_2c7f_fxww_6w6c] |
| CVE-2026-50143 | `@apify/actors-mcp-server` Actor `webServerMcpPath` authority injection / Apify token leak | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_50143] · [mcp-cve-project][link_mcp_cve_project_cve_2026_50143] |
| CVE-2026-50125 | Prior to 0.4.1, cmd/server/main.go exposes the default HTTP endpoint and pkg/mcp/server.go registers the unauthenticated get_resource tool, which accepts attacker-controlled limitBytes and tailLines values for the pods logs subresource. buildPodLogOpts() in pkg/k8s/subresource.go parses those values as unbounded int64 parameters, and defaultGetPodLogs() | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_50125] · [mcp-cve-project][link_mcp_cve_project_cve_2026_50125] · [GHSA][link_ghsa_qw5r_ppcg_f8rj] |
| CVE-2026-50027 | mcp-memory-service is a semantic memory layer for AI applications | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_50027] · [mcp-cve-project][link_mcp_cve_project_cve_2026_50027] |
| CVE-2026-49988 | Repomix is a tool that packs repositories into AI-friendly files | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_49988] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49988] |
| CVE-2026-49986 | The Cortex MCP server (`neuro-cortex-memory`), a cross-platform persistent memory MCP, prior to version 3.17.1 treats the `CLAUDE_PROJECT_DIR` environ | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_49986] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49986] |
| CVE-2026-49857 | auth-fetch-mcp is an MCP server that lets AI assistants fetch content from authenticated web pages | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_49857] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49857] |
| CVE-2026-49856 | @jshookmcp/jshook is an MCP server that gives AI agents tools for JavaScript analysis and security research | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_49856] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49856] |
| CVE-2026-49471 | Serena is a powerful MCP toolkit for coding that provides semantic retrieval and editing capabilities | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_49471] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49471] |
| CVE-2026-49357 | line-desktop-mcp unauthenticated HTTP mode chat access | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_49357] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49357] |
| CVE-2026-49353 | 9Router is an AI router & token saver | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_49353] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49353] |
| CVE-2026-49291 | mcp-memory-service OAuth read-scope tools/call bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_49291] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49291] |
| CVE-2026-49257 | mcp-pinot unauthenticated 0.0.0.0 HTTP MCP server | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_49257] · [mcp-cve-project][link_mcp_cve_project_cve_2026_49257] |
| CVE-2026-48989 | Windows-MCP unauthenticated HTTP control plane / PowerShell execution | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_48989] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48989] |
| CVE-2026-48814 | Network-AI MCP SSE unauthenticated tool invocation | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_48814] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48814] |
| CVE-2026-48787 | gin-vue-admin MCP management code-generation command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_48787] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48787] |
| CVE-2026-48774 | ProxySQL GenAI/MCP run_sql_readonly multi-statement bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_48774] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48774] |
| CVE-2026-48710 | Starlette / FastAPI-based MCP and AI gateways | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_48710] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48710] |
| CVE-2026-48529 | GitHub MCP Server HTTP lockdown-mode repo access cache issue | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_48529] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48529] · [GHSA][link_ghsa_pjp5_fpmr_3349] |
| CVE-2026-48039 | Meta Ads MCP is a Model Context Protocol (MCP) server that lets AI assistants run Meta Ads | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_48039] · [mcp-cve-project][link_mcp_cve_project_cve_2026_48039] |
| CVE-2026-47769 | APIFold reads an OpenAPI 3.x or Swagger 2.x specification and generates a live, production-ready MCP server endpoint | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_47769] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47769] |
| CVE-2026-47751 | Anthropic Claude Code Action (`claude-code-action`) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_47751] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47751] |
| CVE-2026-47708 | MCP-for-Stata is an MCP server for Stata to integrate Stata into an agent | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_47708] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47708] |
| CVE-2026-47427 | GitHub MCP Server is GitHub's official MCP Server | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_47427] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47427] |
| CVE-2026-47394 | PraisonAI is a multi-agent teams system | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_47394] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47394] |
| CVE-2026-47388 | NocoDB MCP token attachment ownership bypass / file read | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_47388] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47388] |
| CVE-2026-47250 | mcp-server-kubernetes kubectl_generic unsafe flags / token exfiltration | Privilege Escalation via Scope Creep | ≥ 3.7.0 | [NVD][link_nvd_cve_2026_47250] · [mcp-cve-project][link_mcp_cve_project_cve_2026_47250] · [GHSA][link_ghsa_6mx4_4h42_r8vh] |
| CVE-2026-46555 | WhatsApp MCP Server is a Model Context Protocol (MCP) server for WhatsApp, enabling Claude to read and send WhatsApp messages | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_46555] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46555] |
| CVE-2026-46549 | NocoDB MCP OAuth token scope bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_46549] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46549] |
| CVE-2026-46519 | mcp-server-kubernetes | Privilege Escalation via Scope Creep | ≥ 3.6.0 | [NVD][link_nvd_cve_2026_46519] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46519] · [GHSA][link_ghsa_cr22_wjx7_2w6m] |
| CVE-2026-46515 | Frogman provides headless PBX control through MCP and HTTP API | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_46515] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46515] |
| CVE-2026-46514 | Frogman provides headless PBX control through MCP and HTTP API | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_46514] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46514] |
| CVE-2026-46513 | Frogman provides headless PBX control through MCP and HTTP API | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_46513] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46513] |
| CVE-2026-46512 | Frogman provides headless PBX control through MCP and HTTP API | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_46512] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46512] |
| CVE-2026-46341 | @apify/actors-mcp-server | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_46341] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46341] |
| CVE-2026-46339 | 9router MCP routes | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_46339] · [mcp-cve-project][link_mcp_cve_project_cve_2026_46339] |
| CVE-2026-45805 | @penpot/mcp | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_45805] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45805] |
| CVE-2026-45781 | MCP Registry | Privilege Escalation via Scope Creep | ≥ 1.7.9 | [NVD][link_nvd_cve_2026_45781] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45781] |
| CVE-2026-45707 | n8n-mcp multi-tenant HTTP transport authentication gap | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_45707] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45707] |
| CVE-2026-45609 | Spring AI mcp-security missing MCP-spec SSRF mitigations | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_45609] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45609] |
| CVE-2026-45582 | n8n-MCP (`czlonkowski/n8n-mcp`) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_45582] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45582] |
| CVE-2026-45555 | Roslyn CodeLens MCP Server arbitrary DiagnosticAnalyzer load | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_45555] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45555] |
| CVE-2026-45350 | Open WebUI chat completion API MCP tool restriction bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_45350] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45350] |
| CVE-2026-45019 | Chainlit (`chainlit`): MCP SSE / streamable-http SSRF via `POST /mcp` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_45019] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45019] |
| CVE-2026-45018 | Chainlit (`chainlit`): MCP stdio command injection via `POST /mcp` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_45018] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45018] |
| CVE-2026-45001 | OpenClaw | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_45001] · [mcp-cve-project][link_mcp_cve_project_cve_2026_45001] |
| CVE-2026-44998 | OpenClaw | Tool Poisoning | See NVD | [NVD][link_nvd_cve_2026_44998] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44998] |
| CVE-2026-44995 | OpenClaw | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_44995] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44995] |
| CVE-2026-44970 | `dbt-mcp`: unredacted MCP tool arguments sent to dbt Labs telemetry by default | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_44970] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44970] |
| CVE-2026-44969 | `dbt-mcp`: plaintext SQL/credentials in tool argument logs when file logging enabled | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_44969] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44969] |
| CVE-2026-44968 | `dbt-mcp`: dbt CLI argument injection via `node_selection` / `resource_type` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_44968] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44968] |
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
| CVE-2026-44192 | A flaw was found in the Ansible Lightspeed Model Context Protocol (MCP) server | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_44192] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44192] |
| CVE-2026-44118 | OpenClaw (loopback MCP owner-context spoofing) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_44118] · [mcp-cve-project][link_mcp_cve_project_cve_2026_44118] |
| CVE-2026-43995 | Flowise is a drag & drop user interface to build a customized large language model flow. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_43995] · [mcp-cve-project][link_mcp_cve_project_cve_2026_43995] |
| CVE-2026-43992 | JunoClaw | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_43992] · [mcp-cve-project][link_mcp_cve_project_cve_2026_43992] |
| CVE-2026-43989 | JunoClaw is an agentic AI platform built on Juno Network. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_43989] · [mcp-cve-project][link_mcp_cve_project_cve_2026_43989] |
| CVE-2026-43901 | Wireshark MCP (`wireshark-mcp`) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_43901] · [mcp-cve-project][link_mcp_cve_project_cve_2026_43901] |
| CVE-2026-42856 | Network-AI is a TypeScript/Node.js multi-agent orchestrator. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_42856] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42856] |
| CVE-2026-42559 | MCP Rust SDK (`rmcp` crate): Streamable HTTP server transport DNS rebinding | Insufficient Authentication & Authorization | ≥ 1.4.0 | [NVD][link_nvd_cve_2026_42559] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42559] |
| CVE-2026-42449 | `n8n-mcp` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_42449] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42449] |
| CVE-2026-42282 | `n8n-mcp` | Lack of Audit and Telemetry | See NVD | [NVD][link_nvd_cve_2026_42282] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42282] |
| CVE-2026-42271 | LiteLLM MCP server preview endpoints | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_42271] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42271] |
| CVE-2026-42260 | Open-WebSearch MCP server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_42260] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42260] |
| CVE-2026-42236 | `n8n` (MCP OAuth client registration DoS) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_42236] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42236] |
| CVE-2026-42235 | n8n is an open source workflow automation platform. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_42235] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42235] |
| CVE-2026-42230 | `n8n` (MCP OAuth open redirect) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_42230] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42230] |
| CVE-2026-42073 | OpenClaude MCP OAuth callback CSRF state bypass / DoS | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_42073] · [mcp-cve-project][link_mcp_cve_project_cve_2026_42073] |
| CVE-2026-41497 | PraisonAI is a multi-agent teams system. Prior to version 4.6.9, the fix for PraisonAI's MCP command handling does not add a command allowlist or argument validation to parse_mcp_command(), allowing arbitrary executables | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_41497] · [mcp-cve-project][link_mcp_cve_project_cve_2026_41497] |
| CVE-2026-41495 | `n8n-mcp` | Lack of Audit and Telemetry | See NVD | [NVD][link_nvd_cve_2026_41495] · [mcp-cve-project][link_mcp_cve_project_cve_2026_41495] |
| CVE-2026-41268 | Flowise Custom MCP `mcpServerConfig` parameter override / `NODE_OPTIONS` injection RCE | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_41268] · [mcp-cve-project][link_mcp_cve_project_cve_2026_41268] |
| CVE-2026-40933 | Flowise (MCP adapter command injection via unsafe stdio serialization) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_40933] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40933] |
| CVE-2026-40775 | Royal MCP unauthenticated broken access control | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_40775] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40775] |
| CVE-2026-40608 | Next AI Draw.io embedded MCP HTTP sidecar | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_40608] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40608] |
| CVE-2026-40576 | `excel-mcp-server` (path traversal in remote file handlers) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_40576] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40576] |
| CVE-2026-40159 | PraisonAI MCP integration:`PraisonAI` (pip) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_40159] · [mcp-cve-project][link_mcp_cve_project_cve_2026_40159] |
| CVE-2026-39987 | Marimo Python notebook server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39987] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39987] |
| CVE-2026-39974 | `n8n-mcp` (authenticated SSRF in multi-tenant HTTP mode) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39974] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39974] |
| CVE-2026-39885 | FrontMCP / `mcp-from-openapi` (OpenAPI `$ref` SSRF):`mcp-from-openapi` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39885] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39885] |
| CVE-2026-39884 | `mcp-server-kubernetes` (`port_forward` argument injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39884] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39884] |
| CVE-2026-39417 | MaxKB workflow MCP node STDIO RCE (incomplete fix for CVE-2025-53928) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39417] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39417] |
| CVE-2026-39313 | `mcp-framework` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_39313] · [mcp-cve-project][link_mcp_cve_project_cve_2026_39313] |
| CVE-2026-38924 | NOTE: the Supplier observed that 0.0.0.0 was a "potential security hazard" but the Serena documentation, at the time of the issue report proposing 127.0.0.1 instead of 0.0.0.0, recommended "use a sandboxed environment for running Serena." | Insufficient Authentication & Authorization | ≥ 1.0.0 | [NVD][link_nvd_cve_2026_38924] · [mcp-cve-project][link_mcp_cve_project_cve_2026_38924] · [GHSA][link_ghsa_m922_r24v_6wff] |
| CVE-2026-37006 | GPT Researcher WebSocket endpoint malicious MCP configuration RCE | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_37006] · [mcp-cve-project][link_mcp_cve_project_cve_2026_37006] |
| CVE-2026-35674 | OpenClaw before 2026.5.18 contains a scope bypass vulnerability in the Gateway chat.send route that allows scoped clients to execute privileged commands. | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_35674] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35674] |
| CVE-2026-35577 | Apollo MCP Server (`apollo-mcp-server`; Streamable HTTP Host validation) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_35577] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35577] |
| CVE-2026-35568 | MCP Java SDK (`io.modelcontextprotocol.sdk`):`io.modelcontextprotocol.sdk:mcp-core` (maven) | Insufficient Authentication & Authorization | ≥ 1.0.0 | [NVD][link_nvd_cve_2026_35568] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35568] |
| CVE-2026-35402 | mcp-neo4j-cypher | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_35402] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35402] |
| CVE-2026-35394 | @mobilenext/mobile-mcp arbitrary Android intent execution | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_35394] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35394] |
| CVE-2026-35228 | Oracle MCP Server Helper Tool (SQL injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_35228] · [mcp-cve-project][link_mcp_cve_project_cve_2026_35228] |
| CVE-2026-34953 | PraisonAI MCP server authentication bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_34953] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34953] |
| CVE-2026-34939 | PraisonAI is a multi-agent teams system. Prior to version 4.5.90, MCPToolIndex.search_tools() compiles a caller-supplied string directly as a Python regular expression with no validation, sanitization, or timeout. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_34939] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34939] |
| CVE-2026-34884 | SSRF via set_skywalking_url Tool and GraphQL expression injection vulnerability in Apache SkyWalking MCP | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_34884] · [mcp-cve-project][link_mcp_cve_project_cve_2026_34884] |
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
| CVE-2026-32632 | Glances REST/WebUI MCP DNS rebinding / missing Host validation | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_32632] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32632] |
| CVE-2026-32625 | LibreChat — MCP server URL `${VAR}` interpolation exfiltrates `JWT_SECRET`, `CREDS_KEY`, `CREDS_IV`, `MONGO_URI` | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_32625] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32625] |
| CVE-2026-32247 | Graphiti MCP server (`getzep/graphiti`) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_32247] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32247] |
| CVE-2026-32211 | Azure MCP Server | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_32211] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32211] |
| CVE-2026-32112 | `ha-mcp` (OAuth consent f-string injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_32112] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32112] |
| CVE-2026-32111 | ha-mcp OAuth consent ha_url SSRF | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_32111] · [mcp-cve-project][link_mcp_cve_project_cve_2026_32111] |
| CVE-2026-31951 | LibreChat | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_31951] · [mcp-cve-project][link_mcp_cve_project_cve_2026_31951] |
| CVE-2026-31945 | LibreChat MCP server-side request forgery via DNS resolution | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_31945] · [mcp-cve-project][link_mcp_cve_project_cve_2026_31945] |
| CVE-2026-31944 | LibreChat (MCP OAuth callback account takeover) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_31944] · [mcp-cve-project][link_mcp_cve_project_cve_2026_31944] |
| CVE-2026-31841 | Hyperterse is a tool-first MCP framework for building AI-ready backend surfaces from declarative config. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_31841] · [mcp-cve-project][link_mcp_cve_project_cve_2026_31841] |
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
| CVE-2026-29872 | A cross-session information disclosure vulnerability exists in the awesome-llm-apps project in commit e46690f99c3f08be80a9877fab52acacf7ab8251 (2026-01-19). | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_29872] · [mcp-cve-project][link_mcp_cve_project_cve_2026_29872] |
| CVE-2026-29791 | Agentgateway is an open source data plane for agentic AI connectivity within or across any agent framework or environment. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_29791] · [mcp-cve-project][link_mcp_cve_project_cve_2026_29791] |
| CVE-2026-29787 | `mcp-memory-service` (`/api/health/detailed` information disclosure) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_29787] · [mcp-cve-project][link_mcp_cve_project_cve_2026_29787] |
| CVE-2026-29783 | GitHub Copilot CLI | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_29783] · [mcp-cve-project][link_mcp_cve_project_cve_2026_29783] |
| CVE-2026-28361 | NocoDB is software for building databases as spreadsheets. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_28361] · [mcp-cve-project][link_mcp_cve_project_cve_2026_28361] |
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
| CVE-2026-24052 | Claude Code (`@anthropic-ai/claude-code`): WebFetch trusted-domain validation bypass | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_24052] · [mcp-cve-project][link_mcp_cve_project_cve_2026_24052] |
| CVE-2026-23882 | Blinko MCP server creation function | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_23882] · [mcp-cve-project][link_mcp_cve_project_cve_2026_23882] |
| CVE-2026-23744 | MCPJam Inspector (unauthenticated RCE via exposed listener) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_23744] · [mcp-cve-project][link_mcp_cve_project_cve_2026_23744] |
| CVE-2026-23523 | Dive MCP Host Desktop Application | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_23523] · [mcp-cve-project][link_mcp_cve_project_cve_2026_23523] |
| CVE-2026-22793 | 5ire MCP client (ECharts option parsing → RCE) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_22793] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22793] |
| CVE-2026-22792 | 5ire Desktop MCP client (unsafe HTML rendering → arbitrary JS execution):`5ire` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_22792] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22792] |
| CVE-2026-22785 | `@orval/mcp` (Orval MCP server generation from OpenAPI) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_22785] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22785] |
| CVE-2026-22708 | Cursor < 2.3 (Auto-Run Mode with Allowlist: shell built-ins `export`, `typeset`, `declare` change environment variables without approval, so trusted commands such as `git branch` or `python3` run attacker code) | Command Injection & Execution | ≥ 2.3 | [NVD][link_nvd_cve_2026_22708] · [GHSA][link_ghsa_82wg_qcm4_fp2w] |
| CVE-2026-22688 | WeKnora (untrusted MCP stdio input) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_22688] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22688] |
| CVE-2026-22252 | LibreChat (untrusted MCP stdio input; cross-referenced in OX advisory) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_22252] · [mcp-cve-project][link_mcp_cve_project_cve_2026_22252] |
| CVE-2026-21852 | Claude Code (Anthropic agentic coding tool) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_21852] · [mcp-cve-project][link_mcp_cve_project_cve_2026_21852] |
| CVE-2026-21518 | Microsoft Visual Studio Code and GitHub Copilot (`mcp.json` handling) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_21518] · [mcp-cve-project][link_mcp_cve_project_cve_2026_21518] |
| CVE-2026-20205 | Splunk MCP Server | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_20205] · [mcp-cve-project][link_mcp_cve_project_cve_2026_20205] |
| CVE-2026-19984 | A flaw has been found in jkawamoto mcp-florence2 up to 0.3.13 | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_19984] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19984] |
| CVE-2026-19801 | The BetterLinks – Link Shortener, Link Cloaking, Redirects, Affiliate Link Manager & MCP plugin for WordPress is vulnerable to authorization bypass in | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_19801] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19801] |
| CVE-2026-19753 | A vulnerability was detected in Model Context Protocol mcp-rdf-explorer 1.0.0 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19753] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19753] |
| CVE-2026-19752 | A vulnerability was found in EnzoVezzaro mcp-dominican-layer up to 39dd373786712650097ad31db27d5c477c8f9c82 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19752] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19752] |
| CVE-2026-19751 | A flaw has been found in EnzoVezzaro mcp-dominican-layer up to 39dd373786712650097ad31db27d5c477c8f9c82 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19751] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19751] |
| CVE-2026-19591 | OpenAI Codex CLI for Windows, macOS, and Linux and Codex Desktop for Windows and macOS misclassified certain PowerShell commands as safe because their command-safety parser interpreted PowerShell's stop-parsing token (-- | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_19591] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19591] |
| CVE-2026-19516 | A caller-supplied X-Grafana-URL request header controls the destination of mcp-grafana's outbound requests, and the grafana_api_request tool lets the | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_19516] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19516] |
| CVE-2026-19338 | A vulnerability was identified in automateyournetwork MCPyATS up to 0.1.4 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_19338] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19338] |
| CVE-2026-19337 | A vulnerability was determined in adenot mcp-google-search up to 0.3.1 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19337] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19337] |
| CVE-2026-19332 | A security vulnerability has been detected in NellyW8 MCP4EDA 1.0.0 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19332] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19332] |
| CVE-2026-19329 | A vulnerability was found in andreahaku codex_mcp up to 1ff521cc6cc57cfe56ddef946c644b8534771390 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19329] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19329] |
| CVE-2026-19279 | A vulnerability was identified in MIMICLab mcp-pdf-vision 1.1.0 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19279] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19279] |
| CVE-2026-19270 | A security flaw has been discovered in Hulupeep mcp-ui-probe up to 0.2.0 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_19270] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19270] |
| CVE-2026-19268 | A vulnerability was identified in abdullah1854 MCPGateway up to 549f494a9e363f40530149de324b8097de424230 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19268] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19268] |
| CVE-2026-19263 | A vulnerability was found in INQUIRELAB mcp-bridge-api up to b30a82aa1d1d1139e0de846c41c8aadee6e06114 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19263] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19263] |
| CVE-2026-19244 | A vulnerability was detected in HKUDS nanobot up to 0.2.1 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_19244] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19244] |
| CVE-2026-19041 | A vulnerability has been found in MissionSquad mcp-api up to 1.11.8 | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_19041] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19041] |
| CVE-2026-19040 | A flaw has been found in MissionSquad mcp-api up to 1.11.9 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19040] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19040] |
| CVE-2026-19039 | A vulnerability was detected in Kino-Kafkaesque ssh-mcp-server up to 8ebbbb99b26f80ff6162fe00957c6dec73fbc5a5 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_19039] · [mcp-cve-project][link_mcp_cve_project_cve_2026_19039] |
| CVE-2026-18954 | Incorrect authorization in the aggregation pipeline tool in Amazon AWS Labs DocumentDB MCP Server before 1.0.12 might allow an authenticated MCP clien | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_18954] · [mcp-cve-project][link_mcp_cve_project_cve_2026_18954] |
| CVE-2026-18905 | IBM ContextForge MCP Gateway (`mcp-contextforge-gateway`): tool-invocation DNS rebinding | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_18905] · [mcp-cve-project][link_mcp_cve_project_cve_2026_18905] |
| CVE-2026-18655 | Improper restriction of intended endpoints in the RabbitMQ broker connection tools of the Amazon MQ MCP Server (awslabs.amazon-mq-mcp-server) before 2 | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_18655] · [mcp-cve-project][link_mcp_cve_project_cve_2026_18655] |
| CVE-2026-18489 | IBM ContextForge MCP Gateway - Translate utility <= 1.0.8 MCP Context Forge could allow a remote attacker to obtain sensitive information from other sessions due to exposure of data elements to the wrong session. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_18489] · [mcp-cve-project][link_mcp_cve_project_cve_2026_18489] |
| CVE-2026-18486 | IBM ContextForge MCP Gateway <= v1.0.7 MCP Context Forge could allow a remote authenticated attacker to obtain sensitive credentials and escalate privileges due to improper validation of jq filters. | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_18486] · [mcp-cve-project][link_mcp_cve_project_cve_2026_18486] |
| CVE-2026-18484 | IBM ContextForge MCP Gateway 1.0.0 through 1.0.11: improper slug normalization lets an authenticated remote attacker collide tool names and cause a denial of service. | Insufficient Authentication & Authorization | ≥ 1.1.0 | [NVD][link_nvd_cve_2026_18484] · [IBM][link_ibm_cve_2026_18484] |
| CVE-2026-18482 | Neo.mjs contains a command injection vulnerability within the FileSystemService.mjs component of the ai/mcp/server/file-system MCP server, where the c | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_18482] · [mcp-cve-project][link_mcp_cve_project_cve_2026_18482] |
| CVE-2026-17626 | IBM Langflow OSS 1.0.0 through 1.10.3 Langflow could allow an authenticated attacker to read, modify, or expose sensitive host files via Docker-based | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_17626] · [mcp-cve-project][link_mcp_cve_project_cve_2026_17626] |
| CVE-2026-17623 | IBM Langflow OSS 1.0.0 through 1.10.3 could allow a remote authenticated attacker to execute arbitrary commands due to improper validation of the comm | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_17623] · [mcp-cve-project][link_mcp_cve_project_cve_2026_17623] |
| CVE-2026-17433 | A vulnerability was detected in nanocoai NanoClaw up to 2.0.64 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_17433] · [mcp-cve-project][link_mcp_cve_project_cve_2026_17433] |
| CVE-2026-16584 | Improper handling of an initialization failure in AWS API MCP Server from 0.2.13 through 1.3.46 might allow an actor to bypass the user-configured sec | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_16584] · [mcp-cve-project][link_mcp_cve_project_cve_2026_16584] |
| CVE-2026-16496 | The terraform-mcp-server before version 1.1.0 is vulnerable to an authorization bypass in the streamable-HTTP stateful transport mode that may allow a | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_16496] · [mcp-cve-project][link_mcp_cve_project_cve_2026_16496] |
| CVE-2026-16133 | A flaw has been found in LiuMengxuan04 MiniCode 0.1.0 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_16133] · [mcp-cve-project][link_mcp_cve_project_cve_2026_16133] |
| CVE-2026-15988 | The AI Engine – The Chatbot, AI Framework & MCP for WordPress plugin for WordPress is vulnerable to Cross-Site Request Forgery in all versions up to, | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_15988] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15988] |
| CVE-2026-15829 | A SQL injection (CWE-89) and security boundary bypass (CWE-863) vulnerability exists in the prebuilt BigQuery forecasting tool (bigquery-forecast) of | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_15829] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15829] |
| CVE-2026-15751 | A security vulnerability has been detected in mastergo-design mastergo-magic-mcp up to 0.2.0 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_15751] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15751] |
| CVE-2026-15750 | A weakness has been identified in mastergo-design mastergo-magic-mcp up to 0.2.0 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_15750] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15750] |
| CVE-2026-15749 | A security flaw has been discovered in mastergo-design mastergo-magic-mcp up to 0.2.0 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_15749] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15749] |
| CVE-2026-15643 | AWS HealthLake MCP Server (awslabs.healthlake-mcp-server) is a Model Context Protocol server that enables AI assistants to interact with AWS HealthLak | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_15643] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15643] |
| CVE-2026-15583 | A confused-deputy flaw in Grafana MCP Server allows an unauthenticated remote attacker to exfiltrate the server's environment-configured Grafana servi | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_15583] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15583] |
| CVE-2026-15501 | A security vulnerability has been detected in AstrBotDevs AstrBot up to 4.25.2 | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_15501] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15501] |
| CVE-2026-15415 | AWS HealthOmics is a HIPAA-eligible service that fully manages the compute, storage, and workflow engine infrastructure required to run bioinformatics | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_15415] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15415] |
| CVE-2026-15189 | A security vulnerability has been detected in aerostackdev aerostack-mcp up to 6315dfde7df0a15aaf743f88d91347115e09ba23 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_15189] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15189] |
| CVE-2026-15138 | A security vulnerability has been detected in tumf mcp-text-editor up to 1.0.2 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_15138] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15138] |
| CVE-2026-15015 | The MountDev AI MCP Connector for WordPress plugin for WordPress is vulnerable to authorization bypass in all versions up to, and including, 1.6.1 | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_15015] · [mcp-cve-project][link_mcp_cve_project_cve_2026_15015] |
| CVE-2026-14748 | A flaw has been found in AIAnytime Awesome-MCP-Server up to a884bb51bcd99e08e14fd712c749d55d9d9a13ab | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_14748] · [mcp-cve-project][link_mcp_cve_project_cve_2026_14748] |
| CVE-2026-14541 | An authentication bypass and audience confusion vulnerability exists in the Google OAuth provider component of Google mcp-toolbox version 1.4.0 | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_14541] · [mcp-cve-project][link_mcp_cve_project_cve_2026_14541] |
| CVE-2026-14540 | A Server-Side Request Forgery (SSRF) vulnerability exists in the generic HTTP source and tool components of Google mcp-toolbox versions 0.3.0 through | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_14540] · [mcp-cve-project][link_mcp_cve_project_cve_2026_14540] |
| CVE-2026-14539 | An allocation of resources without limits vulnerability in the HTTP handler component of Google mcp-toolbox versions up to and including 1.4.0 allows | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_14539] · [mcp-cve-project][link_mcp_cve_project_cve_2026_14539] |
| CVE-2026-14538 | An improper authorization and security-boundary bypass vulnerability in the bigquery-execute-sql tool component of Google mcp-toolbox versions 0.16.1 | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_14538] · [mcp-cve-project][link_mcp_cve_project_cve_2026_14538] |
| CVE-2026-14537 | Incorrect Authorization in the direct HTTP API tool invocation endpoint in Google mcp-toolbox versions v1.3.0 and v1.4.0 allows an unauthenticated att | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_14537] · [mcp-cve-project][link_mcp_cve_project_cve_2026_14537] |
| CVE-2026-14471 | Improper Neutralization of Special Elements in the metrics-service retention policy management component in Amazon mcp-gateway-registry before 1.0.13 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_14471] · [mcp-cve-project][link_mcp_cve_project_cve_2026_14471] |
| CVE-2026-13524 | Cherry Studio MCP OAuth local callback issue | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_13524] · [mcp-cve-project][link_mcp_cve_project_cve_2026_13524] |
| CVE-2026-13489 | xiaozhi-esp32 MCP response handler validation issue | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_13489] · [mcp-cve-project][link_mcp_cve_project_cve_2026_13489] |
| CVE-2026-13341 | Kong Konnect MCP server (`mcp-konnect`) indirect prompt injection | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_13341] · [mcp-cve-project][link_mcp_cve_project_cve_2026_13341] |
| CVE-2026-12958 | Amazon Q Developer / Language Servers for AWS (symlink write outside workspace trust boundary) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_12958] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12958] |
| CVE-2026-12957 | Amazon Q Developer / Language Servers for AWS (`.amazonq/mcp.json` auto-execution) | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_12957] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12957] |
| CVE-2026-12940 | IBM Langflow OSS 1.0.0 through 1.10.1 are vulnerable to unauthenticated remote code execution via environment variable injection in the MCP (Model Con | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_12940] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12940] |
| CVE-2026-12798 | LiteLLM OpenAPI-to-MCP generator SSRF | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_12798] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12798] |
| CVE-2026-12774 | LiteLLM MCP connection testing SSRF | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_12774] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12774] |
| CVE-2026-12773 | LiteLLM MCP Proxy improper authentication | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_12773] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12773] |
| CVE-2026-12763 | IBM Langflow OSS 1.0.0 through 1.11.5 could allow an authenticated attacker to access another user's MCP server context due to improper cache key isolation in the MCP Tools component. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_12763] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12763] |
| CVE-2026-12537 | Google Gemini CLI / `run-gemini-cli` GitHub Action | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_12537] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12537] |
| CVE-2026-12112 | foreman-mcp-server session hijack via non-secret session IDs | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_12112] · [mcp-cve-project][link_mcp_cve_project_cve_2026_12112] |
| CVE-2026-11719 | MCP Toolbox for Databases protocol-version scope bypass | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_11719] · [mcp-cve-project][link_mcp_cve_project_cve_2026_11719] |
| CVE-2026-11624 | MCP Origin/Host validation gap for DNS rebinding controls | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_11624] · [mcp-cve-project][link_mcp_cve_project_cve_2026_11624] |
| CVE-2026-10789 | Autodesk Fusion Desktop MCP extension arbitrary code execution | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_10789] · [mcp-cve-project][link_mcp_cve_project_cve_2026_10789] |
| CVE-2026-10750 | The Royal MCP WordPress plugin before 1.4.26 does not perform capability checks on the majority of its MCP tools after token authentication, allowing | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_10750] · [mcp-cve-project][link_mcp_cve_project_cve_2026_10750] |
| CVE-2026-10280 | mcpilot MCP API call endpoint SSRF via serverBaseUrl | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_10280] · [mcp-cve-project][link_mcp_cve_project_cve_2026_10280] |
| CVE-2026-10277 | mcp-google-workspace Gmail saveToDisk improper access controls | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_10277] · [mcp-cve-project][link_mcp_cve_project_cve_2026_10277] |
| CVE-2026-9810 | The AI Copilot WordPress plugin before 1.5.4 does not bind OAuth access tokens to a WordPress user, and accepts any valid token as an administrator se | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_9810] · [mcp-cve-project][link_mcp_cve_project_cve_2026_9810] |
| CVE-2026-9739 | Vulnerable to DNS rebinding attacks when using SSE ([http://b/499408790](http://b/499408790)). | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_9739] · [mcp-cve-project][link_mcp_cve_project_cve_2026_9739] |
| CVE-2026-9680 | Improper exposure of the MCP server in alibabacloud-rds-openapi-mcp-server allows remote attackers to invoke exposed MCP tools via network access to a | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_9680] · [mcp-cve-project][link_mcp_cve_project_cve_2026_9680] |
| CVE-2026-9467 | debugmcp mcp-debugger up to 0.20.0. Impacted is the function handleGetSourceContext of the file src/server.ts. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_9467] · [mcp-cve-project][link_mcp_cve_project_cve_2026_9467] |
| CVE-2026-9186 | IBM Langflow OSS 1.0.0 through 1.11.2 allows remote authenticated attackers to bypass localhost-only MCP configuration installation by spoofing X-Forwarded-For: 127.0.0.1 header, enabling arbitrary writes to IDE config f | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_9186] · [mcp-cve-project][link_mcp_cve_project_cve_2026_9186] |
| CVE-2026-9135 | IBM Langflow OSS 1.0.0 through 1.10.0 Langflow versions up to 1.9.2 (commit 94981c443d4918517b9e8163d70fc598dc33a32d) contain a code injection vulnera | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_9135] · [mcp-cve-project][link_mcp_cve_project_cve_2026_9135] |
| CVE-2026-9077 | IBM Langflow OSS 1.0.0 through 1.10.3 Langflow allows remote authenticated attackers to bypass localhost-only restrictions and write arbitrary MCP ser | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_9077] · [mcp-cve-project][link_mcp_cve_project_cve_2026_9077] |
| CVE-2026-8719 | The AI Engine – The Chatbot, AI Framework & MCP for WordPress plugin for WordPress is vulnerable to Privilege Escalation in version 3.4.9. | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_8719] · [mcp-cve-project][link_mcp_cve_project_cve_2026_8719] |
| CVE-2026-8446 | IBM Langflow OSS 1.0.0 through 1.10.3 contain an authentication bypass vulnerability in the Model Context Protocol (MCP) composer endpoint when mcp_co | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_8446] · [mcp-cve-project][link_mcp_cve_project_cve_2026_8446] |
| CVE-2026-8355 | IBM ContextForge MCP Gateway 0.1.0 through 1.0.5 is vulnerable to a server-side request Forgery (SSRF) that allows authenticated users with gateway creation privileges to perform arbitrary HTTP POST requests to internal network resources and cloud metadata endpoints. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_8355] · [mcp-cve-project][link_mcp_cve_project_cve_2026_8355] |
| CVE-2026-7812 | 54yyyu code-mcp up to 4cfc4643541a110c906d93635b391bf7e357f4a8. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7812] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7812] |
| CVE-2026-7811 | 54yyyu code-mcp up to 4cfc4643541a110c906d93635b391bf7e357f4a8. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7811] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7811] |
| CVE-2026-7788 | Axle-Bucamp MCP-Docusaurus up to 404bc028e15ec304c9a045528560f4b5f27a17e0. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7788] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7788] |
| CVE-2026-7755 | IBM Langflow OSS 1.0.0 through 1.10.0 Langflow could allow remote code execution due to incomplete validation enforcement on MCP server configuration | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2026_7755] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7755] |
| CVE-2026-7738 | doc-tools-mcp | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7738] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7738] |
| CVE-2026-7730 | `privsim/mcp-test-runner` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7730] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7730] |
| CVE-2026-7729 | directus-mcp | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7729] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7729] |
| CVE-2026-7728 | mcp-rtfm | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7728] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7728] |
| CVE-2026-7715 | mcp-server-arangodb | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7715] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7715] |
| CVE-2026-7664 | IBM Langflow Streamable MCP authorization bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_7664] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7664] |
| CVE-2026-7663 | IBM Langflow Streamable MCP authorization bypass | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_7663] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7663] |
| CVE-2026-7653 | mcp-server-rijksmuseum | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7653] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7653] |
| CVE-2026-7646 | IBM Langflow OSS 1.0.0 through 1.10.3 allows users to read arbitrary files from the server filesystem, including other users' uploaded documents, the | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2026_7646] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7646] |
| CVE-2026-7645 | ruvnet sublinear-time-solver 1.5.0. Affected by this vulnerability is the function export_state of the file src/consciousness-explorer/mcp/server.js of the component MCP Interface. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7645] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7645] |
| CVE-2026-7642 | pskill9 website-downloader up to 0.1.0. This affects the function download_website of the file src/index.ts of the component MCP Interface. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7642] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7642] |
| CVE-2026-7628 | mcp-code-review-server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7628] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7628] |
| CVE-2026-7627 | metatrader-4-mcp | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7627] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7627] |
| CVE-2026-7600 | mcp-server-yii2 | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7600] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7600] |
| CVE-2026-7599 | terminalcraft | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7599] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7599] |
| CVE-2026-7594 | DungeonMind-MCP | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7594] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7594] |
| CVE-2026-7593 | command-executor-mcp-server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7593] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7593] |
| CVE-2026-7591 | `astro-mcp-server` (TimBroddin) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7591] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7591] |
| CVE-2026-7446 | mcp-server-semgrep | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7446] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7446] |
| CVE-2026-7445 | ZachHandley ZMCPTools up to 0.2.2. Affected by this issue is some unknown functionality of the file src/managers/ResourceManager.ts of the component MCP Log Resource Handler. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7445] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7445] |
| CVE-2026-7443 | mcp-dnstwist | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7443] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7443] |
| CVE-2026-7417 | Algovate `xhs-mcp` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7417] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7417] |
| CVE-2026-7416 | PolarVista xcode-mcp-server 1.0.0. This issue affects the function build_project/run_tests of the file src/index.ts of the component MCP Interface. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7416] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7416] |
| CVE-2026-7404 | A weakness has been identified in getsimpletool mcpo-simple-server up to 0.2.0. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7404] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7404] |
| CVE-2026-7386 | mail-mcp-bridge | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7386] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7386] |
| CVE-2026-7384 | mcp-bases: `search_papers` in `research_server.py` uses the `topic` argument as a path and does not confine it (path traversal). | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7384] |
| CVE-2026-7318 | elie mcp-project 0.1.0. The affected element is the function search_papers of the file research_server.py. | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7318] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7318] |
| CVE-2026-7272 | matlab-mcp-server | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_7272] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7272] |
| CVE-2026-7237 | scaffold-mcp | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7237] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7237] |
| CVE-2026-7221 | TencentCloudBase CloudBase-MCP | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7221] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7221] |
| CVE-2026-7215 | egtai gmx-vmd-mcp up to 0.1.0. This issue affects the function launch_vmd_gui_tool of the file mcp_server.py of the component VMD Launch Handler. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7215] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7215] |
| CVE-2026-7211 | A weakness has been identified in dvladimirov MCP up to 0.1.0. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_7211] · [mcp-cve-project][link_mcp_cve_project_cve_2026_7211] |
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
| CVE-2026-6130 | Chatbox StdioClientTransport MCP config args/env code execution | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2026_6130] · [mcp-cve-project][link_mcp_cve_project_cve_2026_6130] |
| CVE-2026-6118 | AstrBotDevs AstrBot up to 4.22.1. Impacted is the function add_mcp_server of the file astrbot/dashboard/routes/tools.py of the component MCP Endpoint. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_6118] · [mcp-cve-project][link_mcp_cve_project_cve_2026_6118] |
| CVE-2026-6108 | MaxKB MCP node OS command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_6108] · [mcp-cve-project][link_mcp_cve_project_cve_2026_6108] |
| CVE-2026-5833 | mcp-server-taskwarrior | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5833] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5833] |
| CVE-2026-5802 | idachev mcp-javadc up to 1.2.4. Impacted is an unknown function of the component HTTP Interface. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5802] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5802] |
| CVE-2026-5619 | Braffolk mcp-summarization-functions up to 0.1.5. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5619] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5619] |
| CVE-2026-5607 | imprvhub `mcp-browser-agent` | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5607] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5607] |
| CVE-2026-5470 | Google-Research-MCP (SSRF in `extractContent`) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5470] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5470] |
| CVE-2026-5379 | allowed MCP agents to access certificate information from outside of their authorized organization scope has been resolved. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_5379] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5379] |
| CVE-2026-5374 | allowed MCP agents to access remediation and asset information from outside of the authorized organization scope has been resolved. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_5374] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5374] |
| CVE-2026-5323 | a11y-mcp | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5323] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5323] |
| CVE-2026-5322 | AlejandroArciniegas mcp-data-vis bc597e391f184d2187062fd567599a3cb72adf51/de5a51525a69822290eaee569a1ab447b490746d. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_5322] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5322] |
| CVE-2026-5059 | `aws-mcp` / aws-mcp-server (command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5059] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5059] |
| CVE-2026-5058 | `aws-mcp` / aws-mcp-server (unauthenticated command injection) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_5058] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5058] |
| CVE-2026-5029 | Code Runner MCP Server | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_5029] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5029] |
| CVE-2026-5023 | `codebase-mcp` (OS command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_5023] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5023] |
| CVE-2026-5007 | `mcp-docs-rag` (OS command injection) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_5007] · [mcp-cve-project][link_mcp_cve_project_cve_2026_5007] |
| CVE-2026-4593 | erupts erupt bis 1.13.3. Affected by this vulnerability is the function EruptDataQuery of the file erupt-ai/src/main/java/xyz/erupt/ai/call/impl/EruptDataQuery.java of the component MCP Tool Interface. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_4593] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4593] |
| CVE-2026-4496 | Git-MCP-Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_4496] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4496] |
| CVE-2026-4339 | Mattermost Agents plugin MCP server internal/private IP validation issue | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_4339] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4339] |
| CVE-2026-4270 | AWS API MCP Server (`awslabs/mcp`):`awslabs.aws-api-mcp-server` (pip) | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2026_4270] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4270] |
| CVE-2026-4199 | bazinga012 mcp_code_executor up to 0.3.0. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_4199] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4199] |
| CVE-2026-4198 | mcp-server-auto-commit | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_4198] · [mcp-cve-project][link_mcp_cve_project_cve_2026_4198] |
| CVE-2026-2178 | `xcode-mcp-server` (command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_2178] · [mcp-cve-project][link_mcp_cve_project_cve_2026_2178] |
| CVE-2026-2130 | BurtTheCoder mcp-maigret up to 1.0.12. This affects an unknown part of the file src/index.ts of the component search_username. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_2130] · [mcp-cve-project][link_mcp_cve_project_cve_2026_2130] |
| CVE-2026-1977 | isaacwasserman mcp-vegalite-server up to 16aefed598b8cd897b78e99b907f6e2984572c61. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_1977] · [mcp-cve-project][link_mcp_cve_project_cve_2026_1977] |
| CVE-2026-1721 | Cloudflare `agents` SDK AI Playground OAuth callback | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_1721] · [mcp-cve-project][link_mcp_cve_project_cve_2026_1721] |
| CVE-2026-0758 | mcp-server-siri-shortcuts | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_0758] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0758] |
| CVE-2026-0757 | MCP Manager for Claude Desktop | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_0757] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0757] |
| CVE-2026-0756 | `github-kanban-mcp-server` (unauthenticated RCE / command injection) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2026_0756] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0756] |
| CVE-2026-0755 | `gemini-mcp-tool` (command injection via unsafe shell execution) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2026_0755] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0755] |
| CVE-2026-0621 | MCP TypeScript SDK (`UriTemplate` ReDoS) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2026_0621] · [mcp-cve-project][link_mcp_cve_project_cve_2026_0621] |
| CVE-2025-71427 | Office-PowerPoint-MCP-Server through 2.0.7 contains a path traversal vulnerability that allows MCP callers to write and read files outside the working directory by supplying absolute paths or ../ sequences. | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2025_71427] · [mcp-cve-project][link_mcp_cve_project_cve_2025_71427] |
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
| CVE-2025-61489 | A command injection vulnerability in the shell_exec function of sonirico mcp-shell v0.3.1 allows attackers to execute arbitrary commands via supplying a crafted command string. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_61489] · [mcp-cve-project][link_mcp_cve_project_cve_2025_61489] |
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
| CVE-2025-55346 | Flowise unsafe dynamic Function constructor remote code execution | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_55346] · [mcp-cve-project][link_mcp_cve_project_cve_2025_55346] |
| CVE-2025-54994 | `@akoskm/create-mcp-server-stdio` (`which-app-on-port` command injection via unsafe `exec`; also cited in OX supply-chain advisory) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_54994] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54994] |
| CVE-2025-54424 | 1Panel MCP Server | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_54424] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54424] |
| CVE-2025-54382 | Cherry Studio | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_54382] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54382] |
| CVE-2025-54136 | Cursor (MCP JSON / stdio exposure) | Software Supply Chain Attacks & Dependency Tampering | See NVD | [NVD][link_nvd_cve_2025_54136] · [mcp-cve-project][link_mcp_cve_project_cve_2025_54136] · [GHSA][link_ghsa_24mc_g4xr_4395] |
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
| CVE-2025-53107 | `@cyanheads/git-mcp-server` (npm) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53107] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53107] · [GHSA][link_ghsa_3q26_f695_pp76] |
| CVE-2025-53100 | RestDB Codehooks.io MCP Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_53100] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53100] |
| CVE-2025-53098 | Roo Code workspace `.roo/mcp.json` project MCP configuration code execution | Shadow MCP Servers | See NVD | [NVD][link_nvd_cve_2025_53098] · [mcp-cve-project][link_mcp_cve_project_cve_2025_53098] |
| CVE-2025-52573 | iOS Simulator MCP Server (`ios-simulator-mcp`) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_52573] · [mcp-cve-project][link_mcp_cve_project_cve_2025_52573] |
| CVE-2025-49596 | MCP Inspector (`@modelcontextprotocol/inspector`) | Command Injection & Execution | ≥ 0.14.1 | [NVD][link_nvd_cve_2025_49596] · [mcp-cve-project][link_mcp_cve_project_cve_2025_49596] · [GHSA][link_ghsa_7f8r_222p_6f5g] |
| CVE-2025-47777 | 5ire MCP client (stored XSS → RCE) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_47777] · [mcp-cve-project][link_mcp_cve_project_cve_2025_47777] |
| CVE-2025-47274 | Stacklok ToolHive | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2025_47274] · [mcp-cve-project][link_mcp_cve_project_cve_2025_47274] |
| CVE-2025-35028 | HexStrike AI MCP server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_35028] · [mcp-cve-project][link_mcp_cve_project_cve_2025_35028] |
| CVE-2025-34072 | `@modelcontextprotocol/server-slack` (Slack link-unfurl data exfiltration) | Context Injection & Over-Sharing | See NVD | [NVD][link_nvd_cve_2025_34072] · [mcp-cve-project][link_mcp_cve_project_cve_2025_34072] |
| CVE-2025-20381 | Splunk MCP Server app | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_20381] · [mcp-cve-project][link_mcp_cve_project_cve_2025_20381] |
| CVE-2025-15063 | Ollama MCP Server (`execAsync` command injection) | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_15063] · [mcp-cve-project][link_mcp_cve_project_cve_2025_15063] |
| CVE-2025-15061 | Framelink Figma MCP Server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_15061] · [mcp-cve-project][link_mcp_cve_project_cve_2025_15061] |
| CVE-2025-13822 | MCPHub in versions below 0.11.0 is vulnerable to authentication bypass. | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_13822] · [mcp-cve-project][link_mcp_cve_project_cve_2025_13822] |
| CVE-2025-11445 | Kilo Code (AI agent IDE; `ClineProvider` / Prompt Handler) | Prompt Injection via Contextual Payloads | See NVD | [NVD][link_nvd_cve_2025_11445] · [mcp-cve-project][link_mcp_cve_project_cve_2025_11445] |
| CVE-2025-11286 | samanhappy MCPHub | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_11286] · [mcp-cve-project][link_mcp_cve_project_cve_2025_11286] |
| CVE-2025-11285 | MCPHub through 0.9.10: `serverController.ts` passes the `command` and `args` fields to the operating system without sanitizing them. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_11285] |
| CVE-2025-10619 | sequa-ai `sequa-mcp` (OAuth redirect issue) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_10619] · [mcp-cve-project][link_mcp_cve_project_cve_2025_10619] |
| CVE-2025-10193 | Neo4j MCP Cypher server (`mcp-neo4j-cypher`) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_10193] · [mcp-cve-project][link_mcp_cve_project_cve_2025_10193] |
| CVE-2025-9654 | mcp-ssh command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_9654] · [mcp-cve-project][link_mcp_cve_project_cve_2025_9654] |
| CVE-2025-9611 | Microsoft Playwright MCP Server (`@playwright/mcp`):`@playwright/mcp` (npm) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_9611] · [mcp-cve-project][link_mcp_cve_project_cve_2025_9611] |
| CVE-2025-9262 | wong2 mcp-cli 1.13.0: `redirectToAuthorization` in the OAuth handler can be turned into an operating-system command. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_9262] |
| CVE-2025-8943 | Flowise Custom MCPs | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_8943] · [mcp-cve-project][link_mcp_cve_project_cve_2025_8943] |
| CVE-2025-8697 | agentUniverse through 0.0.18: `StdioServerParameters` in MCPSessionManager, MCPTool, and MCPToolkit passes through a command that the process then executes. | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_8697] |
| CVE-2025-8665 | agno MCPTools/MultiMCPTools command injection | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_8665] · [mcp-cve-project][link_mcp_cve_project_cve_2025_8665] |
| CVE-2025-6515 | `oatpp-mcp` (oatpp MCP SSE endpoint) | Token Mismanagement & Secret Exposure | See NVD | [NVD][link_nvd_cve_2025_6515] · [mcp-cve-project][link_mcp_cve_project_cve_2025_6515] |
| CVE-2025-6514 | `mcp-remote` (npm) | Token Mismanagement & Secret Exposure | ≥ 0.1.16 | [NVD][link_nvd_cve_2025_6514] · [mcp-cve-project][link_mcp_cve_project_cve_2025_6514] · [GHSA][link_ghsa_6xpm_ggf7_wc3p] |
| CVE-2025-5277 | aws-mcp-server | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_5277] · [mcp-cve-project][link_mcp_cve_project_cve_2025_5277] |
| CVE-2025-5276 | mcp-markdownify-server SSRF via Markdownify.get() | Command Injection & Execution | See NVD | [NVD][link_nvd_cve_2025_5276] · [mcp-cve-project][link_mcp_cve_project_cve_2025_5276] |
| CVE-2025-5273 | mcp-markdownify-server path traversal via get-markdown-file | Privilege Escalation via Scope Creep | See NVD | [NVD][link_nvd_cve_2025_5273] · [mcp-cve-project][link_mcp_cve_project_cve_2025_5273] |
| CVE-2025-4143 | Cloudflare `workers-mcp` (OAuth implementation flaw) | Insufficient Authentication & Authorization | See NVD | [NVD][link_nvd_cve_2025_4143] · [mcp-cve-project][link_mcp_cve_project_cve_2025_4143] |

## GitHub advisories without a CVE

**37** GitHub Security Advisories from [mcp-cve-project](https://github.com/mcp-security-project/mcp-cve-project) that do not have a CVE ID, as of **catalog synced: 2026-11-10**. Sorted by disclosure date (newest first).

| Advisory | Affected component | Issue (OWASP MCP Top 10 category) | Fixed in | Links |
| --- | --- | --- | --- | --- |
| GHSA-c9f9-cp8h-jcj5 | Rust SDK rmcp: Streamable HTTP clients buffer response bodies with no size limit. | Insufficient Authentication & Authorization | ≥ 3.9.0 | [GHSA][link_ghsa_c9f9_cp8h_jcj5] · [mcp-cve-project][link_mcp_cve_project_ghsa_c9f9_cp8h_jcj5] |
| GHSA-h9j8-vj8g-v3gg | MCP Inspector: MCP app escapes its CSP by navigating its own frame. | Insufficient Authentication & Authorization | ≥ 2.14.0 | [GHSA][link_ghsa_h9j8_vj8g_v3gg] · [mcp-cve-project][link_mcp_cve_project_ghsa_h9j8_vj8g_v3gg] |
| GHSA-rwv7-mh2c-ff2p | MCP Inspector: server.json import splices unvalidated runtime arguments into the stdio command. | Command Injection & Execution | ≥ 2.14.0 | [GHSA][link_ghsa_rwv7_mh2c_ff2p] · [mcp-cve-project][link_mcp_cve_project_ghsa_rwv7_mh2c_ff2p] |
| GHSA-2fw8-7jmw-r937 | MCP Inspector can stall on a malicious tool output schema regex. | Insufficient Authentication & Authorization | See advisory | [GHSA][link_ghsa_2fw8_7jmw_r937] · [mcp-cve-project][link_mcp_cve_project_ghsa_2fw8_7jmw_r937] |
| GHSA-x863-g495-4cjc | C# SDK: Missing user-id claims collapse principals and allow session hijacking. | Insufficient Authentication & Authorization | See advisory | [GHSA][link_ghsa_x863_g495_4cjc] · [mcp-cve-project][link_mcp_cve_project_ghsa_x863_g495_4cjc] |
| GHSA-w766-5x43-whvw | mcp-server-git: Nested gitdir file bypasses --repository confinement. | Insufficient Authentication & Authorization | ≥ 2026.10.28 | [GHSA][link_ghsa_w766_5x43_whvw] · [mcp-cve-project][link_mcp_cve_project_ghsa_w766_5x43_whvw] |
| GHSA-f897-62hf-6gxq | @modelcontextprotocol/sdk: MCP TypeScript SDK: HTTP server transports and handlers did not limit request body size or JSON-RPC batch length | Insufficient Authentication & Authorization | See advisory | [GHSA][link_ghsa_f897_62hf_6gxq] · [mcp-cve-project][link_mcp_cve_project_ghsa_f897_62hf_6gxq] |
| GHSA-3jqg-r5pp-rmp2 | robots.txt enforcement bypass via HTTP redirects in mcp-server-fetch | Insufficient Authentication & Authorization | ≥ 2026.10.24 | [GHSA][link_ghsa_3jqg_r5pp_rmp2] · [mcp-cve-project][link_mcp_cve_project_ghsa_3jqg_r5pp_rmp2] |
| GHSA-4gxg-m5jx-9j57 | server-filesystem: Case-variant path bypasses the symlink check. | Insufficient Authentication & Authorization | ≥ 2.0.1 | [GHSA][link_ghsa_4gxg_m5jx_9j57] · [mcp-cve-project][link_mcp_cve_project_ghsa_4gxg_m5jx_9j57] |
| GHSA-53mr-w429-c597 | server-filesystem: Parent-directory fallback race permits writes outside allowed directories. | Insufficient Authentication & Authorization | ≥ 2.0.1 | [GHSA][link_ghsa_53mr_w429_c597] · [mcp-cve-project][link_mcp_cve_project_ghsa_53mr_w429_c597] |
| GHSA-66qx-2266-pmj6 | mcp-server-fetch: SSRF guard treats NAT64 prefix 64:ff9b::/96 as public. | Command Injection & Execution | ≥ 2026.10.24 | [GHSA][link_ghsa_66qx_2266_pmj6] · [mcp-cve-project][link_mcp_cve_project_ghsa_66qx_2266_pmj6] |
| GHSA-7rgq-gccq-qphx | server-filesystem: Path traversal via trailing quote or whitespace in validatePath. | Privilege Escalation via Scope Creep | ≥ 2.0.1 | [GHSA][link_ghsa_7rgq_gccq_qphx] · [mcp-cve-project][link_mcp_cve_project_ghsa_7rgq_gccq_qphx] |
| GHSA-hhwq-wxfx-cj7g | server-filesystem: list_directory_with_sizes follows symlinks and leaks metadata. | Insufficient Authentication & Authorization | ≥ 2.0.1 | [GHSA][link_ghsa_hhwq_wxfx_cj7g] · [mcp-cve-project][link_mcp_cve_project_ghsa_hhwq_wxfx_cj7g] |
| GHSA-mvf5-2qqv-rg3c | server-everything: Cross-origin environment variable exfiltration. | Insufficient Authentication & Authorization | ≥ 2.0.1 | [GHSA][link_ghsa_mvf5_2qqv_rg3c] · [mcp-cve-project][link_mcp_cve_project_ghsa_mvf5_2qqv_rg3c] |
| GHSA-v38p-wf49-hx2j | mcp-server-fetch: Private-address guard bypass via IDNA hostnames. | Insufficient Authentication & Authorization | ≥ 2026.10.24 | [GHSA][link_ghsa_v38p_wf49_hx2j] · [mcp-cve-project][link_mcp_cve_project_ghsa_v38p_wf49_hx2j] |
| GHSA-5p52-q7pq-9fq2 | Rust SDK rmcp: OAuth SSRF filter checks host strings, not resolved addresses. | Command Injection & Execution | ≥ 3.7.0 | [GHSA][link_ghsa_5p52_q7pq_9fq2] · [mcp-cve-project][link_mcp_cve_project_ghsa_5p52_q7pq_9fq2] |
| GHSA-2rq8-f55p-j2jp | MCP Inspector leaks proxy session token to query-controlled proxy origin | Token Mismanagement & Secret Exposure | ≥ 1.0.3 | [GHSA][link_ghsa_2rq8_f55p_j2jp] · [mcp-cve-project][link_mcp_cve_project_ghsa_2rq8_f55p_j2jp] |
| GHSA-4fc4-wcmh-4g86 | MCP Inspector: OAuth callback can switch transport to stdio and run local commands. | Command Injection & Execution | ≥ 1.0.3 | [GHSA][link_ghsa_4fc4_wcmh_4g86] · [mcp-cve-project][link_mcp_cve_project_ghsa_4fc4_wcmh_4g86] |
| GHSA-6x67-4w4w-9f3w | MCP Inspector: Remote MCP app can steal the proxy auth token and run local commands. | Command Injection & Execution | ≥ 1.0.3 | [GHSA][link_ghsa_6x67_4w4w_9f3w] · [mcp-cve-project][link_mcp_cve_project_ghsa_6x67_4w4w_9f3w] |
| GHSA-8qgq-27v6-55w3 | MCP Inspector: SSE auth and custom headers are logged verbatim. | Insufficient Authentication & Authorization | ≥ 1.0.3 | [GHSA][link_ghsa_8qgq_27v6_55w3] · [mcp-cve-project][link_mcp_cve_project_ghsa_8qgq_27v6_55w3] |
| GHSA-f6mc-jg3x-vq53 | MCP Inspector: Fetch proxy leaks Authorization and Cookie headers across cross-origin redirects. | Token Mismanagement & Secret Exposure | ≥ 1.0.3 | [GHSA][link_ghsa_f6mc_jg3x_vq53] · [mcp-cve-project][link_mcp_cve_project_ghsa_f6mc_jg3x_vq53] |
| GHSA-m5pj-3536-3xcp | MCP Inspector: /api/fetch proxy has no response-body size cap. | Insufficient Authentication & Authorization | See advisory | [GHSA][link_ghsa_m5pj_3536_3xcp] · [mcp-cve-project][link_mcp_cve_project_ghsa_m5pj_3536_3xcp] |
| GHSA-q978-78c7-phqw | MCP Inspector: OAuth authorization URL runs PowerShell on Windows and WSL. Related CVE-2026-119025 is on the open package. | Token Mismanagement & Secret Exposure | ≥ 2.12.0 | [GHSA][link_ghsa_q978_78c7_phqw] · [mcp-cve-project][link_mcp_cve_project_ghsa_q978_78c7_phqw] |
| GHSA-vcc9-3xgm-p9v4 | MCP Inspector: Incomplete fix for CVE-2025-49596: DNS rebinding discloses API and OAuth tokens. | Token Mismanagement & Secret Exposure | ≥ 2.12.0 | [GHSA][link_ghsa_vcc9_3xgm_p9v4] · [mcp-cve-project][link_mcp_cve_project_ghsa_vcc9_3xgm_p9v4] |
| GHSA-wmjf-2m46-2352 | MCP Inspector: Missing authentication for a critical function. | Insufficient Authentication & Authorization | ≥ 1.0.3 | [GHSA][link_ghsa_wmjf_2m46_2352] · [mcp-cve-project][link_mcp_cve_project_ghsa_wmjf_2m46_2352] |
| GHSA-2hm9-qff2-hrpj | Unbounded session retention in the Streamable HTTP transport allows an initialize flood DoS | Insufficient Authentication & Authorization | See advisory | [GHSA][link_ghsa_2hm9_qff2_hrpj] · [mcp-cve-project][link_mcp_cve_project_ghsa_2hm9_qff2_hrpj] |
| GHSA-4432-vg92-fqh6 | Rust SDK rmcp: Unbounded tool schema cache in Streamable HTTP server. | Insufficient Authentication & Authorization | ≥ 3.6.0 | [GHSA][link_ghsa_4432_vg92_fqh6] · [mcp-cve-project][link_mcp_cve_project_ghsa_4432_vg92_fqh6] |
| GHSA-hp8w-r5wh-cw9q | Java SDK: Default stateless servlet transport accepts browser cross-origin tool calls. | Insufficient Authentication & Authorization | See advisory | [GHSA][link_ghsa_hp8w_r5wh_cw9q] · [mcp-cve-project][link_mcp_cve_project_ghsa_hp8w_r5wh_cw9q] |
| GHSA-w83x-jw8h-w4rj | Java SDK: Session dispatch returns raw handler exception messages to the peer. | Insufficient Authentication & Authorization | See advisory | [GHSA][link_ghsa_w83x_jw8h_w4rj] · [mcp-cve-project][link_mcp_cve_project_ghsa_w83x_jw8h_w4rj] |
| GHSA-c9xm-49cp-xcr9 | rmcp: rmcp OAuth client fetches server-controlled resource_metadata URLs | Command Injection & Execution | ≥ 2.0.0 | [GHSA][link_ghsa_c9xm_49cp_xcr9] · [mcp-cve-project][link_mcp_cve_project_ghsa_c9xm_49cp_xcr9] |
| GHSA-5648-rgj9-v224 | GitLab MCP safety-control bypasses | Privilege Escalation via Scope Creep | ≥ 2.1.30 | [GHSA][link_ghsa_5648_rgj9_v224] · [mcp-cve-project][link_mcp_cve_project_ghsa_5648_rgj9_v224] |
| GHSA-7fx6-5m9f-89wg | MCP specification repository: Shell command injection in the manual SEP lifecycle workflow. | Command Injection & Execution | See advisory | [GHSA][link_ghsa_7fx6_5m9f_89wg] · [mcp-cve-project][link_mcp_cve_project_ghsa_7fx6_5m9f_89wg] |
| GHSA-5q7x-232h-f834 | Java SDK: Unbounded reads when parsing Server-Sent Events in HTTP client transports. | Insufficient Authentication & Authorization | See advisory | [GHSA][link_ghsa_5q7x_232h_f834] · [mcp-cve-project][link_mcp_cve_project_ghsa_5q7x_232h_f834] |
| GHSA-xhcr-cqfr-m3hv | Atomic Agents HTTP MCP catalog MITM-to-RCE | Software Supply Chain Attacks & Dependency Tampering | ≥ 1.1.0 | [GHSA][link_ghsa_xhcr_cqfr_m3hv] · [mcp-cve-project][link_mcp_cve_project_ghsa_xhcr_cqfr_m3hv] |
| GHSA-4m5j-jjfc-97gx | Ruby SDK: OAuth discovery security check allows SSRF to private hosts over HTTPS. | Command Injection & Execution | ≥ 1.2.0 | [GHSA][link_ghsa_4m5j_jjfc_97gx] · [mcp-cve-project][link_mcp_cve_project_ghsa_4m5j_jjfc_97gx] |
| GHSA-4gph-2hhr-5mwg | Envoy AI Gateway MCP message smuggling | Privilege Escalation via Scope Creep | ≥ 0.6.0 | [GHSA][link_ghsa_4gph_2hhr_5mwg] · [mcp-cve-project][link_mcp_cve_project_ghsa_4gph_2hhr_5mwg] |
| GHSA-q382-vc8q-7jhj | github.com/modelcontextprotocol/go-sdk: Improper handling of null Unicode character when parsing JSON in github.com/modelcontextprotocol/go-sdk | Insufficient Authentication & Authorization | ≥ 1.4.1 | [GHSA][link_ghsa_q382_vc8q_7jhj] · [mcp-cve-project][link_mcp_cve_project_ghsa_q382_vc8q_7jhj] |

---

[link_mcp_cve_project]: https://github.com/mcp-security-project/mcp-cve-project
[link_mcp_cve_project_commits]: https://github.com/mcp-security-project/mcp-cve-project/commits/main/
[link_opencve_modelcontextprotocol]: https://app.opencve.io/cve/?vendor=modelcontextprotocol
[link_github_advisories_mcp_search]: https://github.com/advisories?query=model+context+protocol
[link_mcp_python_sdk_advisories]: https://github.com/modelcontextprotocol/python-sdk/security/advisories
[link_mcp_typescript_sdk_advisories]: https://github.com/modelcontextprotocol/typescript-sdk/security/advisories
[link_mcp_inspector_advisories]: https://github.com/modelcontextprotocol/inspector/security/advisories
[link_pysec_mcp]: https://github.com/pypa/advisory-database/tree/main/vulns/mcp

[link_nvd_cve_2026_124503]: https://nvd.nist.gov/vuln/detail/CVE-2026-124503
[link_nvd_cve_2026_123812]: https://nvd.nist.gov/vuln/detail/CVE-2026-123812
[link_nvd_cve_2026_123811]: https://nvd.nist.gov/vuln/detail/CVE-2026-123811
[link_nvd_cve_2026_123810]: https://nvd.nist.gov/vuln/detail/CVE-2026-123810
[link_nvd_cve_2026_123809]: https://nvd.nist.gov/vuln/detail/CVE-2026-123809
[link_nvd_cve_2026_123272]: https://nvd.nist.gov/vuln/detail/CVE-2026-123272
[link_nvd_cve_2026_123271]: https://nvd.nist.gov/vuln/detail/CVE-2026-123271
[link_nvd_cve_2026_123022]: https://nvd.nist.gov/vuln/detail/CVE-2026-123022
[link_nvd_cve_2026_122140]: https://nvd.nist.gov/vuln/detail/CVE-2026-122140
[link_nvd_cve_2026_121576]: https://nvd.nist.gov/vuln/detail/CVE-2026-121576
[link_nvd_cve_2026_121458]: https://nvd.nist.gov/vuln/detail/CVE-2026-121458
[link_nvd_cve_2026_121419]: https://nvd.nist.gov/vuln/detail/CVE-2026-121419
[link_nvd_cve_2026_120492]: https://nvd.nist.gov/vuln/detail/CVE-2026-120492
[link_nvd_cve_2026_120450]: https://nvd.nist.gov/vuln/detail/CVE-2026-120450
[link_nvd_cve_2026_120338]: https://nvd.nist.gov/vuln/detail/CVE-2026-120338
[link_nvd_cve_2026_119613]: https://nvd.nist.gov/vuln/detail/CVE-2026-119613
[link_nvd_cve_2026_119025]: https://nvd.nist.gov/vuln/detail/CVE-2026-119025
[link_nvd_cve_2026_117573]: https://nvd.nist.gov/vuln/detail/CVE-2026-117573
[link_nvd_cve_2026_117569]: https://nvd.nist.gov/vuln/detail/CVE-2026-117569
[link_nvd_cve_2026_117568]: https://nvd.nist.gov/vuln/detail/CVE-2026-117568
[link_nvd_cve_2026_117567]: https://nvd.nist.gov/vuln/detail/CVE-2026-117567
[link_nvd_cve_2026_117561]: https://nvd.nist.gov/vuln/detail/CVE-2026-117561
[link_nvd_cve_2026_117558]: https://nvd.nist.gov/vuln/detail/CVE-2026-117558
[link_nvd_cve_2026_116686]: https://nvd.nist.gov/vuln/detail/CVE-2026-116686
[link_nvd_cve_2026_116685]: https://nvd.nist.gov/vuln/detail/CVE-2026-116685
[link_nvd_cve_2026_116684]: https://nvd.nist.gov/vuln/detail/CVE-2026-116684
[link_nvd_cve_2026_116635]: https://nvd.nist.gov/vuln/detail/CVE-2026-116635
[link_nvd_cve_2026_116109]: https://nvd.nist.gov/vuln/detail/CVE-2026-116109
[link_nvd_cve_2026_115845]: https://nvd.nist.gov/vuln/detail/CVE-2026-115845
[link_nvd_cve_2026_115751]: https://nvd.nist.gov/vuln/detail/CVE-2026-115751
[link_nvd_cve_2026_115563]: https://nvd.nist.gov/vuln/detail/CVE-2026-115563
[link_nvd_cve_2026_115478]: https://nvd.nist.gov/vuln/detail/CVE-2026-115478
[link_nvd_cve_2026_115477]: https://nvd.nist.gov/vuln/detail/CVE-2026-115477
[link_nvd_cve_2026_115413]: https://nvd.nist.gov/vuln/detail/CVE-2026-115413
[link_nvd_cve_2026_114612]: https://nvd.nist.gov/vuln/detail/CVE-2026-114612
[link_nvd_cve_2026_114123]: https://nvd.nist.gov/vuln/detail/CVE-2026-114123
[link_nvd_cve_2026_114090]: https://nvd.nist.gov/vuln/detail/CVE-2026-114090
[link_nvd_cve_2026_113731]: https://nvd.nist.gov/vuln/detail/CVE-2026-113731
[link_nvd_cve_2026_113378]: https://nvd.nist.gov/vuln/detail/CVE-2026-113378
[link_nvd_cve_2026_111771]: https://nvd.nist.gov/vuln/detail/CVE-2026-111771
[link_nvd_cve_2026_111770]: https://nvd.nist.gov/vuln/detail/CVE-2026-111770
[link_nvd_cve_2026_111769]: https://nvd.nist.gov/vuln/detail/CVE-2026-111769
[link_nvd_cve_2026_111768]: https://nvd.nist.gov/vuln/detail/CVE-2026-111768
[link_nvd_cve_2026_111767]: https://nvd.nist.gov/vuln/detail/CVE-2026-111767
[link_nvd_cve_2026_111091]: https://nvd.nist.gov/vuln/detail/CVE-2026-111091
[link_nvd_cve_2026_110842]: https://nvd.nist.gov/vuln/detail/CVE-2026-110842
[link_nvd_cve_2026_110616]: https://nvd.nist.gov/vuln/detail/CVE-2026-110616
[link_nvd_cve_2026_109527]: https://nvd.nist.gov/vuln/detail/CVE-2026-109527
[link_nvd_cve_2026_109402]: https://nvd.nist.gov/vuln/detail/CVE-2026-109402
[link_nvd_cve_2026_109332]: https://nvd.nist.gov/vuln/detail/CVE-2026-109332
[link_nvd_cve_2026_108953]: https://nvd.nist.gov/vuln/detail/CVE-2026-108953
[link_nvd_cve_2026_108865]: https://nvd.nist.gov/vuln/detail/CVE-2026-108865
[link_nvd_cve_2026_108859]: https://nvd.nist.gov/vuln/detail/CVE-2026-108859
[link_nvd_cve_2026_108856]: https://nvd.nist.gov/vuln/detail/CVE-2026-108856
[link_nvd_cve_2026_108851]: https://nvd.nist.gov/vuln/detail/CVE-2026-108851
[link_nvd_cve_2026_108714]: https://nvd.nist.gov/vuln/detail/CVE-2026-108714
[link_nvd_cve_2026_108671]: https://nvd.nist.gov/vuln/detail/CVE-2026-108671
[link_nvd_cve_2026_108591]: https://nvd.nist.gov/vuln/detail/CVE-2026-108591
[link_nvd_cve_2026_108586]: https://nvd.nist.gov/vuln/detail/CVE-2026-108586
[link_nvd_cve_2026_108585]: https://nvd.nist.gov/vuln/detail/CVE-2026-108585
[link_nvd_cve_2026_108582]: https://nvd.nist.gov/vuln/detail/CVE-2026-108582
[link_nvd_cve_2026_108542]: https://nvd.nist.gov/vuln/detail/CVE-2026-108542
[link_nvd_cve_2026_108395]: https://nvd.nist.gov/vuln/detail/CVE-2026-108395
[link_nvd_cve_2026_107824]: https://nvd.nist.gov/vuln/detail/CVE-2026-107824
[link_nvd_cve_2026_107820]: https://nvd.nist.gov/vuln/detail/CVE-2026-107820
[link_nvd_cve_2026_107745]: https://nvd.nist.gov/vuln/detail/CVE-2026-107745
[link_nvd_cve_2026_105761]: https://nvd.nist.gov/vuln/detail/CVE-2026-105761
[link_nvd_cve_2026_105741]: https://nvd.nist.gov/vuln/detail/CVE-2026-105741
[link_nvd_cve_2026_105740]: https://nvd.nist.gov/vuln/detail/CVE-2026-105740
[link_nvd_cve_2026_105697]: https://nvd.nist.gov/vuln/detail/CVE-2026-105697
[link_nvd_cve_2026_104850]: https://nvd.nist.gov/vuln/detail/CVE-2026-104850
[link_nvd_cve_2026_104634]: https://nvd.nist.gov/vuln/detail/CVE-2026-104634
[link_nvd_cve_2026_104120]: https://nvd.nist.gov/vuln/detail/CVE-2026-104120
[link_nvd_cve_2026_103758]: https://nvd.nist.gov/vuln/detail/CVE-2026-103758
[link_nvd_cve_2026_102943]: https://nvd.nist.gov/vuln/detail/CVE-2026-102943
[link_nvd_cve_2026_102878]: https://nvd.nist.gov/vuln/detail/CVE-2026-102878
[link_nvd_cve_2026_102610]: https://nvd.nist.gov/vuln/detail/CVE-2026-102610
[link_nvd_cve_2026_102503]: https://nvd.nist.gov/vuln/detail/CVE-2026-102503
[link_nvd_cve_2026_101084]: https://nvd.nist.gov/vuln/detail/CVE-2026-101084
[link_nvd_cve_2026_101065]: https://nvd.nist.gov/vuln/detail/CVE-2026-101065
[link_nvd_cve_2026_101064]: https://nvd.nist.gov/vuln/detail/CVE-2026-101064
[link_nvd_cve_2026_101063]: https://nvd.nist.gov/vuln/detail/CVE-2026-101063
[link_nvd_cve_2026_101062]: https://nvd.nist.gov/vuln/detail/CVE-2026-101062
[link_nvd_cve_2026_101057]: https://nvd.nist.gov/vuln/detail/CVE-2026-101057
[link_nvd_cve_2026_100868]: https://nvd.nist.gov/vuln/detail/CVE-2026-100868
[link_nvd_cve_2026_100633]: https://nvd.nist.gov/vuln/detail/CVE-2026-100633
[link_nvd_cve_2026_96620]: https://nvd.nist.gov/vuln/detail/CVE-2026-96620
[link_nvd_cve_2026_96561]: https://nvd.nist.gov/vuln/detail/CVE-2026-96561
[link_nvd_cve_2026_96526]: https://nvd.nist.gov/vuln/detail/CVE-2026-96526
[link_nvd_cve_2026_96525]: https://nvd.nist.gov/vuln/detail/CVE-2026-96525
[link_nvd_cve_2026_96524]: https://nvd.nist.gov/vuln/detail/CVE-2026-96524
[link_nvd_cve_2026_94486]: https://nvd.nist.gov/vuln/detail/CVE-2026-94486
[link_nvd_cve_2026_94485]: https://nvd.nist.gov/vuln/detail/CVE-2026-94485
[link_nvd_cve_2026_94046]: https://nvd.nist.gov/vuln/detail/CVE-2026-94046
[link_nvd_cve_2026_94044]: https://nvd.nist.gov/vuln/detail/CVE-2026-94044
[link_nvd_cve_2026_94037]: https://nvd.nist.gov/vuln/detail/CVE-2026-94037
[link_nvd_cve_2026_93982]: https://nvd.nist.gov/vuln/detail/CVE-2026-93982
[link_nvd_cve_2026_93965]: https://nvd.nist.gov/vuln/detail/CVE-2026-93965
[link_nvd_cve_2026_91988]: https://nvd.nist.gov/vuln/detail/CVE-2026-91988
[link_nvd_cve_2026_91932]: https://nvd.nist.gov/vuln/detail/CVE-2026-91932
[link_nvd_cve_2026_91931]: https://nvd.nist.gov/vuln/detail/CVE-2026-91931
[link_nvd_cve_2026_90474]: https://nvd.nist.gov/vuln/detail/CVE-2026-90474
[link_nvd_cve_2026_89039]: https://nvd.nist.gov/vuln/detail/CVE-2026-89039
[link_nvd_cve_2026_88938]: https://nvd.nist.gov/vuln/detail/CVE-2026-88938
[link_nvd_cve_2026_88755]: https://nvd.nist.gov/vuln/detail/CVE-2026-88755
[link_nvd_cve_2026_88257]: https://nvd.nist.gov/vuln/detail/CVE-2026-88257
[link_nvd_cve_2026_87913]: https://nvd.nist.gov/vuln/detail/CVE-2026-87913
[link_nvd_cve_2026_87911]: https://nvd.nist.gov/vuln/detail/CVE-2026-87911
[link_nvd_cve_2026_86439]: https://nvd.nist.gov/vuln/detail/CVE-2026-86439
[link_nvd_cve_2026_86122]: https://nvd.nist.gov/vuln/detail/CVE-2026-86122
[link_nvd_cve_2026_85787]: https://nvd.nist.gov/vuln/detail/CVE-2026-85787
[link_nvd_cve_2026_85666]: https://nvd.nist.gov/vuln/detail/CVE-2026-85666
[link_nvd_cve_2026_85620]: https://nvd.nist.gov/vuln/detail/CVE-2026-85620
[link_nvd_cve_2026_85580]: https://nvd.nist.gov/vuln/detail/CVE-2026-85580
[link_nvd_cve_2026_85306]: https://nvd.nist.gov/vuln/detail/CVE-2026-85306
[link_nvd_cve_2026_85166]: https://nvd.nist.gov/vuln/detail/CVE-2026-85166
[link_nvd_cve_2026_84779]: https://nvd.nist.gov/vuln/detail/CVE-2026-84779
[link_nvd_cve_2026_84360]: https://nvd.nist.gov/vuln/detail/CVE-2026-84360
[link_nvd_cve_2026_84319]: https://nvd.nist.gov/vuln/detail/CVE-2026-84319
[link_nvd_cve_2026_84318]: https://nvd.nist.gov/vuln/detail/CVE-2026-84318
[link_nvd_cve_2026_84317]: https://nvd.nist.gov/vuln/detail/CVE-2026-84317
[link_nvd_cve_2026_84289]: https://nvd.nist.gov/vuln/detail/CVE-2026-84289
[link_nvd_cve_2026_82905]: https://nvd.nist.gov/vuln/detail/CVE-2026-82905
[link_nvd_cve_2026_82456]: https://nvd.nist.gov/vuln/detail/CVE-2026-82456
[link_nvd_cve_2026_82233]: https://nvd.nist.gov/vuln/detail/CVE-2026-82233
[link_nvd_cve_2026_82021]: https://nvd.nist.gov/vuln/detail/CVE-2026-82021
[link_nvd_cve_2026_81941]: https://nvd.nist.gov/vuln/detail/CVE-2026-81941
[link_nvd_cve_2026_81846]: https://nvd.nist.gov/vuln/detail/CVE-2026-81846
[link_nvd_cve_2026_81845]: https://nvd.nist.gov/vuln/detail/CVE-2026-81845
[link_nvd_cve_2026_81835]: https://nvd.nist.gov/vuln/detail/CVE-2026-81835
[link_nvd_cve_2026_81735]: https://nvd.nist.gov/vuln/detail/CVE-2026-81735
[link_nvd_cve_2026_81486]: https://nvd.nist.gov/vuln/detail/CVE-2026-81486
[link_nvd_cve_2026_81315]: https://nvd.nist.gov/vuln/detail/CVE-2026-81315
[link_nvd_cve_2026_81102]: https://nvd.nist.gov/vuln/detail/CVE-2026-81102
[link_nvd_cve_2026_81101]: https://nvd.nist.gov/vuln/detail/CVE-2026-81101
[link_nvd_cve_2026_81100]: https://nvd.nist.gov/vuln/detail/CVE-2026-81100
[link_nvd_cve_2026_81099]: https://nvd.nist.gov/vuln/detail/CVE-2026-81099
[link_nvd_cve_2026_81098]: https://nvd.nist.gov/vuln/detail/CVE-2026-81098
[link_nvd_cve_2026_81097]: https://nvd.nist.gov/vuln/detail/CVE-2026-81097
[link_nvd_cve_2026_81096]: https://nvd.nist.gov/vuln/detail/CVE-2026-81096
[link_nvd_cve_2026_81095]: https://nvd.nist.gov/vuln/detail/CVE-2026-81095
[link_nvd_cve_2026_81094]: https://nvd.nist.gov/vuln/detail/CVE-2026-81094
[link_nvd_cve_2026_81093]: https://nvd.nist.gov/vuln/detail/CVE-2026-81093
[link_nvd_cve_2026_81092]: https://nvd.nist.gov/vuln/detail/CVE-2026-81092
[link_nvd_cve_2026_81091]: https://nvd.nist.gov/vuln/detail/CVE-2026-81091
[link_nvd_cve_2026_80347]: https://nvd.nist.gov/vuln/detail/CVE-2026-80347
[link_nvd_cve_2026_79786]: https://nvd.nist.gov/vuln/detail/CVE-2026-79786
[link_nvd_cve_2026_79750]: https://nvd.nist.gov/vuln/detail/CVE-2026-79750
[link_nvd_cve_2026_79749]: https://nvd.nist.gov/vuln/detail/CVE-2026-79749
[link_nvd_cve_2026_79748]: https://nvd.nist.gov/vuln/detail/CVE-2026-79748
[link_nvd_cve_2026_79747]: https://nvd.nist.gov/vuln/detail/CVE-2026-79747
[link_nvd_cve_2026_79746]: https://nvd.nist.gov/vuln/detail/CVE-2026-79746
[link_nvd_cve_2026_79745]: https://nvd.nist.gov/vuln/detail/CVE-2026-79745
[link_nvd_cve_2026_79744]: https://nvd.nist.gov/vuln/detail/CVE-2026-79744
[link_nvd_cve_2026_79743]: https://nvd.nist.gov/vuln/detail/CVE-2026-79743
[link_nvd_cve_2026_79534]: https://nvd.nist.gov/vuln/detail/CVE-2026-79534
[link_nvd_cve_2026_78575]: https://nvd.nist.gov/vuln/detail/CVE-2026-78575
[link_nvd_cve_2026_78430]: https://nvd.nist.gov/vuln/detail/CVE-2026-78430
[link_nvd_cve_2026_77825]: https://nvd.nist.gov/vuln/detail/CVE-2026-77825
[link_nvd_cve_2026_77822]: https://nvd.nist.gov/vuln/detail/CVE-2026-77822
[link_nvd_cve_2026_77604]: https://nvd.nist.gov/vuln/detail/CVE-2026-77604
[link_nvd_cve_2026_77518]: https://nvd.nist.gov/vuln/detail/CVE-2026-77518
[link_nvd_cve_2026_77366]: https://nvd.nist.gov/vuln/detail/CVE-2026-77366
[link_nvd_cve_2026_77364]: https://nvd.nist.gov/vuln/detail/CVE-2026-77364
[link_nvd_cve_2026_77363]: https://nvd.nist.gov/vuln/detail/CVE-2026-77363
[link_nvd_cve_2026_77362]: https://nvd.nist.gov/vuln/detail/CVE-2026-77362
[link_nvd_cve_2026_77361]: https://nvd.nist.gov/vuln/detail/CVE-2026-77361
[link_nvd_cve_2026_77339]: https://nvd.nist.gov/vuln/detail/CVE-2026-77339
[link_nvd_cve_2026_77321]: https://nvd.nist.gov/vuln/detail/CVE-2026-77321
[link_nvd_cve_2026_77274]: https://nvd.nist.gov/vuln/detail/CVE-2026-77274
[link_nvd_cve_2026_77272]: https://nvd.nist.gov/vuln/detail/CVE-2026-77272
[link_nvd_cve_2026_77271]: https://nvd.nist.gov/vuln/detail/CVE-2026-77271
[link_nvd_cve_2026_77270]: https://nvd.nist.gov/vuln/detail/CVE-2026-77270
[link_nvd_cve_2026_77269]: https://nvd.nist.gov/vuln/detail/CVE-2026-77269
[link_nvd_cve_2026_77268]: https://nvd.nist.gov/vuln/detail/CVE-2026-77268
[link_nvd_cve_2026_77267]: https://nvd.nist.gov/vuln/detail/CVE-2026-77267
[link_nvd_cve_2026_77266]: https://nvd.nist.gov/vuln/detail/CVE-2026-77266
[link_nvd_cve_2026_77265]: https://nvd.nist.gov/vuln/detail/CVE-2026-77265
[link_nvd_cve_2026_77262]: https://nvd.nist.gov/vuln/detail/CVE-2026-77262
[link_nvd_cve_2026_77261]: https://nvd.nist.gov/vuln/detail/CVE-2026-77261
[link_nvd_cve_2026_77260]: https://nvd.nist.gov/vuln/detail/CVE-2026-77260
[link_nvd_cve_2026_77259]: https://nvd.nist.gov/vuln/detail/CVE-2026-77259
[link_nvd_cve_2026_77258]: https://nvd.nist.gov/vuln/detail/CVE-2026-77258
[link_nvd_cve_2026_77257]: https://nvd.nist.gov/vuln/detail/CVE-2026-77257
[link_nvd_cve_2026_77256]: https://nvd.nist.gov/vuln/detail/CVE-2026-77256
[link_nvd_cve_2026_77255]: https://nvd.nist.gov/vuln/detail/CVE-2026-77255
[link_nvd_cve_2026_77254]: https://nvd.nist.gov/vuln/detail/CVE-2026-77254
[link_nvd_cve_2026_77253]: https://nvd.nist.gov/vuln/detail/CVE-2026-77253
[link_nvd_cve_2026_77252]: https://nvd.nist.gov/vuln/detail/CVE-2026-77252
[link_nvd_cve_2026_77251]: https://nvd.nist.gov/vuln/detail/CVE-2026-77251
[link_nvd_cve_2026_77250]: https://nvd.nist.gov/vuln/detail/CVE-2026-77250
[link_nvd_cve_2026_77249]: https://nvd.nist.gov/vuln/detail/CVE-2026-77249
[link_nvd_cve_2026_77248]: https://nvd.nist.gov/vuln/detail/CVE-2026-77248
[link_nvd_cve_2026_77247]: https://nvd.nist.gov/vuln/detail/CVE-2026-77247
[link_nvd_cve_2026_77246]: https://nvd.nist.gov/vuln/detail/CVE-2026-77246
[link_nvd_cve_2026_77244]: https://nvd.nist.gov/vuln/detail/CVE-2026-77244
[link_nvd_cve_2026_77243]: https://nvd.nist.gov/vuln/detail/CVE-2026-77243
[link_nvd_cve_2026_77242]: https://nvd.nist.gov/vuln/detail/CVE-2026-77242
[link_nvd_cve_2026_77073]: https://nvd.nist.gov/vuln/detail/CVE-2026-77073
[link_nvd_cve_2026_77068]: https://nvd.nist.gov/vuln/detail/CVE-2026-77068
[link_nvd_cve_2026_76894]: https://nvd.nist.gov/vuln/detail/CVE-2026-76894
[link_nvd_cve_2026_76893]: https://nvd.nist.gov/vuln/detail/CVE-2026-76893
[link_nvd_cve_2026_76404]: https://nvd.nist.gov/vuln/detail/CVE-2026-76404
[link_nvd_cve_2026_76286]: https://nvd.nist.gov/vuln/detail/CVE-2026-76286
[link_nvd_cve_2026_75858]: https://nvd.nist.gov/vuln/detail/CVE-2026-75858
[link_nvd_cve_2026_75857]: https://nvd.nist.gov/vuln/detail/CVE-2026-75857
[link_nvd_cve_2026_75845]: https://nvd.nist.gov/vuln/detail/CVE-2026-75845
[link_nvd_cve_2026_75149]: https://nvd.nist.gov/vuln/detail/CVE-2026-75149
[link_nvd_cve_2026_75130]: https://nvd.nist.gov/vuln/detail/CVE-2026-75130
[link_nvd_cve_2026_75062]: https://nvd.nist.gov/vuln/detail/CVE-2026-75062
[link_nvd_cve_2026_75060]: https://nvd.nist.gov/vuln/detail/CVE-2026-75060
[link_nvd_cve_2026_74798]: https://nvd.nist.gov/vuln/detail/CVE-2026-74798
[link_nvd_cve_2026_73846]: https://nvd.nist.gov/vuln/detail/CVE-2026-73846
[link_nvd_cve_2026_73845]: https://nvd.nist.gov/vuln/detail/CVE-2026-73845
[link_nvd_cve_2026_73844]: https://nvd.nist.gov/vuln/detail/CVE-2026-73844
[link_nvd_cve_2026_73601]: https://nvd.nist.gov/vuln/detail/CVE-2026-73601
[link_nvd_cve_2026_73498]: https://nvd.nist.gov/vuln/detail/CVE-2026-73498
[link_nvd_cve_2026_73497]: https://nvd.nist.gov/vuln/detail/CVE-2026-73497
[link_nvd_cve_2026_73496]: https://nvd.nist.gov/vuln/detail/CVE-2026-73496
[link_nvd_cve_2026_73296]: https://nvd.nist.gov/vuln/detail/CVE-2026-73296
[link_nvd_cve_2026_73037]: https://nvd.nist.gov/vuln/detail/CVE-2026-73037
[link_nvd_cve_2026_72846]: https://nvd.nist.gov/vuln/detail/CVE-2026-72846
[link_nvd_cve_2026_72768]: https://nvd.nist.gov/vuln/detail/CVE-2026-72768
[link_nvd_cve_2026_71424]: https://nvd.nist.gov/vuln/detail/CVE-2026-71424
[link_nvd_cve_2026_69263]: https://nvd.nist.gov/vuln/detail/CVE-2026-69263
[link_nvd_cve_2026_69257]: https://nvd.nist.gov/vuln/detail/CVE-2026-69257
[link_nvd_cve_2026_68578]: https://nvd.nist.gov/vuln/detail/CVE-2026-68578
[link_nvd_cve_2026_67531]: https://nvd.nist.gov/vuln/detail/CVE-2026-67531
[link_nvd_cve_2026_67432]: https://nvd.nist.gov/vuln/detail/CVE-2026-67432
[link_nvd_cve_2026_67431]: https://nvd.nist.gov/vuln/detail/CVE-2026-67431
[link_nvd_cve_2026_67430]: https://nvd.nist.gov/vuln/detail/CVE-2026-67430
[link_nvd_cve_2026_67357]: https://nvd.nist.gov/vuln/detail/CVE-2026-67357
[link_nvd_cve_2026_67336]: https://nvd.nist.gov/vuln/detail/CVE-2026-67336
[link_nvd_cve_2026_67333]: https://nvd.nist.gov/vuln/detail/CVE-2026-67333
[link_nvd_cve_2026_66065]: https://nvd.nist.gov/vuln/detail/CVE-2026-66065
[link_nvd_cve_2026_66012]: https://nvd.nist.gov/vuln/detail/CVE-2026-66012
[link_nvd_cve_2026_66005]: https://nvd.nist.gov/vuln/detail/CVE-2026-66005
[link_nvd_cve_2026_65594]: https://nvd.nist.gov/vuln/detail/CVE-2026-65594
[link_nvd_cve_2026_65056]: https://nvd.nist.gov/vuln/detail/CVE-2026-65056
[link_nvd_cve_2026_64684]: https://nvd.nist.gov/vuln/detail/CVE-2026-64684
[link_nvd_cve_2026_63732]: https://nvd.nist.gov/vuln/detail/CVE-2026-63732
[link_nvd_cve_2026_63658]: https://nvd.nist.gov/vuln/detail/CVE-2026-63658
[link_nvd_cve_2026_63657]: https://nvd.nist.gov/vuln/detail/CVE-2026-63657
[link_nvd_cve_2026_63128]: https://nvd.nist.gov/vuln/detail/CVE-2026-63128
[link_nvd_cve_2026_63127]: https://nvd.nist.gov/vuln/detail/CVE-2026-63127
[link_nvd_cve_2026_63119]: https://nvd.nist.gov/vuln/detail/CVE-2026-63119
[link_nvd_cve_2026_63118]: https://nvd.nist.gov/vuln/detail/CVE-2026-63118
[link_nvd_cve_2026_62863]: https://nvd.nist.gov/vuln/detail/CVE-2026-62863
[link_nvd_cve_2026_62674]: https://nvd.nist.gov/vuln/detail/CVE-2026-62674
[link_nvd_cve_2026_62312]: https://nvd.nist.gov/vuln/detail/CVE-2026-62312
[link_nvd_cve_2026_62264]: https://nvd.nist.gov/vuln/detail/CVE-2026-62264
[link_nvd_cve_2026_62208]: https://nvd.nist.gov/vuln/detail/CVE-2026-62208
[link_nvd_cve_2026_62195]: https://nvd.nist.gov/vuln/detail/CVE-2026-62195
[link_nvd_cve_2026_61789]: https://nvd.nist.gov/vuln/detail/CVE-2026-61789
[link_nvd_cve_2026_61788]: https://nvd.nist.gov/vuln/detail/CVE-2026-61788
[link_nvd_cve_2026_61742]: https://nvd.nist.gov/vuln/detail/CVE-2026-61742
[link_nvd_cve_2026_61647]: https://nvd.nist.gov/vuln/detail/CVE-2026-61647
[link_nvd_cve_2026_61612]: https://nvd.nist.gov/vuln/detail/CVE-2026-61612
[link_nvd_cve_2026_61568]: https://nvd.nist.gov/vuln/detail/CVE-2026-61568
[link_nvd_cve_2026_61560]: https://nvd.nist.gov/vuln/detail/CVE-2026-61560
[link_nvd_cve_2026_61559]: https://nvd.nist.gov/vuln/detail/CVE-2026-61559
[link_nvd_cve_2026_61546]: https://nvd.nist.gov/vuln/detail/CVE-2026-61546
[link_nvd_cve_2026_61542]: https://nvd.nist.gov/vuln/detail/CVE-2026-61542
[link_nvd_cve_2026_61462]: https://nvd.nist.gov/vuln/detail/CVE-2026-61462
[link_nvd_cve_2026_61459]: https://nvd.nist.gov/vuln/detail/CVE-2026-61459
[link_nvd_cve_2026_61427]: https://nvd.nist.gov/vuln/detail/CVE-2026-61427
[link_nvd_cve_2026_60083]: https://nvd.nist.gov/vuln/detail/CVE-2026-60083
[link_nvd_cve_2026_59973]: https://nvd.nist.gov/vuln/detail/CVE-2026-59973
[link_nvd_cve_2026_59971]: https://nvd.nist.gov/vuln/detail/CVE-2026-59971
[link_nvd_cve_2026_59951]: https://nvd.nist.gov/vuln/detail/CVE-2026-59951
[link_nvd_cve_2026_59950]: https://nvd.nist.gov/vuln/detail/CVE-2026-59950
[link_nvd_cve_2026_59822]: https://nvd.nist.gov/vuln/detail/CVE-2026-59822
[link_nvd_cve_2026_59809]: https://nvd.nist.gov/vuln/detail/CVE-2026-59809
[link_nvd_cve_2026_59726]: https://nvd.nist.gov/vuln/detail/CVE-2026-59726
[link_nvd_cve_2026_59723]: https://nvd.nist.gov/vuln/detail/CVE-2026-59723
[link_nvd_cve_2026_59563]: https://nvd.nist.gov/vuln/detail/CVE-2026-59563
[link_nvd_cve_2026_59279]: https://nvd.nist.gov/vuln/detail/CVE-2026-59279
[link_nvd_cve_2026_59207]: https://nvd.nist.gov/vuln/detail/CVE-2026-59207
[link_nvd_cve_2026_59176]: https://nvd.nist.gov/vuln/detail/CVE-2026-59176
[link_nvd_cve_2026_58500]: https://nvd.nist.gov/vuln/detail/CVE-2026-58500
[link_nvd_cve_2026_58497]: https://nvd.nist.gov/vuln/detail/CVE-2026-58497
[link_nvd_cve_2026_58485]: https://nvd.nist.gov/vuln/detail/CVE-2026-58485
[link_nvd_cve_2026_58483]: https://nvd.nist.gov/vuln/detail/CVE-2026-58483
[link_nvd_cve_2026_58446]: https://nvd.nist.gov/vuln/detail/CVE-2026-58446
[link_nvd_cve_2026_58201]: https://nvd.nist.gov/vuln/detail/CVE-2026-58201
[link_nvd_cve_2026_58197]: https://nvd.nist.gov/vuln/detail/CVE-2026-58197
[link_nvd_cve_2026_58196]: https://nvd.nist.gov/vuln/detail/CVE-2026-58196
[link_nvd_cve_2026_58195]: https://nvd.nist.gov/vuln/detail/CVE-2026-58195
[link_nvd_cve_2026_58171]: https://nvd.nist.gov/vuln/detail/CVE-2026-58171
[link_nvd_cve_2026_58168]: https://nvd.nist.gov/vuln/detail/CVE-2026-58168
[link_nvd_cve_2026_58057]: https://nvd.nist.gov/vuln/detail/CVE-2026-58057
[link_nvd_cve_2026_57922]: https://nvd.nist.gov/vuln/detail/CVE-2026-57922
[link_nvd_cve_2026_57860]: https://nvd.nist.gov/vuln/detail/CVE-2026-57860
[link_nvd_cve_2026_57496]: https://nvd.nist.gov/vuln/detail/CVE-2026-57496
[link_nvd_cve_2026_57495]: https://nvd.nist.gov/vuln/detail/CVE-2026-57495
[link_nvd_cve_2026_57442]: https://nvd.nist.gov/vuln/detail/CVE-2026-57442
[link_nvd_cve_2026_57441]: https://nvd.nist.gov/vuln/detail/CVE-2026-57441
[link_nvd_cve_2026_57300]: https://nvd.nist.gov/vuln/detail/CVE-2026-57300
[link_nvd_cve_2026_57207]: https://nvd.nist.gov/vuln/detail/CVE-2026-57207
[link_nvd_cve_2026_57139]: https://nvd.nist.gov/vuln/detail/CVE-2026-57139
[link_nvd_cve_2026_57112]: https://nvd.nist.gov/vuln/detail/CVE-2026-57112
[link_nvd_cve_2026_56274]: https://nvd.nist.gov/vuln/detail/CVE-2026-56274
[link_nvd_cve_2026_55887]: https://nvd.nist.gov/vuln/detail/CVE-2026-55887
[link_nvd_cve_2026_55837]: https://nvd.nist.gov/vuln/detail/CVE-2026-55837
[link_nvd_cve_2026_55786]: https://nvd.nist.gov/vuln/detail/CVE-2026-55786
[link_nvd_cve_2026_55640]: https://nvd.nist.gov/vuln/detail/CVE-2026-55640
[link_nvd_cve_2026_55637]: https://nvd.nist.gov/vuln/detail/CVE-2026-55637
[link_nvd_cve_2026_55609]: https://nvd.nist.gov/vuln/detail/CVE-2026-55609
[link_nvd_cve_2026_55608]: https://nvd.nist.gov/vuln/detail/CVE-2026-55608
[link_nvd_cve_2026_55605]: https://nvd.nist.gov/vuln/detail/CVE-2026-55605
[link_nvd_cve_2026_55604]: https://nvd.nist.gov/vuln/detail/CVE-2026-55604
[link_nvd_cve_2026_55582]: https://nvd.nist.gov/vuln/detail/CVE-2026-55582
[link_nvd_cve_2026_55581]: https://nvd.nist.gov/vuln/detail/CVE-2026-55581
[link_nvd_cve_2026_55580]: https://nvd.nist.gov/vuln/detail/CVE-2026-55580
[link_nvd_cve_2026_55557]: https://nvd.nist.gov/vuln/detail/CVE-2026-55557
[link_nvd_cve_2026_55550]: https://nvd.nist.gov/vuln/detail/CVE-2026-55550
[link_nvd_cve_2026_55546]: https://nvd.nist.gov/vuln/detail/CVE-2026-55546
[link_nvd_cve_2026_55544]: https://nvd.nist.gov/vuln/detail/CVE-2026-55544
[link_nvd_cve_2026_55532]: https://nvd.nist.gov/vuln/detail/CVE-2026-55532
[link_nvd_cve_2026_55531]: https://nvd.nist.gov/vuln/detail/CVE-2026-55531
[link_nvd_cve_2026_55529]: https://nvd.nist.gov/vuln/detail/CVE-2026-55529
[link_nvd_cve_2026_55157]: https://nvd.nist.gov/vuln/detail/CVE-2026-55157
[link_nvd_cve_2026_55156]: https://nvd.nist.gov/vuln/detail/CVE-2026-55156
[link_nvd_cve_2026_55096]: https://nvd.nist.gov/vuln/detail/CVE-2026-55096
[link_nvd_cve_2026_55071]: https://nvd.nist.gov/vuln/detail/CVE-2026-55071
[link_nvd_cve_2026_54842]: https://nvd.nist.gov/vuln/detail/CVE-2026-54842
[link_nvd_cve_2026_54785]: https://nvd.nist.gov/vuln/detail/CVE-2026-54785
[link_nvd_cve_2026_54689]: https://nvd.nist.gov/vuln/detail/CVE-2026-54689
[link_nvd_cve_2026_54688]: https://nvd.nist.gov/vuln/detail/CVE-2026-54688
[link_nvd_cve_2026_54618]: https://nvd.nist.gov/vuln/detail/CVE-2026-54618
[link_nvd_cve_2026_54561]: https://nvd.nist.gov/vuln/detail/CVE-2026-54561
[link_nvd_cve_2026_54549]: https://nvd.nist.gov/vuln/detail/CVE-2026-54549
[link_nvd_cve_2026_54547]: https://nvd.nist.gov/vuln/detail/CVE-2026-54547
[link_nvd_cve_2026_54504]: https://nvd.nist.gov/vuln/detail/CVE-2026-54504
[link_nvd_cve_2026_54450]: https://nvd.nist.gov/vuln/detail/CVE-2026-54450
[link_nvd_cve_2026_54449]: https://nvd.nist.gov/vuln/detail/CVE-2026-54449
[link_nvd_cve_2026_54446]: https://nvd.nist.gov/vuln/detail/CVE-2026-54446
[link_nvd_cve_2026_54309]: https://nvd.nist.gov/vuln/detail/CVE-2026-54309
[link_nvd_cve_2026_54149]: https://nvd.nist.gov/vuln/detail/CVE-2026-54149
[link_nvd_cve_2026_54140]: https://nvd.nist.gov/vuln/detail/CVE-2026-54140
[link_nvd_cve_2026_54052]: https://nvd.nist.gov/vuln/detail/CVE-2026-54052
[link_nvd_cve_2026_54030]: https://nvd.nist.gov/vuln/detail/CVE-2026-54030
[link_nvd_cve_2026_53965]: https://nvd.nist.gov/vuln/detail/CVE-2026-53965
[link_nvd_cve_2026_53957]: https://nvd.nist.gov/vuln/detail/CVE-2026-53957
[link_nvd_cve_2026_53937]: https://nvd.nist.gov/vuln/detail/CVE-2026-53937
[link_nvd_cve_2026_53840]: https://nvd.nist.gov/vuln/detail/CVE-2026-53840
[link_nvd_cve_2026_53820]: https://nvd.nist.gov/vuln/detail/CVE-2026-53820
[link_nvd_cve_2026_53818]: https://nvd.nist.gov/vuln/detail/CVE-2026-53818
[link_nvd_cve_2026_53814]: https://nvd.nist.gov/vuln/detail/CVE-2026-53814
[link_nvd_cve_2026_53766]: https://nvd.nist.gov/vuln/detail/CVE-2026-53766
[link_nvd_cve_2026_53710]: https://nvd.nist.gov/vuln/detail/CVE-2026-53710
[link_nvd_cve_2026_53708]: https://nvd.nist.gov/vuln/detail/CVE-2026-53708
[link_nvd_cve_2026_53518]: https://nvd.nist.gov/vuln/detail/CVE-2026-53518
[link_nvd_cve_2026_53512]: https://nvd.nist.gov/vuln/detail/CVE-2026-53512
[link_nvd_cve_2026_53509]: https://nvd.nist.gov/vuln/detail/CVE-2026-53509
[link_nvd_cve_2026_52870]: https://nvd.nist.gov/vuln/detail/CVE-2026-52870
[link_nvd_cve_2026_52869]: https://nvd.nist.gov/vuln/detail/CVE-2026-52869
[link_nvd_cve_2026_52830]: https://nvd.nist.gov/vuln/detail/CVE-2026-52830
[link_nvd_cve_2026_51994]: https://nvd.nist.gov/vuln/detail/CVE-2026-51994
[link_nvd_cve_2026_50758]: https://nvd.nist.gov/vuln/detail/CVE-2026-50758
[link_nvd_cve_2026_50287]: https://nvd.nist.gov/vuln/detail/CVE-2026-50287
[link_nvd_cve_2026_50158]: https://nvd.nist.gov/vuln/detail/CVE-2026-50158
[link_nvd_cve_2026_50143]: https://nvd.nist.gov/vuln/detail/CVE-2026-50143
[link_nvd_cve_2026_50125]: https://nvd.nist.gov/vuln/detail/CVE-2026-50125
[link_nvd_cve_2026_50027]: https://nvd.nist.gov/vuln/detail/CVE-2026-50027
[link_nvd_cve_2026_49988]: https://nvd.nist.gov/vuln/detail/CVE-2026-49988
[link_nvd_cve_2026_49986]: https://nvd.nist.gov/vuln/detail/CVE-2026-49986
[link_nvd_cve_2026_49857]: https://nvd.nist.gov/vuln/detail/CVE-2026-49857
[link_nvd_cve_2026_49856]: https://nvd.nist.gov/vuln/detail/CVE-2026-49856
[link_nvd_cve_2026_49471]: https://nvd.nist.gov/vuln/detail/CVE-2026-49471
[link_nvd_cve_2026_49357]: https://nvd.nist.gov/vuln/detail/CVE-2026-49357
[link_nvd_cve_2026_49353]: https://nvd.nist.gov/vuln/detail/CVE-2026-49353
[link_nvd_cve_2026_49291]: https://nvd.nist.gov/vuln/detail/CVE-2026-49291
[link_nvd_cve_2026_49257]: https://nvd.nist.gov/vuln/detail/CVE-2026-49257
[link_nvd_cve_2026_48989]: https://nvd.nist.gov/vuln/detail/CVE-2026-48989
[link_nvd_cve_2026_48814]: https://nvd.nist.gov/vuln/detail/CVE-2026-48814
[link_nvd_cve_2026_48787]: https://nvd.nist.gov/vuln/detail/CVE-2026-48787
[link_nvd_cve_2026_48774]: https://nvd.nist.gov/vuln/detail/CVE-2026-48774
[link_nvd_cve_2026_48710]: https://nvd.nist.gov/vuln/detail/CVE-2026-48710
[link_nvd_cve_2026_48529]: https://nvd.nist.gov/vuln/detail/CVE-2026-48529
[link_nvd_cve_2026_48039]: https://nvd.nist.gov/vuln/detail/CVE-2026-48039
[link_nvd_cve_2026_47769]: https://nvd.nist.gov/vuln/detail/CVE-2026-47769
[link_nvd_cve_2026_47751]: https://nvd.nist.gov/vuln/detail/CVE-2026-47751
[link_nvd_cve_2026_47708]: https://nvd.nist.gov/vuln/detail/CVE-2026-47708
[link_nvd_cve_2026_47427]: https://nvd.nist.gov/vuln/detail/CVE-2026-47427
[link_nvd_cve_2026_47394]: https://nvd.nist.gov/vuln/detail/CVE-2026-47394
[link_nvd_cve_2026_47388]: https://nvd.nist.gov/vuln/detail/CVE-2026-47388
[link_nvd_cve_2026_47250]: https://nvd.nist.gov/vuln/detail/CVE-2026-47250
[link_nvd_cve_2026_46555]: https://nvd.nist.gov/vuln/detail/CVE-2026-46555
[link_nvd_cve_2026_46549]: https://nvd.nist.gov/vuln/detail/CVE-2026-46549
[link_nvd_cve_2026_46519]: https://nvd.nist.gov/vuln/detail/CVE-2026-46519
[link_nvd_cve_2026_46515]: https://nvd.nist.gov/vuln/detail/CVE-2026-46515
[link_nvd_cve_2026_46514]: https://nvd.nist.gov/vuln/detail/CVE-2026-46514
[link_nvd_cve_2026_46513]: https://nvd.nist.gov/vuln/detail/CVE-2026-46513
[link_nvd_cve_2026_46512]: https://nvd.nist.gov/vuln/detail/CVE-2026-46512
[link_nvd_cve_2026_46341]: https://nvd.nist.gov/vuln/detail/CVE-2026-46341
[link_nvd_cve_2026_46339]: https://nvd.nist.gov/vuln/detail/CVE-2026-46339
[link_nvd_cve_2026_45805]: https://nvd.nist.gov/vuln/detail/CVE-2026-45805
[link_nvd_cve_2026_45781]: https://nvd.nist.gov/vuln/detail/CVE-2026-45781
[link_nvd_cve_2026_45707]: https://nvd.nist.gov/vuln/detail/CVE-2026-45707
[link_nvd_cve_2026_45609]: https://nvd.nist.gov/vuln/detail/CVE-2026-45609
[link_nvd_cve_2026_45582]: https://nvd.nist.gov/vuln/detail/CVE-2026-45582
[link_nvd_cve_2026_45555]: https://nvd.nist.gov/vuln/detail/CVE-2026-45555
[link_nvd_cve_2026_45350]: https://nvd.nist.gov/vuln/detail/CVE-2026-45350
[link_nvd_cve_2026_45019]: https://nvd.nist.gov/vuln/detail/CVE-2026-45019
[link_nvd_cve_2026_45018]: https://nvd.nist.gov/vuln/detail/CVE-2026-45018
[link_nvd_cve_2026_45001]: https://nvd.nist.gov/vuln/detail/CVE-2026-45001
[link_nvd_cve_2026_44998]: https://nvd.nist.gov/vuln/detail/CVE-2026-44998
[link_nvd_cve_2026_44995]: https://nvd.nist.gov/vuln/detail/CVE-2026-44995
[link_nvd_cve_2026_44970]: https://nvd.nist.gov/vuln/detail/CVE-2026-44970
[link_nvd_cve_2026_44969]: https://nvd.nist.gov/vuln/detail/CVE-2026-44969
[link_nvd_cve_2026_44968]: https://nvd.nist.gov/vuln/detail/CVE-2026-44968
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
[link_nvd_cve_2026_44192]: https://nvd.nist.gov/vuln/detail/CVE-2026-44192
[link_nvd_cve_2026_44118]: https://nvd.nist.gov/vuln/detail/CVE-2026-44118
[link_nvd_cve_2026_43995]: https://nvd.nist.gov/vuln/detail/CVE-2026-43995
[link_nvd_cve_2026_43992]: https://nvd.nist.gov/vuln/detail/CVE-2026-43992
[link_nvd_cve_2026_43989]: https://nvd.nist.gov/vuln/detail/CVE-2026-43989
[link_nvd_cve_2026_43901]: https://nvd.nist.gov/vuln/detail/CVE-2026-43901
[link_nvd_cve_2026_42856]: https://nvd.nist.gov/vuln/detail/CVE-2026-42856
[link_nvd_cve_2026_42559]: https://nvd.nist.gov/vuln/detail/CVE-2026-42559
[link_nvd_cve_2026_42449]: https://nvd.nist.gov/vuln/detail/CVE-2026-42449
[link_nvd_cve_2026_42282]: https://nvd.nist.gov/vuln/detail/CVE-2026-42282
[link_nvd_cve_2026_42271]: https://nvd.nist.gov/vuln/detail/CVE-2026-42271
[link_nvd_cve_2026_42260]: https://nvd.nist.gov/vuln/detail/CVE-2026-42260
[link_nvd_cve_2026_42236]: https://nvd.nist.gov/vuln/detail/CVE-2026-42236
[link_nvd_cve_2026_42235]: https://nvd.nist.gov/vuln/detail/CVE-2026-42235
[link_nvd_cve_2026_42230]: https://nvd.nist.gov/vuln/detail/CVE-2026-42230
[link_nvd_cve_2026_42073]: https://nvd.nist.gov/vuln/detail/CVE-2026-42073
[link_nvd_cve_2026_41497]: https://nvd.nist.gov/vuln/detail/CVE-2026-41497
[link_nvd_cve_2026_41495]: https://nvd.nist.gov/vuln/detail/CVE-2026-41495
[link_nvd_cve_2026_41268]: https://nvd.nist.gov/vuln/detail/CVE-2026-41268
[link_nvd_cve_2026_40933]: https://nvd.nist.gov/vuln/detail/CVE-2026-40933
[link_nvd_cve_2026_40775]: https://nvd.nist.gov/vuln/detail/CVE-2026-40775
[link_nvd_cve_2026_40608]: https://nvd.nist.gov/vuln/detail/CVE-2026-40608
[link_nvd_cve_2026_40576]: https://nvd.nist.gov/vuln/detail/CVE-2026-40576
[link_nvd_cve_2026_40159]: https://nvd.nist.gov/vuln/detail/CVE-2026-40159
[link_nvd_cve_2026_39987]: https://nvd.nist.gov/vuln/detail/CVE-2026-39987
[link_nvd_cve_2026_39974]: https://nvd.nist.gov/vuln/detail/CVE-2026-39974
[link_nvd_cve_2026_39885]: https://nvd.nist.gov/vuln/detail/CVE-2026-39885
[link_nvd_cve_2026_39884]: https://nvd.nist.gov/vuln/detail/CVE-2026-39884
[link_nvd_cve_2026_39417]: https://nvd.nist.gov/vuln/detail/CVE-2026-39417
[link_nvd_cve_2026_39313]: https://nvd.nist.gov/vuln/detail/CVE-2026-39313
[link_nvd_cve_2026_38924]: https://nvd.nist.gov/vuln/detail/CVE-2026-38924
[link_nvd_cve_2026_37006]: https://nvd.nist.gov/vuln/detail/CVE-2026-37006
[link_nvd_cve_2026_35674]: https://nvd.nist.gov/vuln/detail/CVE-2026-35674
[link_nvd_cve_2026_35577]: https://nvd.nist.gov/vuln/detail/CVE-2026-35577
[link_nvd_cve_2026_35568]: https://nvd.nist.gov/vuln/detail/CVE-2026-35568
[link_nvd_cve_2026_35402]: https://nvd.nist.gov/vuln/detail/CVE-2026-35402
[link_nvd_cve_2026_35394]: https://nvd.nist.gov/vuln/detail/CVE-2026-35394
[link_nvd_cve_2026_35228]: https://nvd.nist.gov/vuln/detail/CVE-2026-35228
[link_nvd_cve_2026_34953]: https://nvd.nist.gov/vuln/detail/CVE-2026-34953
[link_nvd_cve_2026_34939]: https://nvd.nist.gov/vuln/detail/CVE-2026-34939
[link_nvd_cve_2026_34884]: https://nvd.nist.gov/vuln/detail/CVE-2026-34884
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
[link_nvd_cve_2026_32632]: https://nvd.nist.gov/vuln/detail/CVE-2026-32632
[link_nvd_cve_2026_32625]: https://nvd.nist.gov/vuln/detail/CVE-2026-32625
[link_nvd_cve_2026_32247]: https://nvd.nist.gov/vuln/detail/CVE-2026-32247
[link_nvd_cve_2026_32211]: https://nvd.nist.gov/vuln/detail/CVE-2026-32211
[link_nvd_cve_2026_32112]: https://nvd.nist.gov/vuln/detail/CVE-2026-32112
[link_nvd_cve_2026_32111]: https://nvd.nist.gov/vuln/detail/CVE-2026-32111
[link_nvd_cve_2026_31951]: https://nvd.nist.gov/vuln/detail/CVE-2026-31951
[link_nvd_cve_2026_31945]: https://nvd.nist.gov/vuln/detail/CVE-2026-31945
[link_nvd_cve_2026_31944]: https://nvd.nist.gov/vuln/detail/CVE-2026-31944
[link_nvd_cve_2026_31841]: https://nvd.nist.gov/vuln/detail/CVE-2026-31841
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
[link_nvd_cve_2026_29872]: https://nvd.nist.gov/vuln/detail/CVE-2026-29872
[link_nvd_cve_2026_29791]: https://nvd.nist.gov/vuln/detail/CVE-2026-29791
[link_nvd_cve_2026_29787]: https://nvd.nist.gov/vuln/detail/CVE-2026-29787
[link_nvd_cve_2026_29783]: https://nvd.nist.gov/vuln/detail/CVE-2026-29783
[link_nvd_cve_2026_28361]: https://nvd.nist.gov/vuln/detail/CVE-2026-28361
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
[link_nvd_cve_2026_24052]: https://nvd.nist.gov/vuln/detail/CVE-2026-24052
[link_nvd_cve_2026_23882]: https://nvd.nist.gov/vuln/detail/CVE-2026-23882
[link_nvd_cve_2026_23744]: https://nvd.nist.gov/vuln/detail/CVE-2026-23744
[link_nvd_cve_2026_23523]: https://nvd.nist.gov/vuln/detail/CVE-2026-23523
[link_nvd_cve_2026_22793]: https://nvd.nist.gov/vuln/detail/CVE-2026-22793
[link_nvd_cve_2026_22792]: https://nvd.nist.gov/vuln/detail/CVE-2026-22792
[link_nvd_cve_2026_22785]: https://nvd.nist.gov/vuln/detail/CVE-2026-22785
[link_nvd_cve_2026_22708]: https://nvd.nist.gov/vuln/detail/CVE-2026-22708
[link_nvd_cve_2026_22688]: https://nvd.nist.gov/vuln/detail/CVE-2026-22688
[link_nvd_cve_2026_22252]: https://nvd.nist.gov/vuln/detail/CVE-2026-22252
[link_nvd_cve_2026_21852]: https://nvd.nist.gov/vuln/detail/CVE-2026-21852
[link_nvd_cve_2026_21518]: https://nvd.nist.gov/vuln/detail/CVE-2026-21518
[link_nvd_cve_2026_20205]: https://nvd.nist.gov/vuln/detail/CVE-2026-20205
[link_nvd_cve_2026_19984]: https://nvd.nist.gov/vuln/detail/CVE-2026-19984
[link_nvd_cve_2026_19801]: https://nvd.nist.gov/vuln/detail/CVE-2026-19801
[link_nvd_cve_2026_19753]: https://nvd.nist.gov/vuln/detail/CVE-2026-19753
[link_nvd_cve_2026_19752]: https://nvd.nist.gov/vuln/detail/CVE-2026-19752
[link_nvd_cve_2026_19751]: https://nvd.nist.gov/vuln/detail/CVE-2026-19751
[link_nvd_cve_2026_19591]: https://nvd.nist.gov/vuln/detail/CVE-2026-19591
[link_nvd_cve_2026_19516]: https://nvd.nist.gov/vuln/detail/CVE-2026-19516
[link_nvd_cve_2026_19338]: https://nvd.nist.gov/vuln/detail/CVE-2026-19338
[link_nvd_cve_2026_19337]: https://nvd.nist.gov/vuln/detail/CVE-2026-19337
[link_nvd_cve_2026_19332]: https://nvd.nist.gov/vuln/detail/CVE-2026-19332
[link_nvd_cve_2026_19329]: https://nvd.nist.gov/vuln/detail/CVE-2026-19329
[link_nvd_cve_2026_19279]: https://nvd.nist.gov/vuln/detail/CVE-2026-19279
[link_nvd_cve_2026_19270]: https://nvd.nist.gov/vuln/detail/CVE-2026-19270
[link_nvd_cve_2026_19268]: https://nvd.nist.gov/vuln/detail/CVE-2026-19268
[link_nvd_cve_2026_19263]: https://nvd.nist.gov/vuln/detail/CVE-2026-19263
[link_nvd_cve_2026_19244]: https://nvd.nist.gov/vuln/detail/CVE-2026-19244
[link_nvd_cve_2026_19041]: https://nvd.nist.gov/vuln/detail/CVE-2026-19041
[link_nvd_cve_2026_19040]: https://nvd.nist.gov/vuln/detail/CVE-2026-19040
[link_nvd_cve_2026_19039]: https://nvd.nist.gov/vuln/detail/CVE-2026-19039
[link_nvd_cve_2026_18954]: https://nvd.nist.gov/vuln/detail/CVE-2026-18954
[link_nvd_cve_2026_18905]: https://nvd.nist.gov/vuln/detail/CVE-2026-18905
[link_nvd_cve_2026_18655]: https://nvd.nist.gov/vuln/detail/CVE-2026-18655
[link_nvd_cve_2026_18489]: https://nvd.nist.gov/vuln/detail/CVE-2026-18489
[link_nvd_cve_2026_18486]: https://nvd.nist.gov/vuln/detail/CVE-2026-18486
[link_nvd_cve_2026_18484]: https://nvd.nist.gov/vuln/detail/CVE-2026-18484
[link_nvd_cve_2026_18482]: https://nvd.nist.gov/vuln/detail/CVE-2026-18482
[link_nvd_cve_2026_17626]: https://nvd.nist.gov/vuln/detail/CVE-2026-17626
[link_nvd_cve_2026_17623]: https://nvd.nist.gov/vuln/detail/CVE-2026-17623
[link_nvd_cve_2026_17433]: https://nvd.nist.gov/vuln/detail/CVE-2026-17433
[link_nvd_cve_2026_16584]: https://nvd.nist.gov/vuln/detail/CVE-2026-16584
[link_nvd_cve_2026_16496]: https://nvd.nist.gov/vuln/detail/CVE-2026-16496
[link_nvd_cve_2026_16133]: https://nvd.nist.gov/vuln/detail/CVE-2026-16133
[link_nvd_cve_2026_15988]: https://nvd.nist.gov/vuln/detail/CVE-2026-15988
[link_nvd_cve_2026_15829]: https://nvd.nist.gov/vuln/detail/CVE-2026-15829
[link_nvd_cve_2026_15751]: https://nvd.nist.gov/vuln/detail/CVE-2026-15751
[link_nvd_cve_2026_15750]: https://nvd.nist.gov/vuln/detail/CVE-2026-15750
[link_nvd_cve_2026_15749]: https://nvd.nist.gov/vuln/detail/CVE-2026-15749
[link_nvd_cve_2026_15643]: https://nvd.nist.gov/vuln/detail/CVE-2026-15643
[link_nvd_cve_2026_15583]: https://nvd.nist.gov/vuln/detail/CVE-2026-15583
[link_nvd_cve_2026_15501]: https://nvd.nist.gov/vuln/detail/CVE-2026-15501
[link_nvd_cve_2026_15415]: https://nvd.nist.gov/vuln/detail/CVE-2026-15415
[link_nvd_cve_2026_15189]: https://nvd.nist.gov/vuln/detail/CVE-2026-15189
[link_nvd_cve_2026_15138]: https://nvd.nist.gov/vuln/detail/CVE-2026-15138
[link_nvd_cve_2026_15015]: https://nvd.nist.gov/vuln/detail/CVE-2026-15015
[link_nvd_cve_2026_14748]: https://nvd.nist.gov/vuln/detail/CVE-2026-14748
[link_nvd_cve_2026_14541]: https://nvd.nist.gov/vuln/detail/CVE-2026-14541
[link_nvd_cve_2026_14540]: https://nvd.nist.gov/vuln/detail/CVE-2026-14540
[link_nvd_cve_2026_14539]: https://nvd.nist.gov/vuln/detail/CVE-2026-14539
[link_nvd_cve_2026_14538]: https://nvd.nist.gov/vuln/detail/CVE-2026-14538
[link_nvd_cve_2026_14537]: https://nvd.nist.gov/vuln/detail/CVE-2026-14537
[link_nvd_cve_2026_14471]: https://nvd.nist.gov/vuln/detail/CVE-2026-14471
[link_nvd_cve_2026_13524]: https://nvd.nist.gov/vuln/detail/CVE-2026-13524
[link_nvd_cve_2026_13489]: https://nvd.nist.gov/vuln/detail/CVE-2026-13489
[link_nvd_cve_2026_13341]: https://nvd.nist.gov/vuln/detail/CVE-2026-13341
[link_nvd_cve_2026_12958]: https://nvd.nist.gov/vuln/detail/CVE-2026-12958
[link_nvd_cve_2026_12957]: https://nvd.nist.gov/vuln/detail/CVE-2026-12957
[link_nvd_cve_2026_12940]: https://nvd.nist.gov/vuln/detail/CVE-2026-12940
[link_nvd_cve_2026_12798]: https://nvd.nist.gov/vuln/detail/CVE-2026-12798
[link_nvd_cve_2026_12774]: https://nvd.nist.gov/vuln/detail/CVE-2026-12774
[link_nvd_cve_2026_12773]: https://nvd.nist.gov/vuln/detail/CVE-2026-12773
[link_nvd_cve_2026_12763]: https://nvd.nist.gov/vuln/detail/CVE-2026-12763
[link_nvd_cve_2026_12537]: https://nvd.nist.gov/vuln/detail/CVE-2026-12537
[link_nvd_cve_2026_12112]: https://nvd.nist.gov/vuln/detail/CVE-2026-12112
[link_nvd_cve_2026_11719]: https://nvd.nist.gov/vuln/detail/CVE-2026-11719
[link_nvd_cve_2026_11624]: https://nvd.nist.gov/vuln/detail/CVE-2026-11624
[link_nvd_cve_2026_10789]: https://nvd.nist.gov/vuln/detail/CVE-2026-10789
[link_nvd_cve_2026_10750]: https://nvd.nist.gov/vuln/detail/CVE-2026-10750
[link_nvd_cve_2026_10280]: https://nvd.nist.gov/vuln/detail/CVE-2026-10280
[link_nvd_cve_2026_10277]: https://nvd.nist.gov/vuln/detail/CVE-2026-10277
[link_nvd_cve_2026_9810]: https://nvd.nist.gov/vuln/detail/CVE-2026-9810
[link_nvd_cve_2026_9739]: https://nvd.nist.gov/vuln/detail/CVE-2026-9739
[link_nvd_cve_2026_9680]: https://nvd.nist.gov/vuln/detail/CVE-2026-9680
[link_nvd_cve_2026_9467]: https://nvd.nist.gov/vuln/detail/CVE-2026-9467
[link_nvd_cve_2026_9186]: https://nvd.nist.gov/vuln/detail/CVE-2026-9186
[link_nvd_cve_2026_9135]: https://nvd.nist.gov/vuln/detail/CVE-2026-9135
[link_nvd_cve_2026_9077]: https://nvd.nist.gov/vuln/detail/CVE-2026-9077
[link_nvd_cve_2026_8719]: https://nvd.nist.gov/vuln/detail/CVE-2026-8719
[link_nvd_cve_2026_8446]: https://nvd.nist.gov/vuln/detail/CVE-2026-8446
[link_nvd_cve_2026_8355]: https://nvd.nist.gov/vuln/detail/CVE-2026-8355
[link_nvd_cve_2026_7812]: https://nvd.nist.gov/vuln/detail/CVE-2026-7812
[link_nvd_cve_2026_7811]: https://nvd.nist.gov/vuln/detail/CVE-2026-7811
[link_nvd_cve_2026_7788]: https://nvd.nist.gov/vuln/detail/CVE-2026-7788
[link_nvd_cve_2026_7755]: https://nvd.nist.gov/vuln/detail/CVE-2026-7755
[link_nvd_cve_2026_7738]: https://nvd.nist.gov/vuln/detail/CVE-2026-7738
[link_nvd_cve_2026_7730]: https://nvd.nist.gov/vuln/detail/CVE-2026-7730
[link_nvd_cve_2026_7729]: https://nvd.nist.gov/vuln/detail/CVE-2026-7729
[link_nvd_cve_2026_7728]: https://nvd.nist.gov/vuln/detail/CVE-2026-7728
[link_nvd_cve_2026_7715]: https://nvd.nist.gov/vuln/detail/CVE-2026-7715
[link_nvd_cve_2026_7664]: https://nvd.nist.gov/vuln/detail/CVE-2026-7664
[link_nvd_cve_2026_7663]: https://nvd.nist.gov/vuln/detail/CVE-2026-7663
[link_nvd_cve_2026_7653]: https://nvd.nist.gov/vuln/detail/CVE-2026-7653
[link_nvd_cve_2026_7646]: https://nvd.nist.gov/vuln/detail/CVE-2026-7646
[link_nvd_cve_2026_7645]: https://nvd.nist.gov/vuln/detail/CVE-2026-7645
[link_nvd_cve_2026_7642]: https://nvd.nist.gov/vuln/detail/CVE-2026-7642
[link_nvd_cve_2026_7628]: https://nvd.nist.gov/vuln/detail/CVE-2026-7628
[link_nvd_cve_2026_7627]: https://nvd.nist.gov/vuln/detail/CVE-2026-7627
[link_nvd_cve_2026_7600]: https://nvd.nist.gov/vuln/detail/CVE-2026-7600
[link_nvd_cve_2026_7599]: https://nvd.nist.gov/vuln/detail/CVE-2026-7599
[link_nvd_cve_2026_7594]: https://nvd.nist.gov/vuln/detail/CVE-2026-7594
[link_nvd_cve_2026_7593]: https://nvd.nist.gov/vuln/detail/CVE-2026-7593
[link_nvd_cve_2026_7591]: https://nvd.nist.gov/vuln/detail/CVE-2026-7591
[link_nvd_cve_2026_7446]: https://nvd.nist.gov/vuln/detail/CVE-2026-7446
[link_nvd_cve_2026_7445]: https://nvd.nist.gov/vuln/detail/CVE-2026-7445
[link_nvd_cve_2026_7443]: https://nvd.nist.gov/vuln/detail/CVE-2026-7443
[link_nvd_cve_2026_7417]: https://nvd.nist.gov/vuln/detail/CVE-2026-7417
[link_nvd_cve_2026_7416]: https://nvd.nist.gov/vuln/detail/CVE-2026-7416
[link_nvd_cve_2026_7404]: https://nvd.nist.gov/vuln/detail/CVE-2026-7404
[link_nvd_cve_2026_7386]: https://nvd.nist.gov/vuln/detail/CVE-2026-7386
[link_nvd_cve_2026_7384]: https://nvd.nist.gov/vuln/detail/CVE-2026-7384
[link_nvd_cve_2026_7318]: https://nvd.nist.gov/vuln/detail/CVE-2026-7318
[link_nvd_cve_2026_7272]: https://nvd.nist.gov/vuln/detail/CVE-2026-7272
[link_nvd_cve_2026_7237]: https://nvd.nist.gov/vuln/detail/CVE-2026-7237
[link_nvd_cve_2026_7221]: https://nvd.nist.gov/vuln/detail/CVE-2026-7221
[link_nvd_cve_2026_7215]: https://nvd.nist.gov/vuln/detail/CVE-2026-7215
[link_nvd_cve_2026_7211]: https://nvd.nist.gov/vuln/detail/CVE-2026-7211
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
[link_nvd_cve_2026_6130]: https://nvd.nist.gov/vuln/detail/CVE-2026-6130
[link_nvd_cve_2026_6118]: https://nvd.nist.gov/vuln/detail/CVE-2026-6118
[link_nvd_cve_2026_6108]: https://nvd.nist.gov/vuln/detail/CVE-2026-6108
[link_nvd_cve_2026_5833]: https://nvd.nist.gov/vuln/detail/CVE-2026-5833
[link_nvd_cve_2026_5802]: https://nvd.nist.gov/vuln/detail/CVE-2026-5802
[link_nvd_cve_2026_5619]: https://nvd.nist.gov/vuln/detail/CVE-2026-5619
[link_nvd_cve_2026_5607]: https://nvd.nist.gov/vuln/detail/CVE-2026-5607
[link_nvd_cve_2026_5470]: https://nvd.nist.gov/vuln/detail/CVE-2026-5470
[link_nvd_cve_2026_5379]: https://nvd.nist.gov/vuln/detail/CVE-2026-5379
[link_nvd_cve_2026_5374]: https://nvd.nist.gov/vuln/detail/CVE-2026-5374
[link_nvd_cve_2026_5323]: https://nvd.nist.gov/vuln/detail/CVE-2026-5323
[link_nvd_cve_2026_5322]: https://nvd.nist.gov/vuln/detail/CVE-2026-5322
[link_nvd_cve_2026_5059]: https://nvd.nist.gov/vuln/detail/CVE-2026-5059
[link_nvd_cve_2026_5058]: https://nvd.nist.gov/vuln/detail/CVE-2026-5058
[link_nvd_cve_2026_5029]: https://nvd.nist.gov/vuln/detail/CVE-2026-5029
[link_nvd_cve_2026_5023]: https://nvd.nist.gov/vuln/detail/CVE-2026-5023
[link_nvd_cve_2026_5007]: https://nvd.nist.gov/vuln/detail/CVE-2026-5007
[link_nvd_cve_2026_4593]: https://nvd.nist.gov/vuln/detail/CVE-2026-4593
[link_nvd_cve_2026_4496]: https://nvd.nist.gov/vuln/detail/CVE-2026-4496
[link_nvd_cve_2026_4339]: https://nvd.nist.gov/vuln/detail/CVE-2026-4339
[link_nvd_cve_2026_4270]: https://nvd.nist.gov/vuln/detail/CVE-2026-4270
[link_nvd_cve_2026_4199]: https://nvd.nist.gov/vuln/detail/CVE-2026-4199
[link_nvd_cve_2026_4198]: https://nvd.nist.gov/vuln/detail/CVE-2026-4198
[link_nvd_cve_2026_2178]: https://nvd.nist.gov/vuln/detail/CVE-2026-2178
[link_nvd_cve_2026_2130]: https://nvd.nist.gov/vuln/detail/CVE-2026-2130
[link_nvd_cve_2026_1977]: https://nvd.nist.gov/vuln/detail/CVE-2026-1977
[link_nvd_cve_2026_1721]: https://nvd.nist.gov/vuln/detail/CVE-2026-1721
[link_nvd_cve_2026_0758]: https://nvd.nist.gov/vuln/detail/CVE-2026-0758
[link_nvd_cve_2026_0757]: https://nvd.nist.gov/vuln/detail/CVE-2026-0757
[link_nvd_cve_2026_0756]: https://nvd.nist.gov/vuln/detail/CVE-2026-0756
[link_nvd_cve_2026_0755]: https://nvd.nist.gov/vuln/detail/CVE-2026-0755
[link_nvd_cve_2026_0621]: https://nvd.nist.gov/vuln/detail/CVE-2026-0621
[link_nvd_cve_2025_71427]: https://nvd.nist.gov/vuln/detail/CVE-2025-71427
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
[link_nvd_cve_2025_61489]: https://nvd.nist.gov/vuln/detail/CVE-2025-61489
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
[link_nvd_cve_2025_55346]: https://nvd.nist.gov/vuln/detail/CVE-2025-55346
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
[link_nvd_cve_2025_53098]: https://nvd.nist.gov/vuln/detail/CVE-2025-53098
[link_nvd_cve_2025_52573]: https://nvd.nist.gov/vuln/detail/CVE-2025-52573
[link_nvd_cve_2025_49596]: https://nvd.nist.gov/vuln/detail/CVE-2025-49596
[link_nvd_cve_2025_47777]: https://nvd.nist.gov/vuln/detail/CVE-2025-47777
[link_nvd_cve_2025_47274]: https://nvd.nist.gov/vuln/detail/CVE-2025-47274
[link_nvd_cve_2025_35028]: https://nvd.nist.gov/vuln/detail/CVE-2025-35028
[link_nvd_cve_2025_34072]: https://nvd.nist.gov/vuln/detail/CVE-2025-34072
[link_nvd_cve_2025_20381]: https://nvd.nist.gov/vuln/detail/CVE-2025-20381
[link_nvd_cve_2025_15063]: https://nvd.nist.gov/vuln/detail/CVE-2025-15063
[link_nvd_cve_2025_15061]: https://nvd.nist.gov/vuln/detail/CVE-2025-15061
[link_nvd_cve_2025_13822]: https://nvd.nist.gov/vuln/detail/CVE-2025-13822
[link_nvd_cve_2025_11445]: https://nvd.nist.gov/vuln/detail/CVE-2025-11445
[link_nvd_cve_2025_11286]: https://nvd.nist.gov/vuln/detail/CVE-2025-11286
[link_nvd_cve_2025_11285]: https://nvd.nist.gov/vuln/detail/CVE-2025-11285
[link_nvd_cve_2025_10619]: https://nvd.nist.gov/vuln/detail/CVE-2025-10619
[link_nvd_cve_2025_10193]: https://nvd.nist.gov/vuln/detail/CVE-2025-10193
[link_nvd_cve_2025_9654]: https://nvd.nist.gov/vuln/detail/CVE-2025-9654
[link_nvd_cve_2025_9611]: https://nvd.nist.gov/vuln/detail/CVE-2025-9611
[link_nvd_cve_2025_9262]: https://nvd.nist.gov/vuln/detail/CVE-2025-9262
[link_nvd_cve_2025_8943]: https://nvd.nist.gov/vuln/detail/CVE-2025-8943
[link_nvd_cve_2025_8697]: https://nvd.nist.gov/vuln/detail/CVE-2025-8697
[link_nvd_cve_2025_8665]: https://nvd.nist.gov/vuln/detail/CVE-2025-8665
[link_nvd_cve_2025_6515]: https://nvd.nist.gov/vuln/detail/CVE-2025-6515
[link_nvd_cve_2025_6514]: https://nvd.nist.gov/vuln/detail/CVE-2025-6514
[link_nvd_cve_2025_5277]: https://nvd.nist.gov/vuln/detail/CVE-2025-5277
[link_nvd_cve_2025_5276]: https://nvd.nist.gov/vuln/detail/CVE-2025-5276
[link_nvd_cve_2025_5273]: https://nvd.nist.gov/vuln/detail/CVE-2025-5273
[link_nvd_cve_2025_4143]: https://nvd.nist.gov/vuln/detail/CVE-2025-4143

[link_mcp_cve_project_cve_2026_123272]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-123272.md
[link_mcp_cve_project_cve_2026_123271]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-123271.md
[link_mcp_cve_project_cve_2026_122140]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-122140.md
[link_mcp_cve_project_cve_2026_120492]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-120492.md
[link_mcp_cve_project_cve_2026_120338]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-120338.md
[link_mcp_cve_project_cve_2026_119025]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-119025.md
[link_mcp_cve_project_cve_2026_117573]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-117573.md
[link_mcp_cve_project_cve_2026_117569]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-117569.md
[link_mcp_cve_project_cve_2026_117568]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-117568.md
[link_mcp_cve_project_cve_2026_117567]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-117567.md
[link_mcp_cve_project_cve_2026_117561]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-117561.md
[link_mcp_cve_project_cve_2026_117558]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-117558.md
[link_mcp_cve_project_cve_2026_116686]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-116686.md
[link_mcp_cve_project_cve_2026_116685]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-116685.md
[link_mcp_cve_project_cve_2026_116684]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-116684.md
[link_mcp_cve_project_cve_2026_116635]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-116635.md
[link_mcp_cve_project_cve_2026_116109]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-116109.md
[link_mcp_cve_project_cve_2026_115845]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-115845.md
[link_mcp_cve_project_cve_2026_115751]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-115751.md
[link_mcp_cve_project_cve_2026_115563]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-115563.md
[link_mcp_cve_project_cve_2026_115478]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-115478.md
[link_mcp_cve_project_cve_2026_115477]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-115477.md
[link_mcp_cve_project_cve_2026_115413]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-115413.md
[link_mcp_cve_project_cve_2026_114612]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-114612.md
[link_mcp_cve_project_cve_2026_114123]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-114123.md
[link_mcp_cve_project_cve_2026_114090]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-114090.md
[link_mcp_cve_project_cve_2026_113731]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-113731.md
[link_mcp_cve_project_cve_2026_113378]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-113378.md
[link_mcp_cve_project_cve_2026_111771]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-111771.md
[link_mcp_cve_project_cve_2026_111770]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-111770.md
[link_mcp_cve_project_cve_2026_111769]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-111769.md
[link_mcp_cve_project_cve_2026_111768]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-111768.md
[link_mcp_cve_project_cve_2026_111767]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-111767.md
[link_mcp_cve_project_cve_2026_111091]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-111091.md
[link_mcp_cve_project_cve_2026_110842]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-110842.md
[link_mcp_cve_project_cve_2026_110616]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-110616.md
[link_mcp_cve_project_cve_2026_109527]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-109527.md
[link_mcp_cve_project_cve_2026_109402]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-109402.md
[link_mcp_cve_project_cve_2026_109332]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-109332.md
[link_mcp_cve_project_cve_2026_108953]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108953.md
[link_mcp_cve_project_cve_2026_108865]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108865.md
[link_mcp_cve_project_cve_2026_108859]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108859.md
[link_mcp_cve_project_cve_2026_108856]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108856.md
[link_mcp_cve_project_cve_2026_108851]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108851.md
[link_mcp_cve_project_cve_2026_108714]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108714.md
[link_mcp_cve_project_cve_2026_108671]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108671.md
[link_mcp_cve_project_cve_2026_108591]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108591.md
[link_mcp_cve_project_cve_2026_108586]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108586.md
[link_mcp_cve_project_cve_2026_108585]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108585.md
[link_mcp_cve_project_cve_2026_108582]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108582.md
[link_mcp_cve_project_cve_2026_108542]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108542.md
[link_mcp_cve_project_cve_2026_108395]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-108395.md
[link_mcp_cve_project_cve_2026_107824]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-107824.md
[link_mcp_cve_project_cve_2026_107820]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-107820.md
[link_mcp_cve_project_cve_2026_107745]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-107745.md
[link_mcp_cve_project_cve_2026_105761]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-105761.md
[link_mcp_cve_project_cve_2026_105741]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-105741.md
[link_mcp_cve_project_cve_2026_105740]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-105740.md
[link_mcp_cve_project_cve_2026_105697]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-105697.md
[link_mcp_cve_project_cve_2026_104850]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-104850.md
[link_mcp_cve_project_cve_2026_104634]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-104634.md
[link_mcp_cve_project_cve_2026_104120]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-104120.md
[link_mcp_cve_project_cve_2026_103758]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-103758.md
[link_mcp_cve_project_cve_2026_102878]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-102878.md
[link_mcp_cve_project_cve_2026_102610]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-102610.md
[link_mcp_cve_project_cve_2026_102503]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-102503.md
[link_mcp_cve_project_cve_2026_101084]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-101084.md
[link_mcp_cve_project_cve_2026_101065]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-101065.md
[link_mcp_cve_project_cve_2026_101064]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-101064.md
[link_mcp_cve_project_cve_2026_101063]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-101063.md
[link_mcp_cve_project_cve_2026_101062]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-101062.md
[link_mcp_cve_project_cve_2026_101057]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-101057.md
[link_mcp_cve_project_cve_2026_100868]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-100868.md
[link_mcp_cve_project_cve_2026_100633]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-100633.md
[link_mcp_cve_project_cve_2026_96620]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-96620.md
[link_mcp_cve_project_cve_2026_96561]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-96561.md
[link_mcp_cve_project_cve_2026_96526]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-96526.md
[link_mcp_cve_project_cve_2026_96525]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-96525.md
[link_mcp_cve_project_cve_2026_96524]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-96524.md
[link_mcp_cve_project_cve_2026_94486]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-94486.md
[link_mcp_cve_project_cve_2026_94485]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-94485.md
[link_mcp_cve_project_cve_2026_93982]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-93982.md
[link_mcp_cve_project_cve_2026_93965]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-93965.md
[link_mcp_cve_project_cve_2026_91988]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-91988.md
[link_mcp_cve_project_cve_2026_91932]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-91932.md
[link_mcp_cve_project_cve_2026_91931]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-91931.md
[link_mcp_cve_project_cve_2026_90474]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-90474.md
[link_mcp_cve_project_cve_2026_89039]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-89039.md
[link_mcp_cve_project_cve_2026_88755]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-88755.md
[link_mcp_cve_project_cve_2026_88257]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-88257.md
[link_mcp_cve_project_cve_2026_87913]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-87913.md
[link_mcp_cve_project_cve_2026_87911]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-87911.md
[link_mcp_cve_project_cve_2026_86439]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-86439.md
[link_mcp_cve_project_cve_2026_86122]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-86122.md
[link_mcp_cve_project_cve_2026_85787]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-85787.md
[link_mcp_cve_project_cve_2026_85666]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-85666.md
[link_mcp_cve_project_cve_2026_85620]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-85620.md
[link_mcp_cve_project_cve_2026_85580]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-85580.md
[link_mcp_cve_project_cve_2026_85306]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-85306.md
[link_mcp_cve_project_cve_2026_85166]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-85166.md
[link_mcp_cve_project_cve_2026_84779]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-84779.md
[link_mcp_cve_project_cve_2026_84360]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-84360.md
[link_mcp_cve_project_cve_2026_84319]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-84319.md
[link_mcp_cve_project_cve_2026_84318]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-84318.md
[link_mcp_cve_project_cve_2026_84317]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-84317.md
[link_mcp_cve_project_cve_2026_84289]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-84289.md
[link_mcp_cve_project_cve_2026_82905]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-82905.md
[link_mcp_cve_project_cve_2026_82456]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-82456.md
[link_mcp_cve_project_cve_2026_82233]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-82233.md
[link_mcp_cve_project_cve_2026_82021]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-82021.md
[link_mcp_cve_project_cve_2026_81941]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81941.md
[link_mcp_cve_project_cve_2026_81846]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81846.md
[link_mcp_cve_project_cve_2026_81845]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81845.md
[link_mcp_cve_project_cve_2026_81835]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81835.md
[link_mcp_cve_project_cve_2026_81735]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81735.md
[link_mcp_cve_project_cve_2026_81486]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81486.md
[link_mcp_cve_project_cve_2026_81315]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81315.md
[link_mcp_cve_project_cve_2026_81102]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81102.md
[link_mcp_cve_project_cve_2026_81101]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81101.md
[link_mcp_cve_project_cve_2026_81100]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81100.md
[link_mcp_cve_project_cve_2026_81099]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81099.md
[link_mcp_cve_project_cve_2026_81098]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81098.md
[link_mcp_cve_project_cve_2026_81097]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81097.md
[link_mcp_cve_project_cve_2026_81096]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81096.md
[link_mcp_cve_project_cve_2026_81095]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81095.md
[link_mcp_cve_project_cve_2026_81094]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81094.md
[link_mcp_cve_project_cve_2026_81093]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81093.md
[link_mcp_cve_project_cve_2026_81092]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81092.md
[link_mcp_cve_project_cve_2026_81091]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-81091.md
[link_mcp_cve_project_cve_2026_80347]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-80347.md
[link_mcp_cve_project_cve_2026_79786]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79786.md
[link_mcp_cve_project_cve_2026_79750]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79750.md
[link_mcp_cve_project_cve_2026_79749]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79749.md
[link_mcp_cve_project_cve_2026_79748]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79748.md
[link_mcp_cve_project_cve_2026_79747]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79747.md
[link_mcp_cve_project_cve_2026_79746]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79746.md
[link_mcp_cve_project_cve_2026_79745]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79745.md
[link_mcp_cve_project_cve_2026_79744]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79744.md
[link_mcp_cve_project_cve_2026_79743]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-79743.md
[link_mcp_cve_project_cve_2026_78575]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-78575.md
[link_mcp_cve_project_cve_2026_78430]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-78430.md
[link_mcp_cve_project_cve_2026_77822]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77822.md
[link_mcp_cve_project_cve_2026_77604]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77604.md
[link_mcp_cve_project_cve_2026_77518]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77518.md
[link_mcp_cve_project_cve_2026_77366]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77366.md
[link_mcp_cve_project_cve_2026_77364]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77364.md
[link_mcp_cve_project_cve_2026_77363]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77363.md
[link_mcp_cve_project_cve_2026_77362]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77362.md
[link_mcp_cve_project_cve_2026_77361]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77361.md
[link_mcp_cve_project_cve_2026_77321]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77321.md
[link_mcp_cve_project_cve_2026_77274]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77274.md
[link_mcp_cve_project_cve_2026_77272]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77272.md
[link_mcp_cve_project_cve_2026_77271]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77271.md
[link_mcp_cve_project_cve_2026_77270]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77270.md
[link_mcp_cve_project_cve_2026_77269]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77269.md
[link_mcp_cve_project_cve_2026_77268]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77268.md
[link_mcp_cve_project_cve_2026_77267]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77267.md
[link_mcp_cve_project_cve_2026_77266]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77266.md
[link_mcp_cve_project_cve_2026_77265]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77265.md
[link_mcp_cve_project_cve_2026_77262]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77262.md
[link_mcp_cve_project_cve_2026_77261]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77261.md
[link_mcp_cve_project_cve_2026_77260]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77260.md
[link_mcp_cve_project_cve_2026_77259]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77259.md
[link_mcp_cve_project_cve_2026_77258]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77258.md
[link_mcp_cve_project_cve_2026_77257]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77257.md
[link_mcp_cve_project_cve_2026_77256]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77256.md
[link_mcp_cve_project_cve_2026_77255]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77255.md
[link_mcp_cve_project_cve_2026_77254]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77254.md
[link_mcp_cve_project_cve_2026_77253]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77253.md
[link_mcp_cve_project_cve_2026_77252]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77252.md
[link_mcp_cve_project_cve_2026_77251]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77251.md
[link_mcp_cve_project_cve_2026_77250]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77250.md
[link_mcp_cve_project_cve_2026_77249]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77249.md
[link_mcp_cve_project_cve_2026_77248]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77248.md
[link_mcp_cve_project_cve_2026_77247]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77247.md
[link_mcp_cve_project_cve_2026_77246]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77246.md
[link_mcp_cve_project_cve_2026_77244]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77244.md
[link_mcp_cve_project_cve_2026_77243]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77243.md
[link_mcp_cve_project_cve_2026_77242]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77242.md
[link_mcp_cve_project_cve_2026_77073]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77073.md
[link_mcp_cve_project_cve_2026_77068]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-77068.md
[link_mcp_cve_project_cve_2026_76894]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-76894.md
[link_mcp_cve_project_cve_2026_76893]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-76893.md
[link_mcp_cve_project_cve_2026_76404]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-76404.md
[link_mcp_cve_project_cve_2026_76286]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-76286.md
[link_mcp_cve_project_cve_2026_75858]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-75858.md
[link_mcp_cve_project_cve_2026_75857]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-75857.md
[link_mcp_cve_project_cve_2026_75845]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-75845.md
[link_mcp_cve_project_cve_2026_75149]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-75149.md
[link_mcp_cve_project_cve_2026_75130]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-75130.md
[link_mcp_cve_project_cve_2026_75062]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-75062.md
[link_mcp_cve_project_cve_2026_75060]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-75060.md
[link_mcp_cve_project_cve_2026_74798]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-74798.md
[link_mcp_cve_project_cve_2026_73846]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73846.md
[link_mcp_cve_project_cve_2026_73845]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73845.md
[link_mcp_cve_project_cve_2026_73844]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73844.md
[link_mcp_cve_project_cve_2026_73601]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73601.md
[link_mcp_cve_project_cve_2026_73498]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73498.md
[link_mcp_cve_project_cve_2026_73497]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73497.md
[link_mcp_cve_project_cve_2026_73496]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73496.md
[link_mcp_cve_project_cve_2026_73296]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73296.md
[link_mcp_cve_project_cve_2026_73037]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-73037.md
[link_mcp_cve_project_cve_2026_72846]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-72846.md
[link_mcp_cve_project_cve_2026_72768]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-72768.md
[link_mcp_cve_project_cve_2026_71424]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-71424.md
[link_mcp_cve_project_cve_2026_69263]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-69263.md
[link_mcp_cve_project_cve_2026_69257]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-69257.md
[link_mcp_cve_project_cve_2026_68578]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-68578.md
[link_mcp_cve_project_cve_2026_67531]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-67531.md
[link_mcp_cve_project_cve_2026_67432]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-67432.md
[link_mcp_cve_project_cve_2026_67431]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-67431.md
[link_mcp_cve_project_cve_2026_67430]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-67430.md
[link_mcp_cve_project_cve_2026_67357]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-67357.md
[link_mcp_cve_project_cve_2026_67336]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-67336.md
[link_mcp_cve_project_cve_2026_67333]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-67333.md
[link_mcp_cve_project_cve_2026_66065]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-66065.md
[link_mcp_cve_project_cve_2026_66012]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-66012.md
[link_mcp_cve_project_cve_2026_66005]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-66005.md
[link_mcp_cve_project_cve_2026_65594]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-65594.md
[link_mcp_cve_project_cve_2026_65056]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-65056.md
[link_mcp_cve_project_cve_2026_64684]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-64684.md
[link_mcp_cve_project_cve_2026_63732]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63732.md
[link_mcp_cve_project_cve_2026_63658]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63658.md
[link_mcp_cve_project_cve_2026_63657]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63657.md
[link_mcp_cve_project_cve_2026_63128]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63128.md
[link_mcp_cve_project_cve_2026_63127]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63127.md
[link_mcp_cve_project_cve_2026_63119]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63119.md
[link_mcp_cve_project_cve_2026_63118]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-63118.md
[link_mcp_cve_project_cve_2026_62863]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-62863.md
[link_mcp_cve_project_cve_2026_62674]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-62674.md
[link_mcp_cve_project_cve_2026_62312]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-62312.md
[link_mcp_cve_project_cve_2026_62264]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-62264.md
[link_mcp_cve_project_cve_2026_62208]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-62208.md
[link_mcp_cve_project_cve_2026_62195]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-62195.md
[link_mcp_cve_project_cve_2026_61789]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61789.md
[link_mcp_cve_project_cve_2026_61788]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61788.md
[link_mcp_cve_project_cve_2026_61742]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61742.md
[link_mcp_cve_project_cve_2026_61647]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61647.md
[link_mcp_cve_project_cve_2026_61612]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61612.md
[link_mcp_cve_project_cve_2026_61568]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61568.md
[link_mcp_cve_project_cve_2026_61560]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61560.md
[link_mcp_cve_project_cve_2026_61559]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61559.md
[link_mcp_cve_project_cve_2026_61546]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61546.md
[link_mcp_cve_project_cve_2026_61542]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61542.md
[link_mcp_cve_project_cve_2026_61462]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61462.md
[link_mcp_cve_project_cve_2026_61459]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61459.md
[link_mcp_cve_project_cve_2026_61427]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-61427.md
[link_mcp_cve_project_cve_2026_60083]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-60083.md
[link_mcp_cve_project_cve_2026_59973]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59973.md
[link_mcp_cve_project_cve_2026_59971]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59971.md
[link_mcp_cve_project_cve_2026_59951]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59951.md
[link_mcp_cve_project_cve_2026_59950]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59950.md
[link_mcp_cve_project_cve_2026_59822]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59822.md
[link_mcp_cve_project_cve_2026_59809]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59809.md
[link_mcp_cve_project_cve_2026_59726]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59726.md
[link_mcp_cve_project_cve_2026_59723]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59723.md
[link_mcp_cve_project_cve_2026_59563]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59563.md
[link_mcp_cve_project_cve_2026_59279]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59279.md
[link_mcp_cve_project_cve_2026_59207]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59207.md
[link_mcp_cve_project_cve_2026_59176]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-59176.md
[link_mcp_cve_project_cve_2026_58500]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58500.md
[link_mcp_cve_project_cve_2026_58497]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58497.md
[link_mcp_cve_project_cve_2026_58485]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58485.md
[link_mcp_cve_project_cve_2026_58483]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58483.md
[link_mcp_cve_project_cve_2026_58446]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58446.md
[link_mcp_cve_project_cve_2026_58201]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58201.md
[link_mcp_cve_project_cve_2026_58197]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58197.md
[link_mcp_cve_project_cve_2026_58196]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58196.md
[link_mcp_cve_project_cve_2026_58195]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58195.md
[link_mcp_cve_project_cve_2026_58171]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58171.md
[link_mcp_cve_project_cve_2026_58168]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58168.md
[link_mcp_cve_project_cve_2026_58057]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-58057.md
[link_mcp_cve_project_cve_2026_57922]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57922.md
[link_mcp_cve_project_cve_2026_57860]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57860.md
[link_mcp_cve_project_cve_2026_57496]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57496.md
[link_mcp_cve_project_cve_2026_57495]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57495.md
[link_mcp_cve_project_cve_2026_57442]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57442.md
[link_mcp_cve_project_cve_2026_57441]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57441.md
[link_mcp_cve_project_cve_2026_57300]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57300.md
[link_mcp_cve_project_cve_2026_57207]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57207.md
[link_mcp_cve_project_cve_2026_57139]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57139.md
[link_mcp_cve_project_cve_2026_57112]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-57112.md
[link_mcp_cve_project_cve_2026_56274]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-56274.md
[link_mcp_cve_project_cve_2026_55887]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55887.md
[link_mcp_cve_project_cve_2026_55837]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55837.md
[link_mcp_cve_project_cve_2026_55786]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55786.md
[link_mcp_cve_project_cve_2026_55640]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55640.md
[link_mcp_cve_project_cve_2026_55637]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55637.md
[link_mcp_cve_project_cve_2026_55609]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55609.md
[link_mcp_cve_project_cve_2026_55608]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55608.md
[link_mcp_cve_project_cve_2026_55605]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55605.md
[link_mcp_cve_project_cve_2026_55604]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55604.md
[link_mcp_cve_project_cve_2026_55582]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55582.md
[link_mcp_cve_project_cve_2026_55581]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55581.md
[link_mcp_cve_project_cve_2026_55580]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55580.md
[link_mcp_cve_project_cve_2026_55557]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55557.md
[link_mcp_cve_project_cve_2026_55550]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55550.md
[link_mcp_cve_project_cve_2026_55546]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55546.md
[link_mcp_cve_project_cve_2026_55544]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55544.md
[link_mcp_cve_project_cve_2026_55532]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55532.md
[link_mcp_cve_project_cve_2026_55531]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55531.md
[link_mcp_cve_project_cve_2026_55529]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55529.md
[link_mcp_cve_project_cve_2026_55157]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55157.md
[link_mcp_cve_project_cve_2026_55156]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55156.md
[link_mcp_cve_project_cve_2026_55096]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55096.md
[link_mcp_cve_project_cve_2026_55071]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-55071.md
[link_mcp_cve_project_cve_2026_54842]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54842.md
[link_mcp_cve_project_cve_2026_54785]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54785.md
[link_mcp_cve_project_cve_2026_54689]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54689.md
[link_mcp_cve_project_cve_2026_54688]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54688.md
[link_mcp_cve_project_cve_2026_54618]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54618.md
[link_mcp_cve_project_cve_2026_54561]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54561.md
[link_mcp_cve_project_cve_2026_54549]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54549.md
[link_mcp_cve_project_cve_2026_54547]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54547.md
[link_mcp_cve_project_cve_2026_54504]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54504.md
[link_mcp_cve_project_cve_2026_54450]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54450.md
[link_mcp_cve_project_cve_2026_54449]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54449.md
[link_mcp_cve_project_cve_2026_54446]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54446.md
[link_mcp_cve_project_cve_2026_54309]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54309.md
[link_mcp_cve_project_cve_2026_54149]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54149.md
[link_mcp_cve_project_cve_2026_54140]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54140.md
[link_mcp_cve_project_cve_2026_54052]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54052.md
[link_mcp_cve_project_cve_2026_54030]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-54030.md
[link_mcp_cve_project_cve_2026_53965]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53965.md
[link_mcp_cve_project_cve_2026_53957]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53957.md
[link_mcp_cve_project_cve_2026_53937]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53937.md
[link_mcp_cve_project_cve_2026_53840]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53840.md
[link_mcp_cve_project_cve_2026_53820]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53820.md
[link_mcp_cve_project_cve_2026_53818]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53818.md
[link_mcp_cve_project_cve_2026_53814]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53814.md
[link_mcp_cve_project_cve_2026_53766]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53766.md
[link_mcp_cve_project_cve_2026_53710]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53710.md
[link_mcp_cve_project_cve_2026_53518]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53518.md
[link_mcp_cve_project_cve_2026_53512]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53512.md
[link_mcp_cve_project_cve_2026_53509]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-53509.md
[link_mcp_cve_project_cve_2026_52870]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-52870.md
[link_mcp_cve_project_cve_2026_52869]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-52869.md
[link_mcp_cve_project_cve_2026_52830]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-52830.md
[link_mcp_cve_project_cve_2026_51994]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-51994.md
[link_mcp_cve_project_cve_2026_50758]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-50758.md
[link_mcp_cve_project_cve_2026_50287]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-50287.md
[link_mcp_cve_project_cve_2026_50158]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-50158.md
[link_mcp_cve_project_cve_2026_50143]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-50143.md
[link_mcp_cve_project_cve_2026_50125]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-50125.md
[link_mcp_cve_project_cve_2026_50027]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-50027.md
[link_mcp_cve_project_cve_2026_49988]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49988.md
[link_mcp_cve_project_cve_2026_49986]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49986.md
[link_mcp_cve_project_cve_2026_49857]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49857.md
[link_mcp_cve_project_cve_2026_49856]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49856.md
[link_mcp_cve_project_cve_2026_49471]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49471.md
[link_mcp_cve_project_cve_2026_49357]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49357.md
[link_mcp_cve_project_cve_2026_49353]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49353.md
[link_mcp_cve_project_cve_2026_49291]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49291.md
[link_mcp_cve_project_cve_2026_49257]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-49257.md
[link_mcp_cve_project_cve_2026_48989]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48989.md
[link_mcp_cve_project_cve_2026_48814]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48814.md
[link_mcp_cve_project_cve_2026_48787]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48787.md
[link_mcp_cve_project_cve_2026_48774]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48774.md
[link_mcp_cve_project_cve_2026_48710]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48710.md
[link_mcp_cve_project_cve_2026_48529]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48529.md
[link_mcp_cve_project_cve_2026_48039]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-48039.md
[link_mcp_cve_project_cve_2026_47769]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47769.md
[link_mcp_cve_project_cve_2026_47751]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47751.md
[link_mcp_cve_project_cve_2026_47708]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47708.md
[link_mcp_cve_project_cve_2026_47427]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47427.md
[link_mcp_cve_project_cve_2026_47394]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47394.md
[link_mcp_cve_project_cve_2026_47388]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47388.md
[link_mcp_cve_project_cve_2026_47250]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-47250.md
[link_mcp_cve_project_cve_2026_46555]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46555.md
[link_mcp_cve_project_cve_2026_46549]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46549.md
[link_mcp_cve_project_cve_2026_46519]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46519.md
[link_mcp_cve_project_cve_2026_46515]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46515.md
[link_mcp_cve_project_cve_2026_46514]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46514.md
[link_mcp_cve_project_cve_2026_46513]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46513.md
[link_mcp_cve_project_cve_2026_46512]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46512.md
[link_mcp_cve_project_cve_2026_46341]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46341.md
[link_mcp_cve_project_cve_2026_46339]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-46339.md
[link_mcp_cve_project_cve_2026_45805]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45805.md
[link_mcp_cve_project_cve_2026_45781]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45781.md
[link_mcp_cve_project_cve_2026_45707]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45707.md
[link_mcp_cve_project_cve_2026_45609]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45609.md
[link_mcp_cve_project_cve_2026_45582]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45582.md
[link_mcp_cve_project_cve_2026_45555]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45555.md
[link_mcp_cve_project_cve_2026_45350]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45350.md
[link_mcp_cve_project_cve_2026_45019]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45019.md
[link_mcp_cve_project_cve_2026_45018]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45018.md
[link_mcp_cve_project_cve_2026_45001]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-45001.md
[link_mcp_cve_project_cve_2026_44998]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44998.md
[link_mcp_cve_project_cve_2026_44995]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44995.md
[link_mcp_cve_project_cve_2026_44970]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44970.md
[link_mcp_cve_project_cve_2026_44969]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44969.md
[link_mcp_cve_project_cve_2026_44968]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44968.md
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
[link_mcp_cve_project_cve_2026_44192]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44192.md
[link_mcp_cve_project_cve_2026_44118]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-44118.md
[link_mcp_cve_project_cve_2026_43995]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-43995.md
[link_mcp_cve_project_cve_2026_43992]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-43992.md
[link_mcp_cve_project_cve_2026_43989]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-43989.md
[link_mcp_cve_project_cve_2026_43901]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-43901.md
[link_mcp_cve_project_cve_2026_42856]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42856.md
[link_mcp_cve_project_cve_2026_42559]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42559.md
[link_mcp_cve_project_cve_2026_42449]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42449.md
[link_mcp_cve_project_cve_2026_42282]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42282.md
[link_mcp_cve_project_cve_2026_42271]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42271.md
[link_mcp_cve_project_cve_2026_42260]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42260.md
[link_mcp_cve_project_cve_2026_42236]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42236.md
[link_mcp_cve_project_cve_2026_42235]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42235.md
[link_mcp_cve_project_cve_2026_42230]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42230.md
[link_mcp_cve_project_cve_2026_42073]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-42073.md
[link_mcp_cve_project_cve_2026_41497]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-41497.md
[link_mcp_cve_project_cve_2026_41495]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-41495.md
[link_mcp_cve_project_cve_2026_41268]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-41268.md
[link_mcp_cve_project_cve_2026_40933]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40933.md
[link_mcp_cve_project_cve_2026_40775]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40775.md
[link_mcp_cve_project_cve_2026_40608]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40608.md
[link_mcp_cve_project_cve_2026_40576]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40576.md
[link_mcp_cve_project_cve_2026_40159]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-40159.md
[link_mcp_cve_project_cve_2026_39987]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39987.md
[link_mcp_cve_project_cve_2026_39974]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39974.md
[link_mcp_cve_project_cve_2026_39885]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39885.md
[link_mcp_cve_project_cve_2026_39884]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39884.md
[link_mcp_cve_project_cve_2026_39417]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39417.md
[link_mcp_cve_project_cve_2026_39313]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-39313.md
[link_mcp_cve_project_cve_2026_38924]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-38924.md
[link_mcp_cve_project_cve_2026_37006]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-37006.md
[link_mcp_cve_project_cve_2026_35674]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35674.md
[link_mcp_cve_project_cve_2026_35577]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35577.md
[link_mcp_cve_project_cve_2026_35568]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35568.md
[link_mcp_cve_project_cve_2026_35402]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35402.md
[link_mcp_cve_project_cve_2026_35394]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35394.md
[link_mcp_cve_project_cve_2026_35228]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-35228.md
[link_mcp_cve_project_cve_2026_34953]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34953.md
[link_mcp_cve_project_cve_2026_34939]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34939.md
[link_mcp_cve_project_cve_2026_34884]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-34884.md
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
[link_mcp_cve_project_cve_2026_32632]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32632.md
[link_mcp_cve_project_cve_2026_32625]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32625.md
[link_mcp_cve_project_cve_2026_32247]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32247.md
[link_mcp_cve_project_cve_2026_32211]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32211.md
[link_mcp_cve_project_cve_2026_32112]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32112.md
[link_mcp_cve_project_cve_2026_32111]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-32111.md
[link_mcp_cve_project_cve_2026_31951]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-31951.md
[link_mcp_cve_project_cve_2026_31945]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-31945.md
[link_mcp_cve_project_cve_2026_31944]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-31944.md
[link_mcp_cve_project_cve_2026_31841]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-31841.md
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
[link_mcp_cve_project_cve_2026_29872]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-29872.md
[link_mcp_cve_project_cve_2026_29791]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-29791.md
[link_mcp_cve_project_cve_2026_29787]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-29787.md
[link_mcp_cve_project_cve_2026_29783]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-29783.md
[link_mcp_cve_project_cve_2026_28361]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-28361.md
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
[link_mcp_cve_project_cve_2026_24052]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-24052.md
[link_mcp_cve_project_cve_2026_23882]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-23882.md
[link_mcp_cve_project_cve_2026_23744]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-23744.md
[link_mcp_cve_project_cve_2026_23523]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-23523.md
[link_mcp_cve_project_cve_2026_22793]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22793.md
[link_mcp_cve_project_cve_2026_22792]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22792.md
[link_mcp_cve_project_cve_2026_22785]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22785.md
[link_mcp_cve_project_cve_2026_22688]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22688.md
[link_mcp_cve_project_cve_2026_22252]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-22252.md
[link_mcp_cve_project_cve_2026_21852]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-21852.md
[link_mcp_cve_project_cve_2026_21518]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-21518.md
[link_mcp_cve_project_cve_2026_20205]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-20205.md
[link_mcp_cve_project_cve_2026_19984]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19984.md
[link_mcp_cve_project_cve_2026_19801]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19801.md
[link_mcp_cve_project_cve_2026_19753]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19753.md
[link_mcp_cve_project_cve_2026_19752]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19752.md
[link_mcp_cve_project_cve_2026_19751]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19751.md
[link_mcp_cve_project_cve_2026_19591]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19591.md
[link_mcp_cve_project_cve_2026_19516]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19516.md
[link_mcp_cve_project_cve_2026_19338]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19338.md
[link_mcp_cve_project_cve_2026_19337]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19337.md
[link_mcp_cve_project_cve_2026_19332]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19332.md
[link_mcp_cve_project_cve_2026_19329]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19329.md
[link_mcp_cve_project_cve_2026_19279]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19279.md
[link_mcp_cve_project_cve_2026_19270]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19270.md
[link_mcp_cve_project_cve_2026_19268]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19268.md
[link_mcp_cve_project_cve_2026_19263]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19263.md
[link_mcp_cve_project_cve_2026_19244]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19244.md
[link_mcp_cve_project_cve_2026_19041]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19041.md
[link_mcp_cve_project_cve_2026_19040]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19040.md
[link_mcp_cve_project_cve_2026_19039]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-19039.md
[link_mcp_cve_project_cve_2026_18954]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-18954.md
[link_mcp_cve_project_cve_2026_18905]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-18905.md
[link_mcp_cve_project_cve_2026_18655]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-18655.md
[link_mcp_cve_project_cve_2026_18489]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-18489.md
[link_mcp_cve_project_cve_2026_18486]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-18486.md
[link_mcp_cve_project_cve_2026_18482]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-18482.md
[link_mcp_cve_project_cve_2026_17626]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-17626.md
[link_mcp_cve_project_cve_2026_17623]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-17623.md
[link_mcp_cve_project_cve_2026_17433]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-17433.md
[link_mcp_cve_project_cve_2026_16584]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-16584.md
[link_mcp_cve_project_cve_2026_16496]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-16496.md
[link_mcp_cve_project_cve_2026_16133]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-16133.md
[link_mcp_cve_project_cve_2026_15988]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15988.md
[link_mcp_cve_project_cve_2026_15829]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15829.md
[link_mcp_cve_project_cve_2026_15751]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15751.md
[link_mcp_cve_project_cve_2026_15750]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15750.md
[link_mcp_cve_project_cve_2026_15749]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15749.md
[link_mcp_cve_project_cve_2026_15643]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15643.md
[link_mcp_cve_project_cve_2026_15583]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15583.md
[link_mcp_cve_project_cve_2026_15501]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15501.md
[link_mcp_cve_project_cve_2026_15415]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15415.md
[link_mcp_cve_project_cve_2026_15189]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15189.md
[link_mcp_cve_project_cve_2026_15138]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15138.md
[link_mcp_cve_project_cve_2026_15015]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-15015.md
[link_mcp_cve_project_cve_2026_14748]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-14748.md
[link_mcp_cve_project_cve_2026_14541]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-14541.md
[link_mcp_cve_project_cve_2026_14540]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-14540.md
[link_mcp_cve_project_cve_2026_14539]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-14539.md
[link_mcp_cve_project_cve_2026_14538]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-14538.md
[link_mcp_cve_project_cve_2026_14537]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-14537.md
[link_mcp_cve_project_cve_2026_14471]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-14471.md
[link_mcp_cve_project_cve_2026_13524]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-13524.md
[link_mcp_cve_project_cve_2026_13489]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-13489.md
[link_mcp_cve_project_cve_2026_13341]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-13341.md
[link_mcp_cve_project_cve_2026_12958]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12958.md
[link_mcp_cve_project_cve_2026_12957]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12957.md
[link_mcp_cve_project_cve_2026_12940]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12940.md
[link_mcp_cve_project_cve_2026_12798]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12798.md
[link_mcp_cve_project_cve_2026_12774]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12774.md
[link_mcp_cve_project_cve_2026_12773]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12773.md
[link_mcp_cve_project_cve_2026_12763]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12763.md
[link_mcp_cve_project_cve_2026_12537]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12537.md
[link_mcp_cve_project_cve_2026_12112]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-12112.md
[link_mcp_cve_project_cve_2026_11719]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-11719.md
[link_mcp_cve_project_cve_2026_11624]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-11624.md
[link_mcp_cve_project_cve_2026_10789]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-10789.md
[link_mcp_cve_project_cve_2026_10750]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-10750.md
[link_mcp_cve_project_cve_2026_10280]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-10280.md
[link_mcp_cve_project_cve_2026_10277]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-10277.md
[link_mcp_cve_project_cve_2026_9810]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-9810.md
[link_mcp_cve_project_cve_2026_9739]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-9739.md
[link_mcp_cve_project_cve_2026_9680]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-9680.md
[link_mcp_cve_project_cve_2026_9467]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-9467.md
[link_mcp_cve_project_cve_2026_9186]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-9186.md
[link_mcp_cve_project_cve_2026_9135]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-9135.md
[link_mcp_cve_project_cve_2026_9077]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-9077.md
[link_mcp_cve_project_cve_2026_8719]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-8719.md
[link_mcp_cve_project_cve_2026_8446]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-8446.md
[link_mcp_cve_project_cve_2026_8355]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-8355.md
[link_mcp_cve_project_cve_2026_7812]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7812.md
[link_mcp_cve_project_cve_2026_7811]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7811.md
[link_mcp_cve_project_cve_2026_7788]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7788.md
[link_mcp_cve_project_cve_2026_7755]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7755.md
[link_mcp_cve_project_cve_2026_7738]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7738.md
[link_mcp_cve_project_cve_2026_7730]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7730.md
[link_mcp_cve_project_cve_2026_7729]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7729.md
[link_mcp_cve_project_cve_2026_7728]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7728.md
[link_mcp_cve_project_cve_2026_7715]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7715.md
[link_mcp_cve_project_cve_2026_7664]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7664.md
[link_mcp_cve_project_cve_2026_7663]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7663.md
[link_mcp_cve_project_cve_2026_7653]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7653.md
[link_mcp_cve_project_cve_2026_7646]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7646.md
[link_mcp_cve_project_cve_2026_7645]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7645.md
[link_mcp_cve_project_cve_2026_7642]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7642.md
[link_mcp_cve_project_cve_2026_7628]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7628.md
[link_mcp_cve_project_cve_2026_7627]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7627.md
[link_mcp_cve_project_cve_2026_7600]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7600.md
[link_mcp_cve_project_cve_2026_7599]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7599.md
[link_mcp_cve_project_cve_2026_7594]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7594.md
[link_mcp_cve_project_cve_2026_7593]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7593.md
[link_mcp_cve_project_cve_2026_7591]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7591.md
[link_mcp_cve_project_cve_2026_7446]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7446.md
[link_mcp_cve_project_cve_2026_7445]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7445.md
[link_mcp_cve_project_cve_2026_7443]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7443.md
[link_mcp_cve_project_cve_2026_7417]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7417.md
[link_mcp_cve_project_cve_2026_7416]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7416.md
[link_mcp_cve_project_cve_2026_7404]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7404.md
[link_mcp_cve_project_cve_2026_7386]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7386.md
[link_mcp_cve_project_cve_2026_7318]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7318.md
[link_mcp_cve_project_cve_2026_7272]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7272.md
[link_mcp_cve_project_cve_2026_7237]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7237.md
[link_mcp_cve_project_cve_2026_7221]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7221.md
[link_mcp_cve_project_cve_2026_7215]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7215.md
[link_mcp_cve_project_cve_2026_7211]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-7211.md
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
[link_mcp_cve_project_cve_2026_6130]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-6130.md
[link_mcp_cve_project_cve_2026_6118]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-6118.md
[link_mcp_cve_project_cve_2026_6108]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-6108.md
[link_mcp_cve_project_cve_2026_5833]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5833.md
[link_mcp_cve_project_cve_2026_5802]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5802.md
[link_mcp_cve_project_cve_2026_5619]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5619.md
[link_mcp_cve_project_cve_2026_5607]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5607.md
[link_mcp_cve_project_cve_2026_5470]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5470.md
[link_mcp_cve_project_cve_2026_5379]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5379.md
[link_mcp_cve_project_cve_2026_5374]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5374.md
[link_mcp_cve_project_cve_2026_5323]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5323.md
[link_mcp_cve_project_cve_2026_5322]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5322.md
[link_mcp_cve_project_cve_2026_5059]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5059.md
[link_mcp_cve_project_cve_2026_5058]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5058.md
[link_mcp_cve_project_cve_2026_5029]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5029.md
[link_mcp_cve_project_cve_2026_5023]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5023.md
[link_mcp_cve_project_cve_2026_5007]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-5007.md
[link_mcp_cve_project_cve_2026_4593]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4593.md
[link_mcp_cve_project_cve_2026_4496]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4496.md
[link_mcp_cve_project_cve_2026_4339]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4339.md
[link_mcp_cve_project_cve_2026_4270]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4270.md
[link_mcp_cve_project_cve_2026_4199]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4199.md
[link_mcp_cve_project_cve_2026_4198]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-4198.md
[link_mcp_cve_project_cve_2026_2178]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-2178.md
[link_mcp_cve_project_cve_2026_2130]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-2130.md
[link_mcp_cve_project_cve_2026_1977]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-1977.md
[link_mcp_cve_project_cve_2026_1721]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-1721.md
[link_mcp_cve_project_cve_2026_0758]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0758.md
[link_mcp_cve_project_cve_2026_0757]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0757.md
[link_mcp_cve_project_cve_2026_0756]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0756.md
[link_mcp_cve_project_cve_2026_0755]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0755.md
[link_mcp_cve_project_cve_2026_0621]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2026-0621.md
[link_mcp_cve_project_cve_2025_71427]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-71427.md
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
[link_mcp_cve_project_cve_2025_61489]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-61489.md
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
[link_mcp_cve_project_cve_2025_55346]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-55346.md
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
[link_mcp_cve_project_cve_2025_53098]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-53098.md
[link_mcp_cve_project_cve_2025_52573]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-52573.md
[link_mcp_cve_project_cve_2025_49596]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-49596.md
[link_mcp_cve_project_cve_2025_47777]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-47777.md
[link_mcp_cve_project_cve_2025_47274]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-47274.md
[link_mcp_cve_project_cve_2025_35028]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-35028.md
[link_mcp_cve_project_cve_2025_34072]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-34072.md
[link_mcp_cve_project_cve_2025_20381]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-20381.md
[link_mcp_cve_project_cve_2025_15063]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-15063.md
[link_mcp_cve_project_cve_2025_15061]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-15061.md
[link_mcp_cve_project_cve_2025_13822]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-13822.md
[link_mcp_cve_project_cve_2025_11445]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-11445.md
[link_mcp_cve_project_cve_2025_11286]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-11286.md
[link_mcp_cve_project_cve_2025_10619]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-10619.md
[link_mcp_cve_project_cve_2025_10193]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-10193.md
[link_mcp_cve_project_cve_2025_9654]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-9654.md
[link_mcp_cve_project_cve_2025_9611]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-9611.md
[link_mcp_cve_project_cve_2025_8943]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-8943.md
[link_mcp_cve_project_cve_2025_8665]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-8665.md
[link_mcp_cve_project_cve_2025_6515]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-6515.md
[link_mcp_cve_project_cve_2025_6514]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-6514.md
[link_mcp_cve_project_cve_2025_5277]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-5277.md
[link_mcp_cve_project_cve_2025_5276]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-5276.md
[link_mcp_cve_project_cve_2025_5273]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-5273.md
[link_mcp_cve_project_cve_2025_4143]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/CVE-2025-4143.md

[link_ghsa_22jm_h49p_29qw]: https://github.com/advisories/GHSA-22jm-h49p-29qw
[link_ghsa_24mc_g4xr_4395]: https://github.com/advisories/GHSA-24mc-g4xr-4395
[link_ghsa_2c7f_fxww_6w6c]: https://github.com/advisories/GHSA-2c7f-fxww-6w6c
[link_ghsa_2h44_8472_frjj]: https://github.com/advisories/GHSA-2h44-8472-frjj
[link_ghsa_2v2f_mvfg_ph56]: https://github.com/advisories/GHSA-2v2f-mvfg-ph56
[link_ghsa_2xhg_73j7_rrgx]: https://github.com/advisories/GHSA-2xhg-73j7-rrgx
[link_ghsa_2xj6_xx86_cwwc]: https://github.com/advisories/GHSA-2xj6-xx86-cwwc
[link_ghsa_33f5_2c5q_wgwj]: https://github.com/advisories/GHSA-33f5-2c5q-wgwj
[link_ghsa_345p_7cg4_v4c7]: https://github.com/advisories/GHSA-345p-7cg4-v4c7
[link_ghsa_39w2_rjm5_chcv]: https://github.com/advisories/GHSA-39w2-rjm5-chcv
[link_ghsa_3jxw_vj8m_8x77]: https://github.com/advisories/GHSA-3jxw-vj8m-8x77
[link_ghsa_3m7m_37xf_xp9x]: https://github.com/advisories/GHSA-3m7m-37xf-xp9x
[link_ghsa_3q26_f695_pp76]: https://github.com/advisories/GHSA-3q26-f695-pp76
[link_ghsa_3r68_hf9h_887v]: https://github.com/advisories/GHSA-3r68-hf9h-887v
[link_ghsa_43r2_c7g8_prc8]: https://github.com/advisories/GHSA-43r2-c7g8-prc8
[link_ghsa_4478_h5jv_647m]: https://github.com/advisories/GHSA-4478-h5jv-647m
[link_ghsa_4596_2p6p_28cv]: https://github.com/advisories/GHSA-4596-2p6p-28cv
[link_ghsa_45gf_fjxp_cjpq]: https://github.com/advisories/GHSA-45gf-fjxp-cjpq
[link_ghsa_46jr_4wx8_v453]: https://github.com/advisories/GHSA-46jr-4wx8-v453
[link_ghsa_489g_7rxv_6c8q]: https://github.com/advisories/GHSA-489g-7rxv-6c8q
[link_ghsa_49xv_9743_pw8w]: https://github.com/advisories/GHSA-49xv-9743-pw8w
[link_ghsa_4f6c_2vvp_gw82]: https://github.com/advisories/GHSA-4f6c-2vvp-gw82
[link_ghsa_4prq_p2x5_w9fh]: https://github.com/advisories/GHSA-4prq-p2x5-w9fh
[link_ghsa_4pvg_m42h_c3x2]: https://github.com/advisories/GHSA-4pvg-m42h-c3x2
[link_ghsa_4x39_xh35_w96w]: https://github.com/advisories/GHSA-4x39-xh35-w96w
[link_ghsa_4x8c_5vv7_973f]: https://github.com/advisories/GHSA-4x8c-5vv7-973f
[link_ghsa_595q_jv4r_q7j9]: https://github.com/advisories/GHSA-595q-jv4r-q7j9
[link_ghsa_5h93_6whr_6q8j]: https://github.com/advisories/GHSA-5h93-6whr-6q8j
[link_ghsa_5jr4_xmvf_frmj]: https://github.com/advisories/GHSA-5jr4-xmvf-frmj
[link_ghsa_5qg7_j8mr_9477]: https://github.com/advisories/GHSA-5qg7-j8mr-9477
[link_ghsa_5r62_gj48_897x]: https://github.com/advisories/GHSA-5r62-gj48-897x
[link_ghsa_5wf4_jqxh_8gm3]: https://github.com/advisories/GHSA-5wf4-jqxh-8gm3
[link_ghsa_6529_c226_h328]: https://github.com/advisories/GHSA-6529-c226-h328
[link_ghsa_65h7_9wrw_629c]: https://github.com/advisories/GHSA-65h7-9wrw-629c
[link_ghsa_6cr4_ccf3_x7h4]: https://github.com/advisories/GHSA-6cr4-ccf3-x7h4
[link_ghsa_6fwv_3h4c_37j9]: https://github.com/advisories/GHSA-6fwv-3h4c-37j9
[link_ghsa_6mx4_4h42_r8vh]: https://github.com/advisories/GHSA-6mx4-4h42-r8vh
[link_ghsa_6prh_2h8m_c8cw]: https://github.com/advisories/GHSA-6prh-2h8m-c8cw
[link_ghsa_6qxp_vccf_f47h]: https://github.com/advisories/GHSA-6qxp-vccf-f47h
[link_ghsa_6vmq_24h2_pj7j]: https://github.com/advisories/GHSA-6vmq-24h2-pj7j
[link_ghsa_6xpm_ggf7_wc3p]: https://github.com/advisories/GHSA-6xpm-ggf7-wc3p
[link_ghsa_72fm_whvq_jghf]: https://github.com/advisories/GHSA-72FM-WHVQ-JGHF
[link_ghsa_737x_cwfr_5vvc]: https://github.com/advisories/GHSA-737x-cwfr-5vvc
[link_ghsa_74gp_qhv5_v493]: https://github.com/advisories/GHSA-74gp-qhv5-v493
[link_ghsa_76pc_mqxp_3rq5]: https://github.com/advisories/GHSA-76pc-mqxp-3rq5
[link_ghsa_76pm_mq2q_9gcr]: https://github.com/advisories/GHSA-76pm-mq2q-9gcr
[link_ghsa_76pr_5669_3xf5]: https://github.com/advisories/GHSA-76pr-5669-3xf5
[link_ghsa_798p_78g2_v556]: https://github.com/advisories/GHSA-798p-78g2-v556
[link_ghsa_7f8r_222p_6f5g]: https://github.com/advisories/GHSA-7f8r-222p-6f5g
[link_ghsa_7hp6_4w63_5g45]: https://github.com/advisories/GHSA-7hp6-4w63-5g45
[link_ghsa_7w94_79vh_5mr2]: https://github.com/advisories/GHSA-7w94-79vh-5mr2
[link_ghsa_82wg_qcm4_fp2w]: https://github.com/advisories/GHSA-82wg-qcm4-fp2w
[link_ghsa_84c9_qqpq_2pq5]: https://github.com/advisories/GHSA-84c9-qqpq-2pq5
[link_ghsa_84m7_p3x7_pcfv]: https://github.com/advisories/GHSA-84m7-p3x7-pcfv
[link_ghsa_8764_fh3m_wf7g]: https://github.com/advisories/GHSA-8764-fh3m-wf7g
[link_ghsa_8wx6_g25r_2943]: https://github.com/advisories/GHSA-8wx6-g25r-2943
[link_ghsa_93xw_j965_9mx3]: https://github.com/advisories/GHSA-93xw-j965-9mx3
[link_ghsa_95vg_3r9c_2v5q]: https://github.com/advisories/GHSA-95vg-3r9c-2v5q
[link_ghsa_9c83_rr99_vfwj]: https://github.com/advisories/GHSA-9c83-rr99-vfwj
[link_ghsa_9g45_5xwm_f3wc]: https://github.com/advisories/GHSA-9g45-5xwm-f3wc
[link_ghsa_9g6v_r3xf_673q]: https://github.com/advisories/GHSA-9g6v-r3xf-673q
[link_ghsa_9gfj_28hw_jchp]: https://github.com/advisories/GHSA-9gfj-28hw-jchp
[link_ghsa_9h52_p55h_vw2f]: https://github.com/advisories/GHSA-9h52-p55h-vw2f
[link_ghsa_9jww_cxg5_rj9m]: https://github.com/advisories/GHSA-9jww-cxg5-rj9m
[link_ghsa_9pj6_vhgr_3mwh]: https://github.com/advisories/GHSA-9PJ6-VHGR-3MWH
[link_ghsa_9vhv_g5hf_m7m7]: https://github.com/advisories/GHSA-9vhv-g5hf-m7m7
[link_ghsa_c5xx_h28h_f682]: https://github.com/advisories/GHSA-c5xx-h28h-f682
[link_ghsa_cc5h_2pwp_pvcc]: https://github.com/advisories/GHSA-cc5h-2pwp-pvcc
[link_ghsa_ccrj_frp2_c945]: https://github.com/advisories/GHSA-ccrj-frp2-c945
[link_ghsa_ch2q_6x56_qg5r]: https://github.com/advisories/GHSA-ch2q-6x56-qg5r
[link_ghsa_cr22_wjx7_2w6m]: https://github.com/advisories/GHSA-CR22-WJX7-2W6M
[link_ghsa_cv3r_c5h8_f4g5]: https://github.com/advisories/GHSA-cv3r-c5h8-f4g5
[link_ghsa_cvp8_vvgf_69q4]: https://github.com/advisories/GHSA-cvp8-vvgf-69q4
[link_ghsa_f26r_j276_ggg4]: https://github.com/advisories/GHSA-f26r-j276-ggg4
[link_ghsa_f47c_p7wj_q7gx]: https://github.com/advisories/GHSA-f47c-p7wj-q7gx
[link_ghsa_f4p7_qx46_wc5j]: https://github.com/advisories/GHSA-f4p7-qx46-wc5j
[link_ghsa_f6pj_qv47_g96w]: https://github.com/advisories/GHSA-f6pj-qv47-g96w
[link_ghsa_f87g_xv8r_7p7x]: https://github.com/advisories/GHSA-f87g-xv8r-7p7x
[link_ghsa_ff5q_5r4v_fw4v]: https://github.com/advisories/GHSA-ff5q-5r4v-fw4v
[link_ghsa_fm8p_53ww_hf6w]: https://github.com/advisories/GHSA-fm8p-53ww-hf6w
[link_ghsa_fmmv_w9g8_j3gc]: https://github.com/advisories/GHSA-fmmv-w9g8-j3gc
[link_ghsa_fmvx_487g_mrww]: https://github.com/advisories/GHSA-fmvx-487g-mrww
[link_ghsa_fph8_pg5w_78fv]: https://github.com/advisories/GHSA-fph8-pg5w-78fv
[link_ghsa_g2gw_q38m_vjfc]: https://github.com/advisories/GHSA-g2gw-q38m-vjfc
[link_ghsa_g2r2_3j32_j27x]: https://github.com/advisories/GHSA-g2r2-3j32-j27x
[link_ghsa_g5xv_mhgm_v5f6]: https://github.com/advisories/GHSA-g5xv-mhgm-v5f6
[link_ghsa_g6j9_89xv_v752]: https://github.com/advisories/GHSA-g6j9-89xv-v752
[link_ghsa_h4mw_j7qp_8mwm]: https://github.com/advisories/GHSA-h4mw-j7qp-8mwm
[link_ghsa_h7c4_q426_7jh9]: https://github.com/advisories/GHSA-h7c4-q426-7jh9
[link_ghsa_h7wj_5v37_59r2]: https://github.com/advisories/GHSA-h7wj-5v37-59r2
[link_ghsa_hc55_p739_j48w]: https://github.com/advisories/GHSA-hc55-p739-j48w
[link_ghsa_hgcf_4mq8_5266]: https://github.com/advisories/GHSA-hgcf-4mq8-5266
[link_ghsa_hvfh_5mj3_5f3j]: https://github.com/advisories/GHSA-hvfh-5mj3-5f3j
[link_ghsa_hvrp_rf83_w775]: https://github.com/advisories/GHSA-hvrp-rf83-w775
[link_ghsa_hwhg_mrjc_8g43]: https://github.com/advisories/GHSA-hwhg-mrjc-8g43
[link_ghsa_hxpf_9xvq_wph8]: https://github.com/advisories/GHSA-hxpf-9xvq-wph8
[link_ghsa_j656_3hf2_fvjc]: https://github.com/advisories/GHSA-j656-3hf2-fvjc
[link_ghsa_j99q_93c9_h869]: https://github.com/advisories/GHSA-j99q-93c9-h869
[link_ghsa_j9xx_59ph_wmr6]: https://github.com/advisories/GHSA-j9xx-59ph-wmr6
[link_ghsa_jgh3_fggc_mcpm]: https://github.com/advisories/GHSA-jgh3-fggc-mcpm
[link_ghsa_jgj3_97w2_9v9r]: https://github.com/advisories/GHSA-jgj3-97w2-9v9r
[link_ghsa_jj4w_pfgv_4mrm]: https://github.com/advisories/GHSA-jj4w-pfgv-4mrm
[link_ghsa_jjhp_8crj_mppq]: https://github.com/advisories/GHSA-jjhp-8crj-mppq
[link_ghsa_jm63_cq47_j5jp]: https://github.com/advisories/GHSA-jm63-cq47-j5jp
[link_ghsa_jpw9_pfvf_9f58]: https://github.com/advisories/GHSA-jpw9-pfvf-9f58
[link_ghsa_jr33_mw75_7j8f]: https://github.com/advisories/GHSA-jr33-mw75-7j8f
[link_ghsa_m922_r24v_6wff]: https://github.com/advisories/GHSA-m922-r24v-6wff
[link_ghsa_mfv2_4wvm_9pgp]: https://github.com/advisories/GHSA-mfv2-4wvm-9pgp
[link_ghsa_mj45_84p2_v77q]: https://github.com/advisories/GHSA-mj45-84p2-v77q
[link_ghsa_mrg2_4747_fmpw]: https://github.com/advisories/GHSA-mrg2-4747-fmpw
[link_ghsa_mrq8_fv7v_hhjg]: https://github.com/advisories/GHSA-MRQ8-FV7V-HHJG
[link_ghsa_mrvx_jmjw_vggc]: https://github.com/advisories/GHSA-mrvx-jmjw-vggc
[link_ghsa_mwwr_p57h_56pf]: https://github.com/advisories/GHSA-mwwr-p57h-56pf
[link_ghsa_p6hp_93wp_fh6p]: https://github.com/advisories/GHSA-p6hp-93wp-fh6p
[link_ghsa_pjp5_fpmr_3349]: https://github.com/advisories/GHSA-pjp5-fpmr-3349
[link_ghsa_pph6_vfjv_vpjw]: https://github.com/advisories/GHSA-pph6-vfjv-vpjw
[link_ghsa_pqh8_4pj7_32xx]: https://github.com/advisories/GHSA-pqh8-4pj7-32xx
[link_ghsa_pqmg_rq46_vm4m]: https://github.com/advisories/GHSA-pqmg-rq46-vm4m
[link_ghsa_pr64_jmmf_jp54]: https://github.com/advisories/GHSA-pr64-jmmf-jp54
[link_ghsa_pr6h_vr44_xq8j]: https://github.com/advisories/GHSA-pr6h-vr44-xq8j
[link_ghsa_q344_5v34_gm84]: https://github.com/advisories/GHSA-q344-5v34-gm84
[link_ghsa_q87f_qc2r_2gw4]: https://github.com/advisories/GHSA-q87f-qc2r-2gw4
[link_ghsa_q978_78c7_phqw]: https://github.com/advisories/GHSA-q978-78c7-phqw
[link_ghsa_qg2g_g9w3_m5h8]: https://github.com/advisories/GHSA-qg2g-g9w3-m5h8
[link_ghsa_qpgh_hp5g_4vwp]: https://github.com/advisories/GHSA-qpgh-hp5g-4vwp
[link_ghsa_qvw8_w937_vcmq]: https://github.com/advisories/GHSA-qvw8-w937-vcmq
[link_ghsa_qw5r_ppcg_f8rj]: https://github.com/advisories/GHSA-qw5r-ppcg-f8rj
[link_ghsa_qwr9_cj2c_v3fv]: https://github.com/advisories/GHSA-qwr9-cj2c-v3fv
[link_ghsa_qx49_fqc8_xw99]: https://github.com/advisories/GHSA-qx49-fqc8-xw99
[link_ghsa_r3g7_r4hr_m258]: https://github.com/advisories/GHSA-r3g7-r4hr-m258
[link_ghsa_r57g_mc79_8hj2]: https://github.com/advisories/GHSA-r57g-mc79-8hj2
[link_ghsa_r6hp_67wp_c7jx]: https://github.com/advisories/GHSA-r6hp-67wp-c7jx
[link_ghsa_r6mm_377j_qg8m]: https://github.com/advisories/GHSA-r6mm-377j-qg8m
[link_ghsa_rqfv_2mw9_78g2]: https://github.com/advisories/GHSA-rqfv-2mw9-78g2
[link_ghsa_rqwg_9346_fjjv]: https://github.com/advisories/GHSA-rqwg-9346-fjjv
[link_ghsa_rvq5_wwqv_78pq]: https://github.com/advisories/GHSA-rvq5-wwqv-78pq
[link_ghsa_rwrf_2pqf_9j8j]: https://github.com/advisories/GHSA-rwrf-2pqf-9j8j
[link_ghsa_v3f4_w7r7_v3hm]: https://github.com/advisories/GHSA-v3f4-w7r7-v3hm
[link_ghsa_v9m3_wfh8_5646]: https://github.com/advisories/GHSA-v9m3-wfh8-5646
[link_ghsa_vc25_24vv_fxxm]: https://github.com/advisories/GHSA-VC25-24VV-FXXM
[link_ghsa_vc32_4gwf_77xp]: https://github.com/advisories/GHSA-vc32-4gwf-77xp
[link_ghsa_vc8m_84rp_53hx]: https://github.com/advisories/GHSA-vc8m-84rp-53hx
[link_ghsa_vcwp_f9rq_3887]: https://github.com/advisories/GHSA-vcwp-f9rq-3887
[link_ghsa_vmp7_252j_cwp7]: https://github.com/advisories/GHSA-VMP7-252J-CWP7
[link_ghsa_vqff_r82h_9crc]: https://github.com/advisories/GHSA-vqff-r82h-9crc
[link_ghsa_vvr2_h2jp_838m]: https://github.com/advisories/GHSA-vvr2-h2jp-838m
[link_ghsa_vw82_7fv8_r6gp]: https://github.com/advisories/GHSA-vw82-7fv8-r6gp
[link_ghsa_w48q_cv73_mx4w]: https://github.com/advisories/GHSA-W48Q-CV73-MX4W
[link_ghsa_w4fh_qvv9_3v23]: https://github.com/advisories/GHSA-w4fh-qvv9-3v23
[link_ghsa_w66g_j6c4_hcfc]: https://github.com/advisories/GHSA-w66g-j6c4-hcfc
[link_ghsa_w794_rj3p_xv45]: https://github.com/advisories/GHSA-w794-rj3p-xv45
[link_ghsa_wcjj_9m6g_2fr2]: https://github.com/advisories/GHSA-wcjj-9m6g-2fr2
[link_ghsa_wm45_qh3g_v83f]: https://github.com/advisories/GHSA-wm45-qh3g-v83f
[link_ghsa_wppf_h75h_6pm6]: https://github.com/advisories/GHSA-wppf-h75h-6pm6
[link_ghsa_wrhw_j3f9_8vc6]: https://github.com/advisories/GHSA-wrhw-j3f9-8vc6
[link_ghsa_wv7p_j6qh_3hj4]: https://github.com/advisories/GHSA-wv7p-j6qh-3hj4
[link_ghsa_wv8v_v4c5_v75j]: https://github.com/advisories/GHSA-wv8v-v4c5-v75j
[link_ghsa_x65c_w438_c58f]: https://github.com/advisories/GHSA-x65c-w438-c58f
[link_ghsa_x7x8_95gh_42xm]: https://github.com/advisories/GHSA-x7x8-95gh-42xm
[link_ghsa_x9vc_9ffq_p3gj]: https://github.com/advisories/GHSA-x9vc-9ffq-p3gj
[link_ghsa_xcqx_9jf5_w339]: https://github.com/advisories/GHSA-xcqx-9jf5-w339
[link_ghsa_5cj9_fcqq_g2h7]: https://github.com/advisories/GHSA-5cj9-fcqq-g2h7
[link_ghsa_5gm3_9crp_6g3v]: https://github.com/advisories/GHSA-5gm3-9crp-6g3v
[link_ghsa_5m6c_38r8_5w76]: https://github.com/advisories/GHSA-5m6c-38r8-5w76
[link_ghsa_9hgc_g3w5_67cm]: https://github.com/advisories/GHSA-9hgc-g3w5-67cm
[link_ghsa_gjfv_h634_pxpv]: https://github.com/advisories/GHSA-gjfv-h634-pxpv
[link_ghsa_p7w7_4929_vpj5]: https://github.com/advisories/GHSA-p7w7-4929-vpj5
[link_ghsa_pc2w_4mq8_32qw]: https://github.com/advisories/GHSA-pc2w-4mq8-32qw
[link_ghsa_pgh9_49q4_hqcx]: https://github.com/advisories/GHSA-pgh9-49q4-hqcx
[link_ghsa_pqh8_p93p_2rx7]: https://github.com/advisories/GHSA-pqh8-p93p-2rx7
[link_ghsa_vhmw_fwrr_r6c6]: https://github.com/advisories/GHSA-vhmw-fwrr-r6c6
[link_ghsa_x5cc_8486_8qqx]: https://github.com/advisories/GHSA-x5cc-8486-8qqx
[link_ghsa_xf6j_693p_wqxx]: https://github.com/advisories/GHSA-xf6j-693p-wqxx
[link_ghsa_xrmj_5g4g_8987]: https://github.com/advisories/GHSA-xrmj-5g4g-8987
[link_ibm_cve_2026_18484]: https://www.ibm.com/support/pages/node/7294233
[link_patchstack_cve_2026_121576]: https://patchstack.com/database/wordpress/plugin/ai-workflow-automation-ai-agent-hub/vulnerability/wordpress-mcp-server-for-wordpress-plugin-2-0-1-privilege-escalation-vulnerability
[link_ghsa_xhcr_cqfr_m3hv]: https://github.com/advisories/GHSA-xhcr-cqfr-m3hv
[link_ghsa_xm98_3vcf_fph7]: https://github.com/advisories/GHSA-xm98-3vcf-fph7
[link_ghsa_xr72_j7vj_vp7g]: https://github.com/advisories/GHSA-xr72-j7vj-vp7g
[link_ghsa_xwmw_prc4_v3cr]: https://github.com/advisories/GHSA-xwmw-prc4-v3cr
[link_mcp_cve_project_ghsa_c9f9_cp8h_jcj5]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-c9f9-cp8h-jcj5.md
[link_mcp_cve_project_ghsa_h9j8_vj8g_v3gg]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-h9j8-vj8g-v3gg.md
[link_mcp_cve_project_ghsa_rwv7_mh2c_ff2p]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-rwv7-mh2c-ff2p.md
[link_mcp_cve_project_ghsa_2fw8_7jmw_r937]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-2fw8-7jmw-r937.md
[link_mcp_cve_project_ghsa_x863_g495_4cjc]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-x863-g495-4cjc.md
[link_mcp_cve_project_ghsa_w766_5x43_whvw]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-w766-5x43-whvw.md
[link_mcp_cve_project_ghsa_f897_62hf_6gxq]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-f897-62hf-6gxq.md
[link_mcp_cve_project_ghsa_3jqg_r5pp_rmp2]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-3jqg-r5pp-rmp2.md
[link_mcp_cve_project_ghsa_4gxg_m5jx_9j57]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-4gxg-m5jx-9j57.md
[link_mcp_cve_project_ghsa_53mr_w429_c597]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-53mr-w429-c597.md
[link_mcp_cve_project_ghsa_66qx_2266_pmj6]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-66qx-2266-pmj6.md
[link_mcp_cve_project_ghsa_7rgq_gccq_qphx]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-7rgq-gccq-qphx.md
[link_mcp_cve_project_ghsa_hhwq_wxfx_cj7g]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-hhwq-wxfx-cj7g.md
[link_mcp_cve_project_ghsa_mvf5_2qqv_rg3c]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-mvf5-2qqv-rg3c.md
[link_mcp_cve_project_ghsa_v38p_wf49_hx2j]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-v38p-wf49-hx2j.md
[link_mcp_cve_project_ghsa_5p52_q7pq_9fq2]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-5p52-q7pq-9fq2.md
[link_mcp_cve_project_ghsa_2rq8_f55p_j2jp]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-2rq8-f55p-j2jp.md
[link_mcp_cve_project_ghsa_4fc4_wcmh_4g86]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-4fc4-wcmh-4g86.md
[link_mcp_cve_project_ghsa_6x67_4w4w_9f3w]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-6x67-4w4w-9f3w.md
[link_mcp_cve_project_ghsa_8qgq_27v6_55w3]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-8qgq-27v6-55w3.md
[link_mcp_cve_project_ghsa_f6mc_jg3x_vq53]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-f6mc-jg3x-vq53.md
[link_mcp_cve_project_ghsa_m5pj_3536_3xcp]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-m5pj-3536-3xcp.md
[link_mcp_cve_project_ghsa_q978_78c7_phqw]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-q978-78c7-phqw.md
[link_mcp_cve_project_ghsa_vcc9_3xgm_p9v4]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-vcc9-3xgm-p9v4.md
[link_mcp_cve_project_ghsa_wmjf_2m46_2352]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-wmjf-2m46-2352.md
[link_mcp_cve_project_ghsa_2hm9_qff2_hrpj]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-2hm9-qff2-hrpj.md
[link_mcp_cve_project_ghsa_4432_vg92_fqh6]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-4432-vg92-fqh6.md
[link_mcp_cve_project_ghsa_hp8w_r5wh_cw9q]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-hp8w-r5wh-cw9q.md
[link_mcp_cve_project_ghsa_w83x_jw8h_w4rj]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-w83x-jw8h-w4rj.md
[link_mcp_cve_project_ghsa_c9xm_49cp_xcr9]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-c9xm-49cp-xcr9.md
[link_mcp_cve_project_ghsa_5648_rgj9_v224]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-5648-rgj9-v224.md
[link_mcp_cve_project_ghsa_7fx6_5m9f_89wg]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-7fx6-5m9f-89wg.md
[link_mcp_cve_project_ghsa_5q7x_232h_f834]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-5q7x-232h-f834.md
[link_mcp_cve_project_ghsa_xhcr_cqfr_m3hv]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-xhcr-cqfr-m3hv.md
[link_mcp_cve_project_ghsa_4m5j_jjfc_97gx]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-4m5j-jjfc-97gx.md
[link_mcp_cve_project_ghsa_4gph_2hhr_5mwg]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-4gph-2hhr-5mwg.md
[link_mcp_cve_project_ghsa_q382_vc8q_7jhj]: https://github.com/mcp-security-project/mcp-cve-project/blob/main/cves/GHSA-q382-vc8q-7jhj.md
[link_ghsa_c9f9_cp8h_jcj5]: https://github.com/modelcontextprotocol/rust-sdk/security/advisories/GHSA-c9f9-cp8h-jcj5
[link_ghsa_h9j8_vj8g_v3gg]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-h9j8-vj8g-v3gg
[link_ghsa_rwv7_mh2c_ff2p]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-rwv7-mh2c-ff2p
[link_ghsa_2fw8_7jmw_r937]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-2fw8-7jmw-r937
[link_ghsa_x863_g495_4cjc]: https://github.com/modelcontextprotocol/csharp-sdk/security/advisories/GHSA-x863-g495-4cjc
[link_ghsa_w766_5x43_whvw]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-w766-5x43-whvw
[link_ghsa_f897_62hf_6gxq]: https://github.com/modelcontextprotocol/typescript-sdk/security/advisories/GHSA-f897-62hf-6gxq
[link_ghsa_3jqg_r5pp_rmp2]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-3jqg-r5pp-rmp2
[link_ghsa_4gxg_m5jx_9j57]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-4gxg-m5jx-9j57
[link_ghsa_53mr_w429_c597]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-53mr-w429-c597
[link_ghsa_66qx_2266_pmj6]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-66qx-2266-pmj6
[link_ghsa_7rgq_gccq_qphx]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-7rgq-gccq-qphx
[link_ghsa_hhwq_wxfx_cj7g]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-hhwq-wxfx-cj7g
[link_ghsa_mvf5_2qqv_rg3c]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-mvf5-2qqv-rg3c
[link_ghsa_v38p_wf49_hx2j]: https://github.com/modelcontextprotocol/servers/security/advisories/GHSA-v38p-wf49-hx2j
[link_ghsa_5p52_q7pq_9fq2]: https://github.com/modelcontextprotocol/rust-sdk/security/advisories/GHSA-5p52-q7pq-9fq2
[link_ghsa_2rq8_f55p_j2jp]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-2rq8-f55p-j2jp
[link_ghsa_4fc4_wcmh_4g86]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-4fc4-wcmh-4g86
[link_ghsa_6x67_4w4w_9f3w]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-6x67-4w4w-9f3w
[link_ghsa_8qgq_27v6_55w3]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-8qgq-27v6-55w3
[link_ghsa_f6mc_jg3x_vq53]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-f6mc-jg3x-vq53
[link_ghsa_m5pj_3536_3xcp]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-m5pj-3536-3xcp
[link_ghsa_vcc9_3xgm_p9v4]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-vcc9-3xgm-p9v4
[link_ghsa_wmjf_2m46_2352]: https://github.com/modelcontextprotocol/inspector/security/advisories/GHSA-wmjf-2m46-2352
[link_ghsa_2hm9_qff2_hrpj]: https://github.com/modelcontextprotocol/java-sdk/security/advisories/GHSA-2hm9-qff2-hrpj
[link_ghsa_4432_vg92_fqh6]: https://github.com/modelcontextprotocol/rust-sdk/security/advisories/GHSA-4432-vg92-fqh6
[link_ghsa_hp8w_r5wh_cw9q]: https://github.com/modelcontextprotocol/java-sdk/security/advisories/GHSA-hp8w-r5wh-cw9q
[link_ghsa_w83x_jw8h_w4rj]: https://github.com/modelcontextprotocol/java-sdk/security/advisories/GHSA-w83x-jw8h-w4rj
[link_ghsa_c9xm_49cp_xcr9]: https://github.com/modelcontextprotocol/rust-sdk/security/advisories/GHSA-c9xm-49cp-xcr9
[link_ghsa_5648_rgj9_v224]: https://github.com/zereight/gitlab-mcp/security/advisories/GHSA-5648-rgj9-v224
[link_ghsa_7fx6_5m9f_89wg]: https://github.com/modelcontextprotocol/modelcontextprotocol/security/advisories/GHSA-7fx6-5m9f-89wg
[link_ghsa_5q7x_232h_f834]: https://github.com/modelcontextprotocol/java-sdk/security/advisories/GHSA-5q7x-232h-f834
[link_ghsa_4m5j_jjfc_97gx]: https://github.com/modelcontextprotocol/ruby-sdk/security/advisories/GHSA-4m5j-jjfc-97gx
[link_ghsa_4gph_2hhr_5mwg]: https://github.com/theagentrouter/agent-router/security/advisories/GHSA-4gph-2hhr-5mwg
[link_ghsa_q382_vc8q_7jhj]: https://github.com/modelcontextprotocol/go-sdk/security/advisories/GHSA-q382-vc8q-7jhj
