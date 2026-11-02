# Knowledge Base Index

Wiki articles are compiled from verified `raw/` documents only. Mapping to curriculum modules lives in the Module column.

| Article | Topic | Module | Summary | Updated |
|---|---|---|---|---|
| [primary-network-architecture](avalanche/primary-network-architecture.md) | Primary Network: chains, validators, staking | 5 | C/P/X-Chain roles; 2,000 AVAX minimum stake (unchanged post-Helicon); Helicon staking changes: 90% uptime, 48h/12h min stake, auto-renew, 10%→7.5% ramp | 2026-11-02 |
| [l1s-after-etna](avalanche/l1s-after-etna.md) | L1s after Etna | 6 | Subnets → sovereign L1s (Dec 16, 2024); 512 nAVAX/s ≈ 1.33 AVAX/validator/month; Validator Manager contract; >99% launch-cost drop | 2026-11-02 |
| [dynamic-gas](avalanche/dynamic-gas.md) | Gas in the dynamic era | 7 | Floor history 25→1 nAVAX (ACP-125) → 1e-18 AVAX (ACP-176) → dynamic minimum (ACP-283); validators vote on target (R=2·T, C=10·T); custom gas tokens; fee burn | 2026-11-02 |
| [wallets-sponsorship](avalanche/wallets-sponsorship.md) | Wallets & sponsorship | 8 | Core + free C-Chain gas (Mar 25, 2025); MetaMask/Chainlist; passkeys (ACP-204); ERC-2771 repo; ERC-4337; ACP-209 pending | 2026-11-02 |
| [icm-crosschain](avalanche/icm-crosschain.md) | Cross-chain: ICM | 9 | AWM → ICM branding; Teleporter; ICTT burn-and-mint; icm-contracts archived Dec 3, 2025 → icm-services | 2026-11-02 |
| [upgrade-timeline](avalanche/upgrade-timeline.md) | Upgrade timeline | 10 | Etna → Octane → Granite → Helicon with Fuji-first rehearsal; what an ACP is and where to read proposals | 2026-11-02 |
| [fuji-testnet](avalanche/fuji-testnet.md) | Fuji testnet | 13 | Chain IDs 43113/43114, RPC, explorers, faucet 2 AVAX / 1 drip per 24h + L1 list (DFK/Beam/Dispatch/Echo/PLYR), common Q&A, status page | 2026-11-02 |
| [tempo-myth](avalanche/tempo-myth.md) | Myth-busting | 12 | Tempo = Stripe/Paradigm (Sep 4, 2025), no Avalanche connection (best-effort negative); ARC myth; subnets→L1s; answer script | 2026-11-02 |
| [use-cases-2026](ecosystem/use-cases-2026.md) | 2025–2026 usage map | 3 | Trading dominates revenue (perps ≈$2.7–3.0T FY2025; pump.fun $1B by Mar 2026); DeFi $85.35B & peak $127.2B Jan 18, 2026; treasuries ~$15B; stablecoins ~$295B; "app = chain" pattern; both institutional wins and consumer weakness are true | 2026-11-02 |
| [perps-hyperliquid](ecosystem/perps-hyperliquid.md) | Hyperliquid deep-dive | 3 | HyperCore/HyperEVM; FY2025 ≈ $2.7–3.0T ($633B = Q1 2026 alone, per verify); HYPE airdrop Nov 29, 2024, ATH $97.96 Sept 23, 2026; 56% share caveat; Avalanche economics comparison | 2026-11-02 |
| [memecoins-launchpads](ecosystem/memecoins-launchpads.md) | Memecoins & launchpads | 3 | pump.fun bonding curve + graduation; $1B cumulative Mar 12, 2026; 2025 revenue $620–664M (DefiLlama revision); ~98.5% die; four.meme/Clanker; no dominant Avalanche launchpad | 2026-11-02 |
| [competitive-scoreboard](ecosystem/competitive-scoreboard.md) | Avalanche vs the field | 11 | Nov 2, 2026 tables (Avalanche $584M rank #12 vs Solana/ETH/L2s/Hyperliquid); counter-narratives (~81 L1s, ICM, upgrade cadence, FIFA/Apollo/NYSE); honest criticisms; "what it still has to prove" | 2026-11-02 |
| [blockchain-mental-model](foundations/blockchain-mental-model.md) | Blockchain mental model | 0 | Shared append-only ledger by analogy: blocks chained by hashes, signed transactions, EOA vs contract accounts, wallet = key manager, gas & the EIP-1559 burn, double-spend → why consensus exists | 2026-11-02 |
| [btc-eth-anchors](foundations/btc-eth-anchors.md) | BTC & ETH anchors | 1 | Bitcoin: 21M cap (MAX_MONEY in src/consensus/amount.h), halvings (next ~mid-April 2028, est. Apr 8–14), PoW security budget + Cambridge index; Ethereum: Merge Sep 15, 2022, PoS mechanics (2,048 ETH cap from Pectra/EIP-7251), ~881k validators, finality ~13 min; "digital gold" vs "platform asset" labeled as narratives | 2026-11-02 |
| [consensus-zk-vocabulary](foundations/consensus-zk-vocabulary.md) | Consensus + ZK vocabulary | 2 | PoW vs PoS as contested tradeoffs; finality; optimistic rollups (~7-day challenge window + fraud proofs) vs ZK-rollups (validity proofs); validium/volition; ZK beyond rollups; Scroll-decline & Starknet-PQ caveats | 2026-11-02 |
| [evm-token-standards](foundations/evm-token-standards.md) | EVM + token standards | 4 | EVM compatibility; ERC-20/721/1155/4337 with examples (USDC/USDT, ENS, Enjin gaming, bundlers/paymasters); formally EIP-7702 (not ERC-7702), live with Pectra May 7, 2025 | 2026-11-02 |
| [defi-rwa-primer](foundations/defi-rwa-primer.md) | DeFi + RWA primer | 3 (support) | AMM x·y=k; lending/liquidation; liquid staking/restaking; RWA rationale; tokenized treasuries $14.3B / 119 products (rwa.xyz, Nov 2, 2026; USDY $2.4B / USYC $2.2B / BUIDL $2.1B); stablecoins $298.2B, peak $316.35B (May 20, 2026), peg-is-a-promise | 2026-11-02 |

Topic sections:

- `avalanche/` — Avalanche protocol, upgrades, L1s, Fuji
- `ecosystem/` — industry-wide foundations and use cases
- `foundations/` — industry-wide blockchain basics (Part A: mental model, BTC/ETH, consensus/ZK, EVM/ERCs, DeFi/RWA)
