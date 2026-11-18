# TeamOfOne — 790 AI Agent Skills & Connected OPC Pipeline

**Run a one-person company like an entire organization—with a conflict-free, chained agent pipeline.**

**TeamOfOne** is a modular, open-format collection of **789 specialized AI agent skills** plus **1 Master Pipeline Orchestrator** (**790 `SKILL.md` files total**) organized across **15 directories**. Every agent shares the same `PIPELINE.md` and `pipeline-schema.json` handoff contract so multiple agents can work in a connected chain without arguing or overriding each other.

## Connected Pipeline Architecture (Zero Agent Disagreements)

All 789 specialists share a unified **Pipeline Handoff Protocol** (`PIPELINE.md` + `pipeline-schema.json`):

```text
Stage 1: Strategy & Lock (CEO / CPO)
   ↓  [Locks goal & constraints — read-only downstream]
Stage 2: Intelligence & Signals (200 Daily Researchers + 30 Social/Dev Monitors)
   ↓  [Outputs verified URLs, importance scores 1-5, & leads]
Stage 3: Execution & Build (CTO, CMO, Sales, Ops, Finance, Support)
   ↓  [Produces code, copy, sprints, & financial models]
Stage 4: Watchdog & QA Gate (15 Essential Watchdogs)
   ↓  [Audits security, APIs, billing, & compliance risks]
Stage 5: PDF & Scheduled Connector Delivery (20 PDF/Lead Exporters)
      [Compiles PDF, checks connector folder or asks where to save, exports on schedule]
```

* **Read-only upstream locks:** Downstream agents never re-argue or overwrite Stage 1's locked decisions.

* **Single tie-breaker:** Any flagged conflict is logged once in `conflicts` and resolved by `00-orchestrator/teamofone-orchestrator/SKILL.md`.

## What's Inside

| \# | Department | Directory | Skills | Highlight Roles |
| ----- | ----- | ----- | ----- | ----- |
| 00 | **Pipeline Orchestrator** | `00-orchestrator/` | 1 | `teamofone-orchestrator` |
| 01 | **Executive & Strategy** | `01-executive-strategy/` | 43 | `ceo`, `chief-of-staff`, `board-advisor`, `pricing-strategist` |
| 02 | **Engineering & Architecture** | `02-engineering-architecture/` | 90 | `cto`, `fullstack-builder`, `devops-sre-lead`, `security-engineer` |
| 03 | **AI, Data & Automation** | `03-ai-data-automation/` | 64 | `head-of-ai`, `prompt-engineer`, `rag-architect`, `agent-orchestrator` |
| 04 | **Product & Design** | `04-product-design/` | 63 | `cpo`, `product-manager`, `mvp-architect`, `onboarding-specialist` |
| 05 | **Marketing & Growth** | `05-marketing-growth/` | 74 | `cmo`, `growth-lead`, `seo-content-writer`, `cold-email-strategist` |
| 06 | **Sales & Revenue** | `06-sales-revenue/` | 47 | `vp-sales`, `founder-led-sales-coach`, `demo-script-coach`, `objection-handler` |
| 07 | **Operations & Project Management** | `07-operations-management/` | 47 | `coo`, `project-manager`, `ops-manager`, `sprint-planner` |
| 08 | **Finance, Accounting & Legal** | `08-finance-legal/` | 47 | `cfo`, `cash-flow-forecaster`, `unit-economics-modeler`, `tos-privacy-drafter` |
| 09 | **Customer Success & Support** | `09-customer-success-support/` | 27 | `head-of-customer-success`, `tech-support-engineer`, `help-center-writer` |
| 10 | **People, Contractors & Hiring** | `10-people-contractors/` | 22 | `head-of-people`, `jd-writer`, `paid-trial-designer`, `va-task-delegator` |
| 11 | **Scheduled Daily Web Research** | `11-scheduled-web-research/` | 200 | `daily-research-llm-releases`, `daily-research-micro-saas`, `daily-research-b2b-trigger-events` |
| 12 | **Social & Dev Platform Monitoring** | `12-social-community-monitoring/` | 30 | `fb-product-mentions-monitor`, `ig-product-mentions-monitor`, `x-product-mentions-monitor`, `hn-product-mentions-monitor`, `reddit-product-mentions-monitor`, `threads-product-monitor` |
| 13 | **PDF Reports & Connector Delivery** | `13-pdf-leads-delivery/` | 20 | `pdf-daily-leads-exporter`, `connector-folder-router`, `scheduled-delivery-coordinator` |
| 14 | **Essential Watchdogs & Alerts** | `14-essential-watchdogs/` | 15 | `uptime-ssl-domain-watchdog`, `api-deprecation-watcher`, `ai-token-bill-spike-guard` |
|  | **Total** |  | **790** | **1 Orchestrator + 789 Specialists + `PIPELINE.md` + `pipeline-schema.json`** |

