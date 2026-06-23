# SIGMA Forecast Ledger — Public Timestamp Record

This repository is the **public proof-of-record** for the SIGMA Forecast Ledger, a pre-registered geopolitical conflict-forecasting product from SIGMA Futures Group.

It holds the cryptographic timestamps for the SIGMA Forecast Ledger's frozen snapshots — **not** the ledger's contents. The forecasts themselves are members-only ([sigmafutures.group](https://sigmafutures.group)). What this repository proves to anyone, without their having to trust SIGMA, is that each snapshot existed and was anchored to the Bitcoin blockchain on its date below — so no forecast in it can have been added, altered, or back-dated after the fact.

## What the ledger is

The SIGMA Forecast Ledger records probabilistic forecasts for active geopolitical flashpoints. Every entry is **pre-registered**: a full probability distribution over defined outcomes, an explicit resolution date, and an objective resolution criterion, all fixed *before* the outcome is known — and each is scored on resolution with a multi-category Brier score against a stated benchmark. The ledger is append-only; a revised view is a new dated entry, never an edit.

- **Engine:** UCPF v2.7.5 (frozen)
- **Latest snapshot:** 23 June 2026
- **Method:** pre-registered · scored · benchmarked — see [sigmafutures.group](https://sigmafutures.group)

## The record

Each snapshot is an independent, self-contained freeze of the ledger, with its own fingerprint and proof. Snapshots accumulate; none is ever overwritten.

| Snapshot | File | SHA-256 | Timestamp proof |
|----------|------|---------|-----------------|
| 16 Jun 2026 | `SIGMA-Forecast-Ledger-PUBLIC-20260616.csv` | `106eeeae204a93b992b2ea276028a2eafadfd5a360a9a439958c003a537938fd` | `SIGMA-Forecast-Ledger-PUBLIC-20260616.csv.ots` |
| 16 Jun 2026 | `SIGMA-Forecast-Ledger-PUBLIC-20260616.xlsx` | `2dccd811eaea9c4ff05d2596360410c35a2330778d10a5cb19d8bdadd0c23be2` | `SIGMA-Forecast-Ledger-PUBLIC-20260616.xlsx.ots` |
| 19 Jun 2026 | `SIGMA-Forecast-Ledger-PUBLIC-20260619.csv` | `a4cce4a2e2e2ca3d57f8b38020eb2e973d69a5c7c1904389b29be1d2b89693c4` | `SIGMA-Forecast-Ledger-PUBLIC-20260619.csv.ots` |
| 19 Jun 2026 | `SIGMA-Forecast-Ledger-PUBLIC-20260619.xlsx` | `4301a71d542e75338915889ddea2ef0b94bcd5db13253a6b12347ba26d3e78d3` | `SIGMA-Forecast-Ledger-PUBLIC-20260619.xlsx.ots` |
| 22 Jun 2026 | `SIGMA-Forecast-Ledger-PUBLIC-20260622.csv` | `ed0b079e981dc779e18a83156d72ef499426e99528e5d6a71ba4867eb8d8a061` | `SIGMA-Forecast-Ledger-PUBLIC-20260622.csv.ots` |
| 22 Jun 2026 | `SIGMA-Forecast-Ledger-PUBLIC-20260622.xlsx` | `e089ef7b1c5dc8c17c318a1192e90b6c411617f4aa75533d3e54dbeafab368f9` | `SIGMA-Forecast-Ledger-PUBLIC-20260622.xlsx.ots` |
| 23 Jun 2026 | `SIGMA-Forecast-Ledger-PUBLIC-20260623.csv` | `35457ded71b34c2a39ca5284dd8ad8abc48caf75e3311751f30ea701bb1aca79` | `SIGMA-Forecast-Ledger-PUBLIC-20260623.csv.ots` |
| 23 Jun 2026 | `SIGMA-Forecast-Ledger-PUBLIC-20260623.xlsx` | `5be53258261b4e7559283d169db769c02c6dce940c1dfeaea551dd47c5ae386c` | `SIGMA-Forecast-Ledger-PUBLIC-20260623.xlsx.ots` |

A SHA-256 is a content fingerprint: it depends only on a file's bytes, not its name, and changes completely if even one character changes. The `.ots` files are [OpenTimestamps](https://opentimestamps.org) proofs that anchor these fingerprints to a Bitcoin block.

## How to verify

**1 — Confirm the timestamp (anyone, now).** The `.ots` proofs show that the fingerprints above were committed to Bitcoin no later than a specific block, and therefore that the ledger they fingerprint was fixed by that block's date.

- *Web:* at [opentimestamps.org](https://opentimestamps.org), drop in a `.ots` file; it reports the Bitcoin block and date.
- *Command line:* `pip install opentimestamps-client`, then `ots verify SIGMA-Forecast-Ledger-PUBLIC-20260619.csv.ots` (with the original file in the same folder).

*This repository holds the proofs, not the files, so a full file-plus-proof check is possible once a snapshot is released.*

**2 — Confirm a released file matches (when SIGMA discloses one).** SIGMA releases specific snapshots as forecasts resolve. To confirm a released file is the exact one timestamped here, compute its SHA-256 and check it against the table above:

```
shasum -a 256 SIGMA-Forecast-Ledger-PUBLIC-20260619.csv               # macOS / Linux
certutil -hashfile SIGMA-Forecast-Ledger-PUBLIC-20260619.csv SHA256   # Windows
```

A match means the file is byte-identical to the one anchored to Bitcoin on the snapshot date — unaltered, in full.

## What this does and does not establish

- It **does** establish that a specific ledger existed, complete and unaltered, no later than the timestamped date — the guarantee against back-dating or post-hoc editing.
- It **does not** disclose the forecasts. The contents are members-only; this record commits to them without revealing them, and individual entries are released by SIGMA as they resolve.

---

*SIGMA Futures Group · [sigmafutures.group](https://sigmafutures.group)*
