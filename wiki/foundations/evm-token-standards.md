# The EVM and token standards

> Sources: EIP-20, EIP-721, EIP-1155, EIP-4337, EIP-7702 (eips.ethereum.org); ethereum.org, 2026 (EVM; accounts; Pectra); eco.com support article, Oct 6, 2026; verify pass, 2026-11-02
> Raw: [brief](../../raw/foundations/2026-11-02-blockchain-foundations-brief.md); [verify report](../../raw/foundations/2026-11-02-verify-report-foundations-brief.md)
> Updated: 2026-11-02

## Overview

Module 4 covers the vocabulary developers say constantly: **EVM**, **ERC-20/721/1155/4337**, and **EIP-7702**. After this article a learner can define each standard in one sentence with an example, explain why one contract can deploy across many chains, and avoid the most common naming trap in the ecosystem — calling the standard "ERC-7702" when it is formally EIP-7702.

## What "EVM-compatible" means

The **Ethereum Virtual Machine (EVM)** is Ethereum's computation engine — the sandboxed computer that executes smart-contract bytecode (the simple instruction language contracts are compiled into; "sandboxed" means the code runs inside a box and can't reach outside it).

A chain that is **"EVM-compatible"** implements that same execution environment. That means a contract compiled once can be deployed near-unchanged on **Arbitrum, Base, Polygon**, and other EVM-compatible chains — and the same wallets, libraries, and audits work everywhere. This is why the multi-chain landscape mostly speaks one language.

## The ERC trick: agreed function names

Token standards work because contracts agree to the same **function names** — so wallets and marketplaces know how to talk to *any* token automatically, without custom code per token. The numbers (20, 721, …) are just the order the standards were proposed in.

## ERC-20: fungible tokens

**Fungible** = identical, divisible units — every dollar bill is as good as any other. Example: the stablecoins **USDC** (native ERC-20 issued by Circle) and **USDT** (ERC-20 on Ethereum) are ERC-20s.

## ERC-721: NFTs

Each token is **unique and non-divisible** — one-of-one. Examples: **ENS domain names** (each `.eth` name is an ERC-721) and digital art/collections.

## ERC-1155: semi-fungible, built for games

The "multi-token" standard: **one contract mints many token types**, with each ID fungible within itself. The canonical example is gaming: 100 identical swords plus 1 legendary sword, all in one contract. Its authors include gaming company **Enjin**'s team (Witek Radomski and Eric Binet, per verify pass 2026-11-02).

## ERC-4337: smart accounts without a protocol change

**Account abstraction.** ERC-4337 makes **smart accounts** (contracts acting as wallets) work without protocol changes, via a separate mempool handled by two roles:

- **Bundlers** — operators who package many users' operations (UserOperations) into one transaction.
- **Paymasters** — in the EIP's own words, a "helper contract that agrees to pay for the transaction."

The problem it solves: normal EOAs are all-or-nothing single-key accounts. Smart accounts enable:

- **batching** — approve + swap in one click;
- **gasless UX** — pay fees in the token being traded, or have the app sponsor fees;
- **custom login/recovery** — passkeys, social recovery.

## EIP-7702 (not "ERC-7702")

Naming, verified: the standard is formally **EIP-7702, "Set Code for EOAs"** — Status: Final, Standards Track: Core. **"ERC-7702" is only the common colloquial name**; there is no separate ERC-7702 document (verify pass 2026-11-02).

What it does: it lets a regular EOA **permanently adopt smart-contract code** via a signed authorization — bringing 4337-style powers (batching, sponsorship, sub-key permissions) to *existing* wallet addresses, rather than requiring users to migrate to new smart-account addresses.

It went live with Ethereum's **Pectra upgrade on May 7, 2025** (activated epoch 364032, 07-May-2025 10:05 UTC, per verify pass).

## Cheat sheet

| Standard | What it is | Example |
|---|---|---|
| ERC-20 | fungible tokens (identical, divisible) | USDC, USDT |
| ERC-721 | NFTs (unique, non-divisible) | ENS `.eth` names, digital art |
| ERC-1155 | semi-fungible multi-token, built for games | 100 identical swords + 1 legendary, one contract (Enjin) |
| ERC-4337 | smart accounts via bundlers + paymasters | batching, gasless UX, passkeys/social recovery |
| EIP-7702 | EOAs adopt contract code (Final, Core) | live with Pectra, May 7, 2025 |

## Quick answers

- **"Is it ERC-7702 or EIP-7702?"** → Formally **EIP-7702** ("Set Code for EOAs"); "ERC-7702" is colloquial — no separate ERC document exists.
- **"Why does the same wallet work on many chains?"** → EVM compatibility: the same execution environment everywhere.
- **"What's the difference between ERC-4337 and EIP-7702?"** → 4337 creates smart accounts alongside existing EOAs; 7702 lets an existing EOA adopt smart-account powers in place.

## See Also

- [Wallets and sponsorship on Avalanche](../avalanche/wallets-sponsorship.md) — these account-abstraction ideas implemented on Avalanche (ACP-204 passkeys, ERC-4337)
- [A mental model of a blockchain](blockchain-mental-model.md) — EOAs vs contract accounts, the groundwork for all of this
- [Gas in the dynamic era](../avalanche/dynamic-gas.md) — gas on the EVM-compatible C-Chain, where these standards run
- [Fuji testnet](../avalanche/fuji-testnet.md) — where developers actually try deployed contracts