## Installation Guide

### 1. Claude Code (Plugin Marketplace — Recommended)

Register **TeamOfOne** directly in Claude Code as a plugin marketplace ([docs](https://code.claude.com/docs/en/plugins/overview)):

```text
/plugin marketplace add silenceminds/TeamOfOne
/plugin install teamofone-core@teamofone
```

*(Or install all 790 skills at once with `/plugin install teamofone@teamofone`.)*

Or clone and copy individual skills manually into `~/.claude/skills/` or `.claude/skills/` ([docs](https://code.claude.com/docs/en/skills)):

```bash
git clone https://github.com/silenceminds/TeamOfOne.git
mkdir -p ~/.claude/skills
cp -r TeamOfOne/00-orchestrator/teamofone-orchestrator ~/.claude/skills/
cp -r TeamOfOne/01-executive-strategy/ceo ~/.claude/skills/
cp -r TeamOfOne/02-engineering-architecture/cto ~/.claude/skills/
```

### 2. OpenAI Codex

OpenAI Codex reads `SKILL.md` folders from `.agents/skills/` in your project or user directory ([quickstart](https://agentskills.io/skill-creation/quickstart)).

```bash
git clone https://github.com/silenceminds/TeamOfOne.git
mkdir -p .agents/skills
cp -r TeamOfOne/00-orchestrator/teamofone-orchestrator .agents/skills/
cp -r TeamOfOne/02-engineering-architecture/cto .agents/skills/
```

### 3. GitHub Copilot (VS Code, Visual Studio, & Copilot CLI)

GitHub Copilot looks for `<skill-name>/SKILL.md` inside `.github/skills/` at the root of your repository ([GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills)).

```bash
mkdir -p .github/skills
cp -r TeamOfOne/00-orchestrator/teamofone-orchestrator .github/skills/
cp -r TeamOfOne/01-executive-strategy/ceo .github/skills/
cp -r TeamOfOne/02-engineering-architecture/cto .github/skills/
```

### 4. Google Antigravity (IDE & CLI)

Google Antigravity loads skills from `.agent/skills/` (workspace-scoped) or `~/.gemini/antigravity/skills/` (global) ([Codelabs](https://codelabs.developers.google.com/getting-started-with-antigravity-skills?hl=en)).

```bash
mkdir -p .agent/skills
cp -r TeamOfOne/00-orchestrator/teamofone-orchestrator .agent/skills/
cp -r TeamOfOne/01-executive-strategy/ceo .agent/skills/
```

### 5. Install All 790 Skills at Once (Bash One-Liner)

```bash
TARGET_DIR=".claude/skills"   # Change to .agents/skills, .github/skills, or .agent/skills
mkdir -p "$TARGET_DIR"
for skill in TeamOfOne/*/*/; do
  cp -r "$skill" "$TARGET_DIR/"
done
```

## Example Chained Pipeline Prompts

* **Full OPC Pipeline (`teamofone-orchestrator`):** *"Run the TeamOfOne pipeline: lock my goal of reaching \$10k MRR for my AI dev tool, have the Reddit & HN monitors find buying-intent leads, let CMO draft outreach, and have the PDF Lead Exporter save the report to my connected folder daily at 6:00 PM."*

* **Daily Web Research (`11-scheduled-web-research/daily-research-llm-releases`):** *"Run my daily LLM release research every day at 8:00 AM IST and deliver a 3-minute source-cited report."*

* **Social Importance Scoring (`12-social-community-monitoring/cross-platform-product-importance`):** *"Check recent posts about my product across FB, IG, X, HN, Reddit, and Threads, score their importance, and surface warm leads."*

## License

MIT License. Free to use, fork, customize, and share.
