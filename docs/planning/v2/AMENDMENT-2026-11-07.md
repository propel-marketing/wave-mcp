# Wave MCP — Setup amendment (2026-11-07, Coordinator)

## 1. Blocker disposition — fork

Your block was correct and is accepted as reported: no authenticated GitHub API context in your execution environment, no substitutes attempted. The Coordinator attempted the two API routes available to him: fork via the Muse GitHub connector (403 — not accessible by that integration) and creating the org repo directly (403 — org admin required). **Repository creation now sits with the CEO (org owner) and has been requested.** Do not retry the fork, and do not substitute any other owner, repo, or credential route. When `propel-marketing/wave-mcp` exists, the Coordinator will launch a resume turn in this session; the resume scope is the original brief's legs 2–7, unchanged, plus §2 below.

Your Memory Bank project stands and is the project record: `project_c07e1cec356e4042`. Record this amendment in it when you resume.

## 2. PRD v2 supersedes v1 for planning

`docs/PRD-v2.md` accompanies this amendment. The CEO decided the one open design question: **automated internal-API sign-in with the Wave automation-user credentials stored in Infisical is the default** (PRD v2 §7; OQ-2 closed). Cookie-only enrollment is demoted to a fallback procedure.

On resume:
- File **both** PRDs in the repo, byte-identical: `docs/PRD-v1.md` → `docs/planning/v1/PRD.md`, and `docs/PRD-v2.md` → `docs/planning/v2/PRD.md`. (Planning versioning rule: filed versions are never edited; revisions are new folders.)
- Author the ADW plan against **PRD v2** — note its Phase 1 (automated sign-in enabled against the credential-file mechanism) and Phase 2 (headless browser in the image; Infisical fetch → secret files → container mount; auto-sign-in proven in the deployment environment) deltas when structuring tasks.
- Everything else in the original brief stands: baseline in your environment, ADW install, generous-limits inventory from the real code, bootstrap push, then stop at the gate for the Coordinator's written plan approval. No implementation.
