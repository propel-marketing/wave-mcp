# Universal Spec — wave-invoicing-v2

Source: docs/planning/v2/PRD.md, issued brief and AMENDMENT-2026-11-07.md. Created2026-11-07 by parent manual synthesis from source inspection. Plan directory .agents/runs/wave-invoicing-v2.

## 1. Context
One hybrid billing MCP for Propel, public authoritative standard operations and internal contacts/recurring blind spots. No processor refunds; no recurring/credit-balance commitment beyond research. Phase0 only authorized now. v2 automated sign-in supersedes cookie-default research notes. Full ADW lane2: money/auth/transport architecture cannot use expedited lane. External gates in tasks are evidence collection, not authorization creation.

## 2. File Manifest
Each section one work task and immediately paired reviewer. Max3 expected outputs; existing module tests extended, not duplicated. Generated SDK is one aggregation file. New handwritten modules target15–200 lines; split by actual operation before exceeding role, never minify to fit. Every builder gets whole owning source/interface closure at dispatch and must stop for missing context.

| # | Path | Operation | Section |
|---|---|---|---|
| 1 | docs/planning/v2/PLAN-AUDIT-APPROVAL.md | create | p0-audit-gate |
| 2 | .agents/runs/wave-invoicing-v2/agent-outputs/p0-audit-gate/build-summary.md | create | p0-audit-gate |
| 3 | docs/planning/v2/IMPLEMENTATION-PREREQUISITES.md | create | p1-prerequisites |
| 4 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-prerequisites/build-summary.md | create | p1-prerequisites |
| 5 | package.json | modify | p1-dependency-clearance |
| 6 | package-lock.json | modify | p1-dependency-clearance |
| 7 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-dependency-clearance/build-summary.md | create | p1-dependency-clearance |
| 8 | .agents/provenance/package.json | modify | p1-provenance-clearance |
| 9 | .agents/provenance/package-lock.json | modify | p1-provenance-clearance |
| 10 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-provenance-clearance/build-summary.md | create | p1-provenance-clearance |
| 11 | src/client/public/schema.graphql | create | p1-schema |
| 12 | docs/planning/v2/PUBLIC-SCHEMA-PROVENANCE.md | create | p1-schema |
| 13 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-schema/build-summary.md | create | p1-schema |
| 14 | package.json | modify | p1-codegen-config |
| 15 | package-lock.json | modify | p1-codegen-config |
| 16 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-codegen-config/build-summary.md | create | p1-codegen-config |
| 17 | src/client/public/operations.graphql | create | p1-public-operations |
| 18 | codegen.ts | create | p1-public-operations |
| 19 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-public-operations/build-summary.md | create | p1-public-operations |
| 20 | src/client/public/sdk.ts | create | p1-generate-sdk |
| 21 | .github/workflows/test.yml | modify | p1-generate-sdk |
| 22 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-generate-sdk/build-summary.md | create | p1-generate-sdk |
| 23 | src/client/public/client.ts | create | p1-public-client |
| 24 | src/client/public/client.test.ts | create | p1-public-client |
| 25 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-public-client/build-summary.md | create | p1-public-client |
| 26 | src/client/business-scope.ts | create | p1-business-scope |
| 27 | src/client/business-scope.test.ts | create | p1-business-scope |
| 28 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-business-scope/build-summary.md | create | p1-business-scope |
| 29 | src/tools/tool-catalog.ts | create | p1-tool-catalog |
| 30 | src/tools/tool-catalog.test.ts | create | p1-tool-catalog |
| 31 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-tool-catalog/build-summary.md | create | p1-tool-catalog |
| 32 | src/tools/policy.ts | create | p1-policy |
| 33 | src/tools/policy.test.ts | create | p1-policy |
| 34 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-policy/build-summary.md | create | p1-policy |
| 35 | src/tools/confirmation.ts | create | p1-confirm |
| 36 | src/tools/confirmation.test.ts | create | p1-confirm |
| 37 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-confirm/build-summary.md | create | p1-confirm |
| 38 | src/util/write-audit.ts | create | p1-write-audit |
| 39 | src/util/write-audit.test.ts | create | p1-write-audit |
| 40 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-write-audit/build-summary.md | create | p1-write-audit |
| 41 | src/client/public/pagination.ts | create | p1-pagination |
| 42 | src/client/public/pagination.test.ts | create | p1-pagination |
| 43 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-pagination/build-summary.md | create | p1-pagination |
| 44 | src/tools/public-customers.ts | create | p1-customer-reads |
| 45 | src/tools/public-customers.test.ts | create | p1-customer-reads |
| 46 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-customer-reads/build-summary.md | create | p1-customer-reads |
| 47 | src/tools/public-customer-writes.ts | create | p1-customer-writes |
| 48 | src/tools/public-customer-writes.test.ts | create | p1-customer-writes |
| 49 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-customer-writes/build-summary.md | create | p1-customer-writes |
| 50 | src/tools/public-references.ts | create | p1-reference-reads |
| 51 | src/tools/public-references.test.ts | create | p1-reference-reads |
| 52 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-reference-reads/build-summary.md | create | p1-reference-reads |
| 53 | src/tools/public-products.ts | create | p1-products |
| 54 | src/tools/public-products.test.ts | create | p1-products |
| 55 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-products/build-summary.md | create | p1-products |
| 56 | src/tools/public-product-writes.ts | create | p1-product-writes |
| 57 | src/tools/public-product-writes.test.ts | create | p1-product-writes |
| 58 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-product-writes/build-summary.md | create | p1-product-writes |
| 59 | src/tools/public-invoices.ts | create | p1-invoice-reads |
| 60 | src/tools/public-invoices.test.ts | create | p1-invoice-reads |
| 61 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-invoice-reads/build-summary.md | create | p1-invoice-reads |
| 62 | src/tools/public-invoice-drafts.ts | create | p1-draft-invoices |
| 63 | src/tools/public-invoice-drafts.test.ts | create | p1-draft-invoices |
| 64 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-draft-invoices/build-summary.md | create | p1-draft-invoices |
| 65 | src/tools/public-invoice-lifecycle.ts | create | p1-draft-lifecycle |
| 66 | src/tools/public-invoice-lifecycle.test.ts | create | p1-draft-lifecycle |
| 67 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-draft-lifecycle/build-summary.md | create | p1-draft-lifecycle |
| 68 | src/tools/public-invoice-actions.ts | create | p1-gated-invoices |
| 69 | src/tools/public-invoice-actions.test.ts | create | p1-gated-invoices |
| 70 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-gated-invoices/build-summary.md | create | p1-gated-invoices |
| 71 | src/tools/public-payments.ts | create | p1-manual-payments |
| 72 | src/tools/public-payments.test.ts | create | p1-manual-payments |
| 73 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-manual-payments/build-summary.md | create | p1-manual-payments |
| 74 | src/tools/customer-contacts.ts | create | p1-contacts |
| 75 | src/tools/customer-contacts.test.ts | create | p1-contacts |
| 76 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-contacts/build-summary.md | create | p1-contacts |
| 77 | src/tools/recurring-invoices.ts | modify | p1-recurring-reads |
| 78 | src/tools/recurring-invoices.test.ts | modify | p1-recurring-reads |
| 79 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-recurring-reads/build-summary.md | create | p1-recurring-reads |
| 80 | src/client/index.ts | modify | p1-auth-lifecycle |
| 81 | src/client/index.test.ts | modify | p1-auth-lifecycle |
| 82 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-auth-lifecycle/build-summary.md | create | p1-auth-lifecycle |
| 83 | src/tools/customers.ts | modify | p1-limits |
| 84 | src/tools/customers.test.ts | modify | p1-limits |
| 85 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-limits/build-summary.md | create | p1-limits |
| 86 | src/tools/index.ts | modify | p1-compose |
| 87 | src/server.ts | modify | p1-compose |
| 88 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-compose/build-summary.md | create | p1-compose |
| 89 | src/tools/index.test.ts | modify | p1-composition-tests |
| 90 | src/live/public-read.live.test.ts | create | p1-composition-tests |
| 91 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-composition-tests/build-summary.md | create | p1-composition-tests |
| 92 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-error-audit/silent-failures.md | create | p1-error-audit |
| 93 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-error-audit/log-audit.md | create | p1-error-audit |
| 94 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-error-audit/build-summary.md | create | p1-error-audit |
| 95 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-test-assess/coverage-assessment.md | create | p1-test-assess |
| 96 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-test-assess/build-summary.md | create | p1-test-assess |
| 97 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-test-run/test-results.md | create | p1-test-run |
| 98 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-test-run/build-summary.md | create | p1-test-run |
| 99 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-triage/triage-report.md | create | p1-triage |
| 100 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-triage/build-summary.md | create | p1-triage |
| 101 | docs/planning/v2/HOSTING-AUTHORIZATION.md | create | p2-authority |
| 102 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-authority/build-summary.md | create | p2-authority |
| 103 | src/transports/consumer-auth.ts | create | p2-consumers |
| 104 | src/transports/consumer-auth.test.ts | create | p2-consumers |
| 105 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-consumers/build-summary.md | create | p2-consumers |
| 106 | src/transports/http-guards.ts | create | p2-http-guards |
| 107 | src/transports/http-guards.test.ts | create | p2-http-guards |
| 108 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-http-guards/build-summary.md | create | p2-http-guards |
| 109 | src/transports/http.ts | modify | p2-http-compose |
| 110 | src/transports/http.test.ts | modify | p2-http-compose |
| 111 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-http-compose/build-summary.md | create | p2-http-compose |
| 112 | Dockerfile | create | p2-image |
| 113 | .dockerignore | create | p2-image |
| 114 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-image/build-summary.md | create | p2-image |
| 115 | scripts/fetch-wave-secrets.ts | create | p2-secret-fetch |
| 116 | scripts/fetch-wave-secrets.test.ts | create | p2-secret-fetch |
| 117 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-secret-fetch/build-summary.md | create | p2-secret-fetch |
| 118 | compose.yaml | create | p2-compose |
| 119 | docs/operations/wave-deployment.md | create | p2-compose |
| 120 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-compose/build-summary.md | create | p2-compose |
| 121 | scripts/qualify-wave-sign-in.ts | create | p2-startup |
| 122 | docs/operations/wave-session-recovery.md | create | p2-startup |
| 123 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-startup/build-summary.md | create | p2-startup |
| 124 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-security-audit/security-audit.md | create | p2-security-audit |
| 125 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-security-audit/build-summary.md | create | p2-security-audit |
| 126 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-test-assess/coverage-assessment.md | create | p2-test-assess |
| 127 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-test-assess/build-summary.md | create | p2-test-assess |
| 128 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-live-qualification/deployment-receipt.md | create | p2-live-qualification |
| 129 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-live-qualification/build-summary.md | create | p2-live-qualification |
| 130 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-triage/triage-report.md | create | p2-triage |
| 131 | .agents/runs/wave-invoicing-v2/agent-outputs/p2-triage/build-summary.md | create | p2-triage |
| 132 | src/workflows/recurring-roster.ts | create | p3-roster |
| 133 | src/workflows/recurring-roster.test.ts | create | p3-roster |
| 134 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-roster/build-summary.md | create | p3-roster |
| 135 | src/workflows/audit-recurring.ts | create | p3-audit-workflow |
| 136 | src/workflows/audit-recurring.test.ts | create | p3-audit-workflow |
| 137 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-audit-workflow/build-summary.md | create | p3-audit-workflow |
| 138 | src/workflows/render-recurring-audit.ts | create | p3-report |
| 139 | src/workflows/render-recurring-audit.test.ts | create | p3-report |
| 140 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-report/build-summary.md | create | p3-report |
| 141 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-consumer-acceptance/acceptance-receipt.md | create | p3-consumer-acceptance |
| 142 | docs/reports/recurring-audit-v1.md | create | p3-consumer-acceptance |
| 143 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-consumer-acceptance/build-summary.md | create | p3-consumer-acceptance |
| 144 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-test-assess/coverage-assessment.md | create | p3-test-assess |
| 145 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-test-assess/build-summary.md | create | p3-test-assess |
| 146 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-test-run/test-results.md | create | p3-test-run |
| 147 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-test-run/build-summary.md | create | p3-test-run |
| 148 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-triage/triage-report.md | create | p3-triage |
| 149 | docs/operations/wave-handover.md | create | p3-triage |
| 150 | .agents/runs/wave-invoicing-v2/agent-outputs/p3-triage/build-summary.md | create | p3-triage |
| 151 | docs/planning/v2/S1-AUTHORIZATION.md | create | s1-authority |
| 152 | .agents/runs/wave-invoicing-v2/agent-outputs/s1-authority/build-summary.md | create | s1-authority |
| 153 | docs/research/S1-RESULTS.md | create | s1-research |
| 154 | .agents/runs/wave-invoicing-v2/agent-outputs/s1-research/build-summary.md | create | s1-research |
| 155 | docs/planning/v2/S2-AUTHORIZATION.md | create | s2-authority |
| 156 | .agents/runs/wave-invoicing-v2/agent-outputs/s2-authority/build-summary.md | create | s2-authority |
| 157 | docs/research/S2-RESULTS.md | create | s2-research |
| 158 | .agents/runs/wave-invoicing-v2/agent-outputs/s2-research/build-summary.md | create | s2-research |
| 159 | src/auth/auth0-sign-in.ts | modify | p1-signin-budget |
| 160 | src/auth/auth0-sign-in.test.ts | modify | p1-signin-budget |
| 161 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-signin-budget/build-summary.md | create | p1-signin-budget |
| 162 | src/auth/profile-lock.ts | modify | p1-lock-budget |
| 163 | src/auth/profile-lock.test.ts | modify | p1-lock-budget |
| 164 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-lock-budget/build-summary.md | create | p1-lock-budget |
| 165 | vitest.live.config.ts | modify | p1-live-budget |
| 166 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-live-budget/build-summary.md | create | p1-live-budget |
| 167 | src/client/errors.ts | modify | p1-error-detail |
| 168 | src/client/errors.test.ts | modify | p1-error-detail |
| 169 | .agents/runs/wave-invoicing-v2/agent-outputs/p1-error-detail/build-summary.md | create | p1-error-detail |

