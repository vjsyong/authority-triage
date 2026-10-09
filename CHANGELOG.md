# Changelog - Triage

## 0.12.2 - 2026-10-09

- Curation on `component/page-state`: added the aliases "404 page" and
  "not found page". Evidence: `gap/20261009-024914-945233` — a downstream
  consumer's everyday phrasing fell through to `fallback/scoped-embedding`
  while canonical asks resolved. The record now carries a provenance block
  (extended_in, triggering gap, review decision, tests, source commit).
- Golden set extended 56 → 58: both phrasings pin the new coverage.
- No change beyond the added alias coverage; all prior resolutions
  unchanged (non-regression verified against the prior 56 cases).
- Snapshot unchanged: triage-design-system 0.12.1 @ 97cabe5cd0.

## 0.12.1 - 2026-10-08

- Consolidated as this repository. The pack contents are byte-identical to
  the state previously published in the design-authority repository; this
  repo is now the canonical home.
- History before this point lives in `vjsyong/design-authority`
  (docs/synthesis, docs/portability, docs/evolution for the triage lines).

