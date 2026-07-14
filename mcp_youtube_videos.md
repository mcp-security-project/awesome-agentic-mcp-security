# YouTube Videos

## Contents

- [General and primer videos](#youtube-videos)
- [Security Videos](#security-videos)
- [Curated MCP security picks](#curated-mcp-security-picks)
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
| [MCP Security Master Class - MCP INJECTION ATTACKS][link_youtube_com_watch_20]: **AumLayer**                                                         | 2025-08-25                             | Focuses on MCP injection attacks and how authorization/access-control weaknesses influence attack paths.                                                            |
| [MCP Security Master Class - MCP ACCESS CONTROLS][link_youtube_com_watch_21]: **AumLayer**                                                           | 2025-08-26                             | Explains where access controls should exist in MCP systems and how poor authorization can create risk.                                                              |
| [MCP Security Master Class - MCP COMMON SECURITY MISTAKES][link_youtube_com_watch_22]: **AumLayer**                                                  | 2025-08-28                             | Good candidate for a checklist-style “what not to do” video for developers building MCP integrations.                                                               |
| [MCP Security for Agentic AI Platforms: Attack Vectors & Best ...][link_youtube_com_watch_23]: **APIsec University**                                 | 2026-02-17                             | Covers MCP risks in broader agentic AI platforms, including hidden tool access and cross-context data leakage.                                                      |
| [These Aren't the Tools You're Looking For: MCP Security Awakens][link_youtube_com_watch_24]: **AI Native Dev**                                       | 2025-11-27                             | Security talk-style title focused on malicious MCPs, poisoned tools, and indirect prompt injection against MCP-connected IDEs.                                      |
| [MCP: Model Context Protocol or Malicious Control Path?][link_youtube_com_watch_25]: **HITCON**                                                      | 2025-09-29                             | Useful for helping security teams understand why MCP integrations must be treated as execution and data-access pathways, not harmless chat plugins.                 |
| [The OWASP MCP Top 10 — Every Risk Ranked and Explained][link_youtube_com_watch_51]: **StackOps AI**                                                  | 2026-05-14                             | One-minute ranked walkthrough of all ten OWASP MCP Top 10 risks with brief mitigations—good quick refresher after the formal taxonomy.                              |
| [AI Agents and MCP Security Risks - Risk Mitigation][link_youtube_com_watch_52]: **Black Hills Information Security** - Joff Thyer                     | 2025-12-17                             | Short clip on MCP risks: chroot/filesystem restrictions, logging, RBAC, and validating tool data sources before agent execution.                                    |
| [Agent Identity for MCP: Prefactor's Approach to Secure, Auditable AI Agents][link_youtube_com_watch_53]: **Agentic AI Foundation** - Matt Doughty, Simon | 2025-09-19                             | Demo and deep dive on agent identity beyond OAuth: signed payloads, immutable audit logs, workload identity, and task-based access for MCP.                         |
| [Securing the Future of AI: Securing MCP with Defense in Depth Patterns][link_youtube_com_watch_55]: **Microsoft BlueHat / MSRC** - Jitesh Thakur                                | 2026-05-20                          | Microsoft Security Response Center session on layered defenses for MCP: treating tool descriptions as code, sandboxing, authorization boundaries, tool-integrity verification, and runtime monitoring against tool poisoning and confused-deputy attacks. |


---

## Curated MCP security picks

Common “short list” curations often cluster **Arcade-style tool auth**, **A2A + MCP composition**, **packaging/catalog security (e.g. Docker toolkit)**, **community vetting workflows**, **practitioner threat framing**, and **OAuth/zero-trust talks**. The rows below mirror those picks on YouTube where a stable watch URL exists. **Nick Taylor (Pomerium)** sessions are linked under the table because many curators point at conference pages or recap posts rather than a single canonical YouTube upload.

| Title: Channel — Speaker / Host                                                                                         | Date        | Summary                                                                                                                                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [TanStack AI and the future of agentic tooling][link_youtube_com_watch_44]: **Arcade** - Jack Herrington               | 2026-03-16  | Long-form Arcade channel episode: TanStack AI orchestrating MCP tools, “Code Mode,” human-in-the-loop approval-useful alongside OAuth-focused tutorials when you are threat-modeling **agent + tool orchestration**, not only transport auth.                                                |
| [Unlock the Power of Arcade.dev to Deploy Secure AI Agents TODAY!][link_youtube_com_watch_45]: **Arcade**            | 2025-06-13  | Short Arcade clip on shipping agentic integrations without hard vendor lock-in-frequently bundled with “Arcade + MCP” auth discussions as the **product positioning** companion to deeper OAuth/tool-auth build videos.                                                                      |
| [Agent2Agent + (MCP to Tool) in Multi-Agent AI][link_youtube_com_watch_46]: **Discover AI**                            | 2025-04     | Explains Google **A2A** alongside **MCP-for-tools** patterns (multi-agent + tool access). Valuable when curators label the clip as “A2A/MCP threats/surface” in the sense of **cross-protocol composition and trust propagation**, not only single-server MCP bugs.                              |
| [The last MCP server you'll ever need...][link_youtube_com_watch_47]: **Better Stack**                                 | 2025-06-07  | Better Stack walkthrough of **Docker MCP Toolkit**-style packaging: cataloging, OAuth-forward setup, container isolation-often cited in “fix MCP sprawl/secret soup” curations.                                                                                                                    |
| [MCP Security: Vetting Servers to Mitigate Tool Poisoning Attacks][link_youtube_com_watch_48]: **JeredBlu**             | 2025-04-03  | Practical **vetting methodology** and demo of evaluating a marketplace MCP server before install-matches “don’t YOLO random MCPs” guidance in many lists.                                                                                                                                        |
| [Model Context Protocol (MCP) Security Concerns][link_youtube_com_watch_49]: **Cory Wolff**                             | 2025-04-03  | Practitioner-focused **risk framing** for MCP adoption (attack surface, trust, and operational security mindset)-commonly grouped with early-2025 “MCP is powerful but scary” picks.                                                                                                              |
| [Adding Authentication to your MCP Server Tools][link_youtube_com_watch_50]: **Dev Leonardo**                          | 2025-07-28  | Hands-on **OAuth-style protection** for MCP tools (sessions, metadata, MCP SDK usage). Often appears next to Arcade/Stytch-style “auth for agents” content as a **framework-agnostic implementation** reference.                                                                                 |

**Pomerium + Nick Taylor (talk pages / recordings).** Several lists cite Nick Taylor’s **MCP Developers Summit EU 2025** and related **OAuth + zero trust** talks rather than one long-lived YouTube mirror. Primary entry points:

- [Secure from Day One: Building Production Ready MCP Servers](https://www.nickyt.co/talks/mcp-developers-summit-eu-2025-building-secure-mcp-servers/) — OAuth 2.1 hardening, Pomerium as identity-aware proxy, unscoped tools (MCP Developers Summit EU, 2025-10-02).
- [Securing MCP Servers with Zero Trust](https://www.nickyt.co/talks/securing-mcp-servers-with-zero-trust-apollo-mcp-server-builder-series-2024/) — policy-at-the-edge framing for MCP servers exposed to agent clients.
- [Agentic Access: OAuth Gets You In, Zero Trust Keeps You Safe](https://www.nickyt.co/talks/agentic-access-oauth-gets-you-in-zero-trust-keeps-you-safe-all-things-open-2025/) — companion talk emphasizing authorization after OAuth success.
- Product context: [MCP Apps Are Here. Is Yours Secure on Day One?](https://fixel.pomerium.com/blog/mcp-apps-are-here-is-yours-secure-on-day-one) (Pomerium) and [Protect an MCP Server](https://www.pomerium.com/docs/capabilities/mcp/protect-mcp-server) (docs).

**Overlap note (API keys / client compromise).** [MCP Security is Still Broken][link_youtube_com_watch_19] (**Prompt Engineering**, 2025-04-11) and Maciej Pulikowski’s written deep-dive [Model Context Protocol (MCP) Security - Real Risks for LLM Apps (2025)](https://pulik.dev/blog/mcp-security) (2025-04-27) both stress **malicious servers instructing models toward secrets and unsafe automation**—same theme, different mediums. Keep **both** in rotation: the video for narrative pacing, the blog for reproducible examples and statistics (see also the dated mirror table in `mcp_blogs_whitepapers_academicpapers.md`).

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
| [Securing MCP Servers - OAuth2 Implementation for Model Context Protocol][link_youtube_com_watch_17]: **Devoxx** - Daniel Garnier Moiroux                           | 2025-10-10 | Hands-on implementation of OAuth2 and role-based access restrictions for MCP servers. Strong secure-development demo.                             |
| [Tutorial: Building Custom MCP Servers With FastMCP and ...][link_youtube_com_watch_38]: **The Linux Foundation**                                                   | 2025-11-12 | Introduces building custom MCP servers with FastMCP and connecting them to AI agents.                                                             |
| [How to Test and Debug Servers with Postman's MCP Client][link_youtube_com_watch_39]: **Postman**                                                                    | 2025-05-07 | Demonstrates using Postman’s MCP client to test MCP services visually. Useful for QA, developers, and API security reviewers.                     |
| [Build a Real-world MCP Server with One TypeScript File][link_youtube_com_watch_40]: **Nader Dabit**                                                                 | 2025-03-20 | Walks through creating a TypeScript MCP server that integrates with real APIs. Good for Node.js/TypeScript developers.                            |
| [Beginner's Guide to Building a MCP Server with C# and .NET][link_youtube_com_watch_41]: **James Montemagno**                                                        | 2025-04-10 | Demonstrates building an MCP server from scratch using C# and VS Code. Useful for .NET teams adopting MCP.                                        |
| [Using MCP to solve a CTF Challenge][link_youtube_com_watch_42]: **Hack The Box**                                                                                    | 2025-06-18 | Shows MCP server integration in a CTF workflow. Useful for understanding how MCP can support security analysis and challenge solving.             |


---

# MCP CVE and Exploit Videos


| CVE            | Affected Component                | Issue Type                                                           | Links                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| -------------- | --------------------------------- | -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CVE-2025-49596 | MCP Inspector                     | Remote code execution / missing authentication for critical function | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-49596)<br>[Anthropic MCP Inspector Vulnerability Lets Hackers Run ...][link_youtube_com_shorts_bzx51spdsua]<br>[AI Model Validation Exploit: RCE in Anthropic's MCP Inspector ...][link_youtube_com_shorts_zq1urm0h3pm]<br>[Anthropic's MCP: what OX Security found in 150M downloads][link_youtube_com_shorts_1rp0evuo06c]<br>[MCP Security Master Class][link_youtube_com_watch_26]<br>[Chapter 6.3: Securing MCP (Model Context Protocol)][link_youtube_com_watch_27] |
| CVE-2025-6514  | mcp-remote                        | OS command injection / RCE when connecting to untrusted MCP servers  | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-6514)<br>[MCP Security Master Class][link_youtube_com_watch_26]<br>[MCP Security Fundamentals Workshop 12 2025][link_youtube_com_watch_28]<br>[Docker PM: The Intern Installed an MCP Server, Then This ...][link_youtube_com_watch_29]<br>[The Waiter Attack Every Developer Must Know][link_youtube_com_shorts_ugwipi8nyng] |
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
