# BTC & ETH: the two anchors

> Sources: ethereum.org, 2026 (The Merge; proof-of-stake; staking; Pectra; smart contracts); bitcoin/bitcoin GitHub (src/consensus/amount.h; src/chainparams.cpp); Bitcoin whitepaper, 2008; bitbo halving schedule; Cambridge CCAF (CBESI); Bitwise & KuCoin research, Sept–Oct 2026; Chainlabo, Feb 2026; CoinGecko API, Nov 2, 2026; verify pass, 2026-11-02
> Raw: [brief](../../raw/foundations/2026-11-02-blockchain-foundations-brief.md); [verify report](../../raw/foundations/2026-11-02-verify-report-foundations-brief.md)
> Updated: 2026-11-02

## Overview

Almost every crypto conversation bottoms out in a comparison of Bitcoin and Ethereum, so a Technical Translator needs both anchored — factually, not tribalistically. This article covers what each chain is famous for: Bitcoin's hard-coded 21 million supply cap and its halving schedule (with the corrected date for the next one), proof-of-work as a security budget, and Ethereum's Merge to proof-of-stake with the validator mechanics learners repeat to developers — including the two facts most often gotten wrong (the Pectra/EIP-7251 attribution and the falling validator count). Finally: "digital gold" vs "platform asset" are labeled as what they are — narratives.

## Bitcoin in code and calendar

### The 21 million cap

Bitcoin's total supply is hard-capped at **21 million BTC**, enforced in Bitcoin Core's code: `MAX_MONEY = 21,000,000 × COIN`. Location note per verify pass 2026-11-02: that constant lives in `src/consensus/amount.h` (it is no longer in consensus.h — cite amount.h). Issuance falls geometrically, so most BTC will never be mined.

### Halvings: the supply schedule

The mining reward halves every **210,000 blocks** — roughly every 4 years (the interval constant `nSubsidyHalvingInterval` is set in `src/chainparams.cpp`).

| Halving | When | Reward |
|---|---|---|
| Last | April 20, 2024 (block 840,000) | → **3.125 BTC/block** |
| Next | ~mid-April 2028 — **est. April 8–14, 2028** — at block 1,050,000 | 3.125 → **1.5625 BTC** |

*Correction per verify pass 2026-11-02:* the next halving was previously drafted as "~March–April 2028"; October 2026 sources converge on **April 8–14, 2028**. The exact date depends on block-time luck. Post-halving, miner revenue is ~3.125 BTC/block plus transaction fees.

### PoW: security paid in electricity

Miners compete to solve an arbitrary computational puzzle; the winner proposes the next block and collects the reward plus fees. The puzzle's difficulty auto-adjusts so a block appears ~every **10 minutes**. Rewriting recent history means redoing more computing work than the entire rest of the network combined — so attacking Bitcoin means continuously out-spending the honest network on electricity.

This energy use is Bitcoin's **"security budget"** — and also its main criticism. Estimates are contested; the standard neutral tracker is the [Cambridge Bitcoin Electricity Consumption Index](https://www.ccaf.io/cbesi).

## Ethereum: from mining to staking

### The Merge

Ethereum switched from proof-of-work to proof-of-stake on **September 15, 2022**, cutting energy use by **~99.95%**.

### PoS mechanics: the vocabulary that matters

- **Validators** stake **32 ETH** as a deposit and run validation software; dishonesty gets their stake **slashed** (destroyed).
- Time is divided into **slots of 12 seconds** and **epochs of 32 slots (~6.4 min)**. One validator is randomly picked per slot to propose a block; others vote ("attest").
- A transaction is **finalized** after two epochs are justified by a two-thirds supermajority of stake — **~13 minutes**. Finalized history cannot revert without burning ≥⅓ of all staked ETH.
- The ~13-minute figure is **derived arithmetic** (2 epochs × ~6.4 min = 12.8 min) rather than a number printed on ethereum.org; ethereum.org's staking FAQ does say deposits are recognized "in around 13 minutes." Present it as **~13 minutes**, never as an exact spec number (verify pass 2026-11-02).
- Anyone can stake via pools with as little as **0.01 ETH**.

### Two corrections learners repeat to developers

1. **The 2,048 ETH validator max balance is from Pectra, not Shanghai.** Since the Pectra upgrade (**May 2025, EIP-7251**), validators can hold up to 2,048 ETH each. Shanghai/Capella (April 12, 2023) only enabled withdrawals — it did not raise the balance cap. (Per verify pass 2026-11-02; the earlier "since Shanghai" phrasing is exactly the kind of fact learners repeat to devs, so it must be right.)
2. **The validator count fell on purpose.** There were **~881k validators as of Sept 30, 2026** (863–868k during October 2026), **down from 1.1M** due to Pectra consolidation — EIP-7251 let operators merge validators, so the count fell without stake leaving. A falling count is not people leaving.

### How much ETH is staked

**43.8M ETH — 35.9% of supply —** was staked as of **Sept 30, 2026** (Bitwise, per verify pass 2026-11-02). The 30% milestone was crossed in early February 2026.

## "World computer" — a framing, not a spec

Ethereum is a globally shared computer whose programs (smart contracts) run exactly as written, identically on thousands of nodes, with no downtime or owner — anyone can deploy code that anyone can call. The phrase **"world computer"** is a common community framing rather than a formal spec; say it that way.

## BTC vs ETH: two narratives, labeled as narratives

- **BTC: "digital gold."** Fixed supply, simplest possible use-case, valued as scarce, apolitical money.
- **ETH: the programmable platform asset.** It is the fuel for paying gas, the collateral that secures the network via staking (earning yield), and the base money of the app economy.

The narratives overlap but imply different risks: BTC bets on **monetary scarcity**; ETH bets on **usage of the platform**. Teach both as *narratives*, not facts.

## Where the numbers stood (Nov 2, 2026 snapshot)

- **Total crypto market cap: $2.613T** (CoinGecko, Nov 2, 2026).
- **BTC dominance: 59.96%** (same snapshot). Readings ranged **57–63%** across sources this fall — say **"~60%, fluctuating"** and check CoinMarketCap's dominance chart live rather than memorizing a figure.

## Quick answers

- **"When is the next Bitcoin halving?"** → ~mid-April 2028 (est. April 8–14, 2028), at block 1,050,000; the reward drops 3.125 → 1.5625 BTC.
- **"Why is Ethereum's energy use so low now?"** → The Merge on September 15, 2022 — a ~99.95% cut.
- **"Why did Ethereum's validator count drop below 1M?"** → Pectra consolidation (EIP-7251 merged validators), not attrition — stake didn't leave.
- **"What's the max ETH a validator can hold?"** → 2,048 ETH, since Pectra (May 2025, EIP-7251) — not Shanghai.

## See Also

- [A mental model of a blockchain](blockchain-mental-model.md) — the fundamentals these two chains run on
- [Consensus, rollups & ZK vocabulary](consensus-zk-vocabulary.md) — PoW vs PoS as contested tradeoffs
- [The Primary Network](../avalanche/primary-network-architecture.md) — Avalanche's own proof-of-stake and staking rules
- [Avalanche vs the field](../ecosystem/competitive-scoreboard.md) — dominance and market-cap context, same-day tables
