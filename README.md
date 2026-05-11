<h1 align="center">Greg Barker</h1>
<p align="center">
  <strong>Platform engineer · AI systems · Data analytics</strong><br>
  Building tools that give developers (and game masters) superpowers.
</p>

<p align="center">
  <a href="https://stablepiggy.com">stablepiggy.com</a> · 
  <a href="https://www.linkedin.com/in/greg-barker-savevsgames/">LinkedIn</a> · 
  <a href="https://github.com/savevsgames">GitHub</a>
</p>

---

## What I'm Building

<p align="center">
  <h2><b>StablePiggy.com</b> - StablePiggy: The Dev-Vault</h2> 
  <img src="./assets/SP-LOGO-01-cropped.png" width="400" alt="Napoleon - StablePiggy AI Assistant" />
</p>

**ZERO TRUST JIT Exec Grant Stablecoin Wallet Infrastructure & Tooling for Agentic Platform & Financial Agency**: A multi-tenant developer platform where AI agents operate inside isolated, sandboxed environments — managing containers, vaults, knowledge bases, and deployment pipelines through a unified MCP protocol interface.

Napoleon, the platform's AI assistant, helps developers ship code through managed infrastructure — all within the org-scoped, security-audited system. As a representation of a containerized integration, Napoleon can help game masters run tabletop RPG sessions in Foundry VTT with real module content. Any container run on the platform can be spun up and have integrations built to allow Napoleon to interact with it.

```mermaid
graph LR
    subgraph Platform
        MCP[MCP Protocol Server<br><em>146 tools</em>]
        Vault[Encrypted Vault<br><em>AES-256-GCM · scoped tiers</em>]
        Containers[Container Orchestration<br><em>Docker · Caddy · per-org isolation</em>]
        Bundles[Composite Templates<br><em>multi-container apps</em>]
        Napoleon[Napoleon AI<br><em>multi-provider · tool loop</em>]
    end

    subgraph Clients
        Claude[Claude Code]
        Codex[OpenAI Codex]
        Junie[JetBrains Junie]
        Foundry[Foundry VTT Module]
        Dashboard[Web Dashboard]
    end

    Claude -->|MCP| MCP
    Codex -->|MCP| MCP
    Junie -->|MCP| MCP
    Foundry -->|WebSocket Relay| Napoleon
    Dashboard -->|REST + SSE| MCP
    MCP --> Vault
    MCP --> Containers
    MCP --> Napoleon
    Containers --> Bundles
```

#### Agent wallets & testnet

Built-in wallet system with a live testnet. Agents can hold balances, transfer funds, and settle transactions — real money movement in a sandboxed environment. Designed for testing payment flows, agent-to-agent commerce, and transaction-driven workflows before going live.

#### Open source

