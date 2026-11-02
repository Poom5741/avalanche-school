# DeFi & RWA: the mechanisms behind the usage map

> Sources: Uniswap v2 whitepaper; ethereum.org, 2026 (DeFi; enterprise tokenization); Lido docs; EigenLayer; rwa.xyz (live pull Oct 30–Nov 2, 2026); DefiLlama API, Nov 2, 2026; verify pass, 2026-11-02
> Raw: [brief](../../raw/foundations/2026-11-02-blockchain-foundations-brief.md); [verify report](../../raw/foundations/2026-11-02-verify-report-foundations-brief.md)
> Updated: 2026-11-02

## Overview

Module 3's ecosystem article covers *what* people use blockchains for; this article covers the *mechanisms* underneath, at primer level: how AMMs price trades without an order book, how lending protocols stay solvent through liquidation, what liquid staking and restaking are, why institutions tokenize real-world assets, and how stablecoins hold a peg — all with the corrected November 2, 2026 figures from the verify pass.

## AMMs: pricing by arithmetic (x·y = k)

Instead of an order book (buyers on one side, sellers on the other, matched manually), an **automated market maker (AMM)** is a smart contract that holds a **pool of two tokens** and prices them by the formula **x·y = k**. Each trade shifts the reserves along this **constant-product curve** — so the price is set by arithmetic, not by a market maker.

## Lending and liquidation

You **deposit collateral to borrow** against it. If the collateral's value falls below a threshold, **anyone can liquidate** it — repay your loan and take the collateral at a discount — which keeps the protocol solvent. The design is unsentimental by intention: the system stays healthy even when an individual borrower does not.

## Liquid staking and restaking

- **Liquid staking:** stake ETH via a protocol that gives you a **tradable receipt token** (e.g., stETH). Your ETH keeps earning staking yield while remaining usable elsewhere in DeFi — capital isn't locked away.
- **Restaking:** re-use that staked ETH as security collateral for *additional* services to earn extra yield (the flagship example is EigenLayer). The honest description: **higher returns, higher risk** — describe it exactly that way, and no better.

## RWA: old assets, new rails

**RWA (real-world assets)** means representing off-chain financial instruments on-chain. Why institutions care:

- **settlement in minutes** instead of T+1/T+2;
- **markets that never close** — 24/7/365;
- **fractionalization** — small units of large instruments.

## Tokenized treasuries: the corrected numbers

**Tokenized treasuries / money-market funds** give holders a yield-bearing token backed by T-bills — short-term US government debt.

Per verify pass 2026-11-02, pulling rwa.xyz live (Oct 30–Nov 2, 2026): **$14.32B** of distributed value across **119 products**, with a recent 7-day APY of **3.66%**. The market's arc across the fall: **$15.65B** across 101 funds (Sept 15) → **$14.90B** across 117 (Oct 16) → **$14.32B** across 119 (Nov 2). The earlier "roughly $9–10B" framing from the foundations brief is a stale 2025-era figure — do not use it; **~$14.3B across 119 products (rwa.xyz, Nov 2, 2026)** is the number to teach.

Who leads, from the same pull:

| Product | Value (rwa.xyz, pull Oct 30–Nov 2, 2026) |
|---|---|
| Ondo **USDY** | **$2.4B** |
| **USYC** | **$2.2B** |
| BlackRock **BUIDL** (issued via Securitize) | **$2.1B** |

**Ondo is the largest platform overall (~$3.1B).** Note per verify pass 2026-11-02: BUIDL — long cited as the largest single product — is **no longer #1** as of this snapshot. Leadership has flipped repeatedly through 2026, so the safe answer to "what's the biggest?" is to date your answer and check rwa.xyz.

## Stablecoins: fiat-backed vs crypto-backed

Stablecoins are tokens **pegged to a currency**. Two backing models:

- **Fiat-backed** (USDT, USDC): hold reserves of dollars/T-bills with an issuer.
- **Crypto-backed** (e.g., DAI): lock crypto collateral in contracts, often **over-collateralized** (more collateral locked than the value borrowed).

They are arguably crypto's clearest **product-market fit**: dollar access, instant settlement, and programmability for the **~90% of the world without reliable dollar banking**.

Market size (DefiLlama API, Nov 2, 2026, per verify pass): **$298.2B** total, with USDT at **$179.3B = 60.13%** share. The 2026 peak was **$316.35B on May 20, 2026**.

## The peg is a promise

For learners: **the peg is a promise, not a law of nature.** Issuer quality and reserves matter. The natural follow-up question for any stablecoin is "what backs it, and who says so?" — that question is always in scope for a Technical Translator.

## Quick answers

- **"How big is the stablecoin market?"** → $298.2B total (Nov 2, 2026); 2026 peak was $316.35B on May 20, 2026; USDT holds 60.13%.
- **"What's the largest tokenized-treasury product?"** → Leadership flips: as of the Nov 2, 2026 pull, USDY $2.4B > USYC $2.2B > BUIDL $2.1B — check rwa.xyz for the current order.
- **"How does a DEX price trades with no staff?"** → AMM pools priced by x·y = k.
- **"Is restaking safe?"** → Higher returns, higher risk — that's the whole honest answer.

## See Also

- [What people actually use blockchains for](../ecosystem/use-cases-2026.md) — the full 2025–2026 usage map these mechanisms power, with chain-level RWA and stablecoin data
- [Memecoins & launchpads](../ecosystem/memecoins-launchpads.md) — the speculative corner of the same map
- [Perps & Hyperliquid](../ecosystem/perps-hyperliquid.md) — the trading corner, revenue leader
- [Avalanche vs the field](../ecosystem/competitive-scoreboard.md) — TVL and stablecoin standings by chain
- [BTC & ETH: the two anchors](btc-eth-anchors.md) — the staking yield that liquid staking wraps