## 3. Sections

### p0-audit-gate — Written Coordinator plan audit approval [contract]

Phase: 0; role: planner; depends on accepted reviews: none. Manifest rows: [1, 2].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 0. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: none. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
EXTERNAL GATE ONLY: parent receives and verifies Benny written audit approval of this exact plan revision and limit inventory, persists original approval verbatim with source reference and plan digest. Never dispatch a worker to invent approval. Permission to author setup is NOT approval to implement. Keep needs_revision hold until approval arrives.
Declared write fence: docs/planning/v2/PLAN-AUDIT-APPROVAL.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- exact plan digest named
- approver/source verified
- no feature task starts before approval
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/planning/v2/PLAN-AUDIT-APPROVAL.md
Log actual command exits and complete output; never fabricate output. Named tests: exact plan digest named; approver/source verified; no feature task starts before approval. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p0-audit-gate/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p0-audit-gate status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p0-audit-gate/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p0-audit-gate-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-prerequisites — Record roster and test-business prerequisites [contract]

Phase: 1; role: builder; depends on accepted reviews: p0-audit-gate-r. Manifest rows: [3, 4].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p0-audit-gate-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Resolve OQ-1 roster source and OQ-4 designated test business/customer with Coordinator; record references and ownership, never values. Identify Infisical enrollment/operator grants separately from agent custody. Confirm published public schema source and licensed codegen dependency scan before adoption; GPL kcrosby is pattern-only. No writes against real client records.
Declared write fence: docs/planning/v2/IMPLEMENTATION-PREREQUISITES.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- roster authority known
- dedicated test targets approved
- secrets by reference only
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/planning/v2/IMPLEMENTATION-PREREQUISITES.md
Log actual command exits and complete output; never fabricate output. Named tests: roster authority known; dedicated test targets approved; secrets by reference only. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-prerequisites/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-prerequisites status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-prerequisites/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-prerequisites-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-dependency-clearance — Remediate inherited runtime advisories [config]

Phase: 1; role: builder; depends on accepted reviews: p1-prerequisites-r. Manifest rows: [5, 6, 7].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- package.json
- package-lock.json

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-prerequisites-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Scan and pin supported safe versions for inherited body-parser and fast-uri dependency findings without replacing upstream tests. npm audit fix is not a blind substitute for analysis. Preserve initial audit; rerun full 486 inherited tests, typecheck and audit, document remaining reachability only if Coordinator accepts it. Core provenance zod advisory is separate dev-only remediation task.
Declared write fence: package.json, package-lock.json. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- body-parser high cleared
- fast-uri findings cleared
- inherited identities preserved
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm audit --omit=dev && npm test && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: body-parser high cleared; fast-uri findings cleared; inherited identities preserved. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-dependency-clearance/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-dependency-clearance status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-dependency-clearance/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-dependency-clearance-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-provenance-clearance — Clear development provenance zod advisory [config]

Phase: 1; role: builder; depends on accepted reviews: p1-prerequisites-r. Manifest rows: [8, 9, 10].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- .agents/provenance/package.json
- .agents/provenance/package-lock.json

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-prerequisites-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Patch isolated provenance zod from inherited 4.4.3 to scanned nonvulnerable compatible version, preserving core source and task DB. No shared ADW upstream edits. Regenerate isolated lock, run provenance schema/redaction/ledger tests. Record any optional dependency advisory separately, do not install embeddings/model for this task.
Declared write fence: .agents/provenance/package.json, .agents/provenance/package-lock.json. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- zod advisory cleared
- ledger schema current
- redaction/contract regression green
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm --prefix .agents/provenance audit --omit=optional && npm test && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: zod advisory cleared; ledger schema current; redaction/contract regression green. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-provenance-clearance/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-provenance-clearance status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-provenance-clearance/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-provenance-clearance-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-schema — Pin official public Wave schema [contract]

Phase: 1; role: builder; depends on accepted reviews: p1-prerequisites-r. Manifest rows: [11, 12, 13].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/_queries.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-prerequisites-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Fetch official public schema only through approved access if required. Commit raw schema and source/retrieval digest, classify exact FR/tool field/input mapping. No invented bills/reports/recurring mutations. Verify estimates deferred v1.1. If authenticated schema cannot be obtained, hold codegen; do not synthesize a schema.
Declared write fence: src/client/public/schema.graphql, docs/planning/v2/PUBLIC-SCHEMA-PROVENANCE.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- all v2 public operations map to actual fields
- schema byte digest recorded
- unsupported surfaces absent
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s src/client/public/schema.graphql && test -s docs/planning/v2/PUBLIC-SCHEMA-PROVENANCE.md
Log actual command exits and complete output; never fabricate output. Named tests: all v2 public operations map to actual fields; schema byte digest recorded; unsupported surfaces absent. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-schema/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-schema status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-schema/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-schema-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-codegen-config — Install schema codegen build step [config]

