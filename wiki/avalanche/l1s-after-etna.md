# L1s after Etna: subnets became sovereign chains

> Sources: ava-labs avalanchego release v1.12.0 (Dec 16, 2024); ACP-77 "Reinventing Subnets" (avalanche-foundation/ACPs); AvaCloud Etna docs; verify pass 2026-11-02
> Raw: [brief](../../raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md); [verify report](../../raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md)
> Updated: 2026-11-02

## Overview

Before December 2024, Avalanche's secondary networks were called **subnets**, and every subnet validator also had to validate the Primary Network with a 2,000 AVAX stake. The Etna upgrade (mainnet **Dec 16, 2024**, at 12 PM ET per the verify pass) rebuilt them as **Avalanche L1s** with their own validator sets and a tiny continuous fee instead of a big locked stake. It was the largest upgrade in Avalanche history, and it cut L1 launch cost by more than 99%.

## The upgrade in one look

- Etna bundled **6 ACPs: ACP-77, 103, 118, 125, 131, 151** (per verify pass 2026-11-02 — the avalanchego v1.12.0 release notes list six; earlier drafts said seven).
- **ACP-77 "Reinventing Subnets"** is the one that turned subnets into L1s.
- Also in the bundle: **ACP-125** cut the C-Chain base fee (see [Gas in the dynamic era](dynamic-gas.md)); **ACP-131** activated the Cancun EIPs on C-Chain/Subnet-EVM.

## What changed for validators (ACP-77)

| | Old subnet model | New L1 model (post-Etna) |
|---|---|---|
| Stake | 2,000 AVAX minimum, Primary Network validator required | **No stake** |
| Primary Network sync | Required | Not required |
| Cost | — | Continuous fee to the P-Chain: minimum **512 nAVAX/s ≈ 1.33 AVAX per validator per month** when below the validator target |
| Who manages the validator set | The P-Chain | A **Validator Manager smart contract** on the L1 itself |
| Permissioning | — | L1s can be **permissioned or permissionless** |

The fee is **continuous** — think rent per second, not a deposit — and it applies when the validator set is below the validator target.

## Old subnets did not vanish

Since Etna, the old subnet model and the new L1 model **coexist**: legacy subnets still require validators to be Primary Network validators, with no continuous fee. Existing subnets got a transition window; new launches use the L1 flow. So "subnets are dead" is wrong — "subnets are the old name for the current model" is closer.

## How a team launches an L1 (the 2026 path)

Official tooling is **Avalanche CLI** plus the Builder Hub console flow ("Create L1" → "My L1 Dashboard"), and it is **testnet-first**: Fuji testnet nodes, testnet faucet, ICM Relayer setup, then mainnet conversion. The managed alternative is **AvaCloud**. A typical flow: deploy an EVM chain on Fuji via the CLI, register validators via the Validator Manager contract, verify ICM/ICTT messaging, then convert subnet→L1 on mainnet paying the continuous validator fee.

## Quick answers

- **"How much does it cost to launch an L1 now?"** → No 2,000 AVAX stake; validators pay 512 nAVAX/s ≈ 1.33 AVAX per validator per month below the target — a **>99% reduction in L1 launch cost** versus the old model.
- **"Can an L1 have its own fee token?"** → Yes — L1s can run custom gas tokens and configure their own fee parameters.
- **"Where do L1 validators get managed?"** → Through the Validator Manager smart contract on the L1 itself, not on the P-Chain.

## See Also

- [The Primary Network](primary-network-architecture.md) — the 2,000 AVAX rule this article contrasts with
- [ICM: cross-chain messaging](icm-crosschain.md) — the ICM/ICTT verification step in the launch flow
- [Fuji testnet field guide](fuji-testnet.md) — the testnet-first half of every launch
- [Gas in the dynamic era](dynamic-gas.md) — ACP-125 and custom gas tokens
