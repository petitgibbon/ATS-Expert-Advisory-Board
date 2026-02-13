# PRD — ATS Companion Agent Orchestrator (Board of Directors)

**Document owner:** Philip Fumey  
**Last updated:** 2026-02-11  
**Status:** Draft  

## 1) Summary (1–2 paragraphs)
Build a *Companion Agent Orchestrator* for Microsoft Account Technology Strategists (ATS) that produces C‑suite ready strategy + pitch artifacts for Azure and Microsoft AI adoption. The companion agent coordinates five specialized “director” sub‑agents that provide complementary viewpoints (product/tech vision, UX/storytelling, engineering pragmatism, CFO/finance rigor, and GPU/infra scaling) to help the ATS drive deeper executive engagement and increased Azure Consumed Revenue (ACR).

The system will be implemented using **Microsoft Agent Framework** multi‑agent orchestration patterns (e.g., group chat / manager-based orchestration) and will integrate the **Microsoft Learn MCP Server** for authoritative, up‑to‑date Microsoft documentation grounding.

---

## 2) Problem Statement
ATSs frequently need to:
- translate technical capability into board-level outcomes (growth, risk, productivity, resilience)
- tailor an AI + Azure narrative for each customer’s business model and maturity
- rapidly produce credible, defensible recommendations with references to Microsoft guidance

Today this work is manual, inconsistent, and time consuming—leading to missed moments with executive stakeholders and slower movement from strategy → pilots → production → consumption.

---

## 3) Goals & Success Metrics
### Goals
1. Produce a high-quality C‑suite strategy + pitch in <30 minutes from a structured intake.
2. Increase depth of customer engagement via “board-style” challenge, refinement, and coaching.
3. Improve technical correctness and currency by grounding in Microsoft Learn via MCP.
4. Provide ATS coaching prompts that drive next-best actions, stakeholder mapping, and meeting planning.

### Success Metrics (measurable)
- **Output quality**: C‑suite artifact rubric score (clarity, relevance, differentiation, actionability) 
- **Adoption**: Weekly active ATS users; repeat usage per account
- **Impact proxies**: # exec meetings created; # funded pilots; # production milestones
- **Commercial**: ACR influenced attribution (measured via internal tagging + opportunity notes)
- **Grounding**: % responses with valid Learn citations; hallucination rate in eval set

---

## 4) Personas & Primary Use Cases
### Primary persona: ATS (Microsoft)
- Owns technical strategy and executive narrative across a portfolio
- Needs fast, credible, customer-specific outputs

### Core Use Cases
1. **Executive Pitch Builder**: from account intake → 10–12 slide outline + talk track + CTA.
2. **Strategy Blueprint**: target architecture & operating model narrative (people/process/tech).
3. **Objection Handling**: CFO/security/engineering objections and crisp rebuttals.
4. **Workshop-in-a-box**: agenda, pre-read, discovery questions, outputs.
5. **Coaching Loop**: “How do I elevate this to CxO?” and “What’s the next meeting?”

---

## 5) Non-Goals
- Not a deal desk / pricing authority (no licensing quotes or contractual commitments)
- Not a replacement for account governance tools (CRM remains system of record)
- Not an autonomous agent that sends emails or schedules meetings without human approval

---

## 6) Director Sub-Agents (Board Members)
> **Important:** Use *archetype-based* personas inspired by well-known leadership styles, without impersonation.

Each director has:
- **Mandate** (what they optimize for)
- **Strengths** (how they contribute)
- **Default challenges** (questions they ask)
- **Output format** (what they return)

### Director A — “Visionary Technologist” (inspired by platform strategy & Bill Gates)
- Mandate: long-term platform advantage, developer ecosystem, moat
- Produces: North Star narrative, strategic bets, differentiation

### Director B — “Product Storyteller” (inspired by customer experience + narrative & Steve Jobs)
- Mandate: compelling story, simplicity, emotional resonance, adoption
- Produces: executive story arc, before/after, demo moments, messaging

### Director C — “Chief Technologist / Builder” (inspired by pragmatic engineering leadership & Kevin Scott, Microsoft)
- Mandate: feasibility, operating model, engineering excellence, delivery risk
- Produces: build/buy decisions, reference architectures, delivery plan

### Director D — “CFO Strategist” (inspired by finance & capital allocation & Ruth Porat, Alphabet)
- Mandate: ROI, risk, governance, cost control, value realization
- Produces: business case, value tree, investment phasing, KPIs

