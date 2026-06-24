# .post-indeterminate/ — quarantined census entries (NOT part of the published breaking set)

These 72 entries were classified `breaking` by the census drive
(`fulldrive-lateststable-v11`) but their post-update failure is NOT a code
breakage. Two exhaustively-swept classes (2026-06-11/12):

- 55 lockfile-skew: post commit bumps Cargo.toml without a regenerated
  Cargo.lock; `cargo --locked` refuses before building anything.
- 17 infrastructure failures, each manually adjudicated sole-terminal-cause:
  8 OOM kills (3x aws-sdk-ec2), 5 port-binding races, 3 external-network
  test calls, 1 missing system library.

The dot-dir is deliberately skipped by `rebuild_index.py` (hidden from the
entries index) while keeping the files in git for audit. RQ2 conditions on
the remaining post-determinate reproduced set (995 breaking / 12,155).

Evidence + candidate list: dep-updates-poc/scratch/locked-sweep-results.md
(and scratch/breaking-cohort-validity.md for the originating audit).

NOTE: each entry JSON still carries category=breaking internally — the
classifier does not yet emit a post-indeterminate verdict (deferred:
classifier-backing of the sweep rules). Do not re-add these to the index
without that pass.
