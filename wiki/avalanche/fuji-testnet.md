# Fuji testnet field guide

> Sources: Avalanche Builder Hub Primary Network docs (current as of Sept 2026); ava-labs/avalanche-faucet config.json; status.avax.network; verify pass 2026-11-02
> Raw: [brief](../../raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md); [verify report](../../raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md)
> Updated: 2026-11-02

## Overview

Fuji is Avalanche's public **testnet** — the network where every mainnet upgrade rehearses first and where developers test contracts and L1s before paying real AVAX. It mirrors mainnet architecture: C-Chain (EVM), P-Chain (validators/L1 ops), X-Chain (assets). This article collects the numbers people ask for daily — chain IDs, RPC, explorers, faucets — plus the four most common community questions and their correct answers.

## Network parameters

| Parameter | Fuji (testnet) | Mainnet |
|---|---|---|
| C-Chain chain ID | **43113** (0xA869) | **43114** (0xA86A) |
| C-Chain RPC | `https://api.avax-test.network/ext/bc/C/rpc` | `api.avax.network` |

## Explorers — which one for what

| What they're looking at | Where to look |
|---|---|
| Fuji C-Chain transactions | `explorer-test.avax.network/c-chain` (current official name) |
| Historic testnet explorer name | testnet.snowtrace.io — the Etherscan-powered Snowtrace was sunset (announced Oct 30, 2023; shut down Nov 30, 2023, per verify) and replaced by an Avascan-run version |
| Testnet L1s | `subnets-test.avax.network` |
| Mainnet L1s | `subnets.avax.network` |

Rule of thumb from the docs: C-Chain txs → explorer-test.avax.network; testnet L1s → subnets-test.avax.network. "subnets" in the name means the L1/subnet explorer — and the testnet one gets the `-test` variant.

## Faucets

**Official: faucet.avax.network** — the "Testnet Faucet" in the Builder Hub console; open source at github.com/ava-labs/avalanche-faucet.

- Drip: **2 AVAX** per drip (config value 2,000,000,000 nAVAX; the verify pass saw `DRIP_AMOUNT: 2`, `DECIMALS 18`).
- Rate limit: **1 drip per address per 24h window** (`MAX_LIMIT 1`, `WINDOW_SIZE 1440` min).
- It also serves testnet **L1s**. The current config lists **DFK, Beam, Dispatch, Echo, PLYR, Kite**, etc. — per verify pass 2026-11-02, **WAGMI and Dexalot chains are gone** from the faucet (Dexalot survives only as an ERC-20 drip). Older docs listing WAGMI/Dexalot are stale.

**Core wallet faucet:** core.app/tools/testnet-faucet (URL confirmed live in the verify pass).

**Third-party:** the brief lists QuickNode (free drip, requires a small *mainnet* balance as spam protection), Chainlink (LINK and other assets), and thirdweb (0.01 AVAX/day). Caution: the verify pass **could not load these pages** — these specifics are **unconfirmed; check them before repeating**.

## What developers do on Fuji

Deploy Solidity contracts to the C-Chain, test bridges/ICM/ICTT, and spin up or validate testnet L1s. Builder Hub has dedicated testnet flows: "Create L1," "Testnet Nodes," "ICM Relayer."

## The four most common questions (and correct answers)

1. **"The faucet is dry / I got nothing."** → The official faucet is 1 drip/address/day; try the Core, QuickNode, or Chainlink faucets. And say the key fact out loud: **testnet AVAX has no monetary value and cannot be used on mainnet.**
2. **"Is Fuji down?"** → Check network status at **status.avax.network** before assuming user error (the status page was confirmed in the verify pass).
3. **"Why won't my transaction show?"** → Most common cause: the wallet is on the wrong chain ID (**43113** vs **43114**) or the wrong RPC (`api.avax-test.network` vs `api.avax.network`).
4. **"Why is Fuji different from mainnet?"** → Upgrades activate on **Fuji first**; mainnet follows only after Fuji succeeds. During the gap behavior differs — e.g., Granite hit Fuji Oct 29, 2025, mainnet Nov 19, 2025.

## Recent Fuji changes (ops-relevant)

- **Granite**: AvalancheGo **v1.14-fuji**, **Oct 29, 2025**.
- **Helicon**: **v1.15.0-fuji**, **Jul 28, 2026** — and a real gotcha for node operators: the Helicon docs state **v1.15.0-fuji does not support C-Chain state sync once Helicon is active** on Fuji.

## See Also

- [Reading the upgrade timeline](upgrade-timeline.md) — why Fuji always goes first
- [L1s after Etna](l1s-after-etna.md) — the testnet-first half of every L1 launch
- [The Primary Network](primary-network-architecture.md) — the architecture Fuji mirrors (12h minimum stake on Fuji)
