# Awesome Agentic MCP Security [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated links on agentic AI and Model Context Protocol security: threats, research, tooling, labs, and learning resources.

Maintained and curated by **Vandana Verma Sehgal**.
Each topic page is a standalone reference with tables, summaries, and outbound links.
This list treats MCP as a new security boundary and curates 400+ resources across blogs, papers, talks, scanners, integrations, labs, CVEs, and videos. Each topic page is a standalone reference with tables, summaries, and outbound links.

## Contents

- [Highlights — start here](#highlights--start-here)
- [Project overview](#project-overview)
- [Blogs, whitepapers and research](#blogs-whitepapers-and-research)
- [Conference talks and briefings](#conference-talks-and-briefings)
- [Free trainings and courses](#free-trainings-and-courses)
- [GitHub repos and discovery](#github-repos-and-discovery)
- [Podcasts and webinars](#podcasts-and-webinars)
- [Security tooling](#security-tooling)
- [MCP security servers and integrations](#mcp-security-servers-and-integrations)
- [CVEs and advisories](#cves-and-advisories)
- [Vulnerable environments and labs](#vulnerable-environments-and-labs)
- [YouTube and video library](#youtube-and-video-library)
- [Code of Conduct](#code-of-conduct)

## Highlights — start here

If you only have a few minutes, these are widely-cited starting points across the list.

**Foundations**
- [Model Context Protocol Specification](https://modelcontextprotocol.io/specification/2025-11-25) — Official MCP specification.
- [Security Best Practices](https://modelcontextprotocol.io/docs/tutorials/security/security_best_practices) — Confused deputy, token passthrough, SSRF, session hijacking, and scope minimization.
- [OWASP MCP Top 10](https://owasp.org/www-project-mcp-top-10/) — Community risk taxonomy for MCP-enabled systems.
- [MCP Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/MCP_Security_Cheat_Sheet.html) — OWASP cheat sheet covering tool trust, validation, and supply-chain hygiene.

**Foundational research and incidents**
- [Tool Poisoning Attacks](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks) — Invariant Labs' early notification on malicious instructions hidden in tool descriptions.
- [Jumping the line: How MCP servers can attack you before you ever use them](https://blog.trailofbits.com/2025/04/21/jumping-the-line-how-mcp-servers-can-attack-you-before-you-ever-use-them/) — Trail of Bits.
- [MCP Servers: The New Security Nightmare](https://equixly.com/blog/mcp-security-nightmare) — Equixly's widely-cited empirical vulnerability rates in popular MCP servers.
- [Building Secure MCP Servers: A Developer's Guide](https://snyk.io/articles/building-secure-mcp-servers/) — Snyk developer-focused guide.

**Hands-on**
- [Damn Vulnerable MCP Server (DVMCP)](https://github.com/harishsg993010/damn-vulnerable-MCP-server) — CTF-style lab for prompt injection, tool poisoning, rug pulls, and shadowing.
- [MCP Inspector RCE (CVE-2025-49596)](mcp_cves_and_advisories.md#modelcontextprotocolinspector) — Critical advisory in MCP developer tooling.
- [Snyk Agent Scan / MCP-Scan](https://github.com/snyk/agent-scan) — CLI scanner for prompt injection, tool poisoning, and toxic flows in agent and MCP configurations.

## Project overview

[See full overview →](mcp_overview.md)

Terminology, MCP as a trust boundary, threat framing, audience notes, and how the topic lists fit together with pointers to the MCP specification and OWASP MCP Top 10.

**Key risk areas covered:**
- **Data leakage** — Files, repos, databases, tickets, cloud assets exposed via tool outputs.
- **Unauthorized actions** — Tool execution beyond intended scope.
- **Prompt injection chains** — Untrusted tool outputs becoming model instructions.
- **Tool poisoning** — Malicious or modified tool descriptions in metadata.
- **Supply chain compromise** — Malicious or compromised MCP servers as a foothold.
- **Shadow MCP servers** — Unmanaged installs creating governance blind spots.
- **Weak monitoring and auditability** — No record of which model called which tool, with what parameters.

## Blogs, whitepapers and research

[Browse all blogs and research →](mcp_blogs_whitepapers_academicpapers.md)

70+ blogs, whitepapers, standards, and academic papers with short summaries for theme-based reading. Includes Microsoft, Anthropic, Invariant Labs, Trail of Bits, Snyk, Wiz, OX Security, JFrog, CyberArk, Equixly, Red Hat, Stack Overflow, OWASP, and Cloud Security Alliance. Plus a chronological "Dated incidents" subsection covering AgentFlayer, mcp-remote RCE (CVE-2025-6514), MCPoison, Asana cross-tenant exposure, Cato CTRL PoCs, ANSI deception, and other notable incidents.

**Selected reading:**
- [Tool Poisoning Attacks](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks) — Invariant Labs.
- [Toxic Flow Analysis](https://invariantlabs.ai/blog/toxic-flow-analysis) — Invariant Labs.
- [Insecure credential storage plagues MCP](https://blog.trailofbits.com/2025/04/30/insecure-credential-storage-plagues-mcp/) — Trail of Bits.
- [Building Secure MCP Servers: A Developer's Guide](https://snyk.io/articles/building-secure-mcp-servers/) — Snyk.
- [The Cursor Agentic Jira MCP Attack Explained with Toxic Flow Analysis](https://lirantal.com/blog/cursor-jira-mcp-toxic-flow) — Liran Tal.
- [Is that allowed? Authentication and authorization in Model Context Protocol](https://stackoverflow.blog/2026/01/21/is-that-allowed-authentication-and-authorization-in-model-context-protocol/) — Stack Overflow Blog.
- [OWASP MCP Top 10](https://owasp.org/www-project-mcp-top-10/) — OWASP.

## Conference talks and briefings

[Browse all talks →](mcp_conference_talks.md)

30+ talks and briefings where MCP security is a primary focus, with speakers, venues, links to recordings or slides where public, and relevance to exploits, tool trust, or governance. Spans Black Hat USA, Black Hat Europe, Black Hat Asia, RSAC, OWASP, BSides, SecTor, and regional chapter events.

**Recent highlights:**
- **CoSAI at RSAC 2026** — Securing MCP: Mitigating New Threats in Agentic AI Deployments (Sarah Novotny, Jason Clinton).
- **Black Hat Europe 2025** — [MCP Unchained: Compromising The AI Agent Ecosystem Via Its "Universal Connector"](https://github.com/Tencent/AI-Infra-Guard/blob/main/BHEU-25-MCP-Unchained-Compromising-The-AI-Agent-Ecosystem-Via-Its-Universal-Connector.pdf).
- **Black Hat USA 2025** — [From Prompts to Pwns: Exploiting and Securing AI Agents](https://i.blackhat.com/BH-USA-25/Presentations/US-25-Lynch-From-Prompts-to-Pwns.pdf) (Becca Lynch, Rich Harang).
- **OWASP GenAI @ RSAC 2026** — Securing MCP: OWASP Best Practices – A Practical Guide (Idan Habler, Joshua Beck, Tomer Elias).
- **BSides Seattle 2026** — [MCP LFI in 60 Minutes (or Your Money Back)](https://bsides-seattle-2026.sessionize.com/session/1079777) (Kurt Boberg).

## Free trainings and courses

[Browse all trainings →](mcp_free_trainings_and_courses.md)

Free or low-barrier structured learning for MCP fundamentals and security-aware integration, with notes on format, duration, and sequencing. Organized by skill level (beginner, intermediate, advanced) and split between MCP fundamentals, MCP security, and company-sponsored trainings.

**Selected:**
- [Official MCP Documentation: Getting Started](https://modelcontextprotocol.io/docs/getting-started/intro) — Model Context Protocol project.
- [MCP for Beginners](https://github.com/microsoft/mcp-for-beginners) — Microsoft's open-source curriculum across multiple languages.
- [Model Context Protocol Course](https://huggingface.co/learn/mcp-course/unit0/introduction) — Hugging Face structured course.

## GitHub repos and discovery

[Browse all repos →](mcp_github_repos.md)

50+ official SDKs, reference servers, registries, discovery hubs, scanners, frameworks, and "awesome lists" with brief rationale and security-oriented caveats per row.

**Official SDKs:** [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk) · [Python](https://github.com/modelcontextprotocol/python-sdk) · [C#](https://github.com/modelcontextprotocol/csharp-sdk) · [Go](https://github.com/modelcontextprotocol/go-sdk) · [Java](https://github.com/modelcontextprotocol/java-sdk) · [Rust](https://github.com/modelcontextprotocol/rust-sdk) · [Servers](https://github.com/modelcontextprotocol/servers) · [Registry](https://github.com/modelcontextprotocol/registry)

**Selected scanners and defensive tools:**
- [Snyk Agent Scan](https://github.com/snyk/agent-scan) — Prompt injection, tool poisoning, toxic flows (formerly `invariantlabs-ai/mcp-scan`).
- [Cisco AI Defense MCP Scanner](https://github.com/cisco-ai-defense/mcp-scanner) — Multi-engine MCP server scanning.
- [Ant Group MCP-Security](https://github.com/antgroup/MCP-Security) — Metadata pollution, tool poisoning, malicious URLs, unsafe code snippets.
- [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) — Trail of Bits client wrapper exposing malicious server context.
- [MCP Guardian](https://github.com/eqtylab/mcp-guardian) — Manage assistant access with human approval flows.

## Podcasts and webinars

[Browse all podcasts and webinars →](mcp_podcasts_webinars.md)

Audio and live sessions on MCP security and related agentic risk, with metadata for discovery and executive-friendly context.

**Selected:**
- [Episode 115: Security in Model Context Protocol (MCP)](https://rss.com/podcasts/azsecpodcast/2109364/) — The Azure Security Podcast.
- [Lessons from the Front-line: What Research Reveals about MCP Security](https://www.wiz.io/events/lessons-from-the-front-line-what-research-reveals-about-mcp-security) — Wiz.
- [MCP and the Question of Authorization](https://www.sans.org/webcasts/mcp-question-authorization) — SANS.
- [Authentication and Authorization Patterns for Agents and MCP](https://www.solo.io/resources/webinar/authentication-and-authorization-patterns-for-agents-and-mcp) — Solo.io.
- [Lessons for Security Leaders From the MCP AI Supply Chain Crisis](https://www.ox.security/webinar/lessons-for-security-leaders-from-anthropics-mcp-failure/) — OX Security.

## Security tooling

[Browse all security tooling →](mcp_security_tools.md)

50+ scanners, monitors, policy and gateway controls, secrets and dependency checks, and related utilities with deployment notes and safety warnings where relevant. Organized by category: MCP scanners, runtime monitoring, policy engines, secrets and dependency scanners, red team tools, and blue team / SOC tools.

**Selected MCP scanners:**
- [Cisco AI Defense MCP Scanner](https://github.com/cisco-ai-defense/mcp-scanner) — Multi-engine.
- [Snyk Agent Scan](https://github.com/snyk/agent-scan) — Prompt injection, tool poisoning, toxic flows.
- [SecureMCP](https://github.com/makalin/SecureMCP) — OAuth/token issues, prompt injection probes, TLS/auth posture.
- [MCPSafetyScanner](https://github.com/leidosinc/mcpsafetyscanner) — Adversarial samples, safety reports.

**Selected runtime monitoring and policy:**
- [Invariant Guardrails](https://github.com/invariantlabs-ai/invariant) — Block unsafe agent behavior via rules on tool calls and flows.
- [Lasso MCP Gateway](https://github.com/lasso-security/mcp-gateway) — Centralized lifecycle, intercept, sanitize, scan before load.
- [Agent Wall](https://github.com/agent-wall/agent-wall) — YAML policy on tool calls and responses.
- [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) — Trail of Bits client wrapper.

## MCP security servers and integrations

[Browse all integrations →](mcp_security_servers_and_integrations.md)

60+ MCP servers that wrap AppSec and SAST tools, dependency and OSV data, reverse engineering and mobile stacks, threat intel APIs, cloud and identity platforms, SIEM platforms, and trust or reputation layers (including agent-market style integrations).

**Categories:**
- **AppSec, SAST, dependencies, supply chain** — Semgrep MCP, OSV-MCP, vet, Snyk studio-mcp, agent-bom.
- **Reverse engineering and mobile** — Ghidra, IDA Pro, Radare2, Binary Ninja, JADX.
- **Threat intelligence and OSINT** — Multiple MCP-wrapped APIs.
- **Cloud, identity, and zero-trust access** — Cloud IAM and identity platform integrations.
- **SIEM and security analytics** — Panther SIEM, Wazuh, TheHive, Cortex, RunReveal.
- **Hosting, gateways, and transport helpers** — Enterprise MCP runtimes.

## CVEs and advisories

[Browse all CVEs and advisories →](mcp_cves_and_advisories.md)

Published advisories across MCP reference servers, SDKs, and developer tooling. Organized by repository with patched versions, severity, and CVE/GHSA IDs. The fastest place to watch for new official advisories if you maintain an MCP allowlist or platform standard.

**Notable:**
- [CVE-2025-49596 (GHSA-7f8r-222p-6f5g)](https://github.com/advisories/GHSA-7f8r-222p-6f5g) — **Critical:** MCP Inspector proxy RCE via unauthenticated stdio launches.
- [CVE-2025-53109 / 53110](https://github.com/advisories/GHSA-q66q-fx2p-7w4m) — **High:** `server-filesystem` path validation bypasses.
- [CVE-2025-66416 / 66414](https://github.com/advisories/GHSA-9h52-p55h-vw2f) — **High:** DNS rebinding in Python and TypeScript SDKs.
- [CVE-2026-25536 (GHSA-345p-7cg4-v4c7)](https://github.com/advisories/GHSA-345p-7cg4-v4c7) — **High:** TypeScript SDK cross-client data leak via shared transport instance reuse.
- [CVE-2026-0621 (GHSA-cqwc-fm46-7fff)](https://github.com/modelcontextprotocol/typescript-sdk/security/advisories/GHSA-cqwc-fm46-7fff) — **High:** TypeScript SDK `UriTemplate` ReDoS.

## Vulnerable environments and labs

[Browse all labs →](mcp_vulnerable_environments_and_labs.md)

Intentionally vulnerable MCP setups, goats, CTF-style labs, and PoCs with setup hints, themes, and isolation reminders.

**Selected:**
- [Damn Vulnerable MCP Server (DVMCP)](https://github.com/harishsg993010/damn-vulnerable-MCP-server) — Prompt injection, tool poisoning, rug pull, shadowing, indirect injection, token theft.
- [Vulnerable MCP Servers Lab](https://github.com/appsecco/vulnerable-mcp-servers-lab) — Path traversal, unsandboxed exec, supply chain, secrets/PII (Appsecco).
- [bad-mcp](https://github.com/canack/bad-mcp) — Full-schema poisoning, advanced poisoning, rug pulls, cross-server shadowing.
- [MCP Shark Security Lab](https://github.com/mcp-shark/mcp-shark-security-lab) — Toxic metadata, command injection patterns, oversharing, weak authZ.
- [Sherpa](https://github.com/Azure-Samples/sherpa) — Microsoft Azure Samples workshop covering auth gaps, over-permissioned access, unsafe cloud patterns.

## YouTube and video library

[Browse all videos →](mcp_youtube_videos.md)

Video primers and security-focused sessions with channel, speaker, date, duration, links, and suggested learning outcomes. Organized into general primers, security videos, demo and PoC content, and CVE / exploit walkthroughs.

**Selected:**
- [Securing Model Context Protocol (MCP) with Vandana Verma (OWASP/Snyk)](https://www.youtube.com/watch?v=IKU153eICKk) — Long-form session on production MCP security.
- [First Look - OWASP MCP Top 10 – 2025](https://www.youtube.com/watch?v=P2NHzQdwpWI) — Vandana Verma.
- [Foundations of Secure MCP: Architecture and Threat Model](https://www.youtube.com/watch?v=dWumWR3JK3o) — Google Cloud Tech.
- [MCP Security: Why Your AI Assistant Is an Insider Threat](https://www.youtube.com/watch?v=WCq7bylBbc8) — Liran Tal, Snyk.

### Contributors

We'd like to thank the following contributors for their valuable input:
- **Rohit G** for sharing the mcp repo
- **Liran Tal** for sharing the mcp repo


## Code of Conduct

Community participation follows the [Code of Conduct](CODE_OF_CONDUCT.md).