Phase: 1; role: builder; depends on accepted reviews: p1-schema-r, p1-dependency-clearance-r. Manifest rows: [14, 15, 16].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- package.json

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-schema-r, p1-dependency-clearance-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Adopt scanned maintained GraphQL codegen and typed operation SDK libraries, pinned dev/runtime split. Add codegen and codegen:check scripts; generated SDK deterministic with committed schema, never live introspection during normal build. No rhanka source adopted without clone/scan/license verdict.
Declared write fence: package.json, package-lock.json. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- scanned pinned dependencies
- offline generation command exists
- drift fails check
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm run typecheck && npm test
Log actual command exits and complete output; never fabricate output. Named tests: scanned pinned dependencies; offline generation command exists; drift fails check. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-codegen-config/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-codegen-config status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-codegen-config/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-codegen-config-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-public-operations — Declare exact public operations [contract]

Phase: 1; role: builder; depends on accepted reviews: p1-codegen-config-r. Manifest rows: [17, 18, 19].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/client/public/schema.graphql

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-codegen-config-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Declare only v2 standard reads and mutations with typed variables, fragments and inputErrors selections: business/customer/invoice/product/tax/account reads, customer CRUD, product create/patch/archive, invoice create/patch/clone/delete/approve/send/markSent and manual payment create/patch/delete. Cursor pageInfo complete. Scope business selection in every applicable operation. Configure typed-document generation to sdk.ts.
Declared write fence: src/client/public/operations.graphql, codegen.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- all listed public tools have operation
- inputErrors selected
- pagination complete
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm run codegen && npm run codegen:check && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: all listed public tools have operation; inputErrors selected; pagination complete. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-public-operations/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-public-operations status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-public-operations/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-public-operations-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-generate-sdk — Generate typed SDK and drift CI check [config]

Phase: 1; role: builder; depends on accepted reviews: p1-public-operations-r. Manifest rows: [20, 21, 22].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- codegen.ts
- src/client/public/operations.graphql

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-public-operations-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Run documented generation; SDK is generated-only, never hand-edited. CI regenerates and fails on tracked diff; typecheck includes SDK and codegen configuration. Preserve inherited test lane and secret guard. Generated aggregation may exceed size signal because it represents one schema, not handwritten mixed responsibilities.
Declared write fence: src/client/public/sdk.ts, .github/workflows/test.yml. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- regeneration byte-identical
- mutation variable typing enforced
- CI drift check fails after fixture change
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm run codegen:check && npm run typecheck && npm test
Log actual command exits and complete output; never fabricate output. Named tests: regeneration byte-identical; mutation variable typing enforced; CI drift check fails after fixture change. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-generate-sdk/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-generate-sdk status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-generate-sdk/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-generate-sdk-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-public-client — Build typed public GraphQL boundary [service]

Phase: 1; role: builder; depends on accepted reviews: p1-generate-sdk-r. Manifest rows: [23, 24, 25].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/client/graphql.ts
- src/client/errors.ts
- src/client/public/sdk.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-generate-sdk-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Define IWavePublicClient.execute<T>(document: TypedDocumentNode<T, Variables>, variables: Variables): Promise<T>; implement WavePublicClient using native fetch and generated SDK, Full Access Token env injection only, fixed public endpoint. Validate GraphQL envelope at runtime with schema-derived types; preserve HTTP/auth/GraphQL/inputErrors codes/messages in structured errors. No blind write retry or raw token logging. Apply planned 180s request timeout, explicit truncation errors for response bound.
Declared write fence: src/client/public/client.ts, src/client/public/client.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- HTTP and inputErrors preserved
- token absent from all errors/logs
- write network timeout never retried
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/client/public/client.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: HTTP and inputErrors preserved; token absent from all errors/logs; write network timeout never retried. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-public-client/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-public-client status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-public-client/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-public-client-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-business-scope — Enforce pinned business and resource ownership [service]

Phase: 1; role: builder; depends on accepted reviews: p1-public-client-r. Manifest rows: [26, 27, 28].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/client/index.ts
- src/client/ids.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-public-client-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Define BusinessScopeSchema {businessId:uuid}; derive BusinessScope. assertBusinessScope(configuredBusinessId:string, requestedBusinessId?:string):string rejects mismatch. Resource IDs alone must be resolved to owning business before reads or writes. Public list-businesses diagnostic returns only authorized configured business or explicit scope error; never broadens tool authority. Existing WaveClient.businessId permits override and is not a security pin.
Declared write fence: src/client/business-scope.ts, src/client/business-scope.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- explicit different business rejected
- foreign resource ID rejected
- diagnostic cannot enumerate unauthorized business
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/client/business-scope.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: explicit different business rejected; foreign resource ID rejected; diagnostic cannot enumerate unauthorized business. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-business-scope/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-business-scope status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-business-scope/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-business-scope-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-tool-catalog — Declare public/internal tool policy catalog [service]

Phase: 1; role: builder; depends on accepted reviews: p1-business-scope-r. Manifest rows: [29, 30, 31].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts
- src/tools/tags.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-business-scope-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Define ToolTierSchema enum read/write/destructive; ToolDefinitionSchema {name:string,tier:ToolTier,gated:boolean,backend:public|internal,exposedByDefault:boolean}. Derive types; exact v2 section5 allowlist incl contact and recurring names. Standard operations public-only; inherited bills/receipts/statements/export/tags/transactions and estimates unexposed by default. No GPL implementation copied.
Declared write fence: src/tools/tool-catalog.ts, src/tools/tool-catalog.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- exact catalog matches v2
- out-of-scope defaults deny
- gated contacts categorized
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/tool-catalog.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: exact catalog matches v2; out-of-scope defaults deny; gated contacts categorized. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-tool-catalog/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-tool-catalog status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-tool-catalog/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-tool-catalog-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-policy — Parse policy with read-only deny-first defaults [service]

Phase: 1; role: builder; depends on accepted reviews: p1-tool-catalog-r. Manifest rows: [32, 33, 34].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/tool-catalog.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-tool-catalog-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
ToolPolicySchema {tools:record(toolName,{allow:boolean,tier:ToolTier}),allowedTiers:ToolTier[]}; parseToolPolicy(raw:unknown,catalog:ToolDefinition[]):ToolPolicy validates names at startup. authorizeTool(policy,name):void applies deny before tier, unspecified tools deny unless default catalog in-scope read. Destructive semantics include customer/draft deletion, but require policy enablement even when PRD does not require confirmation. Not a general rights system.
Declared write fence: src/tools/policy.ts, src/tools/policy.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- read-only default
- deny beats tier allow
- unknown names fail startup
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/policy.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: read-only default; deny beats tier allow; unknown names fail startup. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-policy/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-policy status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-policy/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-policy-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-confirm — Build single-use snapshot-bound confirmation [service]

Phase: 1; role: builder; depends on accepted reviews: p1-policy-r. Manifest rows: [35, 36, 37].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/client/errors.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-policy-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
PreviewSchema {tool:string,targetId:string,inputs:unknown,snapshot:unknown,consumerId:string,businessId:uuid,expiresAt:datetime}; derive ConfirmationPreview. previewAction(preview):{summary:ConfirmationPreview,fingerprint:string}; consumeConfirmation(fingerprint,confirm,currentPreview):void checks server-held keyed canonical digest, exact consumer/business/tool/input/current snapshot binding, 30min validity and single use before effects. Concurrent replay may execute at most once. Restart invalidates outstanding previews explicitly. Full human-readable preview, no secret values. No stable unkeyed client-forgeable digest as authorization.
Declared write fence: src/tools/confirmation.ts, src/tools/confirmation.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- changed snapshot invalidates
- cross-consumer/replay rejected
- confirm false never executes
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/confirmation.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: changed snapshot invalidates; cross-consumer/replay rejected; confirm false never executes. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-confirm/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-confirm status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-confirm/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-confirm-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-write-audit — Log structured write outcomes without secrets [service]

Phase: 1; role: builder; depends on accepted reviews: p1-confirm-r. Manifest rows: [38, 39, 40].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/util/log.ts
- src/client/errors.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-confirm-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
WriteAuditSchema {tool:string,targetIds:string[],consumerId:string,outcome:success|failure|unknown,durationMs:number,code?:string}; auditWrite(event:WriteAudit):void records identity/IDs/result only. Never full Wave response, cookies, password, TOTP, headers or fingerprint. Structured boundary errors preserve upstream codes and nextAction, redacted details; no 1k silent clipping of inputErrors. Ambiguous write response reports unknown, never claims success.
Declared write fence: src/util/write-audit.ts, src/util/write-audit.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- all write paths audited
- credential canaries absent
- unknown outcome explicit
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/util/write-audit.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: all write paths audited; credential canaries absent; unknown outcome explicit. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-write-audit/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-write-audit status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-write-audit/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-write-audit-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-pagination — Centralize complete public pagination [service]

Phase: 1; role: builder; depends on accepted reviews: p1-public-client-r. Manifest rows: [41, 42, 43].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/client/types.ts
- src/tools/customers.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-public-client-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
PageCursorSchema {endCursor:string|null,hasNextPage:boolean}; WalkResultSchema {items:array(unknown),complete:boolean,nextCursor:string|null,stopReason?:string}; derive types. walkPublicPages(fetchPage,options):Promise<WalkResult> uses API-verified maximum page size (plan target 500, never assume allowed), 15min total traversal, no fixed page/item ceiling; safe partial return is explicit and audit workflow refuses incomplete source. Detect repeated cursor and empty-progress pages.
Declared write fence: src/client/public/pagination.ts, src/client/public/pagination.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- beyond inherited 5000 finds match
- cursor loop fails explicitly
- timeout marks incomplete
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/client/public/pagination.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: beyond inherited 5000 finds match; cursor loop fails explicitly; timeout marks incomplete. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-pagination/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-pagination status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-pagination/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-pagination-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-customer-reads — Public customer discovery [service]

