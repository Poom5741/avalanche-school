# The Primary Network: three chains, validators, and staking

> Sources: Ava Labs Builder Hub Primary Network docs (current as of Sept 2026); avalanche-foundation/ACPs (Helicon parameters); verify pass 2026-11-02
> Raw: [brief](../../raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md); [verify report](../../raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md)
> Updated: 2026-11-02

## Overview

Avalanche's home base is the **Primary Network**, and Fuji (the testnet) mirrors its architecture — so learning this article teaches both networks at once. The Primary Network runs three chains with different jobs (C-Chain, P-Chain, X-Chain) and one validator set secured by staking AVAX. The Helicon upgrade (mainnet Sept 22, 2026, 15:00 UTC) rewrote several staking rules, so this article records the current numbers a Technical Translator needs to quote.

## The three chains, one line each

| Chain | Role (per current docs) |
|---|---|
| C-Chain | EVM — Solidity contracts are deployed here |
| P-Chain | Validators and L1 operations |
| X-Chain | Assets |

The docs describe the X-Chain's role with the single word "assets" — that narrow scope is all the current sources commit to, so don't embellish it in answers.

## Validators: the 2,000 AVAX rule

- To validate the **Primary Network**, a validator must stake a minimum of **2,000 AVAX**. This number survived every upgrade — the verify pass (2026-11-02) confirmed it on the current post-Helicon docs.
- This rule applies **only** to the Primary Network. L1 validators since Etna stake nothing at all — they pay a small continuous fee instead (see [L1s after Etna](l1s-after-etna.md)). Mixing these two rules up is one of the most common mistakes in community answers.

## Staking rules after Helicon

Helicon activated on mainnet **Sept 22, 2026, 15:00 UTC** and requires **AvalancheGo v1.15.0+**. Four of its ACPs changed staking economics:

| ACP | What changed | New value |
|---|---|---|
| ACP-267 | Validator uptime requirement | **80% → 90%** |
| ACP-273 | Minimum staking duration | **48h mainnet / 12h Fuji** |
| ACP-236 | Staking auto-renews at cycle end | — |
| ACP-285 | Minimum staking reward consumption rate ramps over 90 days post-activation | **from 10% to 7.5%** |

The brief notes staking yield is lower as a result of the ACP-285 ramp.

Helicon's other headline change, **ACP-194 "Continuous Execution"**, is not a staking change — see [the upgrade timeline](upgrade-timeline.md) for it.

## Fees are burned

All fees are burned — they do not pool anywhere as revenue.

## Quick answers for the community

- **"How much AVAX do I need to validate?"** → 2,000 AVAX minimum for the Primary Network.
- **"Do I need 2,000 AVAX to run an L1 validator?"** → No — since Etna, L1 validators stake nothing and pay a continuous fee instead (512 nAVAX/s ≈ 1.33 AVAX per validator per month below the validator target).
- **"What uptime do validators need now?"** → 90% since Helicon (it was 80% before).

## See Also

- [L1s after Etna](l1s-after-etna.md) — where the 2,000 AVAX rule does *not* apply
- [Gas in the dynamic era](dynamic-gas.md) — what happens to the fees users pay
- [Reading the upgrade timeline](upgrade-timeline.md) — when Helicon's changes landed and how to read the next upgrade
- [Fuji testnet field guide](fuji-testnet.md) — the testnet mirror of all of this (12h minimum stake, chain ID 43113)
