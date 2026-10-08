# Triage - authority repo

Version: **0.12.1** (tag `v0.12.1`) - format 0.1

Triage is the app-agnostic, paper-and-ink UI design authority: one token source of truth, one component runtime, one enforceable lint gate. Square corners, hairline rules, ink-on-paper surfaces, two themes (light/dark), two densities, a 35-component contract matrix, and a binding interaction standard. Dependency-free: plain CSS tokens, a small behaviour layer that degrades without JS, and generated artifacts.

This repository owns everything for this authority: the pack (records at the
repo root: authority.json, artifacts.json, rules, prohibitions, fallbacks,
recipes, golden set, verification contract).


## Use it

Point a coding agent at the brief (one line):

    Fetch https://designauthority.seanyong.xyz/authorities/triage/site/agent-brief.md
    and follow it to build my app under the Triage authority.

Or use the CLI directly (the kernel lives in the public design-authority repo):

    git clone --depth 1 https://github.com/vjsyong/design-authority.git
    python3 design-authority/tools/da.py --pack . resolve "primary button" --json

## CI

Every push runs `.github/workflows/ci.yml`: pack parses, golden agreement,
site manifest verification and the generated-chrome traceability gate (the
last two when this authority ships a site).

## Versioning and rollback

Versions live in `authority.json` and are tagged in git (`v0.12.1`).
`CHANGELOG.md` records each bump. To roll back:

    git checkout v0.12.1          # pin the exact released state
    git switch -c rollback/v0.12.1 # or move the branch, then push

A version bump lands with (1) the record edits, (2) an `authority.json`
bump, (3) a CHANGELOG entry, (4) a new tag. The kernel is versionless; the
site refreshes are committed to `site/` history automatically.