Phase: 1; role: builder; depends on accepted reviews: p1-pagination-r, p1-business-scope-r. Manifest rows: [44, 45, 46].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-pagination-r, p1-business-scope-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicCustomerReads(server,client,scope) exposes wave_list_customers and wave_get_customer; schema-validated email/name search, full principal/address/shipping/currency/archive/balance where schema exposes. Use public authoritative results; no internal fallback silently changes semantics.
Declared write fence: src/tools/public-customers.ts, src/tools/public-customers.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- email exact search
- full customer detail
- foreign ID refused
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-customers.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: email exact search; full customer detail; foreign ID refused. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-customer-reads/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-customer-reads status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-customer-reads/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-customer-reads-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-customer-writes — Public customer CRUD [service]

Phase: 1; role: builder; depends on accepted reviews: p1-customer-reads-r, p1-write-audit-r. Manifest rows: [47, 48, 49].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-customer-reads-r, p1-write-audit-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicCustomerWrites exposes create/update/delete. Patch omission differs from explicit clear, no address loss. Policy and scope on every write; deletion destructive. Return inputErrors unchanged. Use generated types, decimal/currency precision from schema.
Declared write fence: src/tools/public-customer-writes.ts, src/tools/public-customer-writes.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- patch preserves omitted fields
- delete denied by default
- inputErrors retained
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-customer-writes.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: patch preserves omitted fields; delete denied by default; inputErrors retained. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-customer-writes/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-customer-writes status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-customer-writes/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-customer-writes-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-reference-reads — Business taxes and account reference reads [service]

Phase: 1; role: builder; depends on accepted reviews: p1-pagination-r, p1-business-scope-r. Manifest rows: [50, 51, 52].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-pagination-r, p1-business-scope-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicReferences exposes get_business/list_businesses/list_sales_taxes/list_accounts for pinned business only. Complete paginated account/tax reads including archives only by explicit request; no accounts hardcoded first-page-only 500 query in public route.
Declared write fence: src/tools/public-references.ts, src/tools/public-references.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- scope pinned
- tax history retained
- accounts beyond first page
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-references.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: scope pinned; tax history retained; accounts beyond first page. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-reference-reads/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-reference-reads status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-reference-reads/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-reference-reads-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-products — Public product discovery [service]

Phase: 1; role: builder; depends on accepted reviews: p1-reference-reads-r. Manifest rows: [53, 54, 55].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-reference-reads-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicProducts exposes list/get products incl unit price, sold/bought flags, description and default sales taxes, strict resource ownership and public pagination.
Declared write fence: src/tools/public-products.ts, src/tools/public-products.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- default taxes retained
- archived product visible on request
- page continuation
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-products.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: default taxes retained; archived product visible on request; page continuation. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-products/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-products status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-products/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-products-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-product-writes — Public product create patch archive [service]

Phase: 1; role: builder; depends on accepted reviews: p1-products-r, p1-write-audit-r. Manifest rows: [56, 57, 58].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-products-r, p1-write-audit-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicProductWrites exposes create/update/archive, typed inputs and audit/deny-first policy, preserve defaultSalesTaxIds when omitted; archive means archive, not inherited delete.
Declared write fence: src/tools/public-product-writes.ts, src/tools/public-product-writes.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- archive not delete
- tax defaults preserved
- write denied by default
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-product-writes.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: archive not delete; tax defaults preserved; write denied by default. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-product-writes/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-product-writes status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-product-writes/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-product-writes-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-invoice-reads — Public invoice discovery [service]

Phase: 1; role: builder; depends on accepted reviews: p1-pagination-r, p1-reference-reads-r. Manifest rows: [59, 60, 61].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-pagination-r, p1-reference-reads-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicInvoiceReads exposes list/get with schema-supported status/customer/date filtering, exact decimal totals/line taxes and current state for confirmation snapshot, complete public pagination.
Declared write fence: src/tools/public-invoices.ts, src/tools/public-invoices.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- filter maps to real schema
- totals exact
- foreign invoice rejected
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-invoices.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: filter maps to real schema; totals exact; foreign invoice rejected. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-invoice-reads/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-invoice-reads status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-invoice-reads/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-invoice-reads-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-draft-invoices — Draft invoice create and edit [service]

Phase: 1; role: builder; depends on accepted reviews: p1-invoice-reads-r, p1-product-writes-r, p1-customer-writes-r. Manifest rows: [62, 63, 64].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-invoice-reads-r, p1-product-writes-r, p1-customer-writes-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicInvoiceDrafts exposes create/update; only DRAFT on input and readback, checks actual current state before patch. Product default taxes applied when omitted, explicit per-line overrides honored; free-form supported. Next-invoice credit is explicit discount/write-down item, not fictitious credit balance or money movement. Never auto-approve/send.
Declared write fence: src/tools/public-invoice-drafts.ts, src/tools/public-invoice-drafts.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- non-draft edit rejected
- product taxes and explicit overrides
- credit line arithmetic preserved
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-invoice-drafts.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: non-draft edit rejected; product taxes and explicit overrides; credit line arithmetic preserved. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-draft-invoices/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-draft-invoices status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-draft-invoices/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-draft-invoices-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-draft-lifecycle — Draft invoice clone and delete [service]

Phase: 1; role: builder; depends on accepted reviews: p1-draft-invoices-r. Manifest rows: [65, 66, 67].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-draft-invoices-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicInvoiceLifecycle exposes clone/delete. Clone output must remain draft, source ownership checked; deletion only existing drafts and destructive policy. No inheritance path that can approve or send behind these tool names.
Declared write fence: src/tools/public-invoice-lifecycle.ts, src/tools/public-invoice-lifecycle.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- clone remains draft
- non-draft delete refused
- destructive policy enforced
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-invoice-lifecycle.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: clone remains draft; non-draft delete refused; destructive policy enforced. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-draft-lifecycle/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-draft-lifecycle status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-draft-lifecycle/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-draft-lifecycle-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-gated-invoices — Gated invoice approve send mark-sent [service]

Phase: 1; role: builder; depends on accepted reviews: p1-draft-lifecycle-r, p1-confirm-r, p1-write-audit-r. Manifest rows: [68, 69, 70].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-draft-lifecycle-r, p1-confirm-r, p1-write-audit-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicInvoiceActions uses two-step confirmation for approve/send/mark-sent; fetch latest target and actual recipients in preview; explicit recipients per-send without modifying customer. Consume single-use confirm before mutation, log unknown on ambiguous failure, no automatic mutation retry. Recipient count limited only by verified upstream schema/service, plan target100 not blind hardcoded10.
Declared write fence: src/tools/public-invoice-actions.ts, src/tools/public-invoice-actions.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- preview makes zero mutations
- recipient change invalidates
- replay sends at most once
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-invoice-actions.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: preview makes zero mutations; recipient change invalidates; replay sends at most once. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-gated-invoices/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-gated-invoices status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-gated-invoices/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-gated-invoices-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-manual-payments — Gated manual payment accounting [service]

Phase: 1; role: builder; depends on accepted reviews: p1-gated-invoices-r. Manifest rows: [71, 72, 73].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-gated-invoices-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerPublicPayments exposes record/update/delete manually recorded payment only. Confirm full amount/currency/account/current snapshot, policy and scope. Reject actual Wave Payments processor refund/reversal and explain permanent UI residual. No token/credential in returned errors.
Declared write fence: src/tools/public-payments.ts, src/tools/public-payments.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- manual patch/delete gated
- processor payment rejected
- ambiguous response never retried
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/public-payments.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: manual patch/delete gated; processor payment rejected; ambiguous response never retried. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-manual-payments/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-manual-payments status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-manual-payments/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-manual-payments-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-contacts — Safe internal contacts read modify write [service]

Phase: 1; role: builder; depends on accepted reviews: p1-customer-writes-r, p1-confirm-r. Manifest rows: [74, 75, 76].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-customer-writes-r, p1-confirm-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
registerCustomerContacts exposes list/set contacts only via internal client. Read existing full customer snapshot including address/shipping, show replace-whole-list deletions incl id-only deletion. Gated execution re-reads snapshot; preserve omitted address/shipping; if drift refuse and preview again. Scope check actual customer business; require internal auth, no public contact fiction.
Declared write fence: src/tools/customer-contacts.ts, src/tools/customer-contacts.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- id-only deletion surfaced
- addresses preserved
- concurrent change invalidates
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/customer-contacts.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: id-only deletion surfaced; addresses preserved; concurrent change invalidates. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-contacts/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-contacts status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-contacts/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-contacts-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-recurring-reads — Internal recurring read verification [service]

Phase: 1; role: builder; depends on accepted reviews: p1-contacts-r. Manifest rows: [77, 78, 79].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.ts
- src/tools/recurring-invoices.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-contacts-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Retain existing list/get names, bind business through scope, paginate to completion at caller/workflow level, return full state/customer/currency/total/payment terms/first previous next date/count/product/taxes/schedule/delivery settings. No recurring write code or invented mutation. Add assertions to existing tests instead of duplicate files.
Declared write fence: src/tools/recurring-invoices.ts, src/tools/recurring-invoices.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- all required fields retained
- foreign business refused
- pagination explicit
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/recurring-invoices.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: all required fields retained; foreign business refused; pagination explicit. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-recurring-reads/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-recurring-reads status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-recurring-reads/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-recurring-reads-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-auth-lifecycle — Wire automated secret-file sign-in with safe retry [service]

