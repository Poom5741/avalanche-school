# The Tempo myth (and other name mix-ups)

> Sources: Paradigm blog (tempo-payments-first-blockchain); tempo.xyz; verify pass 2026-11-02 (best-effort negative)
> Raw: [brief](../../raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md); [verify report](../../raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md)
> Updated: 2026-11-02

## Overview

"Tempo" comes up in community channels as if it were an Avalanche product. It is not. Tempo is the **payments-focused L1 incubated by Stripe and Paradigm**, announced **September 4, 2025** — an independent company with no Avalanche connection found. This article also covers two neighboring mix-ups a Technical Translator will hit: the fake "ARC" standards, and outdated "subnets" vocabulary.

## What Tempo actually is (verified)

- A payments-focused L1 incubated by **Stripe and Paradigm**, announced **September 4, 2025**.
- An **independent company** — Stripe and Paradigm are its first investors; **Matt Huang** is CEO.
- This identity was verified in the verify pass (2026-11-02) against Paradigm's own announcement and tempo.xyz.

## The negative claim — and its honest limit

- What the verify pass found: **Paradigm's post and tempo.xyz contain zero Avalanche references**, and there is **no Avalanche-native feature named "tempo"** in docs, ACPs, or GitHub.
- Honest caveat: this is a **best-effort negative** — a websearch outage prevented an exhaustive search. The safe phrasing is "no connection found," never "guaranteed no connection exists."

## Tech vocabulary — flagged: NOT confirmed by the verify pass

The research brief describes Tempo's stack as: built on **Reth** (Paradigm's Ethereum client), **Simplex consensus** (Commonware), stablecoin-denominated fees via an enshrined **Fee AMM**, its own **TIP-20** token standard, **~0.6s finality**, mainnet **March 2026**.

⚠️ The verify pass **could not confirm these specifics** from the tempo.xyz pages it fetched — it only confirmed that Tempo is live and Stripe/Paradigm-incubated. Treat this list as vocabulary only and **confirm against tempo.xyz before repeating any of it**. What is safe to say regardless: Tempo uses its own standard (TIP-20), **not Avalanche ACPs**.

## The two neighbor myths

**"ARC" standards.** There is **no official "ARC" (Avalanche Request for Comments) standards repo** from the Avalanche Foundation — Avalanche protocol standards are **ACPs** (the Foundation hosts only the ACPs repo, per verify). The **ARC-20** that appears in search results belongs to **Metal Blockchain** (an Avalanche fork — its metalgo is forked from ava-labs/avalanchego, per verify). A community "ASC-20" inscription standard was only a discussion thread (ACPs discussion #55) — minor.

**"Subnets."** Anything describing "subnets" as the current model should be updated to **L1s** (Etna, Dec 16, 2024). See [L1s after Etna](l1s-after-etna.md).

## The correct answer script

When someone asks "Is Tempo part of Avalanche?" or "Does Avalanche support Tempo?":

1. "Tempo is **Stripe and Paradigm's** payments-focused L1, announced **September 4, 2025**. It's an **independent company** — not an Avalanche project."
2. "I haven't seen any Avalanche connection: Paradigm's announcement and Tempo's own site contain zero Avalanche references, and there's no Avalanche feature named 'tempo' in the docs, ACPs, or GitHub."
3. "If you saw 'Tempo support' somewhere, it almost certainly misattributes Stripe's Tempo to Avalanche."
4. "Avalanche's protocol standards are **ACPs** — nothing named TIP-20 is an Avalanche standard."

## Quick answers

- **"Is Tempo built on Avalanche?"** → No connection found — Tempo is Stripe/Paradigm's independent chain (announced September 4, 2025). Caveat: this is a best-effort negative.
- **"Where can I read about ARC-20?"** → ARC-20 is Metal Blockchain's standard, not Avalanche's; Avalanche standards are ACPs.

## See Also

- [L1s after Etna](l1s-after-etna.md) — the subnets → L1s correction in full
- [Reading the upgrade timeline](upgrade-timeline.md) — where to read actual ACPs
- [Wallets and gas sponsorship](wallets-sponsorship.md) — ACP-209: proposed, not activated