### Director E — “Compute & Scale Strategist” (inspired by GPU/infra economics & Colette Kress, Nvidia)
- Mandate: capacity, performance, reliability, GPU/compute strategy
- Produces: scaling plan, cost/perf, infra choices, SRE considerations

---

## 7) Orchestration & Conversation Design
### Orchestration Pattern
- **Manager-led Group Chat / Planning orchestration**: the companion agent acts as chair/manager and routes tasks to directors.
- Support **sequential** passes (draft → critique → revise) and **concurrent** critiques (parallel reviews) depending on scenario.

### Shared Context (“Board Pack”)
Single structured object carried across the workflow:
- Account context (industry, priorities, maturity, constraints)
- Stakeholders and desired outcomes
- Current Microsoft footprint
- Target scenario(s) and success measures
- Risks/objections
- Artifacts requested (deck outline, one-pager, email, etc.)

### Interaction Loop
Allow for a conversation with board, or allow for uploading and review of a document
1. Intake → construct Board Pack
2. First-pass strategy (chair)
3. Parallel director critiques
4. Chair synthesizes and produces v1 artifacts
5. Human review checkpoint (optional)
6. Iterate: refine narrative, architecture, business case

---

## 8) Grounding & Tools (Microsoft Learn MCP)
### Tooling Principles
- Use Learn MCP for: product availability, official guidance, architectures, code samples, best practices.
- Always prefer Learn sources for Microsoft-specific claims.

### Learn MCP Integration
- MCP endpoint: `https://learn.microsoft.com/api/mcp`
- Tools (via MCP): `microsoft_docs_search`, `microsoft_docs_fetch`, `microsoft_code_sample_search`

### WorkIQ MCP Integration 
Connect with WorkIQ Mcp


### When to Call MCP
- Any time the output contains a factual Microsoft claim (pricing aside), service limits, API methods, regional availability, or recommended patterns.

---

## 9) Outputs (Artifacts)
### Executive Pitch Pack (default)
- 1-slide exec summary (problem, opportunity, approach, ask)
- 10–12 slide outline with talk track
- Tailored value narrative (business outcomes + proof points)
- Reference architecture & migration path (high-level)
- Business case model (assumptions, ROI, phasing)
- Risks & mitigations + governance
- Next 2 meetings (agenda + questions + decision goals)

### Formats
- Markdown
- PowerPoint outline (slide-by-slide)
- One-page memo

---

## 10) Requirements
### Functional
- Multi-agent orchestration (chair + 5 directors)
- Reusable “Board Pack” schema
- Template library for pitch artifacts
- Learn MCP grounding + citations section
- Export helpers (copy-ready Markdown)

### Non-Functional
- Security & privacy: no customer secrets in logs; configurable retention
- Observability: trace steps, tool calls, director contributions
- Reliability: deterministic-ish outputs with seeded structure
- Performance: responsive interactive experience

---

## 11) Guardrails, Responsible AI, and Compliance
- No impersonation of real people; only archetype-based roleplay
- No legal/contractual commitments; prompt user to consult account team
- Clear attribution of sources (Learn links)
- Prompt injection defense for any retrieved content
- Human-in-the-loop checkpoints for final customer-facing outputs

---

## 12) Evaluation Plan
### Offline Eval Set
- 20 representative ATS scenarios (industries + maturity)
- For each: expected artifacts + rubric

### Metrics
- Factual accuracy (Learn-grounded)
- Executive clarity score
- Actionability score
- Consistency across runs

---

## 13) Rollout & Adoption
- Pilot with 3–5 ATSs
- Weekly feedback loop
- Add templates per industry (Professional Services, High Tech, etc.)

---

## 14) Open Questions
- Target runtime: .NET vs Python first (depending on orchestration support needs)
- Where will Board Pack be stored (in-memory vs persisted)
- Export: direct PowerPoint generation vs outline only

---

## Appendix A — Board Pack Schema (v0.1)
```yaml
account:
  name: ""
  industry: ""
  region: ""
  size: ""
  current_footprint:
    azure: ""
    m365: ""
    data_platform: ""
objectives:
  exec_outcomes: ["", ""]
  success_metrics: ["", ""]
stakeholders:
  primary_execs: ["", ""]
  influencers: ["", ""]
context:
  pains: ["", ""]
  constraints: ["", ""]
  ai_maturity: ""
scenarios:
  - name: ""
    description: ""
    priority: ""
objections:
  - category: "CFO|Security|Engineering|Legal"
    concern: ""
requested_artifacts:
  - type: "exec_onepager|pitch_outline|talktrack|business_case"
    audience: "CEO|CFO|CIO|CTO"
    deadline: ""
```