Phase: 1; role: builder; depends on accepted reviews: p1-recurring-reads-r, p1-live-budget-r, p1-error-detail-r. Manifest rows: [80, 81, 82].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/client/auth.ts
- src/auth/refresh-session.ts
- src/auth/secrets.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-recurring-reads-r, p1-live-budget-r, p1-error-detail-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Use inherited secretStoreFromEnv and refreshSession, do not reinvent TOTP/browser Auth0 mapping. Test with dummy file-backed credentials. Fresh no-session startup currently loadAuth throws before refresher: explicitly establish first session through inherited refresh CLI/deploy preflight (p2-startup), not a fabricated invalid token. Existing tools auto-retry after rejected auth; ensure contacts write is not repeated after ambiguous network response. Public tools must remain usable when internal session expired/challenged. Refresh single-flight stays profile-locked; do not bypass challenge.
Declared write fence: src/client/index.ts, src/client/index.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- expired session refreshes with files
- rotation rereads files
- internal auth failure does not disable public tools
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/client/index.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: expired session refreshes with files; rotation rereads files; internal auth failure does not disable public tools. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-auth-lifecycle/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-auth-lifecycle status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-auth-lifecycle/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-auth-lifecycle-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-limits — Remove customer search roster ceiling [service]

Phase: 1; role: builder; depends on accepted reviews: p1-pagination-r. Manifest rows: [83, 84, 85].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/customers.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-pagination-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Implement inventory L01 disposition for inherited customer search: no silent first5000 ceiling. Walk actual pages within explicit total deadline; complete flag/continuation on timeout or repeated page. Preserve all co-located inherited assertions; mark deliberate behavior revision explicitly. Internal default unexposed customer tools remain tested. No blind page-size above upstream acceptance.
Declared write fence: src/tools/customers.ts, src/tools/customers.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- customer past5000 found
- deadline returns continuation
- loop explicit failure
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/customers.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: customer past5000 found; deadline returns continuation; loop explicit failure. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-limits/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-limits status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-limits/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-limits-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-compose — Compose public surface with policy and internal blind spots [service]

Phase: 1; role: builder; depends on accepted reviews: p1-manual-payments-r, p1-contacts-r, p1-auth-lifecycle-r, p1-limits-r, p1-error-detail-r. Manifest rows: [86, 87, 88].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/tools/index.test.ts
- src/server.ts
- src/transports/stdio.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-manual-payments-r, p1-contacts-r, p1-auth-lifecycle-r, p1-limits-r, p1-error-detail-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Composition root constructs public/internal clients and policy once per consumer session. Register only in-scope catalog tools (30 v2 names) and deny unconfigured writes. Existing inherited registrations remain callable by their module tests but are not exposed. Public client startup must not require a valid internal session. Consumer identity flows to confirmation/audit; stdio fixed local operator identity explicit, HTTP authenticated identity only. Enforce same policy on all transport paths.
Declared write fence: src/tools/index.ts, src/server.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- exact tool listing
- default no write execution
- expired internal does not block public
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm run typecheck && npm test
Log actual command exits and complete output; never fabricate output. Named tests: exact tool listing; default no write execution; expired internal does not block public. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-compose/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-compose status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-compose/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-compose-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-composition-tests — Prove real server policy and tool routing [test]

Phase: 1; role: builder; depends on accepted reviews: p1-compose-r. Manifest rows: [89, 90, 91].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/server.ts
- src/tools/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-compose-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Extend inherited composition tests without duplicating discovery. Real MCP server/transport to local protocol-faithful test endpoint verifies routing and policy; external live public reads tier separately guarded, never claimed real from fixture evidence. Reconcile exact tool count from v2 section5 programmatically; no fabricated Wave responses counted as live.
Declared write fence: src/tools/index.test.ts, src/live/public-read.live.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- in-scope names only
- internal/public routing exact
- default deny before API mutation
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/tools/index.test.ts src/live/public-read.live.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: in-scope names only; internal/public routing exact; default deny before API mutation. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-composition-tests/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-composition-tests status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-composition-tests/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-composition-tests-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-error-audit — Audit silent failures and credential logging [audit]

Phase: 1; role: silent-failure-hunter; depends on accepted reviews: p1-composition-tests-r. Manifest rows: [92, 93, 94].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/client/public/client.ts
- src/util/write-audit.ts
- src/client/index.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-composition-tests-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Read-only audit all Phase1 error/refresh/confirmation/policy paths for swallowed failures, generic error collapse, secret-bearing output, write retry and ambiguous outcome misclassification. Preserve finding severity and source references; feed triage, never repair in audit task.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p1-error-audit/silent-failures.md, .agents/runs/wave-invoicing-v2/agent-outputs/p1-error-audit/log-audit.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- every error family traced
- no secret logging
- all findings dispositioned
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s .agents/runs/wave-invoicing-v2/agent-outputs/p1-error-audit/log-audit.md
Log actual command exits and complete output; never fabricate output. Named tests: every error family traced; no secret logging; all findings dispositioned. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-error-audit/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-error-audit status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-error-audit/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-error-audit-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-test-assess — Assess Phase 1 contract integration and live coverage [test-assess]

Phase: 1; role: test-creator; depends on accepted reviews: p1-error-audit-r. Manifest rows: [95, 96].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-error-audit-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Test-creator evaluates every v2 FR/tool, generated SDK drift, scope, policy, confirm, contacts preservation, manual payments/credit mechanism and automated sign-in file lifecycle. Prioritize real integration/contract, then pure unit. Register bounded gap tasks with review before execution; parent alone writes ADW state. Live reads are not replaceable by mocks; block acceptance when missing. Docker not required for local tests; Wave test credentials/targets required for approved live tier only.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p1-test-assess/coverage-assessment.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- FR-to-test matrix complete
- named live prerequisites
- gap tasks reviewed
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s .agents/runs/wave-invoicing-v2/agent-outputs/p1-test-assess/coverage-assessment.md
Log actual command exits and complete output; never fabricate output. Named tests: FR-to-test matrix complete; named live prerequisites; gap tasks reviewed. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-test-assess/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-test-assess status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-test-assess/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-test-assess-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-test-run — Run Phase 1 full regression and scoped live reads [test]

Phase: 1; role: tester; depends on accepted reviews: p1-test-assess-r. Manifest rows: [97, 98].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-test-assess-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Run exact full inherited+new suite, typecheck, offline codegen drift, policy and real MCP integration. Verify inherited486 case identities remain green (known root-only chmod artifact documented if environment changes). Run approved read-only live public/internal reads with test credential path, preserve output safely and separate live proof. No real financial mutation in test without designated target and explicit authority. Failure stops at reviewer/triage; resolver can correct tests only within approved semantics.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p1-test-run/test-results.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- 486 inherited preserved
- new contract/integration pass
- approved live reads evidenced
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test && npm run typecheck && npm run codegen:check
Log actual command exits and complete output; never fabricate output. Named tests: 486 inherited preserved; new contract/integration pass; approved live reads evidenced. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-test-run/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-test-run status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-test-run/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-test-run-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-triage — Phase 1 debt triage and Coordinator audit handoff [audit]

Phase: 1; role: planner; depends on accepted reviews: p1-test-run-r. Manifest rows: [99, 100].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-test-run-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Triage all builder/reviewer/auditor/test signals, create bounded managed work for defects, explicit Coordinator-approved residual for nonblocking debt only. No security/credential/scope defects waived silently. Record round evidence and obtain written Coordinator audit before Phase2 hosting. Report ends Triage: CLEAN only if actually clean; approval remains separate external gate.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p1-triage/triage-report.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- all signals classified
- baseline evidence preserved
- Phase2 gate remains explicit
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s .agents/runs/wave-invoicing-v2/agent-outputs/p1-triage/triage-report.md
Log actual command exits and complete output; never fabricate output. Named tests: all signals classified; baseline evidence preserved; Phase2 gate remains explicit. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-triage/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-triage status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-triage/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-triage-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-authority — Obtain hosting and identity enrollment authority [contract]

Phase: 2; role: planner; depends on accepted reviews: p1-triage-r. Manifest rows: [101, 102].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-triage-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
EXTERNAL Coordinator/CEO gate: Phase1 audit approval plus designated server/port/origin/consumer identities and deployment grant; owner Full Access Token grant and dedicated automation-user Infisical enrollment references. No enrollment by agent, no values, no inferred port or changed fleet config. Server read-only diagnostics separately from deployment authority. Stop if access absent.
Declared write fence: docs/planning/v2/HOSTING-AUTHORIZATION.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- written deployment grant
- dedicated-user references
- host/port/origin exact
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/planning/v2/HOSTING-AUTHORIZATION.md
Log actual command exits and complete output; never fabricate output. Named tests: written deployment grant; dedicated-user references; host/port/origin exact. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-authority/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-authority status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-authority/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-authority-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-consumers — Per-consumer bearer auth and revocation [service]

Phase: 2; role: builder; depends on accepted reviews: p2-authority-r. Manifest rows: [103, 104, 105].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/transports/http.ts

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-authority-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
ConsumerSchema {id:string,tokenReference:string,enabled:boolean}; authenticateConsumer(header,registry):AuthenticatedConsumer uses secret values only in server runtime, timing-safe match, disabled/revoked rejected; reject duplicate identities and missing registry on public bind. Session ID does not confer identity; every request reauthenticates and binds session ownership. No shared fallback token across consumers.
Declared write fence: src/transports/consumer-auth.ts, src/transports/consumer-auth.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- revocation rejects existing session
- cross-session identity refused
- token never serialized
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/transports/consumer-auth.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: revocation rejects existing session; cross-session identity refused; token never serialized. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-consumers/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-consumers status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-consumers/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-consumers-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-http-guards — Origin rate and capacity guardrails [service]

