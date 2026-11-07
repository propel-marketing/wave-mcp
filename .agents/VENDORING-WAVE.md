# Wave MCP — core ADW vendoring deviation

Core source pin: propel-marketing/propel-adw at 7f4a075b9b12623d1d79c045ad27f2e579c34c3f.
Authority: Coordinator BENNY-PLAN-AUDIT.md, 2026-11-07, bootstrap commit-blocker disposition.

Only two input literals differ from that pinned core:
- .agents/provenance/tests/provenance-cli.contract.test.ts:1074
- .agents/provenance/tests/provenance-redaction.test.ts:59

Each flagged synthetic bearer input is now exactly `Bearer TEST_redacted`. Assertions consume the input by variable, so no separately written expected-output echo required changing. No other fixture, assertion, implementation, test selection or guard was changed. Before a core sync, deliberately reapply these two replacements if upstream still has the incompatible marker; never blanket-rewrite credential fixtures.

Reason: the inherited Wave precommit secret guard recognizes the TEST_ marker; the original ADW synthetic marker was rejected. The guard scripts/check-secrets.mjs is unchanged. No --no-verify is permitted or used.

Qualification after the replacement, Node22.23.3:
- Exact previously selected provenance suite:41pass,0fail,0skip (identical case/status multiset to accepted baseline).
- Full ADW runtime suite:48pass,0fail,1Windows-only skip (identical case/status multiset).
- Additionally, changed provenance CLI contract file:19pass,0fail,0skip.

Parent custody: setup workdir canary-preimages.json, canary-validation.json and canary-provenance-selected.log/canary-runtime.log/canary-provenance-cli.log. Mechanical inverse reconstruction must equal each complete original file byte-for-byte; all other copied core files remain pinned. Broad automatic single-file lint diagnostics use the wrong TS defaults and were pre-existing; no fixes to unrelated config/optional embeddings were made under this disposition.
