# Wave Invoicing MCP ADW Plan — v2

Status: AWAITING WRITTEN COORDINATOR AUDIT; no implementation authorized.

Authority: docs/planning/v2/PRD.md. Historical v1 immutable. Full spec: spec/universal-spec.md. Parent-owned DB source of truth: .agents/data/tasks.db; portable source declaration: plan-registration.json. Every work section paired with independent review. Entire graph registered but no feature task started.

# Phase structure

| Phase | Task | Outcome | Prerequisite reviews | Review |
|---|---|---|---|---|
| 0 | p0-audit-gate | Written Coordinator plan audit approval | none | p0-audit-gate-r |
| 1 | p1-prerequisites | Record roster and test-business prerequisites | p0-audit-gate-r | p1-prerequisites-r |
| 1 | p1-dependency-clearance | Remediate inherited runtime advisories | p1-prerequisites-r | p1-dependency-clearance-r |
| 1 | p1-provenance-clearance | Clear development provenance zod advisory | p1-prerequisites-r | p1-provenance-clearance-r |
| 1 | p1-schema | Pin official public Wave schema | p1-prerequisites-r | p1-schema-r |
| 1 | p1-codegen-config | Install schema codegen build step | p1-schema-r, p1-dependency-clearance-r | p1-codegen-config-r |
| 1 | p1-public-operations | Declare exact public operations | p1-codegen-config-r | p1-public-operations-r |
| 1 | p1-generate-sdk | Generate typed SDK and drift CI check | p1-public-operations-r | p1-generate-sdk-r |
| 1 | p1-public-client | Build typed public GraphQL boundary | p1-generate-sdk-r | p1-public-client-r |
| 1 | p1-business-scope | Enforce pinned business and resource ownership | p1-public-client-r | p1-business-scope-r |
| 1 | p1-tool-catalog | Declare public/internal tool policy catalog | p1-business-scope-r | p1-tool-catalog-r |
| 1 | p1-policy | Parse policy with read-only deny-first defaults | p1-tool-catalog-r | p1-policy-r |
| 1 | p1-confirm | Build single-use snapshot-bound confirmation | p1-policy-r | p1-confirm-r |
| 1 | p1-write-audit | Log structured write outcomes without secrets | p1-confirm-r | p1-write-audit-r |
| 1 | p1-pagination | Centralize complete public pagination | p1-public-client-r | p1-pagination-r |
| 1 | p1-customer-reads | Public customer discovery | p1-pagination-r, p1-business-scope-r | p1-customer-reads-r |
| 1 | p1-customer-writes | Public customer CRUD | p1-customer-reads-r, p1-write-audit-r | p1-customer-writes-r |
| 1 | p1-reference-reads | Business taxes and account reference reads | p1-pagination-r, p1-business-scope-r | p1-reference-reads-r |
| 1 | p1-products | Public product discovery | p1-reference-reads-r | p1-products-r |
| 1 | p1-product-writes | Public product create patch archive | p1-products-r, p1-write-audit-r | p1-product-writes-r |
| 1 | p1-invoice-reads | Public invoice discovery | p1-pagination-r, p1-reference-reads-r | p1-invoice-reads-r |
| 1 | p1-draft-invoices | Draft invoice create and edit | p1-invoice-reads-r, p1-product-writes-r, p1-customer-writes-r | p1-draft-invoices-r |
| 1 | p1-draft-lifecycle | Draft invoice clone and delete | p1-draft-invoices-r | p1-draft-lifecycle-r |
| 1 | p1-gated-invoices | Gated invoice approve send mark-sent | p1-draft-lifecycle-r, p1-confirm-r, p1-write-audit-r | p1-gated-invoices-r |
| 1 | p1-manual-payments | Gated manual payment accounting | p1-gated-invoices-r | p1-manual-payments-r |
| 1 | p1-contacts | Safe internal contacts read modify write | p1-customer-writes-r, p1-confirm-r | p1-contacts-r |
| 1 | p1-recurring-reads | Internal recurring read verification | p1-contacts-r | p1-recurring-reads-r |
| 1 | p1-auth-lifecycle | Wire automated secret-file sign-in with safe retry | p1-recurring-reads-r, p1-live-budget-r, p1-error-detail-r | p1-auth-lifecycle-r |
| 1 | p1-limits | Remove customer search roster ceiling | p1-pagination-r | p1-limits-r |
| 1 | p1-compose | Compose public surface with policy and internal blind spots | p1-manual-payments-r, p1-contacts-r, p1-auth-lifecycle-r, p1-limits-r, p1-error-detail-r | p1-compose-r |
| 1 | p1-composition-tests | Prove real server policy and tool routing | p1-compose-r | p1-composition-tests-r |
| 1 | p1-error-audit | Audit silent failures and credential logging | p1-composition-tests-r | p1-error-audit-r |
| 1 | p1-test-assess | Assess Phase 1 contract integration and live coverage | p1-error-audit-r | p1-test-assess-r |
| 1 | p1-test-run | Run Phase 1 full regression and scoped live reads | p1-test-assess-r | p1-test-run-r |
| 1 | p1-triage | Phase 1 debt triage and Coordinator audit handoff | p1-test-run-r | p1-triage-r |
| 2 | p2-authority | Obtain hosting and identity enrollment authority | p1-triage-r | p2-authority-r |
| 2 | p2-consumers | Per-consumer bearer auth and revocation | p2-authority-r | p2-consumers-r |
| 2 | p2-http-guards | Origin rate and capacity guardrails | p2-consumers-r | p2-http-guards-r |
| 2 | p2-http-compose | Integrate authenticated HTTP transport | p2-http-guards-r | p2-http-compose-r |
| 2 | p2-image | Build runtime image with headless Chromium | p2-http-compose-r | p2-image-r |
| 2 | p2-secret-fetch | Infisical server-side fetch to secret files | p2-image-r | p2-secret-fetch-r |
| 2 | p2-compose | Compose service and runtime-only secret mounts | p2-secret-fetch-r | p2-compose-r |
| 2 | p2-startup | First session and expired-session deployment qualification | p2-compose-r | p2-startup-r |
| 2 | p2-security-audit | Audit hosted credential custody and HTTP failure paths | p2-startup-r | p2-security-audit-r |
| 2 | p2-test-assess | Assess hosting integration and live sign-in coverage | p2-security-audit-r | p2-test-assess-r |
| 2 | p2-live-qualification | Deploy only after approval and prove hosted endpoint | p2-test-assess-r | p2-live-qualification-r |
| 2 | p2-triage | Hosting round triage and acceptance handoff | p2-live-qualification-r | p2-triage-r |
| 3 | p3-roster | Define expected recurring roster contract | p2-triage-r | p3-roster-r |
| 3 | p3-audit-workflow | Classify missing recurring coverage | p3-roster-r | p3-audit-workflow-r |
| 3 | p3-report | Render exceptions-only named audit report | p3-audit-workflow-r | p3-report-r |
| 3 | p3-consumer-acceptance | Coordinator live tool acceptance and first audit | p3-report-r | p3-consumer-acceptance-r |
| 3 | p3-test-assess | Final acceptance coverage assessment | p3-consumer-acceptance-r | p3-test-assess-r |
| 3 | p3-test-run | Final regression and workflow qualification | p3-test-assess-r | p3-test-run-r |
| 3 | p3-triage | v1 final debt triage and cold handover | p3-test-run-r | p3-triage-r |
| S1 | s1-authority | Recurring-write test-business research authorization | p3-triage-r | s1-authority-r |
| S1 | s1-research | Recurring-write test-business research | s1-authority-r | s1-research-r |
| S2 | s2-authority | Customer-credit BETA test-business research authorization | p3-triage-r | s2-authority-r |
| S2 | s2-research | Customer-credit BETA test-business research | s2-authority-r | s2-research-r |
| 1 | p1-signin-budget | Give automated browser sign-in generous time budget | p1-prerequisites-r | p1-signin-budget-r |
| 1 | p1-lock-budget | Align sign-in profile lock with browser budget | p1-signin-budget-r | p1-lock-budget-r |
| 1 | p1-live-budget | Align live qualification timeout configuration | p1-lock-budget-r | p1-live-budget-r |
| 1 | p1-error-detail | Preserve structured Wave errors and safe excerpts | p1-write-audit-r | p1-error-detail-r |


Limits: LIMITS.md. Phase0 baseline and scan: docs/planning/v2/BASELINE.md and SECURITY-SCAN.md. External approval task intentionally held needs_revision; registration is not permission. Any schema/research uncertainty has an explicit proof task and cannot become guessed implementation. v1 milestone p3-triage-r independent of optional spikes; whole program final triage includes research dispositions.