Phase: 2; role: builder; depends on accepted reviews: p2-consumers-r. Manifest rows: [106, 107, 108].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/transports/http.ts

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-consumers-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
HttpGuardConfigSchema declares allowedOrigins, requestBytes, responseBytes, consumerRate, burst, concurrentCalls, maxSessions, idleSessionMs. Use inventory N01–N09. Strict origin allowlist plus Host validation; authorize before parse; nonbrowser no-Origin accepted only for authenticated consumer. Rate gates apply before effects; 429 Retry-After; no silent eviction of in-flight calls. Session cleanup/stream cancellation and max request/response enforcement explicit.
Declared write fence: src/transports/http-guards.ts, src/transports/http-guards.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- hostile Origin rejected
- rate identity isolated
- large billing payload within generous budget
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/transports/http-guards.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: hostile Origin rejected; rate identity isolated; large billing payload within generous budget. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-http-guards/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-http-guards status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-http-guards/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-http-guards-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-http-compose — Integrate authenticated HTTP transport [service]

Phase: 2; role: builder; depends on accepted reviews: p2-http-guards-r. Manifest rows: [109, 110, 111].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/transports/consumer-auth.ts
- src/transports/http-guards.ts

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-http-guards-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Integrate guards, identity-bound session registry, payload/response streaming ceilings, idle cleanup and long action budget. Preserve inherited 413 behavior without excessive drain; disconnects never trigger financial replay. Full StreamableHTTP initialize/call/GET/delete exercised over real loopback HTTP. Replace global token path only via explicit migration and deny absent consumer registry on public endpoint.
Declared write fence: src/transports/http.ts, src/transports/http.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- real MCP over HTTP
- no cross-consumer session access
- idle session reclaimed safely
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/transports/http.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: real MCP over HTTP; no cross-consumer session access; idle session reclaimed safely. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-http-compose/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-http-compose status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-http-compose/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-http-compose-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-image — Build runtime image with headless Chromium [infra]

Phase: 2; role: builder; depends on accepted reviews: p2-http-compose-r. Manifest rows: [112, 113, 114].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- package.json
- src/auth/playwright.ts

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-http-compose-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Pin supported Node22 runtime and Playwright/browser version, install full Chromium and required shared libraries for inherited automated sign-in. Nonroot UID, writable private profile/session volume, secret files read-only. Exclude .agents/.codex/planning/.git/test logs and dev dependencies from deploy image; ADW is not runtime. No stealth extension/challenge bypass beyond inherited source; visible challenge must stop. Inspect image files for no embedded secrets.
Declared write fence: Dockerfile, .dockerignore. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- Chromium launches as runtime UID
- ADW absent image
- session volume private
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
docker build -t wave-mcp:qualification .
Log actual command exits and complete output; never fabricate output. Named tests: Chromium launches as runtime UID; ADW absent image; session volume private. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-image/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-image status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-image/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-image-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-secret-fetch — Infisical server-side fetch to secret files [infra]

Phase: 2; role: builder; depends on accepted reviews: p2-image-r. Manifest rows: [115, 116, 117].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/auth/secrets.ts
- src/auth/credentials.ts

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-image-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Use existing agency Infisical client/injection mechanism after clone/scan, no new broker. Human-enrolled dedicated login v2 keys LOGIN_IDENTIFIER/PASSWORD/TOTP_SECRET; fetch writes password/TOTP atomically chmod0600 under private host directory, WAVE_EMAIL passed at process launch. Never output values, no agent reads. Replace mounted files by stable directory mount so inode replacement propagates; preserve good files on partial fetch failure; rotate both consistently. Full Access Token environment injection remains separate, no plaintext compose/env credentials.
Declared write fence: scripts/fetch-wave-secrets.ts, scripts/fetch-wave-secrets.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- permissions and atomicity
- partial fetch preserves good pair
- directory mount rotation visible
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- scripts/fetch-wave-secrets.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: permissions and atomicity; partial fetch preserves good pair; directory mount rotation visible. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-secret-fetch/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-secret-fetch status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-secret-fetch/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-secret-fetch-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-compose — Compose service and runtime-only secret mounts [infra]

Phase: 2; role: builder; depends on accepted reviews: p2-secret-fetch-r. Manifest rows: [118, 119, 120].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- Dockerfile
- scripts/fetch-wave-secrets.ts

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-secret-fetch-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Define wave-mcp service on approved host/port only with healthcheck, restart policy, nonroot permissions and dedicated private profile/session volume. Infisical fetch external to image; secret directory read-only bind, WAVE_PASSWORD_FILE/WAVE_TOTP_SECRET_FILE and WAVE_EMAIL references. Public token process injection not committed .env. Document GitHub-first sync without --delete and preserve server .env. Reverse-proxy route exact wave.mcp.propel.marketing/mcp only under approved operator action.
Declared write fence: compose.yaml, docs/operations/wave-deployment.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- compose config no literal secrets
- rotation mount semantics correct
- rollback instructions preserve sessions
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
docker compose config --quiet
Log actual command exits and complete output; never fabricate output. Named tests: compose config no literal secrets; rotation mount semantics correct; rollback instructions preserve sessions. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-compose/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-compose status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-compose/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-compose-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-startup — First session and expired-session deployment qualification [infra]

Phase: 2; role: builder; depends on accepted reviews: p2-compose-r. Manifest rows: [121, 122, 123].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/cli/refresh.ts
- src/client/index.ts
- src/auth/auth0-sign-in.ts

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-compose-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Use inherited refresh CLI mechanism to mint first session before serving internal tools (loadAuth otherwise fails without saved session); no fake invalidated credentials. Deployment-environment proof invalidates an approved test session, internal read triggers headless automated sign-in and retry to success without human action; measure duration, lock contention, rotated files and first boot. Visible hCaptcha/Cloudflare stops and reports manual cookie fallback, never solve. Qualification runner never prints session/password/TOTP; consumers never receive credential paths/material.
Declared write fence: scripts/qualify-wave-sign-in.ts, docs/operations/wave-session-recovery.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- fresh first boot succeeds
- expired session triggers unattended read success
- challenge gives fallback only
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/operations/wave-session-recovery.md && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: fresh first boot succeeds; expired session triggers unattended read success; challenge gives fallback only. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-startup/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-startup status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-startup/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-startup-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-security-audit — Audit hosted credential custody and HTTP failure paths [audit]

Phase: 2; role: log-auditor; depends on accepted reviews: p2-startup-r. Manifest rows: [124, 125].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- compose.yaml
- src/transports/http.ts
- scripts/fetch-wave-secrets.ts

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-startup-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Read-only security/log/silent-failure assessment: image contents, mounted file ownership, Infisical grant scope and atomic rotation, no consumer secret read path, auth/session/origin/rate/input limits, ambiguous writes not replayed, no diagnostic credential leaks. Include actual audit advisories readback and scan of any reused fleet code. No host changes in audit.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p2-security-audit/security-audit.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- no credential consumer path
- all advisories dispositioned
- errors/logs redacted
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s .agents/runs/wave-invoicing-v2/agent-outputs/p2-security-audit/security-audit.md
Log actual command exits and complete output; never fabricate output. Named tests: no credential consumer path; all advisories dispositioned; errors/logs redacted. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-security-audit/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-security-audit status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-security-audit/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-security-audit-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-test-assess — Assess hosting integration and live sign-in coverage [test-assess]

Phase: 2; role: test-creator; depends on accepted reviews: p2-security-audit-r. Manifest rows: [126, 127].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-security-audit-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Test-creator verifies actual HTTP malicious/large payload/expired-session/consumer revocation cases, first-session preflight and secret rotation in mounted deploy layout. Docker required yes; external Wave and designated test user required for unattended proof. Missing live credentials is a blocker, not synthetic PASS. Parent registers/reviews gap tasks only.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p2-test-assess/coverage-assessment.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- real deployed auth tests planned
- cold and expired sign-in covered
- canary leak checks complete
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s .agents/runs/wave-invoicing-v2/agent-outputs/p2-test-assess/coverage-assessment.md
Log actual command exits and complete output; never fabricate output. Named tests: real deployed auth tests planned; cold and expired sign-in covered; canary leak checks complete. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-test-assess/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-test-assess status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-test-assess/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-test-assess-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-live-qualification — Deploy only after approval and prove hosted endpoint [live]

Phase: 2; role: live-runner; depends on accepted reviews: p2-test-assess-r. Manifest rows: [128, 129].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- docs/operations/wave-deployment.md
- docs/planning/v2/HOSTING-AUTHORIZATION.md

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-test-assess-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Parent/operator deploys only pushed reviewed commit and exact granted service; do not restart gateway/shared fleet. Real endpoint initialize/list/call verifies consumer credential, wrong/revoked token rejection, no-Origin vs allowlisted browser origin, expired internal-session auto-sign-in, read-only default, secrets unreachable. Record commit/image/service IDs and redacted logs/readbacks plus rollback outcome if needed. No success if live sign-in unproven.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p2-live-qualification/deployment-receipt.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- endpoint live readback
- auto-sign-in in deployment environment
- consumer revocation exercised
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s .agents/runs/wave-invoicing-v2/agent-outputs/p2-live-qualification/deployment-receipt.md
Log actual command exits and complete output; never fabricate output. Named tests: endpoint live readback; auto-sign-in in deployment environment; consumer revocation exercised. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-live-qualification/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-live-qualification status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-live-qualification/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-live-qualification-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p2-triage — Hosting round triage and acceptance handoff [audit]

