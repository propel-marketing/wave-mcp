# Wave Invoicing MCP — Product Requirements Document

| | |
|---|---|
| Version | **v2** |
| Date | 2026-11-07 |
| Author | Benny (Coordinator), from the CEO's requirements of 2026-11-07 |
| Status | Approved for project setup; implementation gated on the Coordinator's audit of the ADW plan |
| Supersedes | v1 (filed unchanged alongside this version) |
| Changes in v2 | Internal-API authentication: **automated sign-in with Infisical-stored credentials is now the default** (CEO decision 2026-11-07; formerly open question OQ-2, now closed). Cookie-only enrollment (v1's default) is retained as the fallback if automated sign-in is blocked. §2 N5 removed, §7 rewritten, §10–§13 updated accordingly. |
| Repo | `propel-marketing/wave-mcp` (fork of LunaParker/waveapps-mcp, MIT) |
| Evidence base | `AUDIT-2026-11-07.md`, `SCOPE-CHECK-2026-11-07.md`, `RECOMMENDATION.md` (project research files, 2026-11-07) |

**Revision rule (CEO, 2026-11-07):** this plan lives at `docs/planning/v1/`. Any change to the plan is made as a *revised PRD in a new versioned folder* (`docs/planning/v2/`, `v3/`, …). Prior versions are never edited in place — the folder sequence is the change history.

---

## 1. Purpose

Propel bills its clients through Wave (Waveapps). Today every billing action is manual work in the Wave web UI, and there is no reliable way to verify that every recurring-revenue client actually has the recurring billing they should. This MCP gives Propel's agents a tested, gated tool surface over Wave so that:

1. Routine invoicing work (customers, invoices, products, payments) can be done programmatically, with safety gates on the actions that send or move money.
2. The gaps the public Wave API cannot see — additional customer contacts and recurring invoice state — are covered through Wave's internal API, which a proven open-source foundation has already mapped and tested.
3. A recurring-revenue audit can compare the clients who *should* have recurring billing (Care Plans + SEO) against the recurring invoices that *actually* exist in Wave, on facts rather than inference.

## 2. Goals and non-goals

**Goals**
- G1. One MCP server covering the CEO's seven requested functions (§4) to the extent Wave's APIs permit, with every limitation stated explicitly rather than papered over.
- G2. Built on a tested foundation (the LunaParker codebase: 486 tests, 485 passing verified 2026-11-07) — no reinventing of the internal-API mapping, session auth, or test workflow.
- G3. Fleet-standard operation: hosted on propel-mcp-server beside the sibling MCPs, credentials in Infisical, per-consumer authentication, GitHub repo as source of truth.
- G4. Safety model appropriate to a money surface: read-only by default policy, explicit confirmation for send/approve/payment actions, server pinned to Propel's Wave business.

**Non-goals (v1)**
- N1. Creating, editing, or stopping recurring invoices programmatically — no API route exists anywhere; sequenced as a research spike (§11, S1), not a v1 commitment.
- N2. Refunding Wave Payments card/bank payments — no API route exists; stays in the Wave UI permanently unless Wave ships one.
- N3. Multi-business / third-party OAuth access (Wave's post-2025 Pro subscription gate makes it the wrong default); v1 serves Propel's own Wave account only.
- N4. Bills/vendor payments, financial reporting, payroll — outside the requested scope (and, for bills/reports, not exposed by the public API at all).
- N5. Storing Propel's Wave credentials anywhere other than Infisical and the Infisical-fed secret-file mechanism (§7) — never in the repo, never in an agent session, never in plaintext server config.

## 3. Users and consumers

- **Primary consumer (v1):** the Coordinator (Benny) — billing operations and the recurring-revenue audit, from Muse.
- **Secondary consumers (post-v1, by CEO decision):** Hermes agents via the hosted endpoint, each with its own consumer credential. No agent receives Wave credentials; consumers authenticate to the MCP only.
- **Humans** continue to use the Wave UI for the actions reserved to it (§4, FR-6/FR-7 residuals).

## 4. Functional requirements

Priorities: **v1** = in the first release; **spike** = research-gated (§11); **UI** = remains manual permanently.

### FR-1 — Find customers (v1)
- List and search customers on Propel's business, including by email; return full customer detail (principal contact, address, shipping address, currency, archived state, balances where Wave exposes them).
- Source: public API (`business.customers`) and internal API both satisfy this; the public client is authoritative once built (§6).

### FR-2 — Create and edit customers, including additional contacts (v1)
- Create, patch, and delete customers (principal contact, addresses, currency) via the public API.
- **Additional contacts** (name/email per contact) via the internal API — the public schema has no such field. Required behaviours, established by the scope check and the foundation codebase:
  - An internal update *replaces the entire contact list*: every write is read-modify-write, never a blind partial send.
  - Omitting a contact's fields deletes it (sending `{id}` alone); the tool must surface this, not hide it.
  - A customer update that omits address/shipping data clears it server-side; the tool reads and re-sends existing values when the caller did not intend a change.
- Per-send workaround also exposed: invoice send accepts an explicit recipient list, so a one-off recipient (e.g. an added stakeholder at a client) can receive a specific invoice without altering the customer record.

### FR-3 — Create one-time invoices and set taxes (v1)
- Create invoices in **draft** state only; edit drafts; clone; delete drafts.
- Line items reference products or are free-form; **per-line-item sales taxes** are supported, and a product's default sales taxes are applied when the item references that product.
- Lifecycle actions — approve, send, mark-sent — are *gated* actions (§8): preview first, explicit confirmation to execute.

### FR-4 — Recurring invoices
- **Read (v1):** list and get recurring invoices via the internal API: state (active/paused/ended), customer, currency, total, payment terms, first/previous/next scheduled dates, count generated, line items with product and taxes, schedule/delivery settings. This is the data source for FR-7.
- **Create / edit / stop (spike S1, §11):** capture and prove the internal mutations the Wave web app itself uses, on a test business. Ships only if proven; otherwise these stay in the Wave UI and FR-7's report flags the exact items needing manual action.

### FR-5 — Add or edit products (v1)
- Create, patch, archive products/services (name, description, unit price, sold/bought flags, default sales taxes) via the public API.

### FR-6 — Refunds and customer credit (v1 partial; residuals permanent)
- Record, patch, and delete **manually recorded payments** on an invoice (public API) — this reverses the accounting record of an offline refund or an erroneous entry. It does not move money.
- Apply **credit toward future invoices** as a discount/write-down line on the customer's next invoice (v1 mechanism).
- **Spike S2 (§11):** test posting a true customer-credit balance via the public API's BETA money-transaction creation against the Customer Credits account, on a test business. Promoted to a tool only if proven end-to-end.
- **Permanent residual (UI):** refunding an actual Wave Payments card/bank charge. No mutation exists in either API; refunds appear in Wave only as records created by Wave's own payments flow.

### FR-7 — Care Plan + SEO missing-recurring audit (v1)
- Inputs: (a) the expected recurring-client roster — client, service (Care Plan / SEO), expected cadence — from Propel's client records (Freedcamp / client list; exact roster source confirmed at Phase 1 start); (b) Wave recurring state from FR-4 reads; (c) Wave customer/product data for matching.
- Procedure: match roster entries to Wave customers; for each, determine whether an active recurring invoice exists whose products correspond to the expected service; classify each roster entry as **covered**, **paused/ended**, **missing**, or **unmatched** (no Wave customer found).
- Output: a per-client report — covered entries summarised; every missing/paused/unmatched entry listed by client name with the specific gap (no template, template paused, wrong products, no customer record). Completed/covered items are not listed individually (CEO reporting preference: exceptions only, by name).
- Cadence: on demand in v1; a scheduled run is a later decision.

## 5. Tool surface (v1)

Naming follows the fleet convention (`wave_*`). Tools are grouped by backing client. The policy config (§8) decides which tools a given deployment exposes; out-of-scope inherited tools ship **unexposed by default**.

**Public client (authoritative for standard operations)**
- Read: `wave_get_business`, `wave_list_customers`, `wave_get_customer`, `wave_list_invoices`, `wave_get_invoice`, `wave_list_products`, `wave_get_product`, `wave_list_sales_taxes`, `wave_list_accounts`, `wave_list_businesses` (setup/diagnostics)
- Write: `wave_create_customer`, `wave_update_customer`, `wave_delete_customer`, `wave_create_product`, `wave_update_product`, `wave_archive_product`, `wave_create_invoice` (draft), `wave_update_invoice` (draft), `wave_clone_invoice`, `wave_delete_invoice` (draft)
- Gated: `wave_approve_invoice`, `wave_send_invoice`, `wave_mark_invoice_sent`, `wave_record_payment`, `wave_update_payment`, `wave_delete_payment`
- Estimates (v1.1): list/get/create/approve/send/convert-to-invoice, operations ported only after schema verification.

**Internal client (blind spots only)**
- `wave_list_customer_contacts`, `wave_set_customer_contacts` (read-modify-write per FR-2 rules; gated)
- `wave_list_recurring_invoices`, `wave_get_recurring_invoice`

**Inherited from the foundation, unexposed by default:** bills, receipts, customer statements, PDF/report export, and other internal-API tools outside §4. They remain in the codebase (tested) and can be enabled by policy if a future PRD revision brings them into scope.

## 6. Architecture

- **Base:** fork of LunaParker/waveapps-mcp (MIT; license and attribution retained). Its layering is the project model: `src/client` (API clients), `src/auth` (session lifecycle), `src/tools` (one module per domain, tests co-located), `src/transports` (stdio + HTTP), `src/cli` (operator commands), `src/util`.
- **Two clients, one server:**
  - *Internal client* (inherited): Wave internal GraphQL + REST surfaces, session-cookie auth.
  - *Public client* (new): Wave public GraphQL (`https://gql.waveapps.com/graphql/public`), Full Access Token auth. Operations are **generated from the public schema** (GraphQL codegen, the rhanka pattern) so tool operations cannot silently drift from Wave's schema; the generated SDK is produced by a documented build step and verified in CI-equivalent local checks.
  - Where both clients can serve an operation, the public client is authoritative; the internal client serves FR-2 contacts and FR-4 reads.
- **Server pinning:** the server is configured with Propel's Wave business ID at deploy time and rejects operations against any other business (the foundation's and sibling MCPs' single-business pattern), regardless of what a caller passes.
- **Errors:** Wave GraphQL `inputErrors` and HTTP/auth failures are surfaced as structured tool errors with Wave's own codes/messages preserved — never collapsed into a generic failure, never retried blindly on writes.

## 7. Authentication and credential custody

- **Public API:** Full Access Token, created once by the CEO in Wave's developer portal (the one-time owner grant). Stored in Infisical (service-credentials, `/wave`), injected into the server process environment at runtime only. Never in the repo, never in logs, never in any agent session. Revocation/rotation happens in the developer portal + Infisical, independent of any human's Wave login.
- **Internal API:** automated sign-in, with credentials in Infisical (CEO decision 2026-11-07). The sign-in identity is a **dedicated Wave automation user** on Propel's business (own email, password, and TOTP-based 2FA) — not the CEO's personal login — so custody is boundable and revocable independently. The login is enrolled as a standard login item in Infisical **agent-logins** (v2 addressing; keys `LOGIN_IDENTIFIER` / `LOGIN_PASSWORD` / `LOGIN_TOTP_SECRET`); enrollment of the values is a one-time human action. Delivery: a server-side fetch writes the password and TOTP secret to the foundation's secret files (`WAVE_PASSWORD_FILE` / `WAVE_TOTP_SECRET_FILE`, chmod 600) mounted into the container, with `WAVE_EMAIL` set; the foundation re-reads the files on every use, so rotation = re-enroll in Infisical + replace the files, no code change and no restart. Behaviour (foundation-implemented and tested): when a tool call finds the session expired (sessions end ≤ ~18h, or after ~8h idle), the server signs in headlessly — email, password, TOTP code generated from the stored secret, "trust this device for 30 days" — saves the new session, and **retries the original call automatically** (~15–30s). The first session is established the same way at deploy time. No agent or consumer ever sees or handles these credentials.
  - **Fallback:** if Wave blocks automated sign-in (visible hCaptcha / Cloudflare), sign-in stops and the tool error instructs a manual cookie enrollment (the v1 mechanism: human signs in in a browser, session enrolled via the foundation CLI). Manual enrollment is a fallback procedure, not the operating mode.
  - **Recorded trade-off:** storing the password and the TOTP secret together means the vault + the MCP host together can sign in as the automation user — 2FA's separation is deliberately traded for unattended operation (CEO decision). The dedicated user bounds the blast radius: it is not the CEO's login, its access is limited to what Wave grants that user on Propel's business, and revoking it (password change / user removal) kills the automation without touching anyone else's access. Wave may send "new sign-in" notifications to that user; they are expected noise.
- **Consumers:** authenticate to the MCP with per-consumer credentials (bearer tokens, sibling-MCP pattern); the MCP holds the Wave credentials centrally. A compromised consumer credential exposes the tool surface only, never the Wave credentials, and is revocable independently.

## 8. Safety model

- **Policy config** (original implementation, kcrosby pattern): a server-side JSON policy lists each tool as allow/deny with a read / write / destructive tier. **Default posture: read-only.** Write tiers are enabled per deployment, deliberately. Unknown tool names in policy are a startup error, not silently ignored.
- **Confirm gate** (yoyodyne pattern, ported): gated tools (§5) run in two steps — a preview call returns the full action summary plus a fingerprint of (tool, target snapshot, inputs); execution requires the caller to return that fingerprint with an explicit confirm. A changed target invalidates the fingerprint. No gated action executes on a single call.
- **Draft discipline:** invoice creation/editing tools cannot emit a non-draft invoice; sending is only possible through the gated send path.
- **Audit trail:** the server logs every write call (tool, target IDs, caller identity, result) with no credential or session material in the log.
- **Limits:** per the fleet Generous Limits protocol — payload, page-size, timeout, and history limits are sized amply for real billing work; any tight limit in the inherited code or new code is inventoried in the plan and either raised or justified in writing.

## 9. Hosting and deployment

- **Development:** the Coding Agent's environment on the hermes host, checkout under the standard projects root (`/home/propel/projects/cypher/wave-mcp/`).
- **Production:** propel-mcp-server, a separate checkout, Docker compose service `wave-mcp`, host port bound like the sibling MCPs, public route `https://wave.mcp.propel.marketing/mcp` (Streamable HTTP).
- **Flow:** GitHub is the source of truth — changes are pushed to `propel-marketing/wave-mcp` before any deployment; the server checkout is then synced (never with `--delete`; the server-local `.env` is never overwritten) and the container rebuilt.
- **ADW:** the core Propel-ADW is installed in the repo at bootstrap (`.agents/`), owned by the Coding Agent's parent session per the fleet execution model. ADW is development machinery only; it is not part of the deployed image's runtime.

## 10. Testing and acceptance

- **Inherited baseline:** the foundation suite (486 tests) must stay green; the known environment-artifact failure (a chmod assertion that cannot fail as root) is documented, not silently skipped. Typecheck clean.
- **New code:** unit tests for the public client and every new tool, co-located per the foundation pattern; codegen drift check (regenerating from the committed public schema produces no diff); policy-config tests (default read-only, deny overrides, unknown-name rejection — the guarantees §8 claims); confirm-gate tests (fingerprint invalidation on target change).
- **Live tiers** (foundation pattern): read-only live smoke against the real account; write tests only against a designated test customer / test business, never against real client records.
- **Automated sign-in proof (v2):** with the session deliberately expired/invalidated, an internal tool call must trigger headless sign-in and retry to success with no human action, in the deployment environment (not only in development) — this is a named Phase 2/3 acceptance item.
- **Acceptance (fleet protocol):** the consuming agent proves the tools in its own live session on real Wave work — Coordinator-side probes are diagnosis only. Acceptance evidence is recorded in the project record with the residual list (assessed / changed / unchanged / unproven).

## 11. Phasing and research spikes

- **Phase 0 — Setup:** fork into `propel-marketing/wave-mcp`; checkout in the Coding Agent's environment; upstream suite + typecheck baseline recorded in his environment; ADW installed; ADW plan authored from this PRD; PRD v1 filed at `docs/planning/v1/PRD.md` and this v2 at `docs/planning/v2/PRD.md`, both byte-identical to the issued documents. *Exit:* Coordinator's written audit approval of the ADW plan (the fleet audit gate — no implementation before it).
- **Phase 1 — Public client + gates:** codegen pipeline; public client; §5 public tool set; policy config; confirm gate; contacts + recurring internal tools verified against the inherited tests and re-proven live (read-only); automated sign-in enabled against the credential-file mechanism with test credentials. *Exit:* full suite green in the Coding Agent's environment; Coordinator audit of the round.
- **Phase 2 — Hosting:** HTTP transport hardening for fleet use (origin allowlist, rate limiting, per-consumer auth); compose service on propel-mcp-server — the image includes the headless browser the automated sign-in drives; Infisical wiring for the Full Access Token (after the CEO's owner grant) and for the automation-user login (server-side fetch → secret files → container mount, §7); first session established by automated sign-in at deploy. *Exit:* endpoint live, consumer auth proven, no Wave credential reachable from any consumer path, expired-session auto-sign-in proven in the deployment environment.
- **Phase 3 — Acceptance + audit v1:** Coordinator acceptance in a live session on real work; FR-7 audit implemented as a workflow on the tool surface and run once against the real roster. *Exit:* audit report delivered; residuals listed.
- **Spike S1 — Recurring writes:** capture the web app's internal create/edit/stop mutations; prove on a test business (create → verify → stop → verify). Success promotes the operations to gated tools via a PRD revision (new versioned folder). Failure leaves FR-4 writes in the UI, with the audit flagging them.
- **Spike S2 — Customer credit:** prove or disprove BETA money-transaction posting to the Customer Credits account on a test business. Success promotes a gated `wave_add_customer_credit` via PRD revision.

## 12. Risks

- **Internal API drift:** Wave can change its undocumented surfaces on any deploy. Mitigations: the internal surface is confined to FR-2/FR-4; live read tests detect breakage early; the public client carries everything else.
- **Automated sign-in fragility:** Wave watches its sign-in page (hCaptcha, device fingerprinting) and can change it without notice; automated sign-in may intermittently fail or break. Mitigations: the foundation's dedicated browser profile keeps sign-ins looking like one known device; failures surface as explicit tool errors, never silent retries; the manual cookie-enrollment fallback (§7) keeps internal tools usable while a breakage is assessed. The internal surface stays confined to FR-2/FR-4, so a sign-in breakage never touches the public-API tools.
- **Single-maintainer upstream:** the foundation is one developer's project. Mitigation: we own the fork outright (MIT); upstream is a reference, not a dependency.
- **Money-surface error:** a wrong send or payment record has real-world effect. Mitigations: §8 in full — draft discipline, confirm gate, policy tiers, audit trail.

## 13. Open questions

- OQ-1. Roster source of truth for FR-7 (Freedcamp project/list vs. a maintained client register) — confirm at Phase 1 start.
- OQ-2. **DECIDED 2026-11-07 (CEO):** automated internal-session sign-in with credentials stored in Infisical is the default (see §7). Closed in v2.
- OQ-3. Which Hermes agents, if any, become consumers after v1 — CEO decision at Phase 3.
- OQ-4. A Wave test business (or designated test customer) for write-tier live tests and both spikes — arrange at Phase 1.

## Appendix A — Scope-check summary (2026-11-07, vs. Wave's official API reference)

| Request | Public API | Internal API |
|---|---|---|
| Find customers | ✅ | ✅ |
| Create/edit customers (principal) | ✅ | ✅ |
| Additional contacts | ❌ not in schema | ✅ |
| One-time invoices + taxes | ✅ | ✅ |
| Recurring: read | ❌ (id-only stub type) | ✅ rich |
| Recurring: create/edit/stop | ❌ no mutations | ❌ none known — spike S1 |
| Products add/edit | ✅ | ✅ |
| Refund a processor payment | ❌ no mutation | ❌ — Wave UI only |
| Reverse a recorded manual payment | ✅ patch/delete | ✅ |
| Customer credit balance | ⚠️ BETA candidate — spike S2 | ❌ |
| Missing-recurring audit | ⚠️ inference only | ✅ on facts |