The [OINKMOJI protocol](https://stablepiggy.com/docs) and other platform documentation are published openly. Architecture specs, protocol definitions, and integration guides available at [stablepiggy.com/docs](https://stablepiggy.com/docs).

#### Testing & quality

2,800+ automated tests across backend and dashboard. CI runs on every pull request — typecheck, drift guards, migration safety, and security audit gates all enforced before merge.

#### Security

16-phase security audit with zero critical findings. Full threat modeling, GDPR-compliant data lifecycle (erasure cascades, export endpoints), and incident response runbooks. The platform enforces encryption at rest, scoped access tiers, and container-level network isolation out of the box.

#### Multi-container orchestration

Composite template system lets you define multi-container applications with lifecycle-aware volumes — separating runtime services, persistent data, and independently-scaled sidecars. Deploy a full-stack app with one command.

#### Secret management

Encrypted vault with personal, org, and platform tiers. Secrets are injected into containers at runtime, never exposed in chat history or logs. A built-in redaction engine scrubs credentials from stored conversations automatically.

#### AI agent compatibility

Works with Claude Code, Codex, and JetBrains Junie out of the box. Nearly 200 custom MCP tools. The online chat interface supports Anthropic, OpenAI, OpenRouter, and Ollama — pick the model that fits your workflow.

#### Controlled onboarding

Waitlist with seat-capacity management, honeypot defense, and tamper-resistant signup flow. Designed for a measured launch, not a free-for-all.

---

### CVPO — Continuity Video Prompt Orchestrator

An end-to-end video production orchestration system built for a media production client. CVPO transforms story concepts into structured, edit-ready video projects — generating scripts, storyboard frames, voice-over takes, and b-roll selections, then packaging everything for import into Adobe Premiere Pro.

```mermaid
graph TD
    Concept[Story Concept] --> Generate[AI Story Generation]
    Generate --> Scenes[Scene & Shot Breakdown]
    Scenes --> Frames[Frame Generation<br><em>DALL-E</em>]
    Scenes --> VO[Voice-Over Generation<br><em>Gemini TTS · 3 takes per clip</em>]
    Scenes --> BRoll[B-Roll Search<br><em>Internet Archive</em>]
    Frames --> Export[Export Package]
    VO --> Export
    BRoll --> Export
    Export --> Premiere[Adobe Premiere Pro]
```

The system runs on Google Cloud Run with a React frontend on Cloudflare Pages, backed by Supabase (PostgreSQL). AI generation uses OpenAI for story and frame generation and Google Gemini for text-to-speech and vision analysis. Access is restricted to the client's team via Cloudflare Zero Trust with Google OAuth.

Reusable production blocks (camera setups, lighting rigs, character profiles, editing styles) let the team build a library of templates that carry across projects — consistent visual language without rebuilding from scratch every time.

---

### Napoleon Foundry Module

An AI game master assistant for [Foundry VTT](https://foundryvtt.com/) — available on [Docker Hub](https://hub.docker.com/r/savevsgames/napoleon-foundry) and pending Foundry marketplace review.

Napoleon reads real module content — actors, scenes, journals — from purchased adventure modules and answers questions, builds encounters, places walls and lighting, and manages session continuity. All from inside the Foundry interface, scoped per-user so your game data stays yours.

The module ships as a derived Docker image with version-tracked releases, per-org relay isolation, and clear error handling when something goes wrong (five distinct failure cases, each with an actionable notification instead of a silent failure).

---

### PromptBlocker

A Chrome Extension that automatically replaces your real personal information with aliases when using AI chat services — ChatGPT, Claude, Gemini, Perplexity, and Copilot.

Your prompts go out with aliases, responses come back decoded. Profiles never leave your device. 750 passing tests. Free tier available, Pro at $4.99/mo. Its development shaped the zero-trust privacy approach behind StablePiggy's secret redaction system.

---

## What I've shipped professionally

### Data Analytics & Business Intelligence

Founding member of a consultancy delivering data analytics and BI solutions.

**$2.5M in inventory savings** identified for a consumer goods client through predictive modeling and demand forecasting. Built automated reporting pipelines covering sales orders, production actuals vs. forecast, and material costs. Delivered executive dashboards and actionable recommendations that drove procurement and logistics decisions.

Currently preparing StablePiggy for launch by onboarding trusted users in batches. Also building a Java SaaS application with my data analytics team — JHipster foundation, transposed from a working TypeScript prototype into domain-driven Java architecture — that lets enterprise users safely query their own data in natural language. NLP to SQL with deterministic output.

---

## Stack

What I actually use in production:

| Domain | Technologies |
|--------|-------------|
| **Platform & Infrastructure** | Node.js, TypeScript, Express, SQLite (WAL), Docker, Caddy, pm2, GitHub Actions CI/CD |
| **Enterprise & Backend** | Java, Spring Boot (JHipster), domain-driven architecture, PostgreSQL, NLP-to-SQL pipelines |
| **AI & LLM Integration** | Anthropic Claude, OpenAI, OpenRouter, MCP Protocol, RAG with Voyage embeddings, multi-provider tool loops |
| **Cloud & Deployment** | Google Cloud Run, Cloudflare Pages, Cloudflare Zero Trust, Supabase (PostgreSQL), Vultr VPS |
| **Security** | AES-256-GCM encryption, Argon2id hashing, JWT with revocation, HMAC verification, CSP/HSTS, container egress firewalling |
| **Frontend** | React, Vite, Tailwind CSS, SSE streaming, WebSocket |
| **Data & Analytics** | Python, pandas, predictive modeling, BI reporting, demand forecasting |
| **Protocols** | MCP (Model Context Protocol), WebSocket relay, Stripe webhooks, GitHub App webhooks, Foundry VTT module API |

---

## Background

Data Analytics and Pipeline Architecture Design. Full stack development program at the University of Toronto. E-commerce experience (Shopify store management and Liquid code). Former Master Electrician — the kind of background where you learn that cutting corners on safety gets people hurt, which turns out to be a useful instinct when you're writing security audits and building vault encryption systems.

---

<p align="center">
  StablePiggy: <a href="https://stablepiggy.com">stablepiggy.com</a> · 
  <a href="mailto:greg@stablepiggy.com">greg@stablepiggy.com</a><br>
  Other Inquiries: <a href="mailto:gregcbarker@gmail.com">gregcbarker@gmail.com</a> · 
  <a href="https://www.linkedin.com/in/greg-barker-savevsgames/">LinkedIn</a>
</p>
