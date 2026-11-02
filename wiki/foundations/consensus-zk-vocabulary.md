# Consensus, rollups & ZK: the vocabulary

> Sources: ethereum.org, 2026 (PoS vs PoW; scaling; optimistic rollups; ZK-rollups; validium; privacy roadmap); StarkWare docs (Volition); status.starknet.io, Oct 29, 2026; CoinMarketCap Scroll updates, Oct 2026; verify pass, 2026-11-02
> Raw: [brief](../../raw/foundations/2026-11-02-blockchain-foundations-brief.md); [verify report](../../raw/foundations/2026-11-02-verify-report-foundations-brief.md)
> Updated: 2026-11-02

## Overview

Module 2 is awareness level: names and one-line meanings, zero math. After this article a learner can follow (and accurately repeat) a conversation about PoW vs PoS, finality, optimistic vs ZK rollups, and validity proofs — and knows which claims are genuinely contested and which "example projects" come with caveats as of November 2026.

## PoW vs PoS: tradeoffs, not a scoreboard

**Proof-of-work (PoW)** buys security with real-world electricity. It is battle-tested since 2009, and if your mining hardware fails it costs nothing but wasted energy. On the other side: mining concentrates in industrial farms, and power consumption is large.

**Proof-of-stake (PoS)** buys security with locked capital that can be destroyed. It cuts energy use ~99.9%, lowers the hardware barrier (a laptop can validate), and enables faster hard finality. On the other side: it is younger and operationally more complex.

Balance note: Bitcoiners argue PoS's "nothing-at-stake" and governance properties weaken it — this remains genuinely **contested**. Teach these as **tradeoffs**, never as a settled winner.

## Finality: when "done" means done

A transaction is *final* when it can no longer be reversed. In PoW there is never absolute certainty — only an exponentially decreasing probability of reversal (hence the folk rule "wait 6 confirmations"). Ethereum PoS has explicit finality at **~13 minutes** (a derived figure: two epochs × ~6.4 min; see [BTC & ETH anchors](btc-eth-anchors.md)). Many L2s inherit or approximate L1 finality.

## Rollups: L1 security at L2 prices

A **rollup** is an L2 that **executes transactions off Ethereum but posts the transaction data back to Ethereum L1** — so the data stays as available and censorship-resistant as L1 while fees drop **10–100×**. There are two families, and the difference is how they catch cheating.

## Optimistic rollups: innocent until proven guilty

Optimistic rollups **assume results are valid** and run a **challenge window** during which anyone can submit a **fraud proof** showing an invalid result — the bad operator's bond gets slashed. Ethereum.org's own wording is a "challenge period lasting roughly seven days," so **~7 days** is the number to use. Examples: **Arbitrum, Optimism**.

Practical consequence learners hit immediately: **moving funds back to L1 typically means waiting ~7 days** — or paying a liquidity provider to skip the line for a fee.

## ZK-rollups: prove it, then post it

ZK-rollups post a **validity proof** with every batch; the L1 contract cryptographically verifies the proof and accepts the batch **instantly** — no challenge window needed. Named examples (with a health check below): **zkSync, Starknet, Linea, Scroll**.

## What a validity proof actually is

A validity proof (zero-knowledge proof) is a way for one party to *prove a computation was done correctly* without the verifier re-doing the computation. Think of a **tamper-evident math receipt**: the prover crunches thousands of transactions off-chain, then produces a small certificate that, if even one transaction were mis-executed, could not have been generated. The L1 smart contract checks this certificate in milliseconds; if it verifies, the result is as trustworthy as having re-executed everything. One honest nuance: "zero-knowledge" technically means the proof can hide the underlying data while still proving the claim — a feature rollups mostly **don't** use (they publish data on L1); privacy tech does.

## Validium and volition, one line each

- **Validium:** a ZK-rollup variant that keeps the proof but stores data *off-chain* — cheaper, but you now trust a data-availability committee.
- **Volition:** users choose per-transaction between rollup mode (on-chain data) and validium mode (off-chain data) — a StarkEx/Starknet concept.

## Why ZK matters beyond rollups

Proofs let you prove a statement about hidden data:

- prove you're **over 18** without revealing your birthday;
- prove a company **holds enough reserves** to cover customer balances without publishing the full balance sheet (**proof of reserves**);
- enable **private payments and transfers**.

Ethereum's own roadmap lists privacy via ZK as a goal — this is a direction of travel, not a finished feature.

## 2026 health check: the example rollups

Named examples drift; as of November 2026 (verify pass 2026-11-02):

- **Arbitrum, Optimism** — active.
- **zkSync Era** — active (the older ZKsync Lite shut in May 2026).
- **Linea** — active (Lido staking live Oct 15, 2026).
- **Starknet** — all systems operational (status page, Oct 29, 2026; v0.14.4 upgrade Oct 5, 2026). It is **exploring a post-quantum independent L1** — research only, non-binding; it remains an Ethereum L2. Say it that way if asked.
- **Scroll — still operating but in decline.** TVL fell **−98.5%** to **$8.65M**, Phemex delisted the network **Oct 21, 2026**, and it is planning a transition to a **permissioned network**. Keep Scroll as an example of the ZK-rollup *design*, not as an example of health.

## Quick answers

- **"Why does moving funds from Arbitrum to Ethereum take ~7 days?"** → That's the optimistic rollup challenge window; liquidity providers can bridge faster for a fee.
- **"Can I still cite Scroll as a healthy ZK-rollup?"** → Cite the design, not the health: operating but in decline (TVL −98.5%, delisting, permissioned transition planned).
- **"Does ZK mean private?"** → Not by default — rollups mostly publish data on L1. Hiding data is the feature privacy applications use.
- **"Is PoS or PoW better?"** → It's contested; teach tradeoffs.

## See Also

- [BTC & ETH: the two anchors](btc-eth-anchors.md) — the PoS mechanics (slots, epochs, slashing) behind finality
- [The EVM and token standards](evm-token-standards.md) — why contracts port easily onto these EVM-compatible L2s
- [L1s after Etna](../avalanche/l1s-after-etna.md) — Avalanche's different answer to scaling
- [Avalanche vs the field](../ecosystem/competitive-scoreboard.md) — where "Ethereum + L2s" sits in the competitive picture
