# Wallets and gas sponsorship

> Sources: avalabs.org products page; The Block, Mar 25, 2025; ava-labs/avalanche-evm-gasless-transaction; build.avax.network ACP-209 docs; Granite blog; verify pass 2026-11-02
> Raw: [brief](../../raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md); [verify report](../../raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md)
> Updated: 2026-11-02

## Overview

Avalanche's C-Chain is standard EVM, so **any EVM wallet works — including MetaMask** — while **Core** is the official Avalanche-native wallet from Ava Labs. On top of that, gas sponsorship exists on three levels (Core free gas, the AvaCloud Gas Relayer, and open standards), and the passkey era started with ACP-204 in Granite. One item is pending, not live: **ACP-209**.

## Core — the official wallet

Core comes from Ava Labs: browser extension + mobile, **non-custodial**, with built-in staking, swaps, and bridging — and it supports Bitcoin, Ethereum, and Solana alongside Avalanche.

## Free gas on the C-Chain (since Mar 25, 2025)

Since **March 25, 2025**, eligible Core users see **zero gas on approved C-Chain transactions** in the extension. Core markets this as "Enjoy free gas on the Avalanche C-Chain." (Verify note, 2026-11-02: the original The Block article could not be fetched, but its URL slug embeds 2025-03-25, corroborating the date.)

## MetaMask and any EVM wallet

The C-Chain is standard EVM, so MetaMask and any EVM wallet work. Official docs ship one-click "Add to Wallet" buttons, and **Chainlist lists both chain IDs: 43113** (Fuji) **and 43114** (mainnet).

## Sponsorship is real — three levels

| Level | What | Status |
|---|---|---|
| 1. Core "free gas" | Zero gas on approved C-Chain txs for eligible users | Live since Mar 25, 2025 |
| 2. AvaCloud Gas Relayer | Managed fee-delegation for enterprise L1 deployments | Listed as a built-in capability |
| 3. Open standards | ERC-2771-style `avalanche-evm-gasless-transaction` repo (Ava Labs); ERC-4337 bundlers/paymasters from third parties (Openfort, Alchemy, etc.) | Live |

## Passkeys: ACP-204 (Granite, Nov 2025)

Granite (mainnet Nov 19, 2025) shipped **ACP-204**, a precompile for **secp256r1** — the curve behind passkey/biometric, WebAuthn-style signing. This is why "can Avalanche do passkeys?" is now a yes.

## Pending, not live: ACP-209

**ACP-209 "EIP-7702-style Set Code for EOAs"** would enable built-in transaction sponsorship and batching for EOAs. Its status: **proposed but not yet activated** — it requires a future network upgrade and is being adapted to coexist with Continuous Execution. The correct community answer is "ACP-209 is pending, not live."

## Token standards, one line each

- **ERC-20 / 721 / 1155** work as usual — Avalanche is plain EVM here, no forks of these.
- **ERC-4337** account abstraction is live via third-party bundler/paymaster infrastructure.
- Avalanche protocol standards live in **ACPs**, not "ARCs" — see [The Tempo myth](tempo-myth.md) for that mix-up.

## See Also

- [Gas in the dynamic era](dynamic-gas.md) — what the fees being sponsored actually are now
- [Reading the upgrade timeline](upgrade-timeline.md) — where ACP-204 (Granite) and ACP-209 (pending) fit
- [Fuji testnet field guide](fuji-testnet.md) — chain IDs for wallet setup questions
- [The Tempo myth](tempo-myth.md) — the "ARC standards" myth
