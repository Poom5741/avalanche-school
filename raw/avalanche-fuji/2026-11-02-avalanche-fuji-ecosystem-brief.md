# Avalanche Ecosystem Brief — Community Manager Curriculum
**Researched: November 2, 2026.** Sources: build.avax.network (Avalanche Builder Hub, the current home of docs.avax.network), avax.network / avalabs.org, ava-labs + avalanche-foundation GitHub, official blog posts, and ACP (Avalanche Community Proposal) documents. Dates on every load-bearing claim.

---

## 1. Fuji Testnet (key topic)

**What Fuji is.** Fuji is Avalanche's public testnet, the network where every mainnet upgrade rehearses first and where developers test contracts and L1s before paying real AVAX. It mirrors mainnet architecture: C-Chain (EVM), P-Chain (validators/L1 ops), X-Chain (assets). Fuji C-Chain **chain ID 43113** (0xA869), vs mainnet **43114** (0xA86A). RPC: `https://api.avax-test.network/ext/bc/C/rpc`. Explorer per current official docs: `https://explorer-test.avax.network/c-chain`. Source: [Primary Network docs, Builder Hub](https://build.avax.network/docs/primary-network) (current as of Sept 2026, post-Helicon).

**Explorer naming — important nuance for answering community questions.** The docs now list `explorer-test.avax.network`. Historically the testnet explorer was **testnet.snowtrace.io** (Snowtrace); in October 2023 the Etherscan-powered Snowtrace was sunset and replaced by an Avascan-run version ([Yahoo Finance, Oct 30–31, 2023](https://finance.yahoo.com/news/top-avalanche-block-explorer-snowtrace-114300897.html)). **`subnets.avax.network` is the L1/subnet explorer for mainnet; the testnet equivalent is `subnets-test.avax.network`** (AvaCloud Explorer). So: C-Chain txs → explorer-test.avax.network / testnet.snowtrace.io; testnet L1s → subnets-test.avax.network.

**Faucets.**
- **Official:** [faucet.avax.network](https://faucet.avax.network) — "Testnet Faucet" in Builder Hub console; open source at [github.com/ava-labs/avalanche-faucet](https://github.com/ava-labs/avalanche-faucet). Config shows drip of 2,000,000,000 nAVAX (= 2 AVAX), rate limit **1 drip per address per 24h window** (MAX_LIMIT 1, WINDOW_SIZE 1440 min). Also serves testnet L1s (WAGMI, DFK, Dexalot, etc.).
- **Core wallet faucet:** [core.app/tools/testnet-faucet](https://core.app/tools/testnet-faucet).
- **Third-party:** QuickNode ([faucet.quicknode.com/avalanche/fuji](https://faucet.quicknode.com/avalanche/fuji) — free drip, requires small *mainnet* balance as spam protection), Chainlink ([faucets.chain.link/fuji](https://faucets.chain.link/fuji) — LINK and other assets), thirdweb (0.01 AVAX/day).

**What devs do on Fuji:** deploy Solidity contracts to the C-Chain, test bridges/ICM/ICTT, and spin up or validate testnet L1s (Builder Hub has dedicated "Create L1," "Testnet Nodes," "ICM Relayer" flows on testnet — see nav at [faucet.avax.network](https://faucet.avax.network)).

**Common community-manager questions and correct answers:**
- *"Faucet is dry / I got nothing"* → official faucet is 1 drip/address/day; try Core, QuickNode, or Chainlink faucets. Testnet AVAX has **no monetary value and cannot be used on mainnet**.
- *"Is Fuji down?"* → check network status at status.avax.network before assuming user error.
- *"Why won't my transaction show?"* → most common cause: wallet on wrong chain ID (43113 vs 43114) or wrong RPC (`api.avax-test.network` vs `api.avax.network`).
- *"Why is Fuji different from mainnet?"* → upgrades activate on **Fuji first**; mainnet follows only after Fuji succeeds. During the gap, Fuji behavior can differ (e.g., Granite hit Fuji Oct 29, 2025, mainnet Nov 19, 2025).

**Recent Fuji changes (ops-relevant):** Granite (AvalancheGo v1.14-fuji, Oct 29, 2025) and Helicon (v1.15.0-fuji, **July 28, 2026**). Notable: the Helicon docs state v1.15.0-fuji **does not support C-Chain state sync once Helicon is active** on Fuji — a real gotcha for node operators. Sources: [Granite blog](https://build.avax.network/blog/granite-upgrade), [Helicon docs](https://build.avax.network/docs/primary-network/helicon-upgrade) (updated Sept 2026).

---

## 2. Major upgrades, last ~18 months (plus Etna for context)

| Upgrade | Fuji date | Mainnet date | Headline changes |
|---|---|---|---|
| **Avalanche9000 (Etna)** | Nov 2024 | **Dec 16, 2024** | Subnets → Avalanche L1s; validator economics overhaul; cheaper C-Chain gas |
| **Octane** | Mar 13, 2025 | **Apr 8, 2025** | ACP-176: dynamic gas limits & price discovery |
| **Granite** | Oct 29, 2025 | **Nov 19, 2025** | ACP-181, ACP-204, ACP-226: ICM enhancement, passkey/biometric support, dynamic block times |
| **Helicon** | Jul 28, 2026 | **Sep 22, 2026** | ACP-194 "Continuous Execution" + five more ACPs: staking economics overhaul |

**Avalanche9000 / Etna (Dec 16, 2024)** — largest upgrade in Avalanche history, bundling 7 ACPs:
- **ACP-77 "Reinventing Subnets":** subnets became sovereign **Avalanche L1s**. L1 validators no longer stake 2,000 AVAX or validate the Primary Network; instead they pay a continuous fee to the P-Chain — **minimum fee rate 512 nAVAX/s ≈ 1.33 AVAX per validator per month** when below the validator target. Validator-set management moved from the P-Chain to a **Validator Manager smart contract** on the L1. Sources: [AvaCloud Etna docs](https://developers.avacloud.io/data-api/etna), [Builder Hub Etna motivation](https://build.avax.network/blog/etna-upgrade-motivation), [ACP-125 table, avalanche-foundation/ACPs](https://github.com/avalanche-foundation/ACPs).
- **ACP-125:** C-Chain minimum base fee cut **25 nAVAX → 1 nAVAX** ([ACPs repo](https://github.com/avalanche-foundation/ACPs)).
- **ACP-131:** Cancun EIPs activated on C-Chain/Subnet-EVM.
- Net effect: >99% reduction in L1 launch cost (Ava Labs/eco coverage, e.g. [Noode, 2025](https://www.noode.com.tr/en/blog/avalanche-l1-deployment-cost-acp-77-acp-125)).

**Octane (ACP-176, mainnet Apr 8, 2025):** replaces the static 15M-gas/10s target with **dynamic gas limits** — validators vote on the target consumption rate, base fee rises/falls with demand; gas limit = 2× target. Sources: [Builder Hub Octane blog, Mar 11, 2025](https://build.avax.network/blog/octane-optimizing-c-chain-gas-fees), [ACP-176 discussion](https://github.com/avalanche-foundation/ACPs/discussions/178), [Messari](https://messari.io/copilot/share/avalanche-octane-upgrade-b7565398-da6d-4b48-80da-ee2f5ef482c7).

**Granite (mainnet Nov 19, 2025; requires AvalancheGo v1.14):**
- **ACP-181** P-Chain Epoched Views; **ACP-204** precompile for secp256r1 (unlocks passkey/biometric signing); **ACP-226** dynamic minimum block times (block cadence responds to load, works together with ACP-176). Sources: [Granite blog](https://build.avax.network/blog/granite-upgrade), [Chainstack notes](https://docs.chainstack.com/docs/avalanche-granite-upgrade).

**Helicon (mainnet Sept 22, 2026, 15:00 UTC; AvalancheGo v1.15.0+ required):**
- **ACP-194 Continuous Execution:** consensus and execution decoupled via a queue on the C-Chain — blocks are agreed first, executed in parallel; the C-Chain now runs the new Continuous Execution VM (Coreth handled pre-Helicon blocks).
- **ACP-236:** staking auto-renews at cycle end.
- **ACP-267:** validator uptime requirement **80% → 90%**.
- **ACP-273:** minimum staking duration **48h mainnet / 12h Fuji**.
- **ACP-285:** minimum staking reward consumption rate ramps from 10% to **7.5%** over 90 days post-activation (staking yield lower; projected inflation reduction ~0.5–1 percentage point).
- **ACP-283** was in the upgrade but I could not confirm its contents — **UNCERTAIN**; see [Helicon blog](https://build.avax.network/blog/helicon-upgrade) and [Helicon docs](https://build.avax.network/docs/primary-network/helicon-upgrade). Third-party summary: [Crypto Briefing, Sept 2026](https://cryptobriefing.com/avalanche-helicon-upgrade-staking-execution).

Nothing newer than Helicon has activated as of Nov 2, 2026.

---

## 3. What "Avalanche offers" builders — claims vs. reality

### Gas
- C-Chain minimum base fee is **1 nAVAX** (floor set by ACP-125, Dec 2024); actual fees are **dynamic** since Octane/ACP-176 (Apr 2025) — base fee adjusts with demand, and validators can raise the gas target (throughput) by voting rather than waiting for a hard fork ([Octane blog](https://build.avax.network/blog/octane-optimizing-c-chain-gas-fees)).
- L1s can run **custom gas tokens** and configure their own fee parameters ([Etna motivation blog](https://build.avax.network/blog/etna-upgrade-motivation)).
- All fees are burned (see [Snowpeer fee metrics](https://snowpeer.io), cited by the Foundation's channels).

### Wallets
- **Core** (core.app) is the official Avalanche-native wallet from Ava Labs: browser extension + mobile, non-custodial, with staking, swaps, bridging, Bitcoin/Ethereum/Solana support ([avalabs.org/products](https://www.avalabs.org/products)).
- **MetaMask and any EVM wallet work** — C-Chain is standard EVM; official docs ship one-click "Add to Wallet" buttons and Chainlist lists 43113/43114 ([build.avax.network/docs](https://build.avax.network/docs)).

### Sponsor (gas sponsorship / gasless) — YES, this is real, on three levels:
1. **Core "free gas":** since **March 25, 2025**, eligible Core users see zero gas on approved C-Chain transactions in the extension; core.app markets "Enjoy free gas on the Avalanche C-Chain." Sources: [The Block, Mar 25, 2025](https://www.theblock.co/news/ecosystems/2025-03-25-core-wallet-users-on-avalanche-to-no-longer-pay-gas-fees-for-most-c-chain-transactions-347996), [core.app](https://core.app).
2. **AvaCloud Gas Relayer:** managed fee-delegation for enterprise L1 deployments, listed as a built-in capability ([avalabs.org/products](https://www.avalabs.org/products)).
3. **Open standards:** Ava Labs maintains the ERC-2771-style `avalanche-evm-gasless-transaction` repo ([github.com/ava-labs](https://github.com/ava-labs/avalanche-evm-gasless-transaction)); ERC-4337 bundlers/paymasters from third parties (Openfort, Alchemy, etc.) list Avalanche support ([openfort.io](https://www.openfort.io/account-abstraction)). **ACP-209 "EIP-7702-style Set Code for EOAs"** (enables built-in tx sponsorship/batching for EOAs) is **proposed but not yet activated** — it requires a future network upgrade and is being adapted to coexist with Continuous Execution ([ACP-209 docs](https://build.avax.network/docs/acps/209-eip7702-style-account-abstraction), [Avascan proposals](https://avascan.info/staking/proposals)). Flag it as pending, not live.

### Tempo — likely a confusion; NO Avalanche connection found
"Tempo" is the **payments-focused L1 incubated by Stripe and Paradigm**, announced **September 4, 2025**. It is an independent company (Stripe & Paradigm first investors, Matt Huang CEO), EVM-compatible but built on **Reth** (Paradigm's Ethereum client) with **Simplex consensus** (Commonware), stablecoin-denominated fees via an enshrined Fee AMM, its own **TIP-20** token standard, ~0.6s finality, mainnet **March 2026**. Sources: [Paradigm blog](https://www.paradigm.xyz/writing/tempo-payments-first-blockchain), [Patrick Collison](https://www.linkedin.com/posts/patrickcollison_tempo-move-money-at-internet-speed-activity-7369705047955263488-63yq), [Everstake explainer, Jul 22, 2026](https://everstake.com/resources/blog/what-is-tempo-stripe-and-paradigms-stablecoin-payments-blockchain-explained). **I found zero evidence** that Tempo is built on Avalanche, uses Avalanche tech, or has an official Avalanche/Ava Labs partnership, and **no Avalanche-native feature named "tempo" exists** in docs, ACPs, or GitHub. **UNCERTAIN only in the trivial sense:** if the curriculum says "Tempo support," it almost certainly misattributes Stripe's Tempo to Avalanche — recommend removing it or correcting it. Tempo uses TIP-20 (Tempo's standard), not Avalanche ACPs.

### ERC standards
- **ERC-20 / 721 / 1155** all work as usual on C-Chain and any EVM L1 — Avalanche is plain EVM here; there is no Avalanche fork of these.
- **ERC-4337** account abstraction is live via third-party bundler/paymaster infrastructure (see "Sponsor" above).
- **Avalanche-specific standards live in ACPs, not "ARCs":** the Avalanche Foundation's GitHub hosts the **ACPs repo** ([github.com/avalanche-foundation](https://github.com/avalanche-foundation)) — there is **no official "ARC" (Avalanche Request for Comments) standards repo** from the Foundation. Caution: "ARC-20" that appears in search results belongs to **Metal Blockchain** (an Avalanche fork) for its native tokens — not an Avalanche Foundation standard. A community "ASC-20" inscription standard was only a discussion thread ([ACPs discussion #55](https://github.com/avalanche-foundation/ACPs/discussions/55)) — minor.
- Standards-adjacent items worth teaching: **ACP-204 secp256r1 precompile** (Granite, Nov 2025) enables passkey/WebAuthn-style signatures; **ACP-209** (pending) brings EIP-7702-style EOAs.

---

## 4. L1 architecture now

**Subnets → L1s transition.** Since Etna (Dec 16, 2024), the old subnet model and the new L1 model coexist: legacy subnets (validators must be Primary Network validators, no continuous fee) vs. **L1s (own validator sets, pay a continuous per-validator fee, can be permissioned or permissionless)**. Validator-set management runs through a **Validator Manager smart contract** deployed on the L1 ([AvaCloud Etna docs](https://developers.avacloud.io/data-api/etna)). Existing subnets got a transition window; new launches use the L1 flow.

**Validator requirements (what got cheaper).**
- **Primary Network validators: still 2,000 AVAX minimum stake** — unchanged, confirmed on the current post-Helicon docs ([build.avax.network/docs/primary-network](https://build.avax.network/docs/primary-network)).
- **L1 validators: no stake, no Primary Network sync** — just the continuous fee (min **512 nAVAX/s ≈ 1.33 AVAX/validator/month**). This is the ">99.9% cheaper" headline.
- Helicon tweaks (Sept 2026): min P-Chain staking duration now **48h mainnet / 12h Fuji** (ACP-273), uptime bar **90%** (ACP-267), auto-renewal (ACP-236).

**Avalanche Warp Messaging → ICM (current status).** AWM is now branded **Avalanche Interchain Messaging (ICM)**: BLS-signature-aggregated messages signed by an L1's validator set, verifiable by any other L1 — no external bridge. **Teleporter** is the smart-contract framework on top; **ICTT** (Interchain Token Transfer) handles burn-and-mint token movement. In production use by Beam and DeFi Kingdoms, default on AvaCloud L1s; ICM fees are now tracked as a metric ([Builder Hub ICM overview](https://build.avax.network/docs/cross-chain/avalanche-warp-messaging/overview), [avalanchego warp README](https://github.com/ava-labs/avalanchego/blob/master/vms/platformvm/warp/README.md)). Granite enhanced ICM ([Granite blog](https://build.avax.network/blog/granite-upgrade)).

**How a team launches an L1 (2026 path).** Official tooling: **Avalanche CLI** + Builder Hub console flow ("Create L1" → "My L1 Dashboard"), with **testnet-first infrastructure**: Fuji testnet nodes, testnet faucet, **ICM Relayer** setup, then mainnet conversion ([faucet.avax.network nav](https://faucet.avax.network)); managed alternative is **AvaCloud**. A typical flow: deploy an EVM chain on Fuji via CLI, register validators via the Validator Manager contract, verify ICM/ICTT messaging, then convert subnet→L1 on mainnet paying the continuous validator fee.

---

### Quick "correction list" for the curriculum
1. "subnets.avax.network" is the **mainnet L1** explorer; testnet L1s live on `subnets-test.avax.network`; Fuji C-Chain explorer is `explorer-test.avax.network` (formerly testnet.snowtrace.io).
2. "Tempo support" — remove or correct; Tempo is Stripe/Paradigm's chain, no Avalanche relationship found.
3. "ARC standards" — not an Avalanche Foundation thing; Avalanche protocol standards are **ACPs**; ARC-20 is Metal Blockchain's standard.
4. "Sponsor" — real: Core free gas (Mar 2025), AvaCloud Gas Relayer, ERC-4337/2771 tooling; ACP-209 (EIP-7702-style) still pending.
5. Anything describing "subnets" as the current model should be updated to **L1s** (Etna, Dec 2024), and fee/wallet content should reflect dynamic fees (Apr 2025) and Helicon staking changes (Sept 2026).
