# Dev-question drills — starter bank

The learner's end goal: answer these unaided, correctly, in their own words. Each entry: the question as a dev would really ask it, a reference answer skeleton (facts must match the linked wiki article — never invent numbers), and the module it belongs to.

Format for future entries: one file per batch, newest last. Mark each answer with the wiki article it relies on; if the article doesn't exist yet, mark `[pending-verify: source]`.

---

## Q1 — "I want to launch my own chain on Avalanche. How much do I need to stake?" (Module 6)

Reference answer skeleton:
- No stake anymore since Etna/Avalanche9000 (Dec 16, 2024) — L1 validators pay a continuous fee instead: min 512 nAVAX/s ≈ **1.33 AVAX per validator per month** when below the validator target.
- Validator set is managed by a Validator Manager smart contract on the L1 itself.
- Distinguish from Primary Network validators: those still need 2,000 AVAX minimum stake.
- Wiki ref: [pending — `wiki/avalanche/l1s-after-etna.md`]

## Q2 — "Does Avalanche support Tempo?" (Module 12)

Reference answer skeleton:
- Tempo is a separate payments L1 incubated by Stripe + Paradigm (announced Sept 4, 2025; mainnet Mar 18, 2026). Not built on Avalanche; no official partnership; its standards are TIP-20, its consensus Simplex.
- Pivot: Avalanche's payments answer is launching your own L1 with a custom gas token (can be a stablecoin) since Etna.
- Wiki ref: [pending — `wiki/avalanche/tempo-myth.md`]

## Q3 — "Why won't my testnet transaction show up?" (Module 13)

Reference answer skeleton:
- Most common cause: wallet on wrong chain ID (Fuji C-Chain = **43113**, mainnet = **43114**) or wrong RPC (`api.avax-test.network` vs `api.avax.network`).
- Check status.avax.network before assuming network outage.
- Wiki ref: [pending — `wiki/avalanche/fuji-testnet.md`]

## Q4 — "The faucet gave me nothing. Is Fuji dead?" (Module 13)

Reference answer skeleton:
- Official faucet (faucet.avax.network) drips 2 AVAX per address per 24h window — rate-limited, not dry.
- Alternatives: Core wallet faucet, QuickNode, Chainlink faucets.
- Testnet AVAX has no monetary value and cannot be used on mainnet.
- Wiki ref: [pending — `wiki/avalanche/fuji-testnet.md`]

## Q5 — "What's Avalanche's gas fee right now? Is it expensive?" (Module 7)

Reference answer skeleton:
- Fee floor history: cut 25 → 1 nAVAX by ACP-125 (Dec 2024); since Octane (ACP-176, Apr 2025) the floor is 1e-18 AVAX, and Helicon's ACP-283 (Sept 2026) makes the minimum gas price dynamic by stake-weighted validator preference. [corrected by verify pass 2026-11-02]
- Fees adjust with demand — validators vote on the gas target, no hard fork needed.
- L1s can set their own gas token and fee parameters.
- Wiki ref: [pending — `wiki/avalanche/dynamic-gas.md`]

## Q6 — "Is Avalanche still relevant? TVL looks dead." (Module 11)

Reference answer skeleton:
- Both facts are true: consumer metrics are weak (TVL ~$587M, rank #13, Nov 2026) AND the institutional pipeline is the strongest ever (FIFA chain since May 2025 + World Cup 2026 ticketing, Apollo $50M fund, NYSE tokenization tests, ~$1B RWA AUM).
- The honest framing: Avalanche bet on institutions launching their own L1s; the retail wave (memecoins, perps) went to Solana/Hyperliquid.
- Give dates and sources, never spin.
- Wiki ref: [pending — `wiki/avalanche/competitive-scoreboard.md`]

## Q7 — "Which wallets work on Avalanche?" (Module 8)

Reference answer skeleton:
- Core (Ava Labs' official wallet; free gas on approved C-Chain txs since Mar 25, 2025), any EVM wallet incl. MetaMask (add chain via Chainlist), passkey/biometric signing enabled by ACP-204 (Granite, Nov 2025).
- Wiki ref: [pending — `wiki/avalanche/wallets-sponsorship.md`]

## Q8 — "How do tokens move between Avalanche L1s without a bridge?" (Module 9)

Reference answer skeleton:
- ICM (Avalanche Interchain Messaging, formerly Warp Messaging): validator-signed messages verified natively by other L1s; Teleporter is the contract framework; ICTT handles burn-and-mint token transfers.
- Wiki ref: [pending — `wiki/avalanche/icm-crosschain.md`]

## Q9 — "What's the latest Avalanche upgrade?" (Module 10)

Reference answer skeleton:
- Helicon (mainnet Sept 22, 2026): Continuous Execution (ACP-194) + staking changes (90% uptime, 48h min stake, auto-renew, yield ramp to 7.5% consumption rate). Upgrades always hit Fuji first.
- Wiki ref: [pending — `wiki/avalanche/upgrade-timeline.md`]

## Q10 — "What are people even using blockchains for in 2026?" (Module 3)

Reference answer skeleton:
- Trading & speculation lead revenue: perps (Hyperliquid ~$633B volume in 2025), memecoins (pump.fun $1B cumulative revenue by Mar 2026, but ~98.5% of tokens die); plus the serious rails: stablecoins (~$295B supply), tokenized treasuries (~$15B), institutional RWA (~$39B total).
- Wiki ref: [pending — `wiki/ecosystem/use-cases-2026.md`]
