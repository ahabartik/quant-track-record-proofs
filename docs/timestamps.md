# Timestamp log

Record day one: 2026-09-30. Proofs made with opentimestamps-client 0.7.2 (`ots stamp`).
Each `.ots` file sits next to the file it proves. A fresh proof is pending until a Bitcoin block includes it (hours).
Run `ots upgrade <file>.ots` later to embed the Bitcoin attestation, then commit the upgraded proof.
Verify with `ots verify <file>.ots` (needs the original file next to it).

| File | sha256 at stamp time | Proof | Status at 2026-09-30 |
|---|---|---|---|
| PLAN.md | 3a8d75be921b2f2d2798531fadba9d08d12a0f33225b0180d19f837c3fc480cc | PLAN.md.ots | Bitcoin attestation embedded 2026-09-30 (block 969221 in `ots info`) |
| STRESS_TEST.md | 6c58f54275f4000f24a635d439efc7d5e24bcd28eec535129369820067583ac0 | STRESS_TEST.md.ots | Bitcoin attestation embedded 2026-09-30 |

If either file changes, the old proof no longer verifies against the new file. Keep the commit that matches the hash above.

## Stamping rules (adopted 2026-09-30)
- Each iteration end that closes a backlog item writes the HEAD commit hash to `manifests/stamps/<date>_<shortsha>.txt` and stamps it with `ots stamp`; the `.ots` proof is committed in a later commit (a commit cannot contain a proof of its own hash).
- Each session start runs `ots upgrade` on all pending proofs (`*.ots` files) and commits the upgraded ones.
- `ots upgrade` leaves `*.ots.bak` backups; they are gitignored.
- Each session end stamps HEAD, commits the stamp files, then runs `bin/publish_proofs` to copy the proofs (allow-listed files only) to the public hash-only mirror and push.
- Every proof pending at a session start is upgraded (`ots upgrade`) and the upgrade committed before new work.
