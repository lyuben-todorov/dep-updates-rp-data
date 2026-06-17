# dep-updates-rp-data

Canonical schema-**v1.1.0** dependency-update entries for the
[RP 2025/2026 Cargo sub-question](https://github.com/lyuben-todorov/DURP) (DURP).

Each `cargo-*.json` is a single reproduced dependency-update PR, schema-validated
against `schema/entry.schema.json` in the main repo. Since v1.1.0 an entry holds a
`reproductions[]` list (one attempt per `(imageTag, pipelineVersion)`); the headline
`category` is the highest-`pipelineVersion` attempt's outcome.

## Current corpus — the `v11-corpus` branch

The **v11 census**: ~18,476 reproduced entries (schema v1.1.0), organised by cohort:

| Directory | Entries | Cohort |
| --- | ---: | --- |
| `fulldrive-lateststable-v11/` | 12,155 | full-corpus latest-stable drive (the bulk of the v11 census) |
| `livemine-fleet/` | 2,825 | live-mined recent GitHub cohorts (fleet drive) |
| `rebatchi-p1/` | 1,331 | Rebatchi DS1 partition 1 (2017–2021 PRs) |
| `breaking-2025-2026/` | 623 | recent breaking-update cohort (2025–2026) |
| top-level `cargo-*.json` | 1,470 | earlier / ungrouped entries |

`fat-image-fingerprints.json` holds the per-image environment fingerprints (keyed by
image tag × platform × host) — a property of the fat image, not of any entry.

This submodule is the **committed reproduced-entry slice**. The full study census
(20,403 candidates, including the unreproducible ones) was driven on an AWS fleet and
its results live on the host `crack`; the headline numbers are reported in the paper.

## Branches & tags

- **`v11-corpus`** — current corpus (the table above). The main repo pins its tip.
- **`v1-corpus`** (tag `corpus-1.0`) — the earlier 1,415-entry DS1 artifact, migrated
  to schema 1.0.0. Historical.
- **`main`** — early/seed state. Historical.
- Tags: `corpus-0.0.6` (0.0.x freeze), `corpus-1.0` (1.0.0), `corpus-1.1` (1.1.0).

Branches here are **append-only** — never amend/force-push.

## Verifying these entries

To verify the cohort (schema validity, counts, breaking rate, or to rebuild a fat
image and re-confirm a single reproduction's fingerprint), see
`docs/pipeline/6-verify.md` in the main repo. Run findings and provenance are in
`docs/findings/` there.

This repo is included in the main repo as a submodule at `data/cargo/`.
