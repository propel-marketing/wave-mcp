# Wave MCP — Phase 0 setup brief

**From:** the Coordinator. **Project:** Wave Invoicing MCP. **This round:** project setup only — fork, baseline, ADW, plan. No implementation.

## Outcome

A ready-to-plan project: `propel-marketing/wave-mcp` exists as a fork of the approved foundation, checked out in your projects root, its inherited test baseline recorded in your environment, core ADW installed, an ADW plan authored from the PRD, and the PRD filed in the repo. Then stop at the gate for the Coordinator's written audit of the plan.

## Execution model (standing, every Benny-provisioned project)

Your parent session owns all ADW state and records (task DB, runner, artifact persistence, commits) and dispatches Codex as one-shot leaf workers only — self-contained assignment in, result out, parent verifies and records. Never an in-Codex orchestrator.

## Inputs (in this work dir)

- `docs/PRD-v1.md` — the approved product requirements; the plan derives from it (its §11 defines Phase 0–3 and the two spikes).
- `docs/AUDIT-2026-11-07.md`, `docs/SCOPE-CHECK-2026-11-07.md`, `docs/RECOMMENDATION.md` — the evidence base: repo audit with verified test runs, the Wave API scope check, and the architecture recommendation.

## Setup tasks

1. **Fork.** Fork `LunaParker/waveapps-mcp` to `propel-marketing/wave-mcp`, retaining the MIT license and upstream attribution. Clone it to `/home/propel/projects/cypher/wave-mcp`. If org forking is blocked by permissions, report the exact blocker — do not substitute a different owner or a personal fork.
2. **Baseline.** In the checkout, install dependencies and record the inherited baseline in `RESULTS.md`: full unit suite result and typecheck result, as run in your environment. Coordinator-side reference (diagnosis only, not your acceptance): 485/486 tests passing, one chmod assertion that cannot fail as root; typecheck clean. Report your actual numbers, whatever they are.
3. **File the PRD.** Copy `docs/PRD-v1.md` to `docs/planning/v1/PRD.md` in the repo, byte-identical. Planning revisions never edit a filed version; a revision is a new versioned folder (PRD §header rule).
4. **Install ADW.** Bootstrap the core Propel-ADW into the repo root (`.agents/`) per your standard bootstrap; commit the scaffolding with the plan (task 5) as the bootstrap commit.
5. **Author the ADW plan.** From the PRD: phases 0–3 plus spikes S1/S2 as the work structure, tasks sized per your standard (each implementation task small, paired review), and an inventory of every numeric limit you inherit from the foundation or introduce in the plan, checked against the fleet Generous Limits protocol (vault `agents/protocols/generous-limits.md`) — each limit kept, raised, or justified in the plan.
6. **Project record.** Create the Memory Bank project for this software project with your standard topics, and point its profile at this repo and the PRD.
7. **Push.** Push the bootstrap commit (ADW scaffolding, ADW plan, filed PRD) to `propel-marketing/wave-mcp`. GitHub is the source of truth from this commit on.

## Gate

Stop after setup. Deliver in this work dir: `PLAN.md` (what was set up, the ADW plan summary, the limit inventory) and `RESULTS.md` (baseline evidence, repo/branch/commit identifiers, Memory Bank project reference, any blockers). **No feature implementation, no public-client build, no deployment, no Wave credentials** — none exist yet and none are needed for setup. Implementation begins only on the Coordinator's written approval of the plan (fleet audit gate, vault `agents/coding/orchestrating-cypher-projects.md`).

## Constraints

- No Hermes gateway restarts. No changes outside this project: no other repos, no server deployment, no fleet configuration.
- Secrets: none are involved in this round; do not enroll, request, or store any.
- Report blockers plainly in `RESULTS.md` with the exact error and what you tried; a scoped partial delivery with honest blockers is acceptable, a guessed workaround is not.
