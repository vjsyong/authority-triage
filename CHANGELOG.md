# Changelog - Triage

## 0.12.3-rc1 - 2026-10-11

- Release-machinery fix found by the independent adoption test
  (`docs/experiments/08-adoption-test.md`): the declared lint validator ran
  from the pinned design-system checkout (`{snapshot}`), which is not
  public, so `da validate` errored out for every consumer while printing a
  vacuous score. The pack now ships a self-contained lint
  bundle (`lint/`, `spec/rules.json`, `tokens/tokens.json`,
  `rename-map.json`, `core/`, `VERSION`) and `validators.json` runs it with
  `workdir {pack}`; `da validate` works from a bare clone with no external
  checkout. The plugin/emitter (`docs/synthesis/triage/tools/
  build_triage_pack.py`) ships the bundle on every regeneration, and the
  drift gate covers it (16 files + `core/`).
- Records unchanged; all prior resolutions and goldens unchanged.
- Triggering gaps (consumer workspace, adoption run x06):
  `gap/20261011-100129-4b5013` (triage-lint validator unavailable to
  consumers) and `gap/20261011-101032-9ed1d0` (verification contract absent
  from the triage pack; the contract work remains queued).
- rc label per release policy: agent-produced bump, awaiting owner
  finalization.

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

