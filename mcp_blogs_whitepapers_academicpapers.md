# Blogs, Whitepapers, and Research

## Contents

- [Blogs](#blogs)
- [Whitepapers](#whitepapers)
  - [Industry resource hubs](#industry-resource-hubs)
  - [Long-form papers and guides](#long-form-papers-and-guides)
- [Academic Papers](#academic-papers)
- [MCP-Specific Specifications and Guidance](#mcp-specific-specifications-and-guidance)
- [OAuth, Identity, and Authorization References](#oauth-identity-and-authorization-references)
- [AI Security and Governance Standards](#ai-security-and-governance-standards)

---

## Blogs

| Title — Author / Org | Summary |
| --- | --- |
| [Security Best Practices][link_modelcontextprotocol_io_docs_tutorials_security_security_best_practice] — Model Context Protocol | Official security guidance covering confused deputy, token passthrough, SSRF, session hijacking, local server compromise, and scope minimization. |
| [Protecting against indirect prompt injection attacks in MCP][link_developer_microsoft_com_blog_protecting_against_indirect_injection_att] — Microsoft | Explains indirect prompt injection and tool poisoning in MCP-style tool ecosystems, with defensive ideas for AI agents connected to external content and tools. |
| [Securing MCP: A Control Plane for Agent Tool Execution][link_developer_microsoft_com_blog_securing_mcp_a_control_plane_for_agent_to] — Microsoft | Frames MCP security as a control-plane problem for agent tool execution, useful for enterprise architects designing centralized policy and governance. |
| [MCP Security Notification: Tool Poisoning Attacks][link_invariantlabs_ai_blog_mcp_security_notification_tool_poisoning_attacks] — Invariant Labs | Early and influential writeup showing how malicious instructions can be embedded in MCP tool descriptions visible to models but not obvious to users. |
| [WhatsApp MCP Exploited: Exfiltrating your message history via MCP][link_invariantlabs_ai_blog_whatsapp_mcp_exploited] — Invariant Labs | Demonstrates how an untrusted MCP server can influence an agent that also has access to a trusted messaging server, leading to cross-tool data exfiltration. |
| [Introducing MCP-Scan: Protecting MCP with Invariant][link_invariantlabs_ai_blog_introducing_mcp_scan] — Invariant Labs | Introduces MCP-Scan for scanning MCP configurations and detecting tool poisoning, rug pulls, cross-origin escalation, and prompt injection issues. |
| [GitHub MCP Exploited: Accessing private repositories via MCP][link_invariantlabs_ai_blog_mcp_github_vulnerability] — Invariant Labs | Shows that even trusted tools can become dangerous when agents process untrusted content from platforms such as GitHub. |
| [Toxic Flow Analysis][link_invariantlabs_ai_blog_toxic_flow_analysis] — Invariant Labs | Explains a method for detecting dangerous tool-flow combinations where individually acceptable actions become unsafe when chained. |
| [Jumping the line: How MCP servers can attack you before you ever use them][link_blog_trailofbits_com_2025_04_21_jumping_the_line_how_mcp_servers_can_a] — Trail of Bits | Explains “line jumping” attacks where MCP server-provided descriptions enter the model context before explicit user action. |
| [How MCP servers can steal your conversation history][link_blog_trailofbits_com_2025_04_23_how_mcp_servers_can_steal_your_convers] — Trail of Bits | Demonstrates how trigger phrases in tool descriptions can cause exfiltration of sensitive conversation context. |
| [Insecure credential storage plagues MCP][link_blog_trailofbits_com_2025_04_30_insecure_credential_storage_plagues_mc] — Trail of Bits | Highlights risks from long-lived API keys and tokens stored locally in plaintext or weakly protected MCP environments. |
| [We built the security layer MCP always needed][link_blog_trailofbits_com_2025_07_28_we_built_the_security_layer_mcp_always] — Trail of Bits | Introduces mcp-context-protector, a wrapper aimed at exposing malicious server behavior and defending against context-layer attacks. |
| [Building Secure MCP Servers: A Developer’s Guide][link_snyk_io_articles_building_secure_mcp_servers] — Snyk | Developer-focused guide covering common implementation issues such as command injection, path traversal, SQL injection, dependency risk, and secure server design. |
| [Scan AI-Generated Code in Cursor with Snyk MCP][link_snyk_io_blog_scan_your_ai_generated_code_from_cursor_using_model_conte] — Snyk | Shows how MCP can connect coding assistants to security scanning workflows inside developer environments. |
| [Securing Low-Code Agentic AI with MCP Guardrails][link_snyk_io_blog_securing_low_code_agentic_ai_mcp_guardrails] — Snyk | Discusses security guardrails for low-code/no-code agentic AI workflows using MCP integrations. |
| [MCP and LLM Security Research Briefing][link_wiz_io_blog_mcp_security_research_briefing] — Wiz | Curates early MCP security research and frames MCP as an emerging agentic security attack surface. |
| [Model Context Protocol Security Explained][link_wiz_io_academy_ai_security_model_context_protocol_security] — Wiz Academy | Introductory security guide explaining MCP architecture, risks, and why connected AI systems change enterprise boundaries. |
| [MCP Night 2.0 Panel: The Future of AI Integration][link_workos_com_blog_mcp_night_2_0_panel_discussion_openai_anthropic] — WorkOS | Written recap of MCP Night 2.0 (2025-09-03): panel themes from Anthropic and OpenAI on MCP as an open standard, integration direction, developer experience, and security/governance concerns. |
| [Meetup Summary: MCP Panel Discussion][link_solutionstreet_com_blog_2025_09_02_meetup_summary_model_context_protoc] — Solution Street / NOVA SA Roundtable | Recap of a 2025-08-20 NOVA SA roundtable (blog 2025-09-02): MCP architecture, security/privacy/trust, developer productivity, gateway usage, and testing takeaways from the panel. |
| [Is that allowed? Authentication and authorization in Model Context Protocol][link_stackoverflow_blog_2026_01_21_is_that_allowed_authentication_and_autho] — Stack Overflow Blog | Clear explanation of how MCP authorization works with OAuth, protected resource metadata, and scope negotiation. |
| [MCP security: Implementing robust authentication and authorization][link_redhat_com_en_blog_mcp_security_implementing_robust_authentication_and] — Red Hat | Explains MCP authentication/authorization patterns and how newer MCP specs position servers as OAuth resource servers. |
| [Evolving OAuth Client Registration in the Model Context Protocol][link_blog_modelcontextprotocol_io_posts_client_registration] — Paul Carleton / Model Context Protocol | Official MCP blog post on OAuth dynamic client registration as it applies to MCP clients and authorization flows. |
| [MCP, OAuth 2.1, PKCE, and the Future of AI Authorization][link_aembit_io_blog_mcp_oauth_2_1_pkce_and_the_future_of_ai_authorization] — Aembit | Positions OAuth 2.1, PKCE, and emerging AI authorization patterns for MCP-style integrations—supporting material for AppSec and identity teams. |
| [Model Context Protocol: Security Risks & Mitigations][link_socprime_com_blog_mcp_security_risks_and_mitigations] — SOC Prime | Practical risk-and-mitigation overview covering prompt injection, tool poisoning, tool shadowing, confused deputy, overbroad tokens, and audit gaps. |
| [11 Emerging AI Security Risks with MCP][link_checkmarx_com_zero_post_11_emerging_ai_security_risks_with_mcp_model_c] — Checkmarx | Security risk list for MCP adoption, useful for mapping MCP to AppSec and supply-chain practices. |
| [Deep Dive MCP and A2A Attack Vectors for AI Agents][link_solo_io_blog_deep_dive_mcp_and_a2a_attack_vectors_for_ai_agents] — Solo.io | Discusses MCP and A2A attack vectors including naming attacks, rug pulls, and context poisoning. |
| [The Architectural Flaw at the Core of Anthropic’s MCP][link_ox_security_blog_the_mother_of_all_ai_supply_chains_critical_systemic_] — OX Security | Research disclosure arguing that MCP STDIO configuration patterns can enable arbitrary command execution across affected ecosystems. |
| [The Mother of All AI Supply Chains: Technical Deep Dive][link_ox_security_blog_the_mother_of_all_ai_supply_chains_technical_deep_div] — OX Security | Technical detail on MCP STDIO command execution and how framework integrations can inherit command-execution behavior. |
| [Command Injection via Anthropic’s MCP SDK][link_docs_litellm_ai_blog_mcp_stdio_command_injection_april_2026] — LiteLLM | Maintainer-side writeup on authenticated remote command execution in MCP server creation functionality, referencing OX’s advisory. |
| [A Practical Guide for Securely Using Third-Party MCP Servers][link_genai_owasp_org_resource_cheatsheet_a_practical_guide_for_securely_usi] — OWASP GenAI Security Project | Practical guide for evaluating and safely using third-party MCP servers. |
| [A Practical Guide for Secure MCP Server Development][link_genai_owasp_org_resource_a_practical_guide_for_secure_mcp_server_devel] — OWASP GenAI Security Project | Secure development guidance for MCP servers, covering architecture, auth, validation, session isolation, and hardened deployment. |
| [OWASP MCP Top 10][link_owasp_org_www_project_mcp_top_10] — OWASP | Community risk taxonomy for MCP-enabled systems. Useful for mapping written research into common risk categories. |

---

## Whitepapers

This subsection lists long-form industry research, enterprise guides, and structured security reports for CISOs, architects, platform teams, and governance—same two-column layout as blogs (linked title — org; summary).

### Industry resource hubs

| Title — Author / Org | Summary |
| --- | --- |
| [CSA MCP Security Resource Center][link_labs_cloudsecurityalliance_org_mcp] — Cloud Security Alliance | Open industry hub indexing MCP security resources (including server/client risk views and baseline work). Use alongside governance standards below; not a standalone “whitepaper.” |

#### Long-form papers and guides

| Title — Author / Org | Summary |
| --- | --- |
| [MCP Security Considerations and Mitigation Strategies for the Enterprise][link_fractal_ai_docs_whitepaper_fractal_partner_and_alliances_mcp_security_] — Fractal | Enterprise-oriented whitepaper covering MCP interaction model, OAuth/token theft, prompt injection, tool poisoning, RCE/command injection, data governance, supply chain, and layered mitigation. Key actions: MCP governance policy; hardened identity/access; validation; observability; human-in-the-loop for high-risk actions. |
| [Model Context Protocol Strategies on AWS][link_docs_aws_amazon_com_prescriptive_guidance_latest_mcp_strategies_welcom] — AWS Prescriptive Guidance | Enterprise strategy guide for MCP tool design, server hosting, and governance. Emphasizes workflow-scoped tools, permission filtering, token isolation, server lifecycle control, and traceable access (“who, what, when, which permissions”). |
| [Enterprise-Grade Security for the Model Context Protocol: Frameworks and Mitigation Strategies][link_arxiv_org_abs_2504_08623] — Vineeth Sai Narajala, Idan Habler | Research/industry paper translating MCP threat modeling into implementable enterprise controls. Treat MCP security as architecture (identity, access, monitoring, validation, governance), not only code review. |
| [Simplified and Secure MCP Gateways for Enterprise AI Integration][link_arxiv_org_abs_2504_19997] — Ivo Brett | Proposes an MCP Gateway architecture for secure self-hosted enterprise integration (authentication, intrusion detection, secure tunneling, threat mapping). Centralize MCP exposure through a gateway rather than many unmanaged trust boundaries. |
| [Model Context Protocol Security][link_github_com_cosai_oasis_ws4_secure_design_agentic_systems_blob_main_mod] — CoSAI / OASIS Secure Design for Agentic Systems | Security-focused analysis of MCP transport/protocol layers, threat modeling, supply chain, IAM, deployment, and operations. Use MCP-specific threat modeling and supply-chain review—not “just another API.” |
| [A Practical Guide for Securely Using Third-Party MCP Servers][link_genai_owasp_org_resource_cheatsheet_a_practical_guide_for_securely_usi] — OWASP GenAI Security Project | Practitioner guide for safely adopting external MCP servers: provenance review, least privilege, isolation, monitoring, and avoiding auto-approval for sensitive actions. |
| [A Practical Guide for Secure MCP Server Development][link_genai_owasp_org_resource_a_practical_guide_for_secure_mcp_server_devel] — OWASP GenAI Security Project | Secure-by-design guide for MCP server builders: safe defaults, permissions, schema validation, secure sessions, hardened deployment, audit logs. |
| [MCP Server Top 10 Security Risks][link_modelcontextprotocol_security_io_top10_server] — MCP Security Working Group (CSA-linked) | Top 10 risk list for server implementations—use for server-side review checklists and mapping scanner findings. |
| [MCP Client Top 10 Security Risks][link_modelcontextprotocol_security_io_top10_client] — MCP Security Working Group (CSA-linked) | Top 10 risk list for MCP clients, including malicious servers and trust-boundary issues—useful for IDE/host teams evaluating tool metadata and server identity handling. |

---

## Academic Papers

This subsection lists academic and preprint research relevant to MCP security. Each **summary** includes why the paper matters (venue, method, or audience) so you can scan without extra columns.

| Title — Authors — Venue / status | Summary |
| --- | --- |
| [Model Context Protocol: Landscape, Security Threats, and Future Research Directions][link_arxiv_org_abs_2503_23278] — Xinyi Hou, Yanjie Zhao, Shenao Wang, Haoyu Wang — arXiv / ACM listing | Survey and lifecycle-oriented overview of MCP architecture, adoption, and security/privacy risks across create/operate/update phases. Strong first read for MCP as an ecosystem, not only a tool API. |
| [MCP Safety Audit: LLMs with the Model Context Protocol Allow Major Security Exploits][link_arxiv_org_abs_2504_03767] — Brandon Radosevich, John Halloran — arXiv | Shows MCP workflows coerced into malicious execution, remote access, and credential theft; introduces MCPSafetyScanner (adversarial samples and reporting). Useful for red-team methodology, scanners, and lab design. |
| [Enterprise-Grade Security for the Model Context Protocol: Frameworks and Mitigation Strategies][link_arxiv_org_abs_2504_08623] — Vineeth Sai Narajala, Idan Habler — arXiv / conference listing | Threat modeling and enterprise control mapping from MCP architectural risks to implementable patterns. Fits governance, CISO narratives, and enterprise reference architecture. |
| [Simplified and Secure MCP Gateways for Enterprise AI Integration][link_arxiv_org_abs_2504_19997] — Ivo Brett — arXiv | MCP gateway reference architecture with threat mapping and implementation recommendations for self-hosted enterprise use. Anchors gateways and enterprise governance topics. |
| [Systematic Analysis of MCP Security][link_arxiv_org_html_2508_12538v1] — authors per preprint — arXiv HTML | Systematic analysis emphasizing tool poisoning and risks from concise protocol design. Maps protocol design choices to practical attacks. |
| [MCPTox: A Benchmark for Tool Poisoning Attack on Real-World MCP Servers][link_arxiv_org_abs_2508_14925] — Zhiqiang Wang et al. — arXiv / AAAI listing | Benchmark from live MCP servers and authentic tools; malicious cases across risk categories; reports widespread agent vulnerability. Empirical tool-poisoning evidence and defensive evaluation. |
| [MCIP: Protecting MCP Safety via Model Contextual Integrity Protocol][link_aclanthology_org_2025_emnlp_main_62] — Huihao Jing et al. — EMNLP 2025; HKUST / Huawei Technologies | Proposes MCIP: tracking tools and guard model; contextual-integrity framing, trajectory logging, taxonomy, benchmarks/experiments. Information-flow tracking, auditability, policy-aware MCP design. |
| [Securing the Model Context Protocol: Risks, Controls, and Governance][link_arxiv_org_abs_2511_20920] — Herman Errico, Jiquan Ngiam, Shanita Sojan — arXiv | Frames MCP’s move from static APIs to user-driven agents via risk, control, and governance lenses. Suited to board/CISO-level control discussions. |
| [Breaking the Protocol: Security Analysis of the Model Context Protocol Specification and Prompt Injection Vulnerabilities in Tool-Integrated LLM Agents][link_arxiv_org_abs_2601_17549] — Narek Maloyan, Dmitry Namiot — arXiv | Protocol analysis (capability attestation gaps, bidirectional sampling trust, multi-server trust propagation) with scenario evaluation. Protocol-level security, not only implementation bugs. |
| [Model Context Protocol Threat Modeling and Analyzing Vulnerabilities to Prompt Injection with Tool Poisoning][link_arxiv_org_abs_2603_22489] — Charoes Huang, Xin Huang, Ngoc Phu Tran, Amin Milani Fard — arXiv | STRIDE/DREAD across MCP components plus empirical tool-poisoning tests across major MCP clients. Client security, permission UX, host/client risk. |
| [MCP Security Bench: Benchmarking Attacks Against MCP-Based Agents][link_openreview_net_forum] — D. Zhang et al. — OpenReview / preprint | Large benchmark of MCP-based agent attacks across stages, scenarios, tasks, and tools. Supports red-team benchmarking and client/agent regression testing. |
| [Behavioral Detection Methods for Automated MCP Server Security Monitoring][link_digitalcommons_odu_edu_cgi_viewcontent_cgi] — C. Coleman — ODU undergraduate research repository | Explores behavioral detection for MCP server monitoring. SOC detection and anomaly-monitoring ideas. |

---

## MCP-Specific Specifications and Guidance

| Title — Author / Org | Summary |
| --- | --- |
| [Model Context Protocol Specification][link_modelcontextprotocol_io_specification_2025_11_25] — Model Context Protocol | Defines core MCP concepts (hosts, clients, servers, resources, prompts, tools, sampling, roots, elicitation, utilities) and trust/safety principles. **For this project:** trust boundaries, tool safety, consent, logging, roots/sampling/elicitation risks. |
| [MCP Security Best Practices][link_modelcontextprotocol_io_docs_tutorials_security_security_best_practice] — Model Context Protocol | Official guidance on confused deputy, token passthrough, SSRF, session hijacking, local server compromise, scope minimization. **For this project:** baseline attacks, mitigations, common mistakes, checklist items. |
| [MCP Authorization Specification][link_modelcontextprotocol_io_specification_draft_basic_authorization] — Model Context Protocol | OAuth-based authorization for HTTP transports: protected resource metadata, discovery, scopes, token handling. **For this project:** resource-server role, AS discovery, scope challenges, token storage. |
| [MCP Client / Server Top 10 Security Risks][link_modelcontextprotocol_security_io_top10] — MCP Security Working Group | Community Top 10 lists for server and client implementations. **For this project:** map to your risk taxonomy and review checklists. |
| [OWASP MCP Security Cheat Sheet][link_owasp_cheatsheetseries_mcp_security] — OWASP Cheat Sheet Series | Practical MCP hardening guidance covering least privilege, tool/schema integrity, sandboxing, human approval, authN/authZ, replay protection, multi-server isolation, supply chain, monitoring, consent, and prompt injection via tool return values. |
| [OWASP MCP Top 10][link_owasp_org_www_project_mcp_top_10] — OWASP | Community risk taxonomy for MCP-enabled systems. **For this project:** neutral naming layer across blogs, papers, labs, CVEs, and tools. |
| [OWASP MCP Tool Poisoning Attack Page][link_owasp_org_www_community_attacks_mcp_tool_poisoning] — OWASP | Tool poisoning as indirect prompt injection. **For this project:** attack taxonomy and lab references. |
| [OWASP Practical Guide for Securely Using Third-Party MCP Servers][link_genai_owasp_org_resource_cheatsheet_a_practical_guide_for_securely_usi] — OWASP GenAI Security Project | Third-party server adoption checklist. **For this project:** vetting, approval, monitoring, isolation, least privilege. |
| [OWASP Practical Guide for Secure MCP Server Development][link_genai_owasp_org_resource_a_practical_guide_for_secure_mcp_server_devel] — OWASP GenAI Security Project | Secure development for MCP server authors. **For this project:** architecture, auth, validation, session isolation, hardened deployment. |

### OAuth, Identity, and Authorization References

Read **[OAuth 2.1][link_datatracker_ietf_org_doc_draft_ietf_oauth_v2_1]** first (authorization-code flows and modern OAuth deployment). Then use the RFCs in order; each row merges **what the spec defines** with **why it matters for MCP HTTP authorization**.

| Title — Author / Org | Summary |
| --- | --- |
| [OAuth 2.1 (draft)][link_datatracker_ietf_org_doc_draft_ietf_oauth_v2_1] — IETF | Consolidates OAuth 2.0 errata; requires PKCE for public/native clients; tightens redirect URI and sender-constrained token guidance; deprecates implicit grant; aligns refresh-token and scope handling. **MCP:** normative baseline for MCP HTTP authorization before MCP-specific discovery and scopes. |
| [RFC 9728 — OAuth 2.0 Protected Resource Metadata][link_datatracker_ietf_org_doc_html_rfc9728] — IETF | Protected resource metadata (issuer, scopes, authorization_servers, jwks_uri, etc.). **MCP:** MCP servers as OAuth protected resources; clients discover AS and metadata URLs for an MCP endpoint. |
| [RFC 8414 — OAuth 2.0 Authorization Server Metadata][link_datatracker_ietf_org_doc_html_rfc8414] — IETF | Authorization server metadata (issuer, authorize/token/jwks/revocation endpoints) for automatic AS configuration. **MCP:** endpoint discovery after resource metadata points to an AS. |
| [RFC 7591 — OAuth 2.0 Dynamic Client Registration][link_datatracker_ietf_org_doc_html_rfc7591] — IETF | Dynamic client registration without static, out-of-band registration. **MCP:** runtime client registration—high risk for confused deputy and client-identity binding; needs policy and approval. |
| [RFC 9700 — OAuth 2.0 Security BCP][link_datatracker_ietf_org_doc_html_rfc9700] — IETF | Security BCP: tokens, PKCE, redirects, mix-up mitigation, metadata trust, sender-constrained tokens, operations. **MCP:** cross-check deployments for tokens, redirects, metadata trust alongside OAuth 2.1. |
| [RFC 8707 — Resource Indicators for OAuth 2.0][link_datatracker_ietf_org_doc_html_rfc8707] — IETF | `resource` parameter for audience binding and narrowing token scope to a resource URI. **MCP:** bind tokens to the MCP resource server; reduce cross-resource token replay. |
| [OpenID Connect Discovery 1.0][link_openid_net_specs_openid_connect_discovery_1_0_html] — OpenID Foundation | OpenID Provider metadata and discovery (issuer + `.well-known`); overlaps OAuth AS metadata when IdP and AS combine. **MCP:** optional path when OIDC discovery is available for AS metadata. |

### AI Security and Governance Standards

| Title — Author / Org | Summary |
| --- | --- |
| [NIST AI Risk Management Framework 1.0][link_nist_gov_itl_ai_risk_management_framework] — NIST | Governance, mapping, measuring, and managing AI risk at organizational level. Does not replace MCP-specific controls. |
| [NIST AI 600-1: Generative AI Profile][link_nist_gov_itl_ai_risk_management_framework] — NIST | Maps MCP-enabled agentic risks to GenAI risk-management actions (same landing page as AI RMF resources). |
| [ISO/IEC 42001:2023 Artificial Intelligence Management System][link_iso_org_standard_81230_html] — ISO/IEC | AI governance, accountability, risk management, and management-system controls for agentic AI. |
| [OWASP Top 10 for LLM Applications][link_genai_owasp_org_llm_top_10] — OWASP GenAI Security Project | MCP risks overlap with prompt injection, sensitive disclosure, supply chain issues, excessive agency, insecure output handling. |
| [OWASP Top 10 for Agentic Applications][link_genai_owasp_org_resource_owasp_top_10_for_agentic_applications_for_202] — OWASP GenAI Security Project | Agentic risk taxonomy for systems that plan, act, and use tools—companion to MCP-specific risk lists. |
| [CSA AI Controls Matrix][link_labs_cloudsecurityalliance_org_mcp] — Cloud Security Alliance | Control mapping for AI workloads; see also [Industry resource hubs](#industry-resource-hubs) for the broader CSA MCP index. |


[link_aclanthology_org_2025_emnlp_main_62]: https://aclanthology.org/2025.emnlp-main.62/
[link_aembit_io_blog_mcp_oauth_2_1_pkce_and_the_future_of_ai_authorization]: https://aembit.io/blog/mcp-oauth-2-1-pkce-and-the-future-of-ai-authorization/
[link_arxiv_org_abs_2503_23278]: https://arxiv.org/abs/2503.23278
[link_arxiv_org_abs_2504_03767]: https://arxiv.org/abs/2504.03767
[link_arxiv_org_abs_2504_08623]: https://arxiv.org/abs/2504.08623
[link_arxiv_org_abs_2504_19997]: https://arxiv.org/abs/2504.19997
[link_arxiv_org_abs_2508_14925]: https://arxiv.org/abs/2508.14925
[link_arxiv_org_abs_2511_20920]: https://arxiv.org/abs/2511.20920
[link_arxiv_org_abs_2601_17549]: https://arxiv.org/abs/2601.17549
[link_arxiv_org_abs_2603_22489]: https://arxiv.org/abs/2603.22489
[link_arxiv_org_html_2508_12538v1]: https://arxiv.org/html/2508.12538v1
[link_blog_modelcontextprotocol_io_posts_client_registration]: https://blog.modelcontextprotocol.io/posts/client_registration/
[link_blog_trailofbits_com_2025_04_21_jumping_the_line_how_mcp_servers_can_a]: https://blog.trailofbits.com/2025/04/21/jumping-the-line-how-mcp-servers-can-attack-you-before-you-ever-use-them/
[link_blog_trailofbits_com_2025_04_23_how_mcp_servers_can_steal_your_convers]: https://blog.trailofbits.com/2025/04/23/how-mcp-servers-can-steal-your-conversation-history/
[link_blog_trailofbits_com_2025_04_30_insecure_credential_storage_plagues_mc]: https://blog.trailofbits.com/2025/04/30/insecure-credential-storage-plagues-mcp/
[link_blog_trailofbits_com_2025_07_28_we_built_the_security_layer_mcp_always]: https://blog.trailofbits.com/2025/07/28/we-built-the-security-layer-mcp-always-needed/
[link_checkmarx_com_zero_post_11_emerging_ai_security_risks_with_mcp_model_c]: https://checkmarx.com/zero-post/11-emerging-ai-security-risks-with-mcp-model-context-protocol/
[link_datatracker_ietf_org_doc_draft_ietf_oauth_v2_1]: https://datatracker.ietf.org/doc/draft-ietf-oauth-v2-1/
[link_datatracker_ietf_org_doc_html_rfc7591]: https://datatracker.ietf.org/doc/html/rfc7591
[link_datatracker_ietf_org_doc_html_rfc8414]: https://datatracker.ietf.org/doc/html/rfc8414
[link_datatracker_ietf_org_doc_html_rfc8707]: https://datatracker.ietf.org/doc/html/rfc8707
[link_datatracker_ietf_org_doc_html_rfc9700]: https://datatracker.ietf.org/doc/html/rfc9700
[link_datatracker_ietf_org_doc_html_rfc9728]: https://datatracker.ietf.org/doc/html/rfc9728
[link_developer_microsoft_com_blog_protecting_against_indirect_injection_att]: https://developer.microsoft.com/blog/protecting-against-indirect-injection-attacks-mcp
[link_developer_microsoft_com_blog_securing_mcp_a_control_plane_for_agent_to]: https://developer.microsoft.com/blog/securing-mcp-a-control-plane-for-agent-tool-execution
[link_digitalcommons_odu_edu_cgi_viewcontent_cgi]: https://digitalcommons.odu.edu/cgi/viewcontent.cgi?article=1138&context=covacci-undergraduateresearch
[link_docs_aws_amazon_com_prescriptive_guidance_latest_mcp_strategies_welcom]: https://docs.aws.amazon.com/prescriptive-guidance/latest/mcp-strategies/welcome.html
[link_docs_litellm_ai_blog_mcp_stdio_command_injection_april_2026]: https://docs.litellm.ai/blog/mcp-stdio-command-injection-april-2026
[link_fractal_ai_docs_whitepaper_fractal_partner_and_alliances_mcp_security_]: https://fractal.ai/docs/Whitepaper/Fractal-Partner-And-Alliances-MCP-Security-Considerations-And-Mitigation-Strategies-For-The-Enterprise.pdf
[link_genai_owasp_org_llm_top_10]: https://genai.owasp.org/llm-top-10/
[link_genai_owasp_org_resource_a_practical_guide_for_secure_mcp_server_devel]: https://genai.owasp.org/resource/a-practical-guide-for-secure-mcp-server-development/
[link_genai_owasp_org_resource_cheatsheet_a_practical_guide_for_securely_usi]: https://genai.owasp.org/resource/cheatsheet-a-practical-guide-for-securely-using-third-party-mcp-servers-1-0/
[link_genai_owasp_org_resource_owasp_top_10_for_agentic_applications_for_202]: https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/
[link_github_com_cosai_oasis_ws4_secure_design_agentic_systems_blob_main_mod]: https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/blob/main/model-context-protocol-security.md
[link_invariantlabs_ai_blog_introducing_mcp_scan]: https://invariantlabs.ai/blog/introducing-mcp-scan
[link_invariantlabs_ai_blog_mcp_github_vulnerability]: https://invariantlabs.ai/blog/mcp-github-vulnerability
[link_invariantlabs_ai_blog_mcp_security_notification_tool_poisoning_attacks]: https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks
[link_invariantlabs_ai_blog_toxic_flow_analysis]: https://invariantlabs.ai/blog/toxic-flow-analysis
[link_invariantlabs_ai_blog_whatsapp_mcp_exploited]: https://invariantlabs.ai/blog/whatsapp-mcp-exploited
[link_iso_org_standard_81230_html]: https://www.iso.org/standard/81230.html
[link_labs_cloudsecurityalliance_org_mcp]: https://labs.cloudsecurityalliance.org/mcp/
[link_modelcontextprotocol_io_docs_tutorials_security_security_best_practice]: https://modelcontextprotocol.io/docs/tutorials/security/security_best_practices
[link_modelcontextprotocol_io_specification_2025_11_25]: https://modelcontextprotocol.io/specification/2025-11-25
[link_modelcontextprotocol_io_specification_draft_basic_authorization]: https://modelcontextprotocol.io/specification/draft/basic/authorization
[link_modelcontextprotocol_security_io_top10]: https://modelcontextprotocol-security.io/top10/
[link_modelcontextprotocol_security_io_top10_client]: https://modelcontextprotocol-security.io/top10/client/
[link_modelcontextprotocol_security_io_top10_server]: https://modelcontextprotocol-security.io/top10/server/
[link_nist_gov_itl_ai_risk_management_framework]: https://www.nist.gov/itl/ai-risk-management-framework
[link_openid_net_specs_openid_connect_discovery_1_0_html]: https://openid.net/specs/openid-connect-discovery-1_0.html
[link_openreview_net_forum]: https://openreview.net/forum?id=irxxkFMrry
[link_owasp_cheatsheetseries_mcp_security]: https://cheatsheetseries.owasp.org/cheatsheets/MCP_Security_Cheat_Sheet.html
[link_owasp_org_www_community_attacks_mcp_tool_poisoning]: https://owasp.org/www-community/attacks/MCP_Tool_Poisoning
[link_owasp_org_www_project_mcp_top_10]: https://owasp.org/www-project-mcp-top-10/
[link_ox_security_blog_the_mother_of_all_ai_supply_chains_critical_systemic_]: https://www.ox.security/blog/the-mother-of-all-ai-supply-chains-critical-systemic-vulnerability-at-the-core-of-the-mcp/
[link_ox_security_blog_the_mother_of_all_ai_supply_chains_technical_deep_div]: https://www.ox.security/blog/the-mother-of-all-ai-supply-chains-technical-deep-dive/
[link_redhat_com_en_blog_mcp_security_implementing_robust_authentication_and]: https://www.redhat.com/en/blog/mcp-security-implementing-robust-authentication-and-authorization
[link_snyk_io_articles_building_secure_mcp_servers]: https://snyk.io/articles/building-secure-mcp-servers/
[link_snyk_io_blog_scan_your_ai_generated_code_from_cursor_using_model_conte]: https://snyk.io/blog/scan-your-ai-generated-code-from-cursor-using-model-context-protocol-mcp/
[link_snyk_io_blog_securing_low_code_agentic_ai_mcp_guardrails]: https://snyk.io/blog/securing-low-code-agentic-ai-mcp-guardrails/
[link_socprime_com_blog_mcp_security_risks_and_mitigations]: https://socprime.com/blog/mcp-security-risks-and-mitigations/
[link_solo_io_blog_deep_dive_mcp_and_a2a_attack_vectors_for_ai_agents]: https://www.solo.io/blog/deep-dive-mcp-and-a2a-attack-vectors-for-ai-agents
[link_solutionstreet_com_blog_2025_09_02_meetup_summary_model_context_protoc]: https://www.solutionstreet.com/blog/2025/09/02/meetup-summary-model-context-protocol-mcp-panel-discussion/
[link_stackoverflow_blog_2026_01_21_is_that_allowed_authentication_and_autho]: https://stackoverflow.blog/2026/01/21/is-that-allowed-authentication-and-authorization-in-model-context-protocol/
[link_wiz_io_academy_ai_security_model_context_protocol_security]: https://www.wiz.io/academy/ai-security/model-context-protocol-security
[link_wiz_io_blog_mcp_security_research_briefing]: https://www.wiz.io/blog/mcp-security-research-briefing
[link_workos_com_blog_mcp_night_2_0_panel_discussion_openai_anthropic]: https://workos.com/blog/mcp-night-2-0-panel-discussion-openai-anthropic
