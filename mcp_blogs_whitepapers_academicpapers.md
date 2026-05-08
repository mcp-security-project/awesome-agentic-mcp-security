# Blogs, Whitepapers, and Research

## Contents

- [Blogs](#blogs)
  - [Dated incidents, investigations, and community mirrors](#dated-incidents-investigations-and-community-mirrors)
- [Whitepapers](#whitepapers)
  - [Industry resource hubs](#industry-resource-hubs)
  - [Long-form papers and guides](#long-form-papers-and-guides)
- [Academic Papers](#academic-papers)
- [MCP-Specific Specifications and Guidance](#mcp-specific-specifications-and-guidance)
- [OAuth, Identity, and Authorization References](#oauth-identity-and-authorization-references)
- [AI Security and Governance Standards](#ai-security-and-governance-standards)

---

## Blogs

| Title - Author / Org | Summary |
| --- | --- |
| [Security Best Practices][link_modelcontextprotocol_io_docs_tutorials_security_security_best_practice] - Model Context Protocol | Official security guidance covering confused deputy, token passthrough, SSRF, session hijacking, local server compromise, and scope minimization. |
| [Protecting against indirect prompt injection attacks in MCP][link_developer_microsoft_com_blog_protecting_against_indirect_injection_att] - Microsoft | Explains indirect prompt injection and tool poisoning in MCP-style tool ecosystems, with defensive ideas for AI agents connected to external content and tools. |
| [Securing MCP: A Control Plane for Agent Tool Execution][link_developer_microsoft_com_blog_securing_mcp_a_control_plane_for_agent_to] - Microsoft | Frames MCP security as a control-plane problem for agent tool execution, useful for enterprise architects designing centralized policy and governance. |
| [MCP Security Notification: Tool Poisoning Attacks][link_invariantlabs_ai_blog_mcp_security_notification_tool_poisoning_attacks] - Invariant Labs | Early and influential writeup showing how malicious instructions can be embedded in MCP tool descriptions visible to models but not obvious to users. |
| [WhatsApp MCP Exploited: Exfiltrating your message history via MCP][link_invariantlabs_ai_blog_whatsapp_mcp_exploited] - Invariant Labs | Demonstrates how an untrusted MCP server can influence an agent that also has access to a trusted messaging server, leading to cross-tool data exfiltration. |
| [Introducing MCP-Scan: Protecting MCP with Invariant][link_invariantlabs_ai_blog_introducing_mcp_scan] - Invariant Labs | Introduces MCP-Scan for scanning MCP configurations and detecting tool poisoning, rug pulls, cross-origin escalation, and prompt injection issues. |
| [GitHub MCP Exploited: Accessing private repositories via MCP][link_invariantlabs_ai_blog_mcp_github_vulnerability] - Invariant Labs | Shows that even trusted tools can become dangerous when agents process untrusted content from platforms such as GitHub. |
| [Toxic Flow Analysis][link_invariantlabs_ai_blog_toxic_flow_analysis] - Invariant Labs | Explains a method for detecting dangerous tool-flow combinations where individually acceptable actions become unsafe when chained. |
| [Jumping the line: How MCP servers can attack you before you ever use them][link_blog_trailofbits_com_2025_04_21_jumping_the_line_how_mcp_servers_can_a] - Trail of Bits | Explains “line jumping” attacks where MCP server-provided descriptions enter the model context before explicit user action. |
| [How MCP servers can steal your conversation history][link_blog_trailofbits_com_2025_04_23_how_mcp_servers_can_steal_your_convers] - Trail of Bits | Demonstrates how trigger phrases in tool descriptions can cause exfiltration of sensitive conversation context. |
| [Insecure credential storage plagues MCP][link_blog_trailofbits_com_2025_04_30_insecure_credential_storage_plagues_mc] - Trail of Bits | Highlights risks from long-lived API keys and tokens stored locally in plaintext or weakly protected MCP environments. |
| [We built the security layer MCP always needed][link_blog_trailofbits_com_2025_07_28_we_built_the_security_layer_mcp_always] - Trail of Bits | Introduces mcp-context-protector, a wrapper aimed at exposing malicious server behavior and defending against context-layer attacks. |
| [Building Secure MCP Servers: A Developer’s Guide][link_snyk_io_articles_building_secure_mcp_servers] - Snyk | Developer-focused guide covering common implementation issues such as command injection, path traversal, SQL injection, dependency risk, and secure server design. |
| [Scan AI-Generated Code in Cursor with Snyk MCP][link_snyk_io_blog_scan_your_ai_generated_code_from_cursor_using_model_conte] - Snyk | Shows how MCP can connect coding assistants to security scanning workflows inside developer environments. |
| [Securing Low-Code Agentic AI with MCP Guardrails][link_snyk_io_blog_securing_low_code_agentic_ai_mcp_guardrails] - Snyk | Discusses security guardrails for low-code/no-code agentic AI workflows using MCP integrations. |
| [MCP and LLM Security Research Briefing][link_wiz_io_blog_mcp_security_research_briefing] - Wiz | Curates early MCP security research and frames MCP as an emerging agentic security attack surface. |
| [Model Context Protocol Security Explained][link_wiz_io_academy_ai_security_model_context_protocol_security] - Wiz Academy | Introductory security guide explaining MCP architecture, risks, and why connected AI systems change enterprise boundaries. |
| [MCP Night 2.0 Panel: The Future of AI Integration][link_workos_com_blog_mcp_night_2_0_panel_discussion_openai_anthropic] - WorkOS | Written recap of MCP Night 2.0 (2025-09-03): panel themes from Anthropic and OpenAI on MCP as an open standard, integration direction, developer experience, and security/governance concerns. |
| [Meetup Summary: MCP Panel Discussion][link_solutionstreet_com_blog_2025_09_02_meetup_summary_model_context_protoc] - Solution Street / NOVA SA Roundtable | Recap of a 2025-08-20 NOVA SA roundtable (blog 2025-09-02): MCP architecture, security/privacy/trust, developer productivity, gateway usage, and testing takeaways from the panel. |
| [Is that allowed? Authentication and authorization in Model Context Protocol][link_stackoverflow_blog_2026_01_21_is_that_allowed_authentication_and_autho] - Stack Overflow Blog | Clear explanation of how MCP authorization works with OAuth, protected resource metadata, and scope negotiation. |
| [MCP security: Implementing robust authentication and authorization][link_redhat_com_en_blog_mcp_security_implementing_robust_authentication_and] - Red Hat | Explains MCP authentication/authorization patterns and how newer MCP specs position servers as OAuth resource servers. |
| [Evolving OAuth Client Registration in the Model Context Protocol][link_blog_modelcontextprotocol_io_posts_client_registration] - Paul Carleton / Model Context Protocol | Official MCP blog post on OAuth dynamic client registration as it applies to MCP clients and authorization flows. |
| [MCP, OAuth 2.1, PKCE, and the Future of AI Authorization][link_aembit_io_blog_mcp_oauth_2_1_pkce_and_the_future_of_ai_authorization] - Aembit | Positions OAuth 2.1, PKCE, and emerging AI authorization patterns for MCP-style integrations-supporting material for AppSec and identity teams. |
| [Model Context Protocol: Security Risks & Mitigations][link_socprime_com_blog_mcp_security_risks_and_mitigations] - SOC Prime | Practical risk-and-mitigation overview covering prompt injection, tool poisoning, tool shadowing, confused deputy, overbroad tokens, and audit gaps. |
| [11 Emerging AI Security Risks with MCP][link_checkmarx_com_zero_post_11_emerging_ai_security_risks_with_mcp_model_c] - Checkmarx | Security risk list for MCP adoption, useful for mapping MCP to AppSec and supply-chain practices. |
| [Deep Dive MCP and A2A Attack Vectors for AI Agents][link_solo_io_blog_deep_dive_mcp_and_a2a_attack_vectors_for_ai_agents] - Solo.io | Discusses MCP and A2A attack vectors including naming attacks, rug pulls, and context poisoning. |
| [The Architectural Flaw at the Core of Anthropic’s MCP][link_ox_security_blog_the_mother_of_all_ai_supply_chains_critical_systemic_] - OX Security | Research disclosure arguing that MCP STDIO configuration patterns can enable arbitrary command execution across affected ecosystems. |
| [The Mother of All AI Supply Chains: Technical Deep Dive][link_ox_security_blog_the_mother_of_all_ai_supply_chains_technical_deep_div] - OX Security | Technical detail on MCP STDIO command execution and how framework integrations can inherit command-execution behavior. |
| [Command Injection via Anthropic’s MCP SDK][link_docs_litellm_ai_blog_mcp_stdio_command_injection_april_2026] - LiteLLM | Maintainer-side writeup on authenticated remote command execution in MCP server creation functionality, referencing OX’s advisory. |
| [A Practical Guide for Securely Using Third-Party MCP Servers][link_genai_owasp_org_resource_cheatsheet_a_practical_guide_for_securely_usi] - OWASP GenAI Security Project | Practical guide for evaluating and safely using third-party MCP servers. |
| [A Practical Guide for Secure MCP Server Development][link_genai_owasp_org_resource_a_practical_guide_for_secure_mcp_server_devel] - OWASP GenAI Security Project | Secure development guidance for MCP servers, covering architecture, auth, validation, session isolation, and hardened deployment. |
| [OWASP MCP Top 10][link_owasp_org_www_project_mcp_top_10] - OWASP | Community risk taxonomy for MCP-enabled systems. Useful for mapping written research into common risk categories. |

### Dated incidents, investigations, and community mirrors

This subsection is a **chronological-style mirror** of high-signal posts, vendor investigations, and long threads that often circulate together (mcpmanager.ai explainers, Jira + Cursor “0-click” style findings, `mcp-remote` RCE, Cato CTRL PoCs, Asana cross-tenant exposure, CyberArk schema-poisoning research, Windows containment, PromptHub/Equixly statistics, ANSI deception, Cisco community guidance, Pillar Cursor weaponization, Cursor forum YOLO bypass threads, The New Stack “reality check” essays, and related practitioner writeups). Dates are **publication or incident months** when known; use primary sources for legal or incident timelines.

| Date (known / approx.) | Title - Author / Org | Summary |
| --- | --- | --- |
| 2025–2026 | [MCP Security Risks: Common Vulnerabilities and Threats][link_mcpmanager_ai_blog_mcp_security_risks] - MCP Manager (mcpmanager.ai) | Dated series on rug pulls, prompt injection, tool poisoning, token theft, and gateway-oriented mitigations-often the first third-party “explainer hub” people cite alongside vendor posts. |
| 2025–2026 | [MCP Security Best Practices][link_mcpmanager_ai_blog_mcp_security_best_practices] - MCP Manager | Companion piece on policy, OAuth2/identity, logging, and controlling shadow MCP installs. |
| 2025–2026 | [MCP Supply Chain Security & Risks][link_mcpmanager_ai_blog_mcp_supply_chain_security] - MCP Manager | Supply-chain framing (registry risk, vendor-only trust failures) aligned with Asana-class incidents and marketplace sprawl. |
| 2025-08 | [What is the “Cursor + Jira MCP 0-Click” vulnerability?][link_labs_snyk_io_cursor_jira_mcp_vulnerability_explained] - Snyk Labs | Neutral explainer of the **Zenity / “AgentFlayer”** class issue: malicious Jira content + privileged local tools + outbound sink. |
| 2025-08 | [AgentFlayer: When a Jira Ticket Can Steal Your Secrets][link_labs_zenity_io_agentflayer_jira_ticket] - Zenity Labs | Original research narrative and obfuscation details (e.g. “apples” / JWT-shaped secrets) for the Jira + MCP + agent workflow. |
| 2025-08 | [When a Jira ticket can steal your secrets][link_simonwillison_net_2025_aug_9_when_a_jira_ticket_can_steal_your_secrets] - Simon Willison | Accessible recap linking MCP, agent autonomy, and why document-born instructions are not “just phishing.” |
| 2025-08 | [The Cursor Agentic Jira MCP Attack Explained with Toxic Flow Analysis][link_lirantal_com_blog_cursor_jira_mcp_toxic_flow] - Liran Tal | Maps the attack to **toxic multi-tool flows**-useful vocabulary for defenders writing runbooks. |
| 2025-08 | [Cursor + Jira MCP 0-Click Credential Exfiltration][link_vulnerablemcp_info_cursor_jira_mcp_zero_click] - The Vulnerable MCP Project | Community catalog entry summarizing impact and preconditions for the same incident class. |
| 2025-06 | [Asana warns MCP AI feature exposed customer data to other orgs][link_bleepingcomputer_asana_mcp_exposed] - BleepingComputer | News writeup of Asana’s cross-tenant MCP exposure disclosure (incident timing per Asana status communications). |
| 2025-06 | [Asana’s MCP AI connector could have exposed corporate data, CSOs warned][link_csoonline_asana_mcp_connector] - CSO Online | Executive-oriented analysis of the Asana MCP data-boundary failure and governance lessons. |
| 2025-05~ | [Exploiting Model Context Protocol (MCP)][link_catonetworks_blog_exploiting_mcp] - Cato Networks (CTRL threat research) | Proof-of-concept style discussion of MCP-hosted gadgetry and document-driven misuse-good for purple-team tabletop material. |
| 2025-05~ | [PoC Attack Targeting Atlassian’s MCP][link_catonetworks_blog_poc_atlassian_mcp] - Cato Networks | **“Living off AI”** style scenario: malicious Jira/JSM tickets processed by internal agents via MCP integrations. |
| 2025 | [‘CurXecute’ - RCE in Cursor via MCP Auto-Start][link_catonetworks_blog_curxecute_rce] - Cato Networks | Cursor-focused RCE discussion via MCP auto-start patterns-pair with IDE vendor advisories and Cursor release notes. |
| 2025 | [MCP-Remote Control: From OAuth Discovery to RCE (CVE-2025-6514)][link_research_jfrog_mcp_remote_command_injection] - JFrog Security Research | Deep technical root-cause analysis of **OAuth discovery URL → OS command injection** in `mcp-remote`. |
| 2025 | [Critical RCE vulnerability hijacking mcp-remote clients][link_jfrog_press_mcp_remote_rce] - JFrog (press) | Executive summary of blast radius (Claude Desktop, Cursor, Windsurf) and remediation urgency. |
| 2025 | [RCE in mcp-remote (CVE-2025-6514)][link_blog_ogwilliam_mcp_remote_rce] - William OGOU | Independent walkthrough of exploit mechanics and client-side shell invocation-good for defenders reproducing safely in labs. |
| 2025 | [Securing Model Context Protocol (MCP) with Teleport and AWS][link_goteleport_blog_securing_mcp_with_aws] - Teleport | Identity-aware / cert-based access patterns for MCP in cloud estates. |
| 2025 | [Secure AI Agent Infrastructure with Zero-Code MCP][link_goteleport_blog_secure_ai_agents_zero_code_mcp] - Teleport | Positions MCP as an agent **data plane** problem and discusses containment without rewriting every server. |
| 2025 | [The Complicating Factors of Deploying MCP in the Enterprise][link_goteleport_blog_complicating_mcp_enterprise] - Teleport | OAuth-for-humans vs agents, observability gaps, and enterprise rollout friction. |
| 2025 | [Poison everywhere: No output from your MCP server is safe][link_cyberark_poison_everywhere] - CyberArk Labs | Extends tool-poisoning discussion to **full-schema** and **tool-output** manipulation (“no output is safe”). |
| 2025 | [Is your AI safe? Threat analysis of MCP][link_cyberark_threat_analysis_mcp] - CyberArk Labs | Earlier CyberArk threat-analysis primer on MCP abuse classes and monitoring gaps. |
| 2025 | [Securing the Model Context Protocol: Building a safer agentic future on Windows][link_blogs_windows_securing_mcp] - Windows Experience Blog | Microsoft’s Windows-centric MCP threat overview (XPIA, tool poisoning, containment needs) feeding into Agent Workspace / containment storylines. |
| 2025 | [Securely containing MCP servers on Windows][link_learn_microsoft_mcp_containment] - Microsoft Learn | Official documentation for **MCP containment** patterns on Windows-pair with the narrative Windows blog above. |
| 2025-04-29 | [Deceiving users with ANSI terminal codes in MCP][link_trailofbits_ansi_deception_mcp] - Trail of Bits | Documents **ANSI hide-in-plain-sight** attacks in tool descriptions/outputs where terminals hide text the model still consumes. |
| 2025-04-27 | [Model Context Protocol (MCP) Security - Real Risks for LLM Apps (2025)][link_pulik_dev_blog_mcp_security] - Maciej Pulikowski (Puliczek) | Long-form examples (secrets exfiltration, command injection stats citing Equixly) that complement-not duplicate-shorter “MCP is broken” video essays. |
| 2025 | [MCP Security in 2025][link_prompthub_us_mcp_security_in_2025] - PromptHub | Practitioner roundup (Equixly stats, disguised tools, rug pulls, cross-server shadowing) aimed at teams rolling out MCP to non-research users. |
| 2025 | [5 MCP security vulnerabilities you should know][link_prompthub_substack_5_mcp_vulns] - PromptHub (Substack) | Shorter listicle form of overlapping themes (good for onboarding reading lists). |
| 2025-03-29 | [MCP Servers: The New Security Nightmare][link_equixly_blog_mcp_security_nightmare] - Equixly | Widely cited **empirical vulnerability rates** in popular MCP servers (command injection, SSRF, path traversal) and vendor response behaviors. |
| 2026-02-26 | [Offensive security for MCP servers][link_equixly_blog_offensive_security_mcp] - Equixly | Follow-on on continuous offensive testing for MCP servers “in the wild.” |
| 2026-02-12 | [How MCP servers challenge traditional API security models][link_equixly_blog_mcp_api_security_models] - Equixly | Explains why classic API gateway assumptions break once LLMs orchestrate tools. |
| 2025 | [Model Context Protocol (MCP) and Security][link_cisco_community_mcp_and_security] - Cisco Community (Security Blogs) | Vendor-community explainer on MCP trust boundaries, monitoring, and Zero Trust alignment-often surfaced next to Cisco’s open MCP scanner efforts. |
| 2025 | [New Vulnerability in GitHub Copilot and Cursor: How Hackers Can Weaponize Code Agents][link_pillar_weaponize_code_agents] - Pillar Security | **Rules-file / unicode obfuscation** path for weaponizing Copilot + Cursor agent workflows-sibling theme to MCP poisoning in IDEs. |
| 2025 | [The Agent Security Paradox: When Trusted Commands in Cursor Become Attack Vectors][link_pillar_agent_security_paradox] - Pillar Security | Cursor **shell built-in / sandbox bypass** research narrative (CVE-2026-22708) showing how “trusted” primitives become RCE under agents. |
| 2025 | [Cursor IDE's MCP Vulnerability][link_checkpoint_cursor_mcpoison] - Check Point Research | **MCPoison** / MCP-related Cursor vulnerability writeup-useful third-party technical perspective alongside Cursor advisories. |
| 2025 | [Modification of MCP Server Definitions Bypasses Manual Re-approval][link_github_cursor_ghsa_mcp_reapproval] - GitHub Advisory Database (Cursor) | Advisory text for **MCP server definition tampering** / re-approval bypass class issues-link stays stable for auditors. |
| 2025–2026 | [YOLO mode bypasses command allowlist using `&&`][link_cursor_forum_yolo_bypass_allowlist] - Cursor Community Forum | Long-running **support/bug** thread on chained commands bypassing YOLO allowlists-relevant when MCP tool invocations ride shell wrappers. |
| 2025–2026 | [Chained commands (`&&`) bypass yolo mode “denylist”][link_cursor_forum_chained_commands_yolo] - Cursor Community Forum | Related forum thread cataloging bypass patterns and user mitigations. |
| 2025 | [MCP Needs a Security Reality Check][link_thenewstack_mcp_security_reality_check] - The New Stack | Essay-length critique of MCP security posture vs hype-frequently bookmarked as “read this before production.” |
| 2025–2026 | [Beyond the vibe code: The steep mountain MCP must climb to reach production][link_thenewstack_mcp_evolution] - The New Stack | Follow-on on reliability, governance, and security maturity gaps in MCP land. |
| 2025-09 | [Lessons from the MCP Breach: Shadow AI & Discovery][link_oasis_lessons_mcp_breach_shadow_ai] - Oasis Security | Post-incident style narrative (postmark-mcp npm incident, Sep 2025) on **shadow MCP** discovery after ecosystem abuse-useful for GRC “why inventory matters” storylines. |
| 2025 | [Introducing MCP-38: A Comprehensive Threat Taxonomy for Model Context Protocol Systems][link_vulcan_mcp_38_taxonomy] - Vulcan Cyber | Structured **38-threat** taxonomy for MCP systems-good cross-walk to OWASP MCP Top 10 and internal risk registers. |
| 2025 | [MCP Server Security: Threat Model and Controls for the Agent Tool Supply Chain][link_generalanalysis_mcp_server_security] - General Analysis | Long-form guide-style threat model + controls for MCP as an **agent tool supply chain** problem. |
| n/a (repo) | [llm_threat_hunt (MCP server for Elasticsearch / SecOps)][link_github_tierzerosecurity_llm_threat_hunt] - TierZeroSecurity | Open MCP server wiring LLMs to **Windows/Sysmon-style log hunts**-frequently grouped with “MCP for threat hunting” threads even though it is code-first rather than a blog post. |
| 2025-10-02 | [Secure from Day One: Building Production Ready MCP Servers][link_nickyt_mcp_dev_summit_eu_2025] - Nick Taylor (Pomerium) | Talk page for MCP Developers Summit EU session (OAuth 2.1 + Pomerium patterns)-canonical when curators mean “Nick Taylor / Pomerium MCP” but do not link YouTube. |
| 2024–2025 | [Securing MCP Servers with Zero Trust][link_nickyt_securing_mcp_zero_trust_apollo] - Nick Taylor (Pomerium) | Apollo MCP Server Builder series talk page on zero trust for MCP servers. |
| 2025 | [Agentic Access: OAuth Gets You In, Zero Trust Keeps You Safe (All Things Open)][link_nickyt_agentic_access_ato_2025] - Nick Taylor (Pomerium) | Conference-specific instance of the OAuth + zero trust narrative for MCP/agent clients. |

---

## Whitepapers

This subsection lists long-form industry research, enterprise guides, and structured security reports for CISOs, architects, platform teams, and governance—same two-column layout as blogs (linked title — org; summary).

### Industry resource hubs

| Title - Author / Org | Summary |
| --- | --- |
| [CSA MCP Security Resource Center][link_labs_cloudsecurityalliance_org_mcp] - Cloud Security Alliance | Open industry hub indexing MCP security resources (including server/client risk views and baseline work). Use alongside governance standards below; not a standalone “whitepaper.” |

#### Long-form papers and guides

| Title — Author / Org | Summary |
| --- | --- |
| [MCP Security Considerations and Mitigation Strategies for the Enterprise][link_fractal_ai_docs_whitepaper_fractal_partner_and_alliances_mcp_security_] - Fractal | Enterprise-oriented whitepaper covering MCP interaction model, OAuth/token theft, prompt injection, tool poisoning, RCE/command injection, data governance, supply chain, and layered mitigation. Key actions: MCP governance policy; hardened identity/access; validation; observability; human-in-the-loop for high-risk actions. |
| [Model Context Protocol Strategies on AWS][link_docs_aws_amazon_com_prescriptive_guidance_latest_mcp_strategies_welcom] - AWS Prescriptive Guidance | Enterprise strategy guide for MCP tool design, server hosting, and governance. Emphasizes workflow-scoped tools, permission filtering, token isolation, server lifecycle control, and traceable access (“who, what, when, which permissions”). |
| [Enterprise-Grade Security for the Model Context Protocol: Frameworks and Mitigation Strategies][link_arxiv_org_abs_2504_08623] - Vineeth Sai Narajala, Idan Habler | Research/industry paper translating MCP threat modeling into implementable enterprise controls. Treat MCP security as architecture (identity, access, monitoring, validation, governance), not only code review. |
| [Simplified and Secure MCP Gateways for Enterprise AI Integration][link_arxiv_org_abs_2504_19997] - Ivo Brett | Proposes an MCP Gateway architecture for secure self-hosted enterprise integration (authentication, intrusion detection, secure tunneling, threat mapping). Centralize MCP exposure through a gateway rather than many unmanaged trust boundaries. |
| [Model Context Protocol Security][link_github_com_cosai_oasis_ws4_secure_design_agentic_systems_blob_main_mod] - CoSAI / OASIS Secure Design for Agentic Systems | Security-focused analysis of MCP transport/protocol layers, threat modeling, supply chain, IAM, deployment, and operations. Use MCP-specific threat modeling and supply-chain review-not “just another API.” |
| [A Practical Guide for Securely Using Third-Party MCP Servers][link_genai_owasp_org_resource_cheatsheet_a_practical_guide_for_securely_usi] - OWASP GenAI Security Project | Practitioner guide for safely adopting external MCP servers: provenance review, least privilege, isolation, monitoring, and avoiding auto-approval for sensitive actions. |
| [A Practical Guide for Secure MCP Server Development][link_genai_owasp_org_resource_a_practical_guide_for_secure_mcp_server_devel] - OWASP GenAI Security Project | Secure-by-design guide for MCP server builders: safe defaults, permissions, schema validation, secure sessions, hardened deployment, audit logs. |
| [MCP Server Top 10 Security Risks][link_modelcontextprotocol_security_io_top10_server] - MCP Security Working Group (CSA-linked) | Top 10 risk list for server implementations-use for server-side review checklists and mapping scanner findings. |
| [MCP Client Top 10 Security Risks][link_modelcontextprotocol_security_io_top10_client] - MCP Security Working Group (CSA-linked) | Top 10 risk list for MCP clients, including malicious servers and trust-boundary issues-useful for IDE/host teams evaluating tool metadata and server identity handling. |

---

## Academic Papers

This subsection lists academic and preprint research relevant to MCP security. Each **summary** includes why the paper matters (venue, method, or audience) so you can scan without extra columns.

| Title - Authors - Venue / status | Summary |
| --- | --- |
| [Model Context Protocol: Landscape, Security Threats, and Future Research Directions][link_arxiv_org_abs_2503_23278] - Xinyi Hou, Yanjie Zhao, Shenao Wang, Haoyu Wang - arXiv / ACM listing | Survey and lifecycle-oriented overview of MCP architecture, adoption, and security/privacy risks across create/operate/update phases. Strong first read for MCP as an ecosystem, not only a tool API. |
| [MCP Safety Audit: LLMs with the Model Context Protocol Allow Major Security Exploits][link_arxiv_org_abs_2504_03767] - Brandon Radosevich, John Halloran - arXiv | Shows MCP workflows coerced into malicious execution, remote access, and credential theft; introduces MCPSafetyScanner (adversarial samples and reporting). Useful for red-team methodology, scanners, and lab design. |
| [Enterprise-Grade Security for the Model Context Protocol: Frameworks and Mitigation Strategies][link_arxiv_org_abs_2504_08623] - Vineeth Sai Narajala, Idan Habler - arXiv / conference listing | Threat modeling and enterprise control mapping from MCP architectural risks to implementable patterns. Fits governance, CISO narratives, and enterprise reference architecture. |
| [MCP Guardian: A Security-First Layer for Safeguarding MCP-Based AI System][link_arxiv_org_abs_2504_12757] - Sonu Kumar, Anubhav Girdhar, Ritesh Patil, Divyansh Tripathi - arXiv | Defense-in-depth layer for MCP traffic: authentication, rate limiting, logging, tracing, and WAF-style scanning; empirical scenarios against malicious tool servers and integrity risks. Useful for gateway and observability design discussions. |
| [Simplified and Secure MCP Gateways for Enterprise AI Integration][link_arxiv_org_abs_2504_19997] - Ivo Brett - arXiv | MCP gateway reference architecture with threat mapping and implementation recommendations for self-hosted enterprise use. Anchors gateways and enterprise governance topics. |
| [Beyond the Protocol: Unveiling Attack Vectors in the Model Context Protocol Ecosystem][link_arxiv_org_abs_2506_02040] - authors per arXiv - arXiv | Systematic study of MCP ecosystem attacks (e.g. tool poisoning, puppet and rug-pull patterns, malicious external resources) including marketplace-style distribution risks and user-study angles on discoverability of malicious servers. Complements survey and benchmark papers. |
| [Systematic Analysis of MCP Security][link_arxiv_org_html_2508_12538v1] - authors per preprint - arXiv HTML | Systematic analysis emphasizing tool poisoning and risks from concise protocol design. Maps protocol design choices to practical attacks. |
| [MCPTox: A Benchmark for Tool Poisoning Attack on Real-World MCP Servers][link_arxiv_org_abs_2508_14925] - Zhiqiang Wang et al. - arXiv / AAAI listing | Benchmark from live MCP servers and authentic tools; malicious cases across risk categories; reports widespread agent vulnerability. Empirical tool-poisoning evidence and defensive evaluation. |
| [MCIP: Protecting MCP Safety via Model Contextual Integrity Protocol][link_aclanthology_org_2025_emnlp_main_62] - Huihao Jing et al. - EMNLP 2025; HKUST / Huawei Technologies | Proposes MCIP: tracking tools and guard model; contextual-integrity framing, trajectory logging, taxonomy, benchmarks/experiments. Information-flow tracking, auditability, policy-aware MCP design. |
| [Securing the Model Context Protocol: Risks, Controls, and Governance][link_arxiv_org_abs_2511_20920] - Herman Errico, Jiquan Ngiam, Shanita Sojan - arXiv | Frames MCP’s move from static APIs to user-driven agents via risk, control, and governance lenses. Suited to board/CISO-level control discussions. |
| [Breaking the Protocol: Security Analysis of the Model Context Protocol Specification and Prompt Injection Vulnerabilities in Tool-Integrated LLM Agents][link_arxiv_org_abs_2601_17549] - Narek Maloyan, Dmitry Namiot - arXiv | Protocol analysis (capability attestation gaps, bidirectional sampling trust, multi-server trust propagation) with scenario evaluation. Protocol-level security, not only implementation bugs. |
| [Model Context Protocol Threat Modeling and Analyzing Vulnerabilities to Prompt Injection with Tool Poisoning][link_arxiv_org_abs_2603_22489] - Charoes Huang, Xin Huang, Ngoc Phu Tran, Amin Milani Fard - arXiv | STRIDE/DREAD across MCP components plus empirical tool-poisoning tests across major MCP clients. Client security, permission UX, host/client risk. |
| [MCP Security Bench: Benchmarking Attacks Against MCP-Based Agents][link_openreview_net_forum] - D. Zhang et al. - OpenReview / preprint | Large benchmark of MCP-based agent attacks across stages, scenarios, tasks, and tools. Supports red-team benchmarking and client/agent regression testing. |
| [Behavioral Detection Methods for Automated MCP Server Security Monitoring][link_digitalcommons_odu_edu_cgi_viewcontent_cgi] - C. Coleman - ODU undergraduate research repository | Explores behavioral detection for MCP server monitoring. SOC detection and anomaly-monitoring ideas. |

---

## MCP-Specific Specifications and Guidance

| Title - Author / Org | Summary |
| --- | --- |
| [Model Context Protocol Specification][link_modelcontextprotocol_io_specification_2025_11_25] - Model Context Protocol | Defines core MCP concepts (hosts, clients, servers, resources, prompts, tools, sampling, roots, elicitation, utilities) and trust/safety principles. **For this project:** trust boundaries, tool safety, consent, logging, roots/sampling/elicitation risks. |
| [MCP Security Best Practices][link_modelcontextprotocol_io_docs_tutorials_security_security_best_practice] - Model Context Protocol | Official guidance on confused deputy, token passthrough, SSRF, session hijacking, local server compromise, scope minimization. **For this project:** baseline attacks, mitigations, common mistakes, checklist items. |
| [MCP Authorization Specification][link_modelcontextprotocol_io_specification_draft_basic_authorization] - Model Context Protocol | OAuth-based authorization for HTTP transports: protected resource metadata, discovery, scopes, token handling. **For this project:** resource-server role, AS discovery, scope challenges, token storage. |
| [MCP Client / Server Top 10 Security Risks][link_modelcontextprotocol_security_io_top10] - MCP Security Working Group | Community Top 10 lists for server and client implementations. **For this project:** map to your risk taxonomy and review checklists. |
| [OWASP MCP Security Cheat Sheet][link_owasp_cheatsheetseries_mcp_security] - OWASP Cheat Sheet Series | Practical MCP hardening guidance covering least privilege, tool/schema integrity, sandboxing, human approval, authN/authZ, replay protection, multi-server isolation, supply chain, monitoring, consent, and prompt injection via tool return values. |
| [OWASP MCP Top 10][link_owasp_org_www_project_mcp_top_10] - OWASP | Community risk taxonomy for MCP-enabled systems. **For this project:** neutral naming layer across blogs, papers, labs, CVEs, and tools. |
| [OWASP MCP Tool Poisoning Attack Page][link_owasp_org_www_community_attacks_mcp_tool_poisoning] - OWASP | Tool poisoning as indirect prompt injection. **For this project:** attack taxonomy and lab references. |
| [OWASP Practical Guide for Securely Using Third-Party MCP Servers][link_genai_owasp_org_resource_cheatsheet_a_practical_guide_for_securely_usi] - OWASP GenAI Security Project | Third-party server adoption checklist. **For this project:** vetting, approval, monitoring, isolation, least privilege. |
| [OWASP Practical Guide for Secure MCP Server Development][link_genai_owasp_org_resource_a_practical_guide_for_secure_mcp_server_devel] - OWASP GenAI Security Project | Secure development for MCP server authors. **For this project:** architecture, auth, validation, session isolation, hardened deployment. |

### OAuth, Identity, and Authorization References

Read **[OAuth 2.1][link_datatracker_ietf_org_doc_draft_ietf_oauth_v2_1]** first (authorization-code flows and modern OAuth deployment). Then use the RFCs in order; each row merges **what the spec defines** with **why it matters for MCP HTTP authorization**.

| Title - Author / Org | Summary |
| --- | --- |
| [OAuth 2.1 (draft)][link_datatracker_ietf_org_doc_draft_ietf_oauth_v2_1] - IETF | Consolidates OAuth 2.0 errata; requires PKCE for public/native clients; tightens redirect URI and sender-constrained token guidance; deprecates implicit grant; aligns refresh-token and scope handling. **MCP:** normative baseline for MCP HTTP authorization before MCP-specific discovery and scopes. |
| [RFC 9728 - OAuth 2.0 Protected Resource Metadata][link_datatracker_ietf_org_doc_html_rfc9728] - IETF | Protected resource metadata (issuer, scopes, authorization_servers, jwks_uri, etc.). **MCP:** MCP servers as OAuth protected resources; clients discover AS and metadata URLs for an MCP endpoint. |
| [RFC 8414 - OAuth 2.0 Authorization Server Metadata][link_datatracker_ietf_org_doc_html_rfc8414] - IETF | Authorization server metadata (issuer, authorize/token/jwks/revocation endpoints) for automatic AS configuration. **MCP:** endpoint discovery after resource metadata points to an AS. |
| [RFC 7591 - OAuth 2.0 Dynamic Client Registration][link_datatracker_ietf_org_doc_html_rfc7591] - IETF | Dynamic client registration without static, out-of-band registration. **MCP:** runtime client registration-high risk for confused deputy and client-identity binding; needs policy and approval. |
| [RFC 9700 - OAuth 2.0 Security BCP][link_datatracker_ietf_org_doc_html_rfc9700] - IETF | Security BCP: tokens, PKCE, redirects, mix-up mitigation, metadata trust, sender-constrained tokens, operations. **MCP:** cross-check deployments for tokens, redirects, metadata trust alongside OAuth 2.1. |
| [RFC 8707 - Resource Indicators for OAuth 2.0][link_datatracker_ietf_org_doc_html_rfc8707] - IETF | `resource` parameter for audience binding and narrowing token scope to a resource URI. **MCP:** bind tokens to the MCP resource server; reduce cross-resource token replay. |
| [OpenID Connect Discovery 1.0][link_openid_net_specs_openid_connect_discovery_1_0_html] - OpenID Foundation | OpenID Provider metadata and discovery (issuer + `.well-known`); overlaps OAuth AS metadata when IdP and AS combine. **MCP:** optional path when OIDC discovery is available for AS metadata. |

### AI Security and Governance Standards

| Title - Author / Org | Summary |
| --- | --- |
| [NIST AI Risk Management Framework 1.0][link_nist_gov_itl_ai_risk_management_framework] - NIST | Governance, mapping, measuring, and managing AI risk at organizational level. Does not replace MCP-specific controls. |
| [NIST AI 600-1: Generative AI Profile][link_nist_gov_itl_ai_risk_management_framework] - NIST | Maps MCP-enabled agentic risks to GenAI risk-management actions (same landing page as AI RMF resources). |
| [ISO/IEC 42001:2023 Artificial Intelligence Management System][link_iso_org_standard_81230_html] - ISO/IEC | AI governance, accountability, risk management, and management-system controls for agentic AI. |
| [OWASP Top 10 for LLM Applications][link_genai_owasp_org_llm_top_10] - OWASP GenAI Security Project | MCP risks overlap with prompt injection, sensitive disclosure, supply chain issues, excessive agency, insecure output handling. |
| [OWASP Top 10 for Agentic Applications][link_genai_owasp_org_resource_owasp_top_10_for_agentic_applications_for_202] - OWASP GenAI Security Project | Agentic risk taxonomy for systems that plan, act, and use tools-companion to MCP-specific risk lists. |
| [CSA AI Controls Matrix][link_labs_cloudsecurityalliance_org_mcp] - Cloud Security Alliance | Control mapping for AI workloads; see also [Industry resource hubs](#industry-resource-hubs) for the broader CSA MCP index. |


[link_aclanthology_org_2025_emnlp_main_62]: https://aclanthology.org/2025.emnlp-main.62/
[link_aembit_io_blog_mcp_oauth_2_1_pkce_and_the_future_of_ai_authorization]: https://aembit.io/blog/mcp-oauth-2-1-pkce-and-the-future-of-ai-authorization/
[link_arxiv_org_abs_2503_23278]: https://arxiv.org/abs/2503.23278
[link_arxiv_org_abs_2504_03767]: https://arxiv.org/abs/2504.03767
[link_arxiv_org_abs_2504_08623]: https://arxiv.org/abs/2504.08623
[link_arxiv_org_abs_2504_12757]: https://arxiv.org/abs/2504.12757
[link_arxiv_org_abs_2504_19997]: https://arxiv.org/abs/2504.19997
[link_arxiv_org_abs_2506_02040]: https://arxiv.org/abs/2506.02040
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
[link_bleepingcomputer_asana_mcp_exposed]: https://www.bleepingcomputer.com/news/security/asana-warns-mcp-ai-feature-exposed-customer-data-to-other-orgs/
[link_blog_ogwilliam_mcp_remote_rce]: https://blog.ogwilliam.com/post/mcp-remote-rce-vulnerability-cve-2025-6514.html
[link_blogs_windows_securing_mcp]: https://blogs.windows.com/windowsexperience/?p=179739
[link_catonetworks_blog_curxecute_rce]: https://www.catonetworks.com/blog/curxecute-rce/
[link_catonetworks_blog_exploiting_mcp]: https://www.catonetworks.com/blog/cato-ctrl-exploiting-model-context-protocol-mcp
[link_catonetworks_blog_poc_atlassian_mcp]: https://www.catonetworks.com/blog/cato-ctrl-poc-attack-targeting-atlassians-mcp
[link_checkpoint_cursor_mcpoison]: https://research.checkpoint.com/2025/cursor-vulnerability-mcpoison
[link_cisco_community_mcp_and_security]: https://community.cisco.com/t5/security-blogs/ai-model-context-protocol-mcp-and-security/ba-p/5274394
[link_cursor_forum_chained_commands_yolo]: https://forum.cursor.com/t/chained-commands-bypass-yolo-mode-denylist/50775
[link_cursor_forum_yolo_bypass_allowlist]: https://forum.cursor.com/t/yolo-mode-bypasses-command-allowlist-using/36505
[link_csoonline_asana_mcp_connector]: https://www.csoonline.com/article/4009373/asanas-mcp-ai-connector-could-have-exposed-corporate-data-csos-warned.html
[link_cyberark_poison_everywhere]: https://www.cyberark.com/resources/threat-research-blog/poison-everywhere-no-output-from-your-mcp-server-is-safe
[link_cyberark_threat_analysis_mcp]: https://www.cyberark.com/resources/threat-research-blog/is-your-ai-safe-threat-analysis-of-mcp-model-context-protocol
[link_equixly_blog_mcp_api_security_models]: https://equixly.com/blog/2026/02/12/how-mcp-servers-challenge-traditional-api-security-models/
[link_equixly_blog_mcp_security_nightmare]: https://equixly.com/blog/2025/03/29/mcp-server-new-security-nightmare
[link_equixly_blog_offensive_security_mcp]: https://equixly.com/blog/2026/02/26/offensive-security-for-mcp-servers/
[link_generalanalysis_mcp_server_security]: https://generalanalysis.com/guides/mcp-server-security
[link_github_cursor_ghsa_mcp_reapproval]: https://github.com/cursor/cursor/security/advisories/GHSA-24mc-g4xr-4395
[link_github_tierzerosecurity_llm_threat_hunt]: https://github.com/TierZeroSecurity/llm_threat_hunt
[link_goteleport_blog_complicating_mcp_enterprise]: https://goteleport.com/blog/complicating-mcp-enterprise
[link_goteleport_blog_securing_mcp_with_aws]: https://goteleport.com/blog/securing-model-context-protocol-with-teleport-and-aws
[link_goteleport_blog_secure_ai_agents_zero_code_mcp]: https://goteleport.com/blog/secure-ai-agents-zero-code-mcp/
[link_jfrog_press_mcp_remote_rce]: https://jfrog.com/press-room/jfrog-security-research-team-discovers-critical-remote-code-execution-vulnerability-hijacking-mcp-remote-clients/
[link_labs_snyk_io_cursor_jira_mcp_vulnerability_explained]: https://labs.snyk.io/resources/cursor-jira-mcp-vulnerability-explained/
[link_labs_zenity_io_agentflayer_jira_ticket]: https://labs.zenity.io/p/when-a-jira-ticket-can-steal-your-secrets
[link_learn_microsoft_mcp_containment]: https://learn.microsoft.com/en-us/windows/ai/mcp/servers/mcp-containment
[link_lirantal_com_blog_cursor_jira_mcp_toxic_flow]: https://lirantal.com/blog/the-cursor-jira-mcp-attack-explained-with-toxic-flow-analysis
[link_mcpmanager_ai_blog_mcp_security_best_practices]: https://mcpmanager.ai/blog/mcp-security-best-practices/
[link_mcpmanager_ai_blog_mcp_security_risks]: https://mcpmanager.ai/blog/mcp-security-risks-model-context-protocol/
[link_mcpmanager_ai_blog_mcp_supply_chain_security]: https://mcpmanager.ai/blog/mcp-supply-chain-security/
[link_nickyt_agentic_access_ato_2025]: https://www.nickyt.co/talks/agentic-access-oauth-gets-you-in-zero-trust-keeps-you-safe-all-things-open-2025/
[link_nickyt_mcp_dev_summit_eu_2025]: https://www.nickyt.co/talks/mcp-developers-summit-eu-2025-building-secure-mcp-servers/
[link_nickyt_securing_mcp_zero_trust_apollo]: https://www.nickyt.co/talks/securing-mcp-servers-with-zero-trust-apollo-mcp-server-builder-series-2024/
[link_oasis_lessons_mcp_breach_shadow_ai]: https://www.oasis.security/blog/lessons-from-the-mcp-breach-shadow-ai
[link_pillar_agent_security_paradox]: https://www.pillar.security/blog/the-agent-security-paradox-when-trusted-commands-in-cursor-become-attack-vectors
[link_pillar_weaponize_code_agents]: https://www.pillar.security/blog/new-vulnerability-in-github-copilot-and-cursor-how-hackers-can-weaponize-code-agents
[link_prompthub_substack_5_mcp_vulns]: https://prompthub.substack.com/p/5-mcp-security-vulnerabilities-you
[link_prompthub_us_mcp_security_in_2025]: https://www.prompthub.us/blog/mcp-security-in-2025
[link_pulik_dev_blog_mcp_security]: https://pulik.dev/blog/mcp-security
[link_research_jfrog_mcp_remote_command_injection]: https://research.jfrog.com/vulnerabilities/mcp-remote-command-injection-rce-jfsa-2025-001290844/
[link_simonwillison_net_2025_aug_9_when_a_jira_ticket_can_steal_your_secrets]: https://simonwillison.net/2025/Aug/9/when-a-jira-ticket-can-steal-your-secrets/
[link_thenewstack_mcp_evolution]: https://thenewstack.io/model-context-protocol-evolution/
[link_thenewstack_mcp_security_reality_check]: https://thenewstack.io/the-model-context-protocol-security-reality-check/
[link_trailofbits_ansi_deception_mcp]: https://blog.trailofbits.com/2025/04/29/deceiving-users-with-ansi-terminal-codes-in-mcp/
[link_vulcan_mcp_38_taxonomy]: https://vulcanlab.ai/introducing-mcp-38/
[link_vulnerablemcp_info_cursor_jira_mcp_zero_click]: https://vulnerablemcp.info/vuln/cursor-jira-mcp-zero-click.html
