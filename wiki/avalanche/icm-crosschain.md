# ICM: cross-chain messaging without an external bridge

> Sources: Builder Hub ICM overview; ava-labs avalanchego warp README; ava-labs/icm-contracts (archived Dec 3, 2025); Granite blog; verify pass 2026-11-02
> Raw: [brief](../../raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md); [verify report](../../raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md)
> Updated: 2026-11-02

## Overview

What used to be called Avalanche Warp Messaging (AWM) is now branded **Avalanche Interchain Messaging (ICM)**: an L1's validator set signs messages, and any other L1 can verify them — no external bridge in the middle. **Teleporter** is the smart-contract framework on top, and **ICTT** moves tokens burn-and-mint style. The code now lives in `ava-labs/icm-services`, after `icm-contracts` was archived.

## The renaming: AWM → ICM

AWM is now branded **Avalanche Interchain Messaging (ICM)**. The mechanism in one sentence: **BLS-signature-aggregated messages** signed by an L1's validator set, **verifiable by any other L1 — no external bridge**.

## Teleporter and ICTT

- **Teleporter** — the smart-contract framework built on top of ICM.
- **ICTT** (Interchain Token Transfer) — burn-and-mint token movement between chains.

## Who uses it

ICM is in production use by **Beam** and **DeFi Kingdoms**, and it is **default on AvaCloud L1s**. ICM fees are now tracked as a metric. Granite (mainnet Nov 19, 2025) enhanced ICM.

## The repo pointer (corrected by the verify pass)

`github.com/ava-labs/teleporter` redirects to **icm-contracts** — which was **archived Dec 3, 2025** and moved entirely to **`ava-labs/icm-services`** (per verify pass 2026-11-02). When a dev asks where the Teleporter code lives, point them at **icm-services**; links to icm-contracts are stale.

## Quick answers

- **"Does Avalanche need third-party bridges between its chains?"** → For L1-to-L1 messaging, ICM verifies messages via validator signatures — no external bridge.
- **"Where is the Teleporter code?"** → `ava-labs/icm-services` (icm-contracts was archived Dec 3, 2025).
- **"How do tokens move between chains?"** → ICTT, burn-and-mint.

## See Also

- [L1s after Etna](l1s-after-etna.md) — the launch flow includes verifying ICM/ICTT messaging
- [Reading the upgrade timeline](upgrade-timeline.md) — Granite enhanced ICM
- [Fuji testnet field guide](fuji-testnet.md) — where devs set up an ICM Relayer on testnet
