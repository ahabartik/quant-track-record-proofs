# quant-track-record-proofs

Hash-only public mirror for a private quant research project. It holds OpenTimestamps proofs and the commit hashes they
prove, so that the timing of the private repository's states can be checked by anyone. It contains no data, no code and no results.

All results of the project are hypothetical paper results and research data, not investment performance.

- Source repository HEAD when this mirror was written: `9894714f5c1db948f3139f69fad4c98cd64eb0f0`
- Written: 2026-10-14
- Files: 52 proof files (`manifests/stamps/*.txt` with their `.ots`, `PLAN.md.ots`, `STRESS_TEST.md.ots`, `registrations/*.json.ots`, `docs/timestamps.md`)

Verify a proof with `ots verify <file>.ots` (opentimestamps-client) next to the file it proves; the `.txt` stamp files hold a git commit hash.
