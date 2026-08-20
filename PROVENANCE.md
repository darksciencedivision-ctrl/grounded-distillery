# Provenance

## Source

| Field | Value |
|---|---|
| Repository | `ryguy-pixel/Sovereign-Distillery` |
| Visibility | private |
| Branch | `main` |
| Path | `docs/THESIS.md` |
| Commit at mirror time | `23523bde90241da482eacb741de086df36642c06` |
| Git blob SHA-1 | `c1ec0ca394ec3b450116cc76741552948e9e2228` |
| Content SHA-256 | `c273744875a90d398b56ecb0a5247c701391bbb79c051b40e95e80db4eebfdd0` |
| Size | 42,183 bytes |
| Line endings | LF |
| Mirrored | 2026-08-20 |

The thesis text was shipped upstream at
`a34187cf480a86d0c89eff0d0a4b7ae8fa3b71f4` — "Ship Grounded Distillery thesis v1.1",
2026-08-20T18:46:59Z, rewriting `docs/THESIS.md` +1500/-213.

## Verify

    gh api "repos/ryguy-pixel/Sovereign-Distillery/contents/docs/THESIS.md?ref=main" \
      --jq '.content' | base64 -d | sha256sum

This must equal the Content SHA-256 above. The file is stored here with LF line endings;
on Windows, clone with `core.autocrlf=input` or the hash will not match.

## Divergences recorded at mirror time

1. **Claim labels were removed by the shipping rewrite.** The v1.1 shipping-candidate
   text dropped the `ARGUED` / `MEASURED` / `OPEN` labels, the C1–C13 core-claims table
   with per-claim falsification status, the statement that no claim is yet `MEASURED`,
   the revision-provenance disclosure, the `DRAFT` status, the date, the companion-spec
   pointer, and the Authorship section. The preceding text carried 14 `ARGUED` markers.
   This mirror preserves the shipped text as-is and does not restore them.

2. **`a332e688…` does not resolve.** The thesis header cites
   `a332e68823ab426310c5d37f3c0bfed5c52cc1f0` as "Preserved RC3 provenance". It is not a
   reachable commit in the upstream repository. It exists only as the Git bundle
   `docs/integration/rc3/grounded-rc3-a332e688.bundle` on `integration/grounded-rc3`, and
   that path does not exist on `main`.

3. **Pinned hashes are superseded.** The header's canonical integration commit
   `c3594cfc…` is behind the integration branch tip; the canonical baseline
   `f1904399…` is behind `main`.

4. **§39 and §41 lag the integration branch.** They describe the state at `c3594cfc`
   (G0 `STARTED_PARTIAL`, HG-0 `BLOCKED / PARTIAL LIVE`, 25/25 tests). On
   `integration/grounded-rc3`, `runs/G0-live/hg0-status.json` records HG-0 `PASS` and
   `runs/post-integration/result.json` records 27/27. That branch is unmerged, and
   PR #1 is open with conflicts.

5. **No licence.** Upstream has no `LICENSE` file, and its ship checklist leaves
   "Repository license explicitly resolved by owners" unchecked.
