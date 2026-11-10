# YouTube Videos

## Contents

- [General and primer videos](#youtube-videos)
- [Security Videos](#security-videos)
- [MCP Demo and PoC Videos](#mcp-demo-and-poc-videos)
- [MCP CVE and Exploit Videos](#mcp-cve-and-exploit-videos)

Include videos that help learners understand, build, break, defend, or govern MCP-based systems.


| Title: Channel - Speaker / Host                                                                                                      | Date       | Summary                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Why we built—and donated—the Model Context Protocol (MCP)][link_youtube_com_watch]: **Anthropic** - Stuart Ritchie, David Soria Parra | 2025-12-11 | Background on why MCP was created, how it evolved, and why standardizing tool/data access matters for the agent ecosystem. Good first “why this exists” video.                     |
| [The Model Context Protocol (MCP)][link_youtube_com_watch_2]: **Anthropic** - Theo Chu, David Soria Parra, Alex Albert                | 2025-06-16 | A creator/developer discussion covering MCP fundamentals, what problem it solves, and how it changes AI application architecture.                                                  |
| [The Creators of Model Context Protocol][link_youtube_com_watch_3]: **Latent Space** - Justin Spahr-Summers, David Soria Parra        | 2025-04-03 | Origin story and design discussion from MCP creators. Useful for understanding the intent behind hosts, clients, servers, and standardized tool access.                            |
| [The Future of MCP - David Soria Parra, Anthropic][link_youtube_com_watch_4]: **AI Engineer** - David Soria Parra                     | 2026-04-19 | Forward-looking talk on the direction of MCP, ecosystem growth, and future protocol patterns. Good for advanced readers tracking where MCP is going.                               |
| [MCP In 26 Minutes (Model Context Protocol)][link_youtube_com_watch_5]: **Tina Huang**                                                | 2025-10-15 | Beginner-friendly overview of MCP fundamentals, common use cases, how MCP servers work, and how to build/use MCP integrations. Good for non-security readers starting from zero.   |
| [Model Context Protocol (MCP): Architecture, Servers, Workflows Automation][link_youtube_com_watch_6]: **DataTalks.Club** - Bhavani Ravi | 2025-11-04 | Workshop-style deep dive into MCP architecture, primitives such as tools/resources/prompts, external servers, and workflow automation examples.                                    |
| [Model Context Protocol (MCP) Explained in 17 Minutes][link_youtube_com_watch_7]: **Jan Marshal**                                     | 2025-05-04 | Short conceptual introduction explaining MCP as a standardized way to connect AI applications to external tools and data sources.                                                  |
| [Model Context Protocol (MCP) Explained in 20 Minutes][link_youtube_com_watch_8]: **Shaw Talebi**                                     | 2025-04-27 | Concise overview of MCP concepts, use cases, and demos. Useful as a quick refresher for developers before hands-on labs.                                                           |
| [Understanding MCP Architecture with Examples][link_youtube_com_watch_9]: **Amit Thinks**                                             | 2026-01-17 | Explains MCP’s client-server architecture with examples. Useful for readers who prefer visual diagrams and practical analogies.                                                    |
| [Model Context Protocol: Principles and Practice][link_youtube_com_watch_10]: **Python Milano**                                       | 2026-03-05 | Covers MCP principles and applied usage patterns. Good candidate for readers who want both concepts and implementation context.                                                    |
| [Claude's Model Context Protocol is here... Let's test it][link_youtube_com_watch_56]: **Fireship**                                     | 2025-03-31 | High-reach primer and build demo framing MCP as “USB-C for AI,” with a TypeScript server walkthrough. One of the most-cited introductory MCP videos.                               |
| [MCP Servers Explained in 5 Minutes (for beginners)][link_youtube_com_watch_57]: **corbin**                                            | 2025-04-06 | Fast conceptual overview of MCP servers, tools, and how hosts connect—good “first five minutes” before longer labs.                                                                |
| [Build Anything with MCP Agents… Here's How][link_youtube_com_watch_58]: **Tech With Tim**                                             | 2025-03-27 | Practical Cursor-focused demo: installing MCP servers, using Smithery, and wiring agents to external tools like Firecrawl.                                                           |
| [Full Course (Lessons 1–11) MCP for Beginners][link_youtube_com_watch_59]: **Microsoft Developer** - April Gittens                     | 2025-07-28 | Official Microsoft course covering MCP core concepts, hands-on development, and **Lesson 3: MCP security best practices** (prompt injection, tool poisoning, Prompt Shields).      |
| [Power up your LLMs: Gemini CLI and Model Context Protocol (MCP)][link_youtube_com_watch_60]: **Google for Developers**               | 2025-08-29 | Google tutorial on building an MCP server, connecting Gemini CLI, and OAuth flows for third-party actions (e.g. Linear).                                                           |
| [Understanding MCP From Scratch][link_youtube_com_watch_63]: **LangChain**                                                             | 2025-03-18 | Builds an MCP server from scratch and connects it to Claude, Cursor, and Windsurf—useful for understanding host/client/server wiring end to end.                                 |
| [Model Context Protocol Tutorial for Beginners \| Build with MCP Server][link_youtube_com_watch_64]: **Amit Thinks**                   | 2025-12-07 | Beginner build tutorial complementing Amit Thinks’ architecture overview—hands-on MCP server setup for learners starting in 2026.                                                    |
| [Everyone Is Talking About MCP. Here's Why.][link_youtube_com_watch_62]: **World Wide Technology**                                     | 2026-06-22 | Hands-on lab using Docker Desktop MCP Toolkit, VS Code, Continue.dev, and NVIDIA NIM—good for packaging, catalog, and sandboxed MCP deployment context.                           |
| [MCP Explained: The Only Video You Need !][link_youtube_com_watch_61]: **CsMadeEz**                                                    | 2026-07-06 | Deep-dive explainer covering architecture, JSON-RPC transports, tool poisoning, supply-chain risks, OAuth 2.0, and MCP Apps/Tasks in the 2026 spec.                                  |
| [Remote MCPs: What we learned from shipping — John Welsh, Anthropic][link_youtube_com_watch_82]: **AI Engineer** - John Welsh          | 2025-06-19 | Anthropic’s production lessons from remote MCP deployments, including centralized gateways, credential management, rate limiting, observability, auditing, and policy enforcement. |


---

# Security Videos


| Title: Channel - Speaker / Host                                                                                                                     | Date                                | Summary                                                                                                                                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Securing Model Context Protocol (MCP) with Vandana Verma (OWASP/Snyk)][link_youtube_com_watch_11]: **Daniel Zivkovic** - Vandana Verma           | 2025-12-05 (live); 2025-12-06 (YouTube) | Long-form security session covering production concerns for MCP-powered agents, practical controls, and how MCP risks map to broader AI security guidance.          |
| [First Look - OWASP MCP Top 10 - 2025][link_youtube_com_watch_12]: **Vandana Verma**                                                                | 2025-10-30                             | Quick introduction to MCP security risk categories and why the OWASP MCP Top 10 matters for builders and defenders.                                                 |
| [OWASP GenAI Webinar: Why MCP Agents Are the Next ...][link_youtube_com_watch_13]: **OWASP GenAI Security Project**                                  | 2026-01-21                             | Useful for readers connecting MCP risks with OWASP GenAI guidance and agentic application security.                                                                 |
| [Foundations of Secure MCP: Architecture and Threat Model][link_youtube_com_watch_14]: **Google Cloud Tech**                                         | 2026-01-27                             | Focuses on core MCP security architecture and threat vectors. Good for defenders designing secure MCP deployments.                                                  |
| [Security for MCP][link_youtube_com_watch_15]: **S&P Global Market Intelligence**                                                                   | 2025-07-10                             | A security-focused discussion on MCP’s security model and risks introduced when AI applications gain broad access to data sources.                                  |
| [MCP Security: Why Your AI Assistant Is an Insider Threat (with Liran Tal, Snyk)][link_youtube_com_watch_16]: **Obot AI** - Liran Tal               | 2026-03-02                             | Practical discussion on why MCP-connected assistants can become insider-risk amplifiers when easy install/publish workflows meet sensitive data and powerful tools. |
| [Securing MCP Servers by Daniel Garnier Moiroux][link_youtube_com_watch_17]: **Devoxx** - Daniel Garnier Moiroux                                      | 2025-10-10                             | Developer-focused talk on securing public MCP servers with OAuth2 and access-control patterns. Strong fit for secure implementation guidance.                       |
| [MCP Prompt Injection: How AI Gets Hacked][link_youtube_com_watch_18]: **TestMu AI (Formerly LambdaTest)**                                            | 2025-11-12                             | Explains how MCP-connected systems can be manipulated through malicious instructions, poisoned tools, and dynamic behavior changes.                                 |
| [MCP Security is Still Broken][link_youtube_com_watch_19]: **Prompt Engineering**                                                                   | 2025-04-11                             | Reviews MCP security concerns and tool-poisoning-style attack vectors. Good discussion video for why MCP security cannot rely on user trust alone.                  |
| [MCP Security Master Class Playlist][link_youtube_com_playlist]: **AumLayer**                                                                       | 2025-2026                           | Multi-video playlist covering MCP injection attacks, access control, threat modeling, and common security mistakes. Useful as a structured learning path.           |
| [MCP Security Master Class \| MCP Security Explained \| Introduction to the Series.][link_youtube_com_watch_65]: **AumLayer**                          | 2025-08-16                             | Series opener: MCP security scope, STRIDE + OWASP LLM-10 threat model, and AppSec-style design/code review framing for MCP systems.                                 |
| [MCP Security Master Class \| MCP Fundamentals and Architecture Part - 1][link_youtube_com_watch_66]: **AumLayer**                                    | 2025-08-17                             | First fundamentals episode—MCP architecture from a defender’s lens before diving into communication flows and attack scenarios.                                     |
| [MCP Security Master Class \| MCP Fundamentals and Architecture Part - 2][link_youtube_com_watch_67]: **AumLayer**                                    | 2025-08-19                             | Continues architecture deep dive with security-relevant primitives (tools, resources, prompts) and trust-boundary setup.                                            |
| [MCP Security Master Class \| MCP Communication Flow Part - 1][link_youtube_com_watch_68]: **AumLayer**                                               | 2025-08-19                             | Walks JSON-RPC message flow and where intercept/tamper/injection risks appear across client–server exchanges.                                                       |
| [MCP Security Master Class \| MCP Communication Flow Part - 2][link_youtube_com_watch_69]: **AumLayer**                                               | 2025-08-20                             | Extends communication-flow analysis to transport choices (stdio vs HTTP/SSE) and session/state considerations.                                                      |
| [MCP Security Master Class \| MCP Communication Flow Part - 3][link_youtube_com_watch_70]: **AumLayer**                                               | 2025-08-20                             | Completes the communication-flow arc with sampling, elicitation, and runtime data-path risks defenders should monitor.                                              |
| [MCP Security Master Class \| MCP Threat Modelling][link_youtube_com_watch_71]: **AumLayer**                                                           | 2025-08-22                             | STRIDE applied across the User→AI→Client→Server→Backend chain; attack-surface mapping and priority matrices for MCP implementations.                                |
| [MCP Security Master Class - MCP INJECTION ATTACKS][link_youtube_com_watch_20]: **AumLayer**                                                         | 2025-08-25                             | Focuses on MCP injection attacks and how authorization/access-control weaknesses influence attack paths.                                                            |
| [MCP Security Master Class - MCP ACCESS CONTROLS][link_youtube_com_watch_21]: **AumLayer**                                                           | 2025-08-26                             | Explains where access controls should exist in MCP systems and how poor authorization can create risk.                                                              |
| [MCP Security Master Class - MCP COMMON SECURITY MISTAKES][link_youtube_com_watch_22]: **AumLayer**                                                  | 2025-08-28                             | Good candidate for a checklist-style “what not to do” video for developers building MCP integrations.                                                               |
| [MCP Security for Agentic AI Platforms: Attack Vectors & Best ...][link_youtube_com_watch_23]: **APIsec University**                                 | 2026-02-17                             | Covers MCP risks in broader agentic AI platforms, including hidden tool access and cross-context data leakage.                                                      |
| [These Aren't the Tools You're Looking For: MCP Security Awakens][link_youtube_com_watch_24]: **AI Native Dev**                                       | 2025-11-27                             | Security talk-style title focused on malicious MCPs, poisoned tools, and indirect prompt injection against MCP-connected IDEs.                                      |
| [MCP: Model Context Protocol or Malicious Control Path?][link_youtube_com_watch_25]: **HITCON**                                                      | 2025-09-29                             | Useful for helping security teams understand why MCP integrations must be treated as execution and data-access pathways, not harmless chat plugins.                 |
| [The OWASP MCP Top 10 — Every Risk Ranked and Explained][link_youtube_com_watch_51]: **StackOps AI**                                                  | 2026-05-14                             | One-minute ranked walkthrough of all ten OWASP MCP Top 10 risks with brief mitigations—good quick refresher after the formal taxonomy.                              |
| [AI Agents and MCP Security Risks - Risk Mitigation][link_youtube_com_watch_52]: **Black Hills Information Security** - Joff Thyer                     | 2025-12-17                             | Short clip from the full BHIS webcast listed below: chroot and filesystem restrictions, logging, RBAC, and validating tool data sources before agent execution.                                    |
| [Agent Identity for MCP: Prefactor's Approach to Secure, Auditable AI Agents][link_youtube_com_watch_53]: **Agentic AI Foundation** - Matt Doughty, Simon | 2025-09-19                             | Demo and deep dive on agent identity beyond OAuth: signed payloads, immutable audit logs, workload identity, and task-based access for MCP.                         |
| [Securing the Future of AI: Securing MCP with Defense in Depth Patterns][link_youtube_com_watch_55]: **Microsoft BlueHat / MSRC** - Jitesh Thakur                                | 2026-05-20                          | Microsoft Security Response Center session on layered defenses for MCP: treating tool descriptions as code, sandboxing, authorization boundaries, tool-integrity verification, and runtime monitoring against tool poisoning and confused-deputy attacks. |
| [MCP Security: The Exploit Playbook (And How to Stop Them)][link_youtube_com_watch_73]: **AAIF Live** - Vitor Balocco                                                      | 2026-02-21                             | Agents in Production recording of the Runlayer playbook: tool poisoning, rug pulls, conversation-history theft, and cross-server tool shadowing, with a defensive checklist. The MCP Dev Summit EU 2025 cut is listed separately. |
| [Bsides Seattle 2026: MCP LFI in 60 minutes (or your money back)][link_youtube_com_watch_72]: **Kurt Boberg**                                                                       | 2026-04-28                             | Hands-on BSides session on local file inclusion and related abuse paths in MCP-oriented setups—good red-team lab companion.                                         |
| [Securing the AI Frontier: Navigating MCP Vulnerabilities][link_youtube_com_watch_74]: **CISO Marketplace**                                                                           | 2026-05-22                             | Discusses MCP design weaknesses (unrestricted repo access, parameter injection, RCE class issues) and defenses: sandboxing, input validation, and trust boundaries. |
| [Snyk MCP Server: AI-Powered Developer Security][link_youtube_com_watch_75]: **Snyk**                                                                                               | 2026-05-25                             | Short overview of Snyk’s MCP integrations for in-agent SAST/SCA/SBOM scanning—defensive tooling for secure AI coding workflows.                                     |
| [MCP In Production: Building Secure and Agent-Ready Model Context Protocol Servers][link_youtube_com_watch_83]: **Microsoft Developer** - Nate Tindall, Wils Dawson                  | 2025-07-30                             | Production guidance for OAuth 2.1, token validation, and defenses against confused-deputy attacks, session hijacking, and token passthrough.                         |
| [MCP Security: What Happens When Your Agents Talk to Everything?][link_youtube_com_watch_84]: **AAIF Live**                                                                          | 2026-01-11                             | Explains policy enforcement for over-privileged agents, with role-aware tools, anomaly detection, behavioral limits, and human escalation for sensitive actions.    |
| [Building secure, real time AI agents with Google ADK & MCP Toolbox][link_youtube_com_watch_85]: **Google Cloud Tech** - Paul Ramsey                                                   | 2026-02-12                             | Secure database-agent architecture using predefined parameterized tools, IAP, Secret Manager, private networking, connection pooling, and credential isolation.    |
| [Session Replay \| How to Secure the Full AI Agent Stack From Identity to Authorization][link_youtube_com_watch_86]: **Gravitee**                                                     | 2026-08-04                             | End-to-end agent and user identity demo covering OAuth, delegated identity, granular scopes, MCP gateway enforcement, consent, and auditable authorization.          |
| [TanStack AI and the future of agentic tooling][link_youtube_com_watch_44]: **Arcade** - Jack Herrington               | 2026-03-16  | Long-form Arcade channel episode: TanStack AI orchestrating MCP tools, “Code Mode,” human-in-the-loop approval-useful alongside OAuth-focused tutorials when you are threat-modeling **agent + tool orchestration**, not only transport auth.                                                |
| [Unlock the Power of Arcade.dev to Deploy Secure AI Agents TODAY!][link_youtube_com_watch_45]: **Arcade**            | 2025-06-13  | Short Arcade clip on shipping agentic integrations without hard vendor lock-in-frequently bundled with “Arcade + MCP” auth discussions as the **product positioning** companion to deeper OAuth/tool-auth build videos.                                                                      |
| [Agent2Agent + (MCP to Tool) in Multi-Agent AI][link_youtube_com_watch_46]: **Discover AI**                            | 2025-04     | Explains Google **A2A** alongside **MCP-for-tools** patterns (multi-agent + tool access). Valuable when curators label the clip as “A2A/MCP threats/surface” in the sense of **cross-protocol composition and trust propagation**, not only single-server MCP bugs.                              |
| [The last MCP server you'll ever need...][link_youtube_com_watch_47]: **Better Stack**                                 | 2025-06-07  | Better Stack walkthrough of **Docker MCP Toolkit**-style packaging: cataloging, OAuth-forward setup, container isolation-often cited in “fix MCP sprawl/secret soup” curations.                                                                                                                    |
| [MCP Security: Vetting Servers to Mitigate Tool Poisoning Attacks][link_youtube_com_watch_48]: **JeredBlu**             | 2025-04-03  | Practical **vetting methodology** and demo of evaluating a marketplace MCP server before install-matches “don’t YOLO random MCPs” guidance in many lists.                                                                                                                                        |
| [Model Context Protocol (MCP) Security Concerns][link_youtube_com_watch_49]: **Cory Wolff**                             | 2025-04-03  | Practitioner-focused **risk framing** for MCP adoption (attack surface, trust, and operational security mindset)-commonly grouped with early-2025 “MCP is powerful but scary” picks.                                                                                                              |
| [Adding Authentication to your MCP Server Tools][link_youtube_com_watch_50]: **Dev Leonardo**                          | 2025-07-28  | Hands-on **OAuth-style protection** for MCP tools (sessions, metadata, MCP SDK usage). Often appears next to Arcade/Stytch-style “auth for agents” content as a **framework-agnostic implementation** reference.                                                                                 |
| [MCP Security Fundamentals Course][link_youtube_com_watch_90]: **freeCodeCamp.org** - Dan Barahona | 2026-10-22 | Two-hour AI Security University course on MCP anatomy, the lethal trifecta, and each OWASP MCP Top 10 risk with a real incident and a mitigation. Quiz, badge, and CPE credits sit on aisec.university. |
| [MCP Security \| Video 1 \| MCP The Universal Adapter for AI][link_youtube_com_watch_112]: **Vandana Verma** | 2026-09-21 | Opens the short series by treating MCP as the adapter between AI clients and tools, and as a security boundary rather than a convenience plugin. |
| [MCP Security \| Explained MCP Security][link_youtube_com_watch_117]: **Vandana Verma** | 2026-09-21 | Explains how hosts, servers, tools, and external systems expand the attack surface once a model can take actions. |
| [MCP Security \| Video 2 \| The MCP Security Stack Exploded][link_youtube_com_watch_113]: **Vandana Verma** | 2026-09-21 | Breaks the MCP security stack into separate layers so identity, tool trust, and runtime controls are not collapsed into one gateway. |
| [MCP Security \| Video 3 \| Build Your Own MCP or Use a Managed Service][link_youtube_com_watch_114]: **Vandana Verma** | 2026-09-22 | Compares owning an MCP server with consuming a managed one, and where security ownership sits in each choice. |
| [MCP Security \| Video 4 \| Dont Build One Giant SOC Agent][link_youtube_com_watch_115]: **Vandana Verma** | 2026-09-23 | Argues for narrower SOC agents: scoped tools and a smaller blast radius instead of one agent that can reach every system. |
| [MCP Security \| Video 5 \| The 4 A M Threat Hunt][link_youtube_com_watch_116]: **Vandana Verma** | 2026-09-24 | Closes the series on threat hunting when MCP-connected agents are already in the SOC workflow. |
| [Trust Issues: How MCP Servers Hijack Your AI Agent — and How to Stop Them][link_youtube_com_watch_91]: **SANS Cyber Defense** - Seth Misenar | 2026-05-14 | SANS SEC411 session on context injection: tool poisoning, rug pulls, and cross-server poisoning of a shared context window, plus the Lethal Trifecta++ and 4A control frames. |
| [Governing AI Agents at Runtime: Open Source Zero-Trust with AGT \| Ubuntu Summit 26.04][link_youtube_com_watch_103]: **Canonical Ubuntu** - Imran Siddique | 2026-06-22 | Microsoft’s open-source Agent Governance Toolkit: policy before every tool call, including an MCP security gateway aimed at poisoned tool descriptions and related agent abuse. |
| [Designing MCP for Real-World Agents with Jeremiah Lowin][link_youtube_com_watch_110]: **Open Data Science and AI Conference** - Jeremiah Lowin | 2026-05-27 | FastMCP author’s production lessons: guardrails, code mode, MCP Apps, and REST-to-MCP patterns security teams should audit before a server ships. |
| [Confused Deputies and Stolen Tokens: Breaking and Rebuilding MCP Auth with Brooks McMillin][link_youtube_com_watch_98]: **Off By One Security** - Brooks McMillin | 2026-05-23 | Walks a typical MCP auth deployment: bearer-token leakage through prompt injection, scope creep, confused-deputy abuse, and audience binding when rebuilding the flow. |
| [BSidesSF 2026 - MCPwned: Hacking MCP Servers with One Skeleton Key Vulnerability][link_youtube_com_watch_104]: **Security BSides San Francisco** - Jonathan Leitschuh | 2026-03-22 (talk); 2026-05-11 (YouTube) | DNS rebinding against local SSE and Streamable HTTP MCP servers: a malicious site drives a developer’s localhost server. Live demos and the bounty follow-up across common SDKs. |
| [Secure Your MCP Servers With OAuth, JWT, SPIFFE and More][link_youtube_com_watch_92]: **CNCF** - Lin Sun, Yi Yang | 2026-03-23 | Open Source SecurityCon demo from in-process OAuth on one server to a gateway that enforces OAuth, JWT, and SPIFFE and multiplexes backends. |
| [Model Context Protocol (MCP) Authorization for Enterprise Use Case With Keycloak][link_youtube_com_watch_93]: **CNCF** - Yutaka Obuchi | 2026-03-23 (talk); 2026-04-13 (YouTube) | KeycloakCon walkthrough of enterprise-managed authorization: identity assertion, token exchange, and central IdP control for MCP (SEP-646, RFC 7523). |
| [MCP Security: Keep Your AI Agents from Spilling the Tea][link_youtube_com_watch_94]: **NDC Conferences** - Manfred Bjørlin, Awar Abdulkarim | 2026-03-04 (talk); 2026-05-11 (YouTube) | NDC Security Oslo demo of layered MCP auth: network controls, an AI firewall, RFC 8693 token exchange versus elicitation, and KAgent on Kubernetes with OIDC, Kyverno, and scoped tools. |
| [SAFE-MCP: A Security Framework for AI+MCP (Model Context Protocol)][link_youtube_com_watch_102]: **CNCF** - Frederick Kautz | 2025-11-10 (talk); 2025-11-24 (YouTube) | TestifySec’s SAFE-MCP framework: attack techniques such as tool poisoning, command injection, and rug pulls, mapped to detection and mitigation playbooks. |
| [MCP Security Survival Guide: Best Practices, Pitfalls & Real-World Lessons][link_youtube_com_watch_105]: **Agentic AI Foundation** - Hailey Thao Q. | 2025-11-02 | IBM walkthrough of authorization and confused-deputy traps, open binds, token leaks, SQL injection in reference servers, and indirect injection, with a checklist. |
| [State of MCP Security][link_youtube_com_watch_106]: **Akto** - Raji Vanninathan | 2025-10-25 | MCP & Agentic Security Conference session from Microsoft: terminology, enterprise adoption, and the threat themes showing up as MCP spreads. |
| [MCP Security Best Practices][link_youtube_com_watch_107]: **Akto** - Ashish Bhadouria | 2025-10-25 | IKEA product-security lessons from a global MCP rollout: internal registries, auditability, and layered defense. |
| [CISO Perspectives on Agentic AI & MCP Security][link_youtube_com_watch_101]: **HiddenLayer** - Malcolm Harkins, Beth-Anne Bygum, Gary McAlum | 2025-11-24 | CISO panel on agent governance, data access, privilege escalation, prompt injection, supply chain, monitoring, and red-team testing for MCP-connected systems. |
| [MCP and AI Agents: Identity Strategies for Safe API Access][link_youtube_com_watch_100]: **Curity** - Gary Archer, Judith Kahrer | 2025-12-18 | Webinar on MCP authorization, cross-organization agent trust, least-privilege tokens, human approval, and time-limited API access. |
| [MCP Hacking Guide (Ep. 148)][link_youtube_com_watch_99]: **Critical Thinking - Bug Bounty Podcast** - Justin Gardner | 2025-11-13 | Offensive walkthrough of MCP architecture, JSON-RPC transports, authentication, roots, sampling, elicitation, tools, and resources. |
| [Session: MCP Security: The Exploit Playbook (And How to Stop Them)][link_youtube_com_watch_95]: **Agentic AI Foundation** - Vitor Balocco | 2025-10-02 (talk); 2025-10-14 (YouTube) | Original MCP Dev Summit EU recording: live tool poisoning, rug pulls, conversation-history theft, and cross-server shadowing, with a defensive checklist per class. |
| [Why is MCP Auth Hard and What Are We Planning to Do About It][link_youtube_com_watch_96]: **Agentic AI Foundation** - Paul Carleton | 2025-10-02 (talk); 2025-10-09 (YouTube) | Anthropic maintainer view of MCP OAuth threats (phishing, MITM, dynamic client registration abuse), conformance testing, and spec work on ad-hoc client-server trust. |
| [When the Model Takes Control: The Hidden Risks of AI Autonomy Through MCP][link_youtube_com_watch_97]: **BruCON Security Conference** - Philippe Bogaerts | 2025-09-25 | BruCON 0x11 on line-jumping and tool poisoning: malicious servers and workflows that steer the model before explicit tool consent. |
| [Black Hat USA 2025 \| AI Enterprise Compromise - 0click Exploit Methods][link_youtube_com_watch_108]: **Black Hat** - Michael Bargury, Tamir Ishay Sharbat | 2025-08-06 (talk); 2026-02-22 (YouTube) | AgentFlayer zero-click chains, including Cursor with the Jira MCP: weaponized tickets hijack tool calls and exfiltrate secrets without a user click. |
| [Back to the Future: Hacking and Securing Connection-based OAuth Architectures][link_youtube_com_watch_109]: **Black Hat** - Kaixuan Luo, Xianbo Wang, Pui Ho Adonis Fung, Yanxiang Bi, Wing Cheong Lau | 2025-08-06 (talk); 2025-12-19 (YouTube) | Session fixation and cross-agent account takeover in connection-based OAuth used by agent platforms and MCP-style token managers, plus post-redirect mitigations. |
| [Understanding MCP Security Risks & Challenges][link_youtube_com_watch_111]: **TestMu AI (Formerly LambdaTest)** | 2025-12-11 | Short walkthrough of MCP’s delegated, multi-step tool use and where that unpredictability shows up as security exposure. |
| [OWASP MCP Top 10: Securing the New Trust Boundary for Agentic AI][link_youtube_com_watch_122]: **DZone Events** - Vandana Verma | 2026-09-04 | Walks the OWASP MCP Top 10 with real attack paths—prompt injection, tool poisoning, supply-chain abuse—and the controls teams can apply. |
| [OWASP Spotlight - Project 39 - OWASP MCP Governance and Risk][link_youtube_com_watch_123]: **Vandana Verma** | 2026-10-05 | Moves from ad-hoc MCP adoption to a governance framework: discovery and inventory, ownership, risk tiering, and tool controls. |
| [Shadow MCP Servers: The AI Security Risk Hiding on Your Developers' Laptops][link_youtube_com_watch_124]: **The Application Security Podcast** - Vandana Verma Sehgal | 2026-10-12 | Why most organizations cannot count the MCP servers on developer machines, and how that turns a chatbot into an uninventoried tool runtime. |
| [Security and Authorization for Model Context Protocol (MCP)][link_youtube_com_watch_125]: **OWASP Foundation** | 2026-10-24 | OWASP Foundation session on securing and authorizing MCP. |
| [Black Hat Asia 2026 \| Remote Server, Local Root. Welcome to MCP.][link_youtube_com_watch_126]: **Black Hat** - Jiacheng Zhong, Shuyang Wang, Zhengyu Liu, Aonan Guan | 2026-04-24 (talk); 2026-08-20 (YouTube) | Malicious remote MCP servers supply the authorization URL the client opens, yielding local code execution across browser, process, and hybrid clients. |
| [Black Hat Europe 2025 \| Compromising The AI Agent Ecosystem Via Its "Universal Connector"][link_youtube_com_watch_127]: **Black Hat** - Cheng Huangsheng, Jing Guo, Wu Huiyu, Sim Zheng | 2025-12-10 (talk); 2026-07-13 (YouTube) | Eight-month audit of public MCP projects: hundreds of vulnerabilities, and how the protocol becomes a path into the agent ecosystem. |
| [Breaking the Control Plane: Exploiting MCP Servers in AI Workflows][link_youtube_com_watch_128]: **TROOPERS IT Security Conference** - Yotam Perkal | 2026-06-24 (talk); 2026-07-27 (YouTube) | Troopers 26 offensive research: header-injection control-plane override and SSRF-to-file-write-to-RCE chains, including Atlassian MCP CVE-2026-27825 and CVE-2026-27826. |
| [Building A Zero Trust MCP Server Gateway][link_youtube_com_watch_129]: **BSides Toronto** - Aakansha Puri, Navjot Singh | 2025-10-04 (talk); 2025-10-12 (YouTube) | Gateway between agents and MCP tools: per-tool allow and deny, schema validation, isolation, and audit for prompt injection and tool abuse. |
| [Breaking Model Context Protocol - Back to Security Basics][link_youtube_com_watch_130]: **CactusCon** - Brooks McMillin | 2026-02-06 (talk); 2026-08-14 (YouTube) | Audit of a task-management MCP server: tool-description abuse, command injection, missing PKCE, DNS rebinding, and token-handling failures, with CVE walkthroughs. |
| [DEF CON 34 - MCPwned: How Exposed AI Agents Became the Net’s New Recon Toy][link_youtube_com_watch_131]: **DEFCONConference** - Eli Woodward | 2026-08 (DEF CON 34); 2026-11-06 (YouTube) | Honeypot research on internet scanners hitting exposed LLM gateways, MCP servers, and local AI developer tooling. Separate from the BSidesSF DNS-rebinding MCPwned talk. |
| [MCP: Revolution or Security Regression][link_youtube_com_watch_132]: **LLMday** - Adrian Sroka | 2026-02-12 (talk); 2026-03-03 (YouTube) | LLMday Warsaw on the MCP attack surface that shows up once assistants can call tools, and where that regresses existing security assumptions. |
| [The Model Context Protocol: A Deep Dive into the New AI Security Attack Surface][link_youtube_com_watch_133]: **Devworld Conference** - Ricardo Goncalves | 2026-06-03 | How standardizing model-to-tool calls creates an attack surface development teams miss when they treat MCP as an integration convenience. |
| [MCP Threat Landscape][link_youtube_com_watch_134]: **Akto** - Harish Ramadoss | 2025-10-25 | Rippling’s offensive and defensive tour of MCP integrations with tools such as GitHub, Slack, and Jira, from the 2025 MCP and Agentic Security Conference. |
| [Least-Privilege for AI: Authorizing Agents and MCP Tools with Agentgateway and Kyverno][link_youtube_com_watch_135]: **CNCF** - Luc Chmielowski, Nina Polshakova | 2026-03-24 (talk); 2026-04-08 (YouTube) | KubeCon: Kyverno policies on agentgateway MCP traffic, tool allowlists, tenant isolation, and Kubernetes actions tied back to user identity. |
| [MCPIdentity: Keyless MCP Agent Authentication Patterns on Kubernetes With Keycloak][link_youtube_com_watch_136]: **CNCF** - M. Dayıoğlu | 2026-08-17 | Keyless authentication patterns for MCP agents on Kubernetes, using Keycloak rather than long-lived agent passwords. |
| [Your Agent Shouldn't Log in as You: Identity for MCP in Backstage][link_youtube_com_watch_137]: **CNCF** - Shivay Lamba, Hrittik Roy | 2026-11-09 | Backstage scoped, short-lived MCP tokens, and what goes wrong when teams still let an agent act with a human’s login. |
| [Intro to OAuth for MCP Servers][link_youtube_com_watch_138]: **Agentic AI Foundation** - Aaron Parecki | 2025-05-31 | Okta identity-standards intro to OAuth for MCP servers: delegated access without sharing passwords, aimed at people implementing the auth spec. |
| [Agentic Access: Securing MCP Servers in Enterprise Environments][link_youtube_com_watch_139]: **Pomerium** - Nick Taylor, Denis Mishin | 2025-06-10 | Per-request access control and a single policy point in front of enterprise MCP servers. |
| [The Binding Gap: The MCP Tool Your Agent Vetted Is Not the Tool It Calls][link_youtube_com_watch_140]: **Pomerium** - Gautam Bharti, Nick Taylor | 2026-10-14 | The gap between the tool an agent discovers and approves and the tool it later invokes, and what that does to MCP trust. |
| [MCP Security & Authorization][link_youtube_com_watch_141]: **Pomerium** - Den Delimarsky, Nick Taylor | 2025-07-23 | MCP steering-committee security maintainer on authorization: what the spec requires and where implementers still get it wrong. |
| [Agentic Access: OAuth Gets You In, Zero Trust Keeps You Safe][link_youtube_com_watch_142]: **Pomerium** - Nick Taylor | 2025-08-20 | Black Hat USA 2025 cut: OAuth 2.1 and resource indicators get an agent in, and authorization after that still has to be enforced per request. |
| [AI Agents and MCP Security Risks][link_youtube_com_watch_143]: **Black Hills Information Security** - Joff Thyer | 2025-10-30 | Full webcast behind the short clip above: agent and MCP risk, filesystem bounds, logging, RBAC, and checking tool data before execution. Slides are linked from the video. |
| [MCP Security Deep Dive][link_youtube_com_watch_144]: **The AI Security Summit** - Jared Hanson | 2025-12-01 | AI Security Summit deep dive on MCP security from Keycard. |
| [Hacking MCP: Supply Chain Attacks & Tool Execution Hijacking][link_youtube_com_watch_145]: **APIsec University** - Paul Zenker, Justin Szczepaniak | 2026-02-17 | Live demos of backdooring user-writable MCP config files and hijacking tool execution. |
| [Securing MCP Servers in Production: Threat Modeling with STRIDE, MAESTRO and the OWASP MCP Top 10][link_youtube_com_watch_146]: **VamiSec** | 2026-08-12 | End-to-end threat model of an MCP server through STRIDE, MAESTRO, and the OWASP MCP Top 10, including where the spec leaves security to the implementer. |
| [MCP security best practices][link_youtube_com_watch_147]: **Microsoft Developer** | 2025-07-28 | Standalone lesson from Microsoft’s MCP for Beginners course: prompt injection, tool poisoning, dynamic tool swaps, token passthrough, and session hijacking. |
| [How to implement secure MCP patterns: Identity, authorization, and runtime protection][link_youtube_com_watch_148]: **Google Cloud Tech** - Aron Eidelman | 2026-02-13 | Short implementation follow-up to the foundations talk: identity, authorization, and runtime protection from the agent through the MCP server to the tool. |
| [MCP Servers are Security Nightmares...][link_youtube_com_watch_149]: **Better Stack** | 2025-04-09 | Early explainer of tool-description abuse, sleeper changes after approval, tool shadowing, and a path to code execution through a legitimate-looking server. |
| [First Malicious MCP Server Discovered: What You Need to Know][link_youtube_com_watch_150]: **Infosec Now** | 2026-01-30 | Briefing on the postmark-mcp npm incident: a useful email server that later blind-copied messages to an attacker. |
| [Secure Salesforce Hosted MCP Servers: Authentication, Authorization & Permissions][link_youtube_com_watch_151]: **Salesforce Developers** - Philippe Ozil | 2026-11-03 | How Salesforce-hosted MCP servers authenticate callers, authorize tools, and expose Salesforce data to agents. |
| [Identity Best Practices to Secure and Scale Agentic AI / MCP Deployments][link_youtube_com_watch_152]: **Global AI Community** - Kevin Gao | 2026-06-16 | Identity patterns for MCP deployments: what has to be true for governance and scale once agents call tools on behalf of users. |
| [How to Secure your MCP Servers with Spring Security & Spring AI][link_youtube_com_watch_153]: **Dan Vega** | 2025-10-24 | Moves a Spring AI MCP server from local dev to OAuth2 and API-key authentication. |
| [How to Secure MCP Servers: Tool-Level RBAC and Audit Logs][link_youtube_com_watch_154]: **Teleport** | 2025-06-02 | Short walkthrough of per-tool RBAC, just-in-time elevation, and an audit log on every MCP tool call. |
| [MCP Security #1 — The Fundamentals \| Overview \| OWASP MCP Top 10 Explained][link_youtube_com_watch_155]: **SecureTechWithJKA** | 2026-07-24 | Opens a six-part lab series: what MCP changes about the attack surface, and the OWASP MCP Top 10 as the map for the labs that follow. |
| [MCP Security #2 — How to Find Shadow MCP Servers and Hardcoded Credentials in Your Environment][link_youtube_com_watch_156]: **SecureTechWithJKA** | 2026-07-24 | Lab on finding unapproved MCP servers and credentials wired straight into local config. |
| [MCP Security #3 — Scope Creep, Broken Auth, & the Token Passthrough Pattern That Took Down Obsidian][link_youtube_com_watch_157]: **SecureTechWithJKA** | 2026-07-24 | How individually reasonable grants become admin-level agent access, including token passthrough and the Obsidian incident pattern. |
| [MCP Security #4 — How to Scan Tool Schemas, Detect Command Injection, and Tag Untrusted Content][link_youtube_com_watch_158]: **SecureTechWithJKA** | 2026-07-25 | Lab on tool-schema scanning, command injection, and marking untrusted tool output so the agent does not treat it as instructions. |
| [MCP Security #5 — How to Harden MCP Dependencies and Stop Supply Chain Attacks][link_youtube_com_watch_159]: **SecureTechWithJKA** | 2026-07-25 | Pins versions, checks what is installed, and generates an SBOM for MCP server dependencies. |
| [MCP Security #6 — How to Build Structured Logging, Tenant Isolation and Incident Response][link_youtube_com_watch_160]: **SecureTechWithJKA** | 2026-07-27 | Closes the series on audit logs, tenant isolation, and incident response for the OWASP gap around missing telemetry. |

### Related security talks and resources

Pomerium sessions with a public YouTube recording are in the table above. These pages still cover the talks that are easier to find off YouTube:

- [Secure from Day One: Building Production Ready MCP Servers](https://www.nickyt.co/talks/mcp-developers-summit-eu-2025-building-secure-mcp-servers/) — OAuth 2.1 hardening, Pomerium as identity-aware proxy, unscoped tools (MCP Developers Summit EU, 2025-10-02).
- [Securing MCP Servers with Zero Trust](https://www.nickyt.co/talks/securing-mcp-servers-with-zero-trust-apollo-mcp-server-builder-series-2024/) — policy-at-the-edge framing for MCP servers exposed to agent clients.
- [Agentic Access: OAuth Gets You In, Zero Trust Keeps You Safe](https://www.nickyt.co/talks/agentic-access-oauth-gets-you-in-zero-trust-keeps-you-safe-all-things-open-2025/) — companion talk emphasizing authorization after OAuth success.
- Product context: [MCP Apps Are Here. Is Yours Secure on Day One?](https://fixel.pomerium.com/blog/mcp-apps-are-here-is-yours-secure-on-day-one) (Pomerium) and [Protect an MCP Server](https://www.pomerium.com/docs/capabilities/mcp/protect-mcp-server) (docs).

---

# MCP Demo and PoC Videos


| Title: Channel - Speaker / Host                                                                                                                                     | Date    | Summary                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Open Sourcing Vulnerable MCP Servers to learn Pentesting][link_youtube_com_watch_54]: **Appsecco**                                                    | 2025-12-16 | Teaser for open-source vulnerable MCP servers from BSides London (injection, auth bypass, prompt injection)—companion to the Sep 2025 masterclass. |
| [Appsecco MasterClass Pentesting MCP Servers Model Context Protocol - Hands-On Demo & Attack Examples][link_youtube_com_watch_30]: **Appsecco**                    | 2025-09-16 | Hands-on security session for testing MCP servers. Useful for red-teamers and defenders who want practical attack examples in a training context. |
| [Uncovering Vulnerabilities in Model Context Protocol (Part 2)][link_youtube_com_watch_31]: **Network Intelligence**                                                | 2025-10-17 | Deep dive into hacking MCP servers and thinking about guardrails. Include with lab-only safety framing.                                           |
| [MCP Servers for Pen Testing: AI-Driven Vulnerability ...][link_youtube_com_watch_32]: **APIsec University** - Christian                                           | 2026-02-17 | Shows how MCP servers can extend security testing workflows, moving from CVE discovery toward automated analysis and exploit generation.          |
| [MCP Tutorial: Build Your First MCP Server and Client from Scratch (Free Labs)][link_youtube_com_watch_33]: **KodeKloud**                                          | 2025-07-21 | Beginner-friendly end-to-end lab for building an MCP server and client from scratch. Good practical starting point for developers.                |
| [MCP Tutorial: Build Your First MCP Server][link_youtube_com_watch_34]: **codebasics**                                                                              | 2025-04-18 | Beginner-friendly real-life use-case tutorial for creating a first MCP server. Useful for developer onboarding.                                   |
| [FastMCP: Build your First MCP Server][link_youtube_com_watch_35]: **MLWorks**                                                                                       | 2026-02-22 | Demonstrates building an MCP server using FastMCP. Good for Python-focused readers.                                                               |
| [Python + MCP: Building MCP servers with FastMCP][link_youtube_com_watch_36]: **Microsoft Reactor**                                                                 | 2025-12-16 | Shows how to build an MCP server with Python FastMCP and consume it from AI tools such as GitHub Copilot in VS Code.                              |
| [Set Up MCP Server In Python - Step-By-Step Tutorial][link_youtube_com_watch_37]: **Jie Jenn**                                                                       | 2025-03-30 | Step-by-step Python MCP setup including testing with MCP Inspector. Good for practical lab learners.                                              |
| [Build AI's Future - Model Context Protocol (MCP) with Spring AI in Minutes][link_youtube_com_watch_43]: **Dan Vega**                                                | 2025-10-22 | Demonstrates Spring AI MCP server setup, tool creation, MCP Inspector testing, Claude integration, and ChatGPT integration.                       |
| [Tutorial: Building Custom MCP Servers With FastMCP and ...][link_youtube_com_watch_38]: **The Linux Foundation**                                                   | 2025-11-12 | Introduces building custom MCP servers with FastMCP and connecting them to AI agents.                                                             |
| [How to Test and Debug Servers with Postman's MCP Client][link_youtube_com_watch_39]: **Postman**                                                                    | 2025-05-07 | Demonstrates using Postman’s MCP client to test MCP services visually. Useful for QA, developers, and API security reviewers.                     |
| [Build a Real-world MCP Server with One TypeScript File][link_youtube_com_watch_40]: **Nader Dabit**                                                                 | 2025-03-20 | Walks through creating a TypeScript MCP server that integrates with real APIs. Good for Node.js/TypeScript developers.                            |
| [Beginner's Guide to Building a MCP Server with C# and .NET][link_youtube_com_watch_41]: **James Montemagno**                                                        | 2025-04-10 | Demonstrates building an MCP server from scratch using C# and VS Code. Useful for .NET teams adopting MCP.                                        |
| [Using MCP to solve a CTF Challenge][link_youtube_com_watch_42]: **Hack The Box**                                                                                    | 2025-06-18 | Shows MCP server integration in a CTF workflow. Useful for understanding how MCP can support security analysis and challenge solving.             |
| [Build ANYTHING With an Advanced MCP Server (Python, Authentication, Databases & More)][link_youtube_com_watch_76]: **Tech With Tim**                               | 2025-07-25 | Advanced Python MCP server with OAuth-style auth, databases, and transport deep dive—strong secure-build reference for production-minded devs.    |
| [Building MCP Server From Scratch (Complete Tutorial)][link_youtube_com_watch_77]: **Mehul Mohan**                                                                   | 2026-05-01 | Voice-driven Claude Code build of a read-only Postgres MCP server—demonstrates least-privilege DB access patterns (`BEGIN READ ONLY`).          |
| [Learn MCP Servers with Python (EASY)][link_youtube_com_watch_78]: **corbin**                                                                                        | 2025-03-12 | Python MCP server build with MCP Inspector debugging; connects to Claude Desktop and Claude Code.                                                 |
| [Build an MCP Server using Rust and Docker][link_youtube_com_watch_79]: **Francesco Ciulla**                                                                         | 2026-04-21 | Rust MCP server containerized with Docker—useful for isolation/portability patterns when threat-modeling MCP deployments.                       |
| [Build an MCP Server in Python \| Claude Desktop Tutorial][link_youtube_com_watch_80]: **Building Saas**                                                              | 2026-05-20 | FastMCP + Claude Desktop end-to-end lab covering tools, resources, prompts, and one-command install workflow.                                     |
| [MCP Core Concepts (MCP for Beginners)][link_youtube_com_watch_81]: **Microsoft Developer**                                                                          | 2025-07-28 | Official Microsoft **MCP for Beginners** module on hosts, clients, servers, transports, and implementation best practices.                        |
| [Model Context Protocol (MCP) for Google Cloud Security][link_youtube_com_watch_87]: **Mandiant & Google Cloud Security**                                             | 2025-06-18 | Demonstrates MCP-driven SecOps, SOAR, and threat-intelligence workflows with isolated credentials and explicit approval of tool actions.          |
| [Build A Remote MCP Server With TypeScript (Streamable HTTP)][link_youtube_com_watch_88]: **Tom Dohnal**                                                              | 2025-07-14 | Builds and deploys a stateless TypeScript MCP server over Streamable HTTP, then tests it with MCP Inspector and connects it to Cursor.             |
| [Ultimate MCP Tutorial \| Learn Model Context Protocol and Deploy your MCP Server][link_youtube_com_watch_89]: **Lama Dev**                                           | 2025-10-29 | Full Node.js course covering tools, resources, prompts, Inspector testing, remote Cloudflare deployment, persistence, authentication, and clients. |
| [Build enterprise-ready security agents with MCP servers][link_youtube_com_watch_118]: **Google Cloud Events** - Kyle Champlin | 2026-07-07 | Google SecOps session on multi-agent defense with the Security Operations MCP server and Agent Development Kit, from a hello-world agent to a production-shaped SOC workflow. |
| [Vulnerable MCP Server Hacking with Burp Suite \| Launching Damn Vulnerable MCP Server][link_youtube_com_watch_119]: **Rahul Singh** | 2026-05-02 | Burp walkthrough of a deliberately vulnerable MCP server: unauthenticated tools, default credentials, filesystem access, SSRF, and SQL injection. Lab-only; this repo is separate from the harishsg993010 DVMCP challenges. |
| [MCP Tool poisoning demo. Are you sure your MCP servers are not malicious?][link_youtube_com_watch_120]: **Martin Voelk** | 2025-04-15 | Early hands-on demo of a malicious MCP server whose tool description steers the agent. Useful as a short “what tool poisoning looks like” clip beside the longer conference talks. |
| [Pentesting MCP Servers: Live Demo & Attacks (OWASP Bay Area)][link_youtube_com_watch_161]: **Appsecco** - Riyaz Walikar | 2025-11-27 | OWASP Bay Area pentest of MCP servers with live exploitation and a 10-point checklist. Companion to the September masterclass and the BSides London workshop. |
| [Hacking & Pentesting MCP Servers \| BSides London \| Part 1][link_youtube_com_watch_162]: **Appsecco** - Riyaz Walikar | 2025-12-13 (workshop); 2025-12-17 (YouTube) | First published hour of the four-hour BSides London workshop: intercepting MCP traffic and walking real attacks. Lab-only. |
| [MCP Security AI Runbooks Series: IOC Enrichment][link_youtube_com_watch_163]: **Mandiant & Google Cloud Security** | 2025-08-25 | SecOps runbook that enriches indicators through Google Threat Intelligence and the Google Cloud Security MCP server, with analyst-facing output for the next step. |


---

# MCP CVE and Exploit Videos


| CVE            | Affected Component                | Issue Type                                                           | Links                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| -------------- | --------------------------------- | -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CVE-2025-49596 | MCP Inspector                     | Remote code execution / missing authentication for critical function | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-49596)<br>[Anthropic MCP Inspector Vulnerability Lets Hackers Run ...][link_youtube_com_shorts_bzx51spdsua]<br>[AI Model Validation Exploit: RCE in Anthropic's MCP Inspector ...][link_youtube_com_shorts_zq1urm0h3pm]<br>[Anthropic's MCP: what OX Security found in 150M downloads][link_youtube_com_shorts_1rp0evuo06c]<br>[MCP Security Master Class][link_youtube_com_watch_26]<br>[Chapter 6.3: Securing MCP (Model Context Protocol)][link_youtube_com_watch_27] |
| CVE-2025-6514  | mcp-remote                        | OS command injection / RCE when connecting to untrusted MCP servers  | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-6514)<br>[MCP Security Fundamentals Workshop 12 2025][link_youtube_com_watch_28]<br>[Docker PM: The Intern Installed an MCP Server, Then This ...][link_youtube_com_watch_29]<br>[The Waiter Attack Every Developer Must Know][link_youtube_com_shorts_ugwipi8nyng]<br>[CVE-2025-6514: OAuth URL Shell Command Injection in Client Library][link_youtube_com_watch_121] |
| CVE-2025-68143 | Git MCP server                    | Unrestricted `git_init` behavior                                     | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-68143)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CVE-2025-68144 | Git MCP server                    | Argument injection in `git_diff`                                     | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-68144)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CVE-2025-68145 | Git MCP server                    | Path validation bypass                                               | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-68145)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CVE-2026-22252 | LibreChat MCP-related STDIO issue | Command injection / RCE class issue                                  | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2026-22252)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CVE-2026-22688 | WeKnora MCP-related STDIO issue   | Command injection / RCE class issue                                  | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2026-22688)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CVE-2025-54994 | `@akoskm/create-mcp-server-stdio` | STDIO command injection class issue                                  | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-54994)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CVE-2025-54136 | Cursor MCP-related issue          | STDIO command injection class issue                                  | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-54136)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |


[link_youtube_com_playlist]: https://www.youtube.com/playlist?list=PL1f72Oxv5SyljPLIoNEIS_SFOM_-ungqW
[link_youtube_com_shorts_1rp0evuo06c]: https://www.youtube.com/shorts/1Rp0eVUO06c
[link_youtube_com_shorts_bzx51spdsua]: https://www.youtube.com/shorts/BzX51SPdsUA
[link_youtube_com_shorts_ugwipi8nyng]: https://www.youtube.com/shorts/UgwiPi8NyNg
[link_youtube_com_shorts_zq1urm0h3pm]: https://www.youtube.com/shorts/zq1Urm0h3pM
[link_youtube_com_watch]: https://www.youtube.com/watch?v=PLyCki2K0Lg
[link_youtube_com_watch_10]: https://www.youtube.com/watch?v=G5YoeMQwgiY
[link_youtube_com_watch_11]: https://www.youtube.com/watch?v=IKU153eICKk
[link_youtube_com_watch_12]: https://www.youtube.com/watch?v=P2NHzQdwpWI
[link_youtube_com_watch_13]: https://www.youtube.com/watch?v=0NRq7umRyyY
[link_youtube_com_watch_14]: https://www.youtube.com/watch?v=dWumWR3JK3o
[link_youtube_com_watch_15]: https://www.youtube.com/watch?v=TZ_WWrRZtM0
[link_youtube_com_watch_16]: https://www.youtube.com/watch?v=WCq7bylBbc8
[link_youtube_com_watch_17]: https://www.youtube.com/watch?v=O6G6ufT03fk
[link_youtube_com_watch_18]: https://www.youtube.com/watch?v=bO-7DB-3dL8
[link_youtube_com_watch_19]: https://www.youtube.com/watch?v=86e49wcXst4
[link_youtube_com_watch_2]: https://www.youtube.com/watch?v=CQywdSdi5iA
[link_youtube_com_watch_20]: https://www.youtube.com/watch?v=GFGtpHe3vvQ
[link_youtube_com_watch_21]: https://www.youtube.com/watch?v=bWEca0AQMbg
[link_youtube_com_watch_22]: https://www.youtube.com/watch?v=5OqWK6v_w3c
[link_youtube_com_watch_23]: https://www.youtube.com/watch?v=YWGaMZxIynM
[link_youtube_com_watch_24]: https://www.youtube.com/watch?v=McB4Sth3_Ss
[link_youtube_com_watch_25]: https://www.youtube.com/watch?v=eH9H-VGzQp0
[link_youtube_com_watch_26]: https://www.youtube.com/watch?v=6QdluEaTGfY
[link_youtube_com_watch_27]: https://www.youtube.com/watch?v=D8CWFwYRJMM
[link_youtube_com_watch_28]: https://www.youtube.com/watch?v=GX6Cqt7FF2M
[link_youtube_com_watch_29]: https://www.youtube.com/watch?v=En8TVF2H6g0
[link_youtube_com_watch_3]: https://www.youtube.com/watch?v=m2VqaNKstGc
[link_youtube_com_watch_30]: https://www.youtube.com/watch?v=aetmfPUuqms
[link_youtube_com_watch_31]: https://www.youtube.com/watch?v=_3W-9Ou5k5I
[link_youtube_com_watch_32]: https://www.youtube.com/watch?v=yvDJbQ5mM0o
[link_youtube_com_watch_33]: https://www.youtube.com/watch?v=RhTiAOGwbYE
[link_youtube_com_watch_34]: https://www.youtube.com/watch?v=jLM6n4mdRuA
[link_youtube_com_watch_35]: https://www.youtube.com/watch?v=UVf-hLVbdrQ
[link_youtube_com_watch_36]: https://www.youtube.com/watch?v=_mUuhOwv9PY
[link_youtube_com_watch_37]: https://www.youtube.com/watch?v=8g0z3DNi_fU
[link_youtube_com_watch_38]: https://www.youtube.com/watch?v=Zv7sBQ9dZzU
[link_youtube_com_watch_39]: https://www.youtube.com/watch?v=5MdSgQ87FfM
[link_youtube_com_watch_4]: https://www.youtube.com/watch?v=v3Fr2JR47KA
[link_youtube_com_watch_40]: https://www.youtube.com/watch?v=kXuRJXEzrE0
[link_youtube_com_watch_41]: https://www.youtube.com/watch?v=MKD-sCZWpZQ
[link_youtube_com_watch_42]: https://www.youtube.com/watch?v=zxt2b-9U_qo
[link_youtube_com_watch_43]: https://www.youtube.com/watch?v=MarSC2dFA9g
[link_youtube_com_watch_44]: https://www.youtube.com/watch?v=DKkE_-Ky3AA
[link_youtube_com_watch_45]: https://www.youtube.com/watch?v=Sw5AeNDXVgI
[link_youtube_com_watch_46]: https://www.youtube.com/watch?v=DAQ6msUVOp0
[link_youtube_com_watch_47]: https://www.youtube.com/watch?v=_821hYFZyCo
[link_youtube_com_watch_48]: https://www.youtube.com/watch?v=LYUDUOevtqk
[link_youtube_com_watch_49]: https://www.youtube.com/watch?v=3DEqIquWCQ4
[link_youtube_com_watch_50]: https://www.youtube.com/watch?v=LazYBEgfF1M
[link_youtube_com_watch_51]: https://www.youtube.com/watch?v=GRuff6FSo5A
[link_youtube_com_watch_52]: https://www.youtube.com/watch?v=tKvKgJWJ57A
[link_youtube_com_watch_53]: https://www.youtube.com/watch?v=MqQCMYSpSE0
[link_youtube_com_watch_54]: https://www.youtube.com/watch?v=G7hKl96qZTE
[link_youtube_com_watch_55]: https://www.youtube.com/watch?v=cVWB58kEt-Y
[link_youtube_com_watch_5]: https://www.youtube.com/watch?v=kOhLoixrJXo
[link_youtube_com_watch_6]: https://www.youtube.com/watch?v=0IhZdcjddo4
[link_youtube_com_watch_7]: https://www.youtube.com/watch?v=G5KyIzV-254
[link_youtube_com_watch_8]: https://www.youtube.com/watch?v=N3vHJcHBS-w
[link_youtube_com_watch_9]: https://www.youtube.com/watch?v=nkpjyXJqGhg
[link_youtube_com_watch_56]: https://www.youtube.com/watch?v=HyzlYwjoXOQ
[link_youtube_com_watch_57]: https://www.youtube.com/watch?v=tTw1z10yMCI
[link_youtube_com_watch_58]: https://www.youtube.com/watch?v=L94WBLL0KjY
[link_youtube_com_watch_59]: https://www.youtube.com/watch?v=VfZlglOWWZw
[link_youtube_com_watch_60]: https://www.youtube.com/watch?v=IYpt25GHB1U
[link_youtube_com_watch_61]: https://www.youtube.com/watch?v=hI1mDGh5YTI
[link_youtube_com_watch_62]: https://www.youtube.com/watch?v=H7Fl-8huzfQ
[link_youtube_com_watch_63]: https://www.youtube.com/watch?v=CDjjaTALI68
[link_youtube_com_watch_64]: https://www.youtube.com/watch?v=0WH0yRxExA0
[link_youtube_com_watch_65]: https://www.youtube.com/watch?v=XGHPfQoDrt4
[link_youtube_com_watch_66]: https://www.youtube.com/watch?v=k0ohQ4U7ZTE
[link_youtube_com_watch_67]: https://www.youtube.com/watch?v=6CzCrsp0RhY
[link_youtube_com_watch_68]: https://www.youtube.com/watch?v=P5Gv4GBL-aE
[link_youtube_com_watch_69]: https://www.youtube.com/watch?v=sUblFnZnNXA
[link_youtube_com_watch_70]: https://www.youtube.com/watch?v=F0BiCxPB9KA
[link_youtube_com_watch_71]: https://www.youtube.com/watch?v=chdHAV__Des
[link_youtube_com_watch_72]: https://www.youtube.com/watch?v=_iZDkQ9q40U
[link_youtube_com_watch_73]: https://www.youtube.com/watch?v=xsiQRePC5-s
[link_youtube_com_watch_74]: https://www.youtube.com/watch?v=QomOUH5BOoM
[link_youtube_com_watch_75]: https://www.youtube.com/watch?v=wDFL09jtD8E
[link_youtube_com_watch_76]: https://www.youtube.com/watch?v=j5f2EQf5hkw
[link_youtube_com_watch_77]: https://www.youtube.com/watch?v=OmWjC_M44Ss
[link_youtube_com_watch_78]: https://www.youtube.com/watch?v=Ek8JHgZtmcI
[link_youtube_com_watch_79]: https://www.youtube.com/watch?v=gGRJpwyCAio
[link_youtube_com_watch_80]: https://www.youtube.com/watch?v=tw78GKDi8DI
[link_youtube_com_watch_81]: https://www.youtube.com/watch?v=earDzWGtE84
[link_youtube_com_watch_82]: https://www.youtube.com/watch?v=0NHCyq8bBcM
[link_youtube_com_watch_83]: https://www.youtube.com/watch?v=hTV5jgjvYiY
[link_youtube_com_watch_84]: https://www.youtube.com/watch?v=wQrTqw7yV_A
[link_youtube_com_watch_85]: https://www.youtube.com/watch?v=6NXDc4cPNG8
[link_youtube_com_watch_86]: https://www.youtube.com/watch?v=5YFe32XbWMg
[link_youtube_com_watch_87]: https://www.youtube.com/watch?v=qGCdbAn0nk8
[link_youtube_com_watch_88]: https://www.youtube.com/watch?v=nTPeM8l3zTg
[link_youtube_com_watch_89]: https://www.youtube.com/watch?v=DAuZuj0BUZA
[link_youtube_com_watch_90]: https://www.youtube.com/watch?v=gYXLRMycVMk
[link_youtube_com_watch_91]: https://www.youtube.com/watch?v=_kOc7MOpONc
[link_youtube_com_watch_92]: https://www.youtube.com/watch?v=SsxKgsdKsAg
[link_youtube_com_watch_93]: https://www.youtube.com/watch?v=gzy2phZQ6w4
[link_youtube_com_watch_94]: https://www.youtube.com/watch?v=Myg3A-AVjyo
[link_youtube_com_watch_95]: https://www.youtube.com/watch?v=guC1VeYZpQ4
[link_youtube_com_watch_96]: https://www.youtube.com/watch?v=wvtGlur2SdI
[link_youtube_com_watch_97]: https://www.youtube.com/watch?v=B0bwUnpt2Lo
[link_youtube_com_watch_98]: https://www.youtube.com/watch?v=Wp8U1CEl3RI
[link_youtube_com_watch_99]: https://www.youtube.com/watch?v=1VzT7CuWp3Y
[link_youtube_com_watch_100]: https://www.youtube.com/watch?v=8fN4AELdFXU
[link_youtube_com_watch_101]: https://www.youtube.com/watch?v=hMqYU9MW5s8
[link_youtube_com_watch_102]: https://www.youtube.com/watch?v=0oavLuzErDQ
[link_youtube_com_watch_103]: https://www.youtube.com/watch?v=YtjjoPTN0U8
[link_youtube_com_watch_104]: https://www.youtube.com/watch?v=4_Om7f_2dro
[link_youtube_com_watch_105]: https://www.youtube.com/watch?v=VrNCes10kH8
[link_youtube_com_watch_106]: https://www.youtube.com/watch?v=dbGCJiQtqmk
[link_youtube_com_watch_107]: https://www.youtube.com/watch?v=cUO4IVFpHw4
[link_youtube_com_watch_108]: https://www.youtube.com/watch?v=M_BDq2hTJxU
[link_youtube_com_watch_109]: https://www.youtube.com/watch?v=__NtTfL0oPw
[link_youtube_com_watch_110]: https://www.youtube.com/watch?v=qGGlVHTzujw
[link_youtube_com_watch_111]: https://www.youtube.com/watch?v=JBTUwRPQRhY
[link_youtube_com_watch_112]: https://www.youtube.com/watch?v=hzbS5fdU8BM
[link_youtube_com_watch_113]: https://www.youtube.com/watch?v=b7f-WgnF3YU
[link_youtube_com_watch_114]: https://www.youtube.com/watch?v=McmPg-Xo2OY
[link_youtube_com_watch_115]: https://www.youtube.com/watch?v=BDVPnbh5Jhk
[link_youtube_com_watch_116]: https://www.youtube.com/watch?v=BHg8qCyZITA
[link_youtube_com_watch_117]: https://www.youtube.com/watch?v=g1PcOUZU_5c
[link_youtube_com_watch_118]: https://www.youtube.com/watch?v=oi_oEdT95G8
[link_youtube_com_watch_119]: https://www.youtube.com/watch?v=kZnojNOeFBU
[link_youtube_com_watch_120]: https://www.youtube.com/watch?v=Q4cQDMaTfwU
[link_youtube_com_watch_121]: https://www.youtube.com/watch?v=onWTzBtPdnM
[link_youtube_com_watch_122]: https://www.youtube.com/watch?v=LWMrm3DpEqY
[link_youtube_com_watch_123]: https://www.youtube.com/watch?v=3enEn_k0PcU
[link_youtube_com_watch_124]: https://www.youtube.com/watch?v=1YHI88OZxWs
[link_youtube_com_watch_125]: https://www.youtube.com/watch?v=b3mV4fKlbpY
[link_youtube_com_watch_126]: https://www.youtube.com/watch?v=wYcG_6SS788
[link_youtube_com_watch_127]: https://www.youtube.com/watch?v=fG36PSl_sgo
[link_youtube_com_watch_128]: https://www.youtube.com/watch?v=DAbyi6MZR9w
[link_youtube_com_watch_129]: https://www.youtube.com/watch?v=xFATAUt5gQw
[link_youtube_com_watch_130]: https://www.youtube.com/watch?v=3ag5DziQqO0
[link_youtube_com_watch_131]: https://www.youtube.com/watch?v=sbjTg-MNr5M
[link_youtube_com_watch_132]: https://www.youtube.com/watch?v=AmkBRMfL9hI
[link_youtube_com_watch_133]: https://www.youtube.com/watch?v=_fAH3fJvcMw
[link_youtube_com_watch_134]: https://www.youtube.com/watch?v=-pX4hBN5JI8
[link_youtube_com_watch_135]: https://www.youtube.com/watch?v=tEAkoZpdhSc
[link_youtube_com_watch_136]: https://www.youtube.com/watch?v=6qkmHBKLhwY
[link_youtube_com_watch_137]: https://www.youtube.com/watch?v=QJ-C_CBU2cQ
[link_youtube_com_watch_138]: https://www.youtube.com/watch?v=mYKMwZcGynw
[link_youtube_com_watch_139]: https://www.youtube.com/watch?v=p0UJ_VlaWxY
[link_youtube_com_watch_140]: https://www.youtube.com/watch?v=sc8ZfAbPoGM
[link_youtube_com_watch_141]: https://www.youtube.com/watch?v=U9rSRnjis7c
[link_youtube_com_watch_142]: https://www.youtube.com/watch?v=V33Go0nIufs
[link_youtube_com_watch_143]: https://www.youtube.com/watch?v=MEfPairE5xE
[link_youtube_com_watch_144]: https://www.youtube.com/watch?v=LR3jZQG91Oo
[link_youtube_com_watch_145]: https://www.youtube.com/watch?v=P4jvUzdI5Hc
[link_youtube_com_watch_146]: https://www.youtube.com/watch?v=6Xh36mDaSqM
[link_youtube_com_watch_147]: https://www.youtube.com/watch?v=88No8pw706o
[link_youtube_com_watch_148]: https://www.youtube.com/watch?v=9CoVNqbLdZU
[link_youtube_com_watch_149]: https://www.youtube.com/watch?v=CRKYNyMc4PM
[link_youtube_com_watch_150]: https://www.youtube.com/watch?v=bhZWRvsRKEk
[link_youtube_com_watch_151]: https://www.youtube.com/watch?v=DopuqJIJhyU
[link_youtube_com_watch_152]: https://www.youtube.com/watch?v=Wl77m9HJZ40
[link_youtube_com_watch_153]: https://www.youtube.com/watch?v=Xiw4bMD3SOg
[link_youtube_com_watch_154]: https://www.youtube.com/watch?v=JdiNX4pIUaU
[link_youtube_com_watch_155]: https://www.youtube.com/watch?v=UBG68zi3ZH0
[link_youtube_com_watch_156]: https://www.youtube.com/watch?v=VhzKAgWD2B8
[link_youtube_com_watch_157]: https://www.youtube.com/watch?v=X3Mk86hnuC8
[link_youtube_com_watch_158]: https://www.youtube.com/watch?v=90sMm9m_p08
[link_youtube_com_watch_159]: https://www.youtube.com/watch?v=Ar-IXzgzErY
[link_youtube_com_watch_160]: https://www.youtube.com/watch?v=5B96k27i6Ks
[link_youtube_com_watch_161]: https://www.youtube.com/watch?v=epek2OFtTMg
[link_youtube_com_watch_162]: https://www.youtube.com/watch?v=pHOSlPgauBg
[link_youtube_com_watch_163]: https://www.youtube.com/watch?v=0tYP_iaW-8s
