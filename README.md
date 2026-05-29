# dep-updates-rp-data

Canonical schema-**v0.0.5** dependency-update entries for the
[RP 2025/2026 Cargo sub-question](https://github.com/lyuben-todorov/DURP).

Each `cargo-*.json` is a single reproduced dependency-update PR,
schema-validated against `schema/entry.schema.json` in the main repo.

## Branches

- **`main`** — two seed entries (smoke-test fixtures).
- **`ds1-full-crack-r2`** — the full reproduced cohort: **1,407 entries**
  from Rebatchi DS1 (Cargo Dependabot PRs, 2017–2021). This is the
  published artifact behind the headline reproducibility results
  (53.9 %, merged Run B + OpenSSL-stretch sub-cohort).

## Verifying these entries

To verify the cohort (schema validity, counts, breaking rate, or to
rebuild a fat image and re-confirm a single reproduction's fingerprint),
see `docs/cargo/reproduction-runbook.md` in the main repo. Run findings
and provenance are in `docs/findings/` there.

This repo is included in the main repo as a submodule at
`data/cargo/`.
