# Gas in the dynamic era: from 25 nAVAX to a dynamic minimum

> Sources: avalanche-foundation/ACPs (ACP-125, ACP-176, ACP-283); Builder Hub Octane blog, Mar 11, 2025; Helicon docs (updated Sept 2026); verify pass 2026-11-02
> Raw: [brief](../../raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md); [verify report](../../raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md)
> Updated: 2026-11-02

## Overview

Three upgrades in a row changed how C-Chain fees work: Etna cut the minimum base fee from 25 nAVAX to 1 nAVAX, Octane replaced static gas limits with dynamic ones, and Helicon made the minimum gas price itself dynamic, driven by validator preference. If you still say "the minimum base fee is 1 nAVAX," you are describing 2024. The canonical up-to-date wording is: **25 nAVAX → 1 nAVAX (ACP-125) → 1e-18 AVAX dynamic floor (ACP-176/ACP-283)**.

## Step 1 — Etna: 25 nAVAX → 1 nAVAX (ACP-125)

ACP-125 cut the C-Chain minimum base fee from **25 nAVAX to 1 nAVAX** (status: Activated; verified verbatim). Per the verify pass (2026-11-02): that 1 nAVAX floor was the truth only from **Dec 2024 to Mar 2025** — quotes of "1 nAVAX minimum" as *today's* floor are stale.

## Step 2 — Octane: dynamic gas limits (ACP-176, Apr 8, 2025)

Octane activated on Fuji **Mar 13, 2025** and mainnet **Apr 8, 2025**. ACP-176 replaced the static **15M gas/10s** target with **dynamic gas limits**: validators vote on the target consumption rate, and the base fee rises and falls with demand.

The math, corrected per verify pass 2026-11-02: ACP-176 sets the capacity-add rate **R = 2·T** and the max block capacity **C = 10·T**, where T is the target validators vote on. (An earlier summary said "gas limit = 2× target" — that was wrong; the 2× describes R, not the gas limit.)

The practical headline: since Octane, validators can raise the gas target — throughput — **by voting rather than waiting for a hard fork**.

## Step 3 — Helicon: dynamic minimum gas price (ACP-283)

The research brief had ACP-283 marked UNCERTAIN; the verify pass (2026-11-02) identified it: **ACP-283 = Dynamic Minimum Gas Price**. The C-Chain minimum gas price becomes dynamic, set by **stake-weighted validator preference**. Before Helicon, the floor had been set at **M = 1e-18 AVAX** by ACP-176 — effectively zero. So since Helicon (mainnet Sept 22, 2026), even the floor is not a fixed number.

## L1s set their own rules

L1s can run **custom gas tokens** and configure their own fee parameters. So "what's the gas price?" can be a per-chain question, not one global answer.

## Fees are burned

All fees are burned.

## Related: block cadence

Granite's **ACP-226** (dynamic minimum block times — block cadence responds to load) was designed to work together with ACP-176.

## Quick answers

- **"What's the minimum gas price on the C-Chain?"** → There is no fixed one anymore: the floor went 25 → 1 nAVAX (ACP-125), then to 1e-18 AVAX (ACP-176), and since Helicon the minimum is dynamic per stake-weighted validator preference (ACP-283).
- **"Can Avalanche scale throughput without a hard fork?"** → Since Octane, validators vote on the gas target.

## See Also

- [Wallets and gas sponsorship](wallets-sponsorship.md) — how users may pay less than the sticker price
- [Reading the upgrade timeline](upgrade-timeline.md) — when each step activated
- [L1s after Etna](l1s-after-etna.md) — custom gas tokens in context
- [The Primary Network](primary-network-architecture.md) — fee burn and the validator set that votes on targets
