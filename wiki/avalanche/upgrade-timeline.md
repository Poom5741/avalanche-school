# Reading the upgrade timeline: Etna → Octane → Granite → Helicon

> Sources: ava-labs avalanchego release notes (v1.12.0; v1.13.0/-fuji; v1.14.0/-fuji; v1.15.0/-fuji); avalanche-foundation/ACPs; Builder Hub upgrade blogs (Octane blog, Mar 11, 2025); Helicon docs (updated Sept 2026); verify pass 2026-11-02
> Raw: [brief](../../raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md); [verify report](../../raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md)
> Updated: 2026-11-02

## Overview

Avalanche upgrades ship as a batch of ACPs, activate on **Fuji first**, then reach mainnet only after Fuji succeeds. In the last two years: **Etna** (Dec 16, 2024) rebuilt L1 economics, **Octane** (Apr 8, 2025) made gas dynamic, **Granite** (Nov 19, 2025) added passkeys and smarter block times, and **Helicon** (Sept 22, 2026) decoupled execution and overhauled staking. As of Nov 2, 2026, nothing newer than Helicon has activated.

## What an ACP is, and where to read one

- **ACP = Avalanche Community Proposal** — the format for protocol changes. They live in the **avalanche-foundation/ACPs** repo on GitHub.
- Avalanche-specific standards are ACPs — there is no official "ARC" repo (that's a myth; see [The Tempo myth](tempo-myth.md)).
- Other places to read: the docs at **build.avax.network** (the current home of docs.avax.network), the official upgrade blogs, and the **avalanchego release notes** on github.com/ava-labs — which list exactly which ACPs each version schedules.

## Fuji first — always

Every mainnet upgrade rehearses on Fuji first; mainnet follows only after Fuji succeeds. During the gap the two networks behave differently — e.g., Granite hit Fuji **Oct 29, 2025** and mainnet **Nov 19, 2025**.

## The four upgrades at a glance

| Upgrade | Fuji | Mainnet | Headline changes |
|---|---|---|---|
| **Avalanche9000 (Etna)** | Nov 2024 | **Dec 16, 2024** (12 PM ET, per verify) | Subnets → Avalanche L1s; validator economics overhaul; cheaper C-Chain gas |
| **Octane** | Mar 13, 2025 | **Apr 8, 2025** | ACP-176: dynamic gas limits & price discovery |
| **Granite** | Oct 29, 2025 | **Nov 19, 2025** | ACP-181, ACP-204, ACP-226: ICM enhancement, passkey/biometric support, dynamic block times |
| **Helicon** | Jul 28, 2026 | **Sept 22, 2026, 15:00 UTC** | ACP-194 "Continuous Execution" + five more ACPs (staking economics + C-Chain gas pricing) |

## Upgrade by upgrade

**Etna — the largest upgrade in Avalanche history.** It bundled **6 ACPs: ACP-77, 103, 118, 125, 131, 151** (per verify pass 2026-11-02 — the v1.12.0 release notes list six; earlier drafts said seven). ACP-77 reinvented subnets as L1s ([details](l1s-after-etna.md)); ACP-125 cut the C-Chain base fee 25 → 1 nAVAX ([details](dynamic-gas.md)); ACP-131 activated the Cancun EIPs.

**Octane.** ACP-176 replaced the static 15M gas/10s target with dynamic gas limits — validators vote on the target, and the base fee moves with demand. Corrected math (R = 2·T, C = 10·T) in [Gas in the dynamic era](dynamic-gas.md).

**Granite.** Requires **AvalancheGo v1.14**. Three ACPs: **ACP-181** (P-Chain Epoched Views), **ACP-204** (precompile for secp256r1 — unlocks passkey/biometric signing), **ACP-226** (dynamic minimum block times — block cadence responds to load, works together with ACP-176).

**Helicon.** Requires **AvalancheGo v1.15.0+**. Six ACPs total (per verify pass 2026-11-02):

| ACP | Change |
|---|---|
| **ACP-194** "Continuous Execution" | Consensus and execution decoupled via a queue on the C-Chain — blocks are agreed first, executed in parallel. The C-Chain now runs the new Continuous Execution VM (Coreth handled pre-Helicon blocks) |
| **ACP-236** | Staking auto-renews at cycle end |
| **ACP-267** | Validator uptime requirement 80% → 90% |
| **ACP-273** | Minimum staking duration 48h mainnet / 12h Fuji |
| **ACP-285** | Minimum staking reward consumption rate ramps from 10% to 7.5% over 90 days post-activation |
| **ACP-283** | **Dynamic Minimum Gas Price** (per verify pass 2026-11-02 — the brief had marked it UNCERTAIN): C-Chain minimum gas price set dynamically by stake-weighted validator preference. Note: this one is C-Chain gas pricing, not staking |

## Status as of Nov 2, 2026

- **Nothing newer than Helicon has activated.** The ACP repo tops out at 285.
- Fuji ops gotcha: the Helicon docs state **v1.15.0-fuji does not support C-Chain state sync once Helicon is active** on Fuji — a real issue for node operators.

## Quick answers

- **"When does mainnet get the new upgrade?"** → After Fuji — and there is always a gap (Granite: Fuji Oct 29, 2025 → mainnet Nov 19, 2025).
- **"Where do I read what's in an upgrade?"** → The ACPs repo, the upgrade blog, and the avalanchego release notes for the version that schedules it.
- **"What's the latest upgrade?"** → Helicon (mainnet Sept 22, 2026, 15:00 UTC), as of Nov 2, 2026.

## See Also

- [L1s after Etna](l1s-after-etna.md) — the upgrade that renamed and rebuilt subnets
- [Gas in the dynamic era](dynamic-gas.md) — ACP-125 → ACP-176 → ACP-283, one upgrade at a time
- [Wallets and gas sponsorship](wallets-sponsorship.md) — ACP-204 shipped in Granite; ACP-209 still pending
- [ICM: cross-chain messaging](icm-crosschain.md) — what Granite changed for ICM
- [The Primary Network](primary-network-architecture.md) — Helicon's staking parameters in context