Phase: 2; role: planner; depends on accepted reviews: p2-live-qualification-r. Manifest rows: [130, 131].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-live-qualification-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Triage all hosting findings, retain failures, verify deployment authority and real endpoint/expired-session evidence. No security exception by omission. Handoff with exact endpoint/commit and consumer reconnection instructions; get Coordinator audit before real acceptance.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p2-triage/triage-report.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- all hosting findings dispositioned
- no unproven sign-in hidden
- consumer handoff complete
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s .agents/runs/wave-invoicing-v2/agent-outputs/p2-triage/triage-report.md
Log actual command exits and complete output; never fabricate output. Named tests: all hosting findings dispositioned; no unproven sign-in hidden; consumer handoff complete. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p2-triage/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p2-triage status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p2-triage/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p2-triage-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p3-roster — Define expected recurring roster contract [contract]

Phase: 3; role: builder; depends on accepted reviews: p2-triage-r. Manifest rows: [132, 133, 134].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- docs/planning/v2/IMPLEMENTATION-PREREQUISITES.md

## CURRENT STATE
PRD v2 governs. Phase 3. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p2-triage-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
RecurringRosterEntrySchema {clientName:string,service:CarePlan|SEO,expectedCadence:string,waveCustomerId?:string,expectedProductIds:string[]}; derive type. parseRecurringRoster(raw:unknown):RecurringRosterEntry[] validates authoritative source with source reference/retrievedAt and ambiguity reporting; no invented roster or fuzzy auto-write. One client may have both services. No narrow row cap, full source traversal completeness.
Declared write fence: src/workflows/recurring-roster.ts, src/workflows/recurring-roster.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- dual-service client retained
- ambiguous identity flagged
- incomplete roster rejected
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/workflows/recurring-roster.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: dual-service client retained; ambiguous identity flagged; incomplete roster rejected. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p3-roster/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p3-roster status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p3-roster/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p3-roster-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p3-audit-workflow — Classify missing recurring coverage [service]

Phase: 3; role: builder; depends on accepted reviews: p3-roster-r. Manifest rows: [135, 136, 137].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/workflows/recurring-roster.ts
- src/tools/recurring-invoices.ts

## CURRENT STATE
PRD v2 governs. Phase 3. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p3-roster-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
RecurringAuditEntrySchema {clientName,service,classification:covered|paused/ended|missing|unmatched,gap:string|null,sourceIds:string[]}; derive exact report type. auditRecurring(roster,customers,products,recurring):RecurringAuditEntry[] uses explicit IDs first, exact normalized unambiguous matches otherwise; wrong product/cadence is missing coverage with precise reason, not covered. Internal recurring facts only, never invoice-history inference. Refuse incomplete/expired source as unproven rather than false missing. No mutation.
Declared write fence: src/workflows/audit-recurring.ts, src/workflows/audit-recurring.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- paused vs never-created distinct
- wrong products gap explicit
- unmatched no fabricated customer
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/workflows/audit-recurring.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: paused vs never-created distinct; wrong products gap explicit; unmatched no fabricated customer. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p3-audit-workflow/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p3-audit-workflow status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p3-audit-workflow/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p3-audit-workflow-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p3-report — Render exceptions-only named audit report [service]

Phase: 3; role: builder; depends on accepted reviews: p3-audit-workflow-r. Manifest rows: [138, 139, 140].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/workflows/audit-recurring.ts

## CURRENT STATE
PRD v2 governs. Phase 3. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p3-audit-workflow-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
renderRecurringAudit(entries,provenance):string summarizes covered counts only; every missing/paused/unmatched exception by client name, expected service/cadence and exact gap. Include data freshness/completeness and source refs, manual recurring-write/processor-refund/true-credit residual. No individually listed covered clients, no silent truncation, pagination/attachment if response budget exceeded.
Declared write fence: src/workflows/render-recurring-audit.ts, src/workflows/render-recurring-audit.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- covered summary only
- all exceptions by name
- large roster no dropped exceptions
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/workflows/render-recurring-audit.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: covered summary only; all exceptions by name; large roster no dropped exceptions. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p3-report/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p3-report status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p3-report/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p3-report-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p3-consumer-acceptance — Coordinator live tool acceptance and first audit [live]

Phase: 3; role: live-runner; depends on accepted reviews: p3-report-r. Manifest rows: [141, 142, 143].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- docs/operations/wave-session-recovery.md
- src/workflows/render-recurring-audit.ts

## CURRENT STATE
PRD v2 governs. Phase 3. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p3-report-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Coordinator consumes hosted tools in own Muse session on real Wave work, then runs FR7 workflow once using approved real roster. Read proofs real account; write proofs only designated test customer/business and explicit approved action confirmation. Expire session and prove unattended recovery in deployed environment. Record assessed/changed/unchanged/unproven residuals, deny unsupported processor refunds/recurring writes. No simulated acceptance or self-approval by builder.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p3-consumer-acceptance/acceptance-receipt.md, docs/reports/recurring-audit-v1.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- consumer-owned live proof
- real roster report
- residuals explicit
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/reports/recurring-audit-v1.md
Log actual command exits and complete output; never fabricate output. Named tests: consumer-owned live proof; real roster report; residuals explicit. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p3-consumer-acceptance/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p3-consumer-acceptance status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p3-consumer-acceptance/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p3-consumer-acceptance-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p3-test-assess — Final acceptance coverage assessment [test-assess]

Phase: 3; role: test-creator; depends on accepted reviews: p3-consumer-acceptance-r. Manifest rows: [144, 145].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 3. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p3-consumer-acceptance-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Test-creator reconciles all FR1–7, v2 auth and policy/codegen/deploy/live evidence, tests versus actual tool catalog, large multi-page roster and report completeness, independent consumer receipt. No synthetic proof for external live cells. Any missing required case blocks final clean triage.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p3-test-assess/coverage-assessment.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- FR matrix closed
- live proof current
- all residuals recorded
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s .agents/runs/wave-invoicing-v2/agent-outputs/p3-test-assess/coverage-assessment.md
Log actual command exits and complete output; never fabricate output. Named tests: FR matrix closed; live proof current; all residuals recorded. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p3-test-assess/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p3-test-assess status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p3-test-assess/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p3-test-assess-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p3-test-run — Final regression and workflow qualification [test]

Phase: 3; role: tester; depends on accepted reviews: p3-test-assess-r. Manifest rows: [146, 147].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 3. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p3-test-assess-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Tester executes complete unit/integration/contract and codegen/typecheck against exact frozen candidate, verifies inherited486 and added cases with no silent skips, audit golden outputs and real endpoint evidence. Conditional test-resolver after FAIL/PARTIAL only; source/security defects stop for Coordinator disposition. This is the mandatory final test pipeline for v1.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p3-test-run/test-results.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- full suite green
- case identities reconciled
- workflow complete
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test && npm run typecheck && npm run codegen:check
Log actual command exits and complete output; never fabricate output. Named tests: full suite green; case identities reconciled; workflow complete. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p3-test-run/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p3-test-run status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p3-test-run/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p3-test-run-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p3-triage — v1 final debt triage and cold handover [audit]

Phase: 3; role: planner; depends on accepted reviews: p3-test-run-r. Manifest rows: [148, 149, 150].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase 3. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p3-test-run-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Triage every finding, audit signal, test resolver outcome and unresolved OQ. Handover build/run/Infisical references/rotation/revocation/challenge fallback and production pins in project Memory Bank, no credentials. v1 acceptance is at this milestone, separate from optional research. No claim recurring writes or customer-credit balance exists. Final triage must include npm audit and limits compliance readback.
Declared write fence: .agents/runs/wave-invoicing-v2/agent-outputs/p3-triage/triage-report.md, docs/operations/wave-handover.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- cold engineer takeover possible
- v1 residuals exact
- Coordinator acceptance attached
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/operations/wave-handover.md
Log actual command exits and complete output; never fabricate output. Named tests: cold engineer takeover possible; v1 residuals exact; Coordinator acceptance attached. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p3-triage/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p3-triage status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p3-triage/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p3-triage-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### s1-authority — Recurring-write test-business research authorization [contract]

Phase: S1; role: planner; depends on accepted reviews: p3-triage-r. Manifest rows: [151, 152].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase S1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p3-triage-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
EXTERNAL GATE: Coordinator grants separately scheduled optional post-v1 research and exact test-business/identity/write-cleanup scope. No worker invents authorization. Research not a v1 release dependency. No credentials in artifacts.
Declared write fence: docs/planning/v2/S1-AUTHORIZATION.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- separate research grant
- test target explicit
- cleanup authority explicit
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/planning/v2/S1-AUTHORIZATION.md
Log actual command exits and complete output; never fabricate output. Named tests: separate research grant; test target explicit; cleanup authority explicit. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/s1-authority/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=s1-authority status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/s1-authority/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: s1-authority-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### s1-research — Recurring-write test-business research [live]

Phase: S1; role: live-runner; depends on accepted reviews: s1-authority-r. Manifest rows: [153, 154].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- docs/planning/v2/S1-AUTHORIZATION.md

## CURRENT STATE
PRD v2 governs. Phase S1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: s1-authority-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Capture actual Wave web app create/edit/stop operations with human-approved test-business access. Prove create/readback/stop/readback and safe cleanup; capture error/concurrency/schedule semantics. No known route is promised. Record success or disproven/unproven evidence without publishing session material; no feature implementation, API bypass or production recurring writes. Successful promotion requires new PRD folder plus new audited implementation plan.
Declared write fence: docs/research/S1-RESULTS.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- test-business-only execution
- exact readback evidence
- no promotion without PRD revision
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/research/S1-RESULTS.md
Log actual command exits and complete output; never fabricate output. Named tests: test-business-only execution; exact readback evidence; no promotion without PRD revision. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/s1-research/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=s1-research status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/s1-research/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: s1-research-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### s2-authority — Customer-credit BETA test-business research authorization [contract]

Phase: S2; role: planner; depends on accepted reviews: p3-triage-r. Manifest rows: [155, 156].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md

