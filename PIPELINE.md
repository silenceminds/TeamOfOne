# TeamOfOne Shared Pipeline Protocol

This document defines the **shared chain-workflow contract** used by `teamofone-orchestrator` and all **789 specialist agents** in **TeamOfOne** so multiple agents can collaborate in a connected pipeline without arguing, duplicating work, or overwriting each other.

## The 5-Stage Connected Pipeline

Every multi-agent task flows strictly forward through these five stages:

1. **Stage 1 — Strategy & Lock (`01-executive-strategy`, `04-product-design`):**
   - Sets `goal`, `constraints` (time, budget, stack), and `scope`.
   - Once Stage 1 completes, `goal` and `constraints` are **locked** for all downstream stages.
2. **Stage 2 — Intelligence & Signals (`11-scheduled-web-research`, `12-social-community-monitoring`):**
   - Gathers fresh web research and social/dev platform posts (FB, IG, X, HN, Reddit, Threads, GitHub).
   - Outputs `verified_facts` (with source URLs), `importance_scores` (1-5), and `leads`.
3. **Stage 3 — Execution & Build (`02`, `03`, `05`, `06`, `07`, `08`, `09`, `10`):**
   - Consumes Stage 1's locked constraints and Stage 2's verified data to produce code, copy, plans, models, or replies.
   - Never alters Stage 1's strategic goal.
4. **Stage 4 — Watchdog & QA Gate (`14-essential-watchdogs`):**
   - Audits Stage 3 outputs for security, billing, compliance, or deadline risks.
   - Flags `conflicts` or `risks` to the orchestrator without rewriting strategy.
5. **Stage 5 — PDF & Scheduled Connector Delivery (`13-pdf-leads-delivery`):**
   - Compiles final `leads` and `findings` into a formatted PDF.
   - Checks for a connected storage folder (asks the user where to save if unconfigured) and saves on the user's chosen schedule.

## Conflict-Free Rules (No Agent Disagreements)

- **Single Writer Per Field:** Each stage writes only to its own section in `pipeline-schema.json`.
- **Tie-Breaker Authority:** Only `00-orchestrator/teamofone-orchestrator` (or `ceo` in Stage 1) resolves a flagged conflict and locks the decision.
- **No Circular Loops:** Downstream agents cannot reject or re-open an upstream stage's locked decision; they only execute or flag a concrete blocker in `conflicts`.
