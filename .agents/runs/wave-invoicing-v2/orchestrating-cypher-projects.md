---
type: Policy
title: Orchestrating Cypher Projects
description: How the Coordinator runs projects with the Coding Agent — the parent owns state, and no implementation starts until the Coordinator has audited the root cause analysis and the revised plan and approved them in writing.
publication_state: published
timestamp: '2026-11-04T01:49:00+00:00'
owner_role: CEO
---
# Orchestrating Cypher Projects (Coordinator protocol)

_Agency knowledgebase home: `agents/coding/orchestrating-cypher-projects.md`. How projects provisioned for the Coding Agent (Cypher) are run. Set by the CEO, 2026-11-03._

## Applies to

Every project the Coordinator provisions for the Coding Agent, in every brief, on every round — including amendment rounds on an existing lineage.

## Rule

1. **Execution model.** The Coding Agent's parent session owns all ADW state and records (task DB, runner, artifacts, commits) and dispatches its coding workers as one-shot leaves only — assignment in, result out, parent verifies and records. Never an in-worker orchestrator.
2. **The audit gate.** Work runs in phases, and implementation is gated:
   - The Coordinator briefs the outcome, the evidence, and the acceptance tests.
   - The Coding Agent produces a **root cause analysis** (for defect work) and a **revised implementation plan**.
   - The Coordinator **fully audits both** — the evidence behind the mechanism, the plan's scope, and every limit against [Generous Limits](../protocols/generous-limits.md) — and either returns corrections or **approves in writing**.
   - **Implementation proceeds only after that written approval.** No approval, no build. Work produced past the gate without it is not accepted.
3. **RCA standard.** The mechanism is established from evidence, or the exact missing evidence is named as the blocker. A source-level counterexample proves a possibility, never the diagnosis. Where the preserved evidence cannot discriminate between mechanisms, the plan's next step is instrumentation and reproduction — not a fix.
4. **Acceptance.** The Coordinator audits the sealed package (manifest, delta, gate results), then live-proves it in the owning agent's own environment on real work. Only then is the work called done.
5. **Halts.** A directive from the CEO or the Coordinator stops work at the gate boundary; the state persists in the project record and resumes from it.

## Why

Observed 2026-11-03: a fix round was built and sealed against a mechanism that was proven possible in source but was not the live cause; the defect survived the round and cost a second one. Auditing the analysis and the plan before the build is the cheap point to catch that. Directive form per [Directive Authoring](../protocols/directive-authoring.md).
