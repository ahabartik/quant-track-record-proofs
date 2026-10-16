# quant-track-record-proofs

Hash-only public mirror for a private quant research project. It holds OpenTimestamps proofs and the commit hashes they
prove, so that the timing of the private repository's states can be checked by anyone. It contains no data, no code and no results.

All results of the project are hypothetical paper results and research data, not investment performance.

- Source repository HEAD when this mirror was written: `8a4057f39790ed5c907ac765d4a6ec13a0e01967`
- Written: 2026-10-16
- Files: 56 proof files (`manifests/stamps/*.txt` with their `.ots`, `PLAN.md.ots`, `STRESS_TEST.md.ots`, `registrations/*.json.ots`, `docs/timestamps.md`)

Verify a proof with `ots verify <file>.ots` (opentimestamps-client) next to the file it proves; the `.txt` stamp files hold a git commit hash.