## CURRENT STATE
PRD v2 governs. Phase S2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p3-triage-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
EXTERNAL GATE: Coordinator grants separately scheduled optional post-v1 research and exact test-business/identity/write-cleanup scope. No worker invents authorization. Research not a v1 release dependency. No credentials in artifacts.
Declared write fence: docs/planning/v2/S2-AUTHORIZATION.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- separate research grant
- test target explicit
- cleanup authority explicit
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/planning/v2/S2-AUTHORIZATION.md
Log actual command exits and complete output; never fabricate output. Named tests: separate research grant; test target explicit; cleanup authority explicit. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/s2-authority/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=s2-authority status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/s2-authority/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: s2-authority-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### s2-research — Customer-credit BETA test-business research [live]

Phase: S2; role: live-runner; depends on accepted reviews: s2-authority-r. Manifest rows: [157, 158].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- docs/planning/v2/S2-AUTHORIZATION.md

## CURRENT STATE
PRD v2 governs. Phase S2. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: s2-authority-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Verify official moneyTransactionCreate BETA candidate against Customer Credits account on approved test business. Prove accounting balance/readback and cleanup, distinguish manual-record reversal, next-invoice discount and processor refund. No positive result from schema existence alone. Record success/disproof/unproven; no promoted tool until new PRD and written plan audit.
Declared write fence: docs/research/S2-RESULTS.md. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- test-business-only execution
- exact readback evidence
- no promotion without PRD revision
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
test -s docs/research/S2-RESULTS.md
Log actual command exits and complete output; never fabricate output. Named tests: test-business-only execution; exact readback evidence; no promotion without PRD revision. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/s2-research/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=s2-research status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/s2-research/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: s2-research-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-signin-budget — Give automated browser sign-in generous time budget [service]

Phase: 1; role: builder; depends on accepted reviews: p1-prerequisites-r. Manifest rows: [159, 160, 161].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/auth/playwright.ts
- src/auth/refresh-session.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-prerequisites-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Apply L10/L11/D03: five-minute total sign-in deadline and explicit remaining-budget navigation/actions rather than implicit30s browser defaults. Keep TOTP30s/5s margin, two-code rejection cap,500ms observation and60ms key delay; best-effort trust clicks3s. Sanitize diagnostics before widening optional detail; preserve clear challenge refusal, never CAPTCHA solve. No credential values in widened error outputs.
Declared write fence: src/auth/auth0-sign-in.ts, src/auth/auth0-sign-in.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- slow but valid sign-in within5min
- challenge stops immediately
- redacted error diagnostics
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/auth/auth0-sign-in.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: slow but valid sign-in within5min; challenge stops immediately; redacted error diagnostics. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-signin-budget/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-signin-budget status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-signin-budget/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-signin-budget-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-lock-budget — Align sign-in profile lock with browser budget [service]

Phase: 1; role: builder; depends on accepted reviews: p1-signin-budget-r. Manifest rows: [162, 163, 164].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/auth/auth0-sign-in.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-signin-budget-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Apply L13: wait10min and stale15min while retaining1s polling. Verify positive owner/death or equivalent safe freshness before breaking a still-live browser lock; do not merely enlarge TTL and claim safe mutual exclusion. Bound total queue + login + read within20min tool action; return explicit blocked error at deadline.
Declared write fence: src/auth/profile-lock.ts, src/auth/profile-lock.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- live owner not stolen
- dead stale owner recoverable
- wait deadline explicit
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/auth/profile-lock.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: live owner not stolen; dead stale owner recoverable; wait deadline explicit. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-lock-budget/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-lock-budget status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-lock-budget/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-lock-budget-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-live-budget — Align live qualification timeout configuration [config]

Phase: 1; role: builder; depends on accepted reviews: p1-lock-budget-r. Manifest rows: [165, 166].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- vitest.config.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-lock-budget-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Apply L15/N11: set live testTimeout/hookTimeout to1200000ms for browser expiry/lock workflow, retain unit defaults and modes. No test skips or assertion changes. Future integration/qualification must set actual total budgets explicitly; do not let a30s hook invalidate the5min sign-in plan.
Declared write fence: vitest.live.config.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- live budget20min
- unit baseline unchanged
- mode guards preserved
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm run typecheck && npm test
Log actual command exits and complete output; never fabricate output. Named tests: live budget20min; unit baseline unchanged; mode guards preserved. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-live-budget/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-live-budget status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-live-budget/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-live-budget-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

### p1-error-detail — Preserve structured Wave errors and safe excerpts [service]

Phase: 1; role: builder; depends on accepted reviews: p1-write-audit-r. Manifest rows: [167, 168, 169].

## READ FIRST
- .agents/runs/wave-invoicing-v2/AGENT_SYSTEM.md
- .agents/runs/wave-invoicing-v2/spec/universal-spec.md
- docs/planning/v2/PRD.md
- src/auth/auth0-sign-in.ts

## CURRENT STATE
PRD v2 governs. Phase 1. Foundation baseline486/486, typecheck clean, no product changes at plan authorship. Prerequisite reviews: p1-write-audit-r. Parent owns every ADW mutation; this task is not authorization to cross the external audit/deployment/research gate.

## WORK ITEMS
Apply L10/N09: structured Wave inputErrors retained independently of optional body excerpt; safe summary1024chars with explicit truncation metadata, redacted optional detail up to64KiB and full-evidence reference for excess. Never raw auth page/credential material in error. Inherited string error compatibility preserved where safe; new public boundary errors include stable codes and next action.
Declared write fence: src/client/errors.ts, src/client/errors.test.ts. No product files outside this set; stop/replan before adding another file. Reuse local foundation patterns, generated schema contracts and co-located tests; no generic abstraction or copied third-party code without recorded scan.

## ACCEPTANCE CRITERIA
- many inputErrors retained
- oversize safe detail explicit
- secret canaries never emitted
- Review all policy/business/credential/limits constraints in governing spec.
- Do not treat a source grep or mock as live acceptance.

## VERIFICATION
npm test -- src/client/errors.test.ts && npm run typecheck
Log actual command exits and complete output; never fabricate output. Named tests: many inputErrors retained; oversize safe detail explicit; secret canaries never emitted. Test failure or new ambiguity stops for parent disposition.

## OUTPUT LOCATION
.agents/runs/wave-invoicing-v2/agent-outputs/p1-error-detail/build-summary.md; include actual read/mutation manifest, test receipts, discovered-context and self-audit returned to parent. Reports ending in PASS must be supported by execution where required.

## TASK MANAGEMENT
Parent alone runs tasks.ts get/start/log-read/log-mutation/complete and runner, persists artifacts and commits. Codex leaf never orchestrates or touches .agents/data, registry or another task. Return required context/self-audit to parent. End final return with ORCHESTRATOR_SIGNAL: DONE task=p1-error-detail status=COMPLETE output=.agents/runs/wave-invoicing-v2/agent-outputs/p1-error-detail/build-summary.md next=continue. BLOCKED/FAIL return original evidence and stop; do not loop to green beyond authority.

Paired independent review: p1-error-detail-r; reviews actual full changed modules and all declared acceptance cases; STATUS: FAIL stops.

## 4. Phase Structure

0 Foundation: setup performed by parent; pending p0-audit-gate preserves external written audit.
1 Feature + cross-cutting safety: authoritative public tools, policy/confirmation, draft discipline/manual payments, internal contacts/recurring, automatic secret-file session lifecycle; p1 error audit → test assessment → full test run → triage and Coordinator audit.
2 Feature hosting: independent authority gate → consumer auth → HTTP → browser image → Infisical fetch → compose → startup qualification → security audit → test assessment → real deployment qualification → triage. Deployment only inside future grant.
3 Feature acceptance/audit: roster → classify → exceptions-only render → consumer-owned real acceptance → final assessment/test pipeline → v1 triage/handover.
S1/S2 optional post-v1 research: independent authorizations after Phase3, each research/report plus review. Not v1 release dependencies; they gate only whole-program final-triage. Success never silently adds a tool: revise PRD in new folder and obtain new audit approval.

Each named section has a paired read-only review; consumers depend on reviews, not builder completion. Conditional test-resolver after FAIL/PARTIAL limited to tests; source defects require parent disposition. Test-creator gap tasks created by parent and paired review, no bypass. Final clean triage waits for all scheduled research dispositions; v1 delivery separately at p3-triage-r. All tasks are execute descendants. No execute invocation during this setup.

## 5. Constraints

Security/data integrity and issued PRD outrank ADW default preferences. Retain inherited module style, no blanket conversion to new classes/interfaces; new boundaries named explicitly in sections. GraphQL input/output shapes derive from committed official schema, not guessed before schema retrieval. Other schemas derive z.infer types. This deliberately defers generated field declarations to p1-schema instead of inventing API fields now. Schema-mapping failure is a hold, not permission to implement unsupported tools.

Public tool names are the exact30 v2 section5 entries (10read+10write+6gated+4internal); estimates v1.1 excluded. Consumer/business/tool/input/snapshot/expiry bound confirmation; single-use and at-most-once local admission, not an exactly-once network delivery claim. No credential plaintext in source, chat, logs, managed records or consumer paths. Written host/identity/research grants required. No gateway restart or changes to other repos/fleet config in Phase0. No runtime state DB in Git. Filed PRDs never edited; future revisions new versioned folders.

## 6. Limits

LIMITS.md in this plan is normative for every inherited/planned bound and justification. numeric-census.json is a reproducible source-line candidate inventory, not a claim every numeral is a cap. Protocol copy and digests in plan evidence; dependency implementation defaults are assessed when adopting/updating dependency, not silently treated as hard product caps. No numeric product changes made in Phase0.
