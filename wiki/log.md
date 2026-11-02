# Wiki Log

## [2026-11-03] lint | 66 fidelity suspects reviewed, 0 real mismatches
- Ran check_evidence.py: 0 evidence errors, 0 unreferenced raw files
- All 66 fidelity suspects judged: FAQ headers, verbatim raw quotes, or correction-context mentions (spot-checked "1 nAVAX" in dynamic-gas.md and "$587.1M/#13" in competitive-scoreboard.md — both appear only as explicitly-marked outdated/corrected teaching content)
- Verdict: grounding invariant holds across all 17 articles

## [2026-11-02] init | repository scaffolding
- Created raw/ and wiki/ structure; ingested two research briefs (avalanche-fuji, use-cases) into raw/
- Both briefs awaiting verify pass; wiki compilation deferred until verdicts land

## [2026-11-02] verify | avalanche-fuji brief — VERIFIED with 7 corrections
- 31/35 claims verified; corrections: ACP-283 = Dynamic Minimum Gas Price; C-Chain floor now 1e-18 AVAX (ACP-176) + dynamic minimum (ACP-283); Etna = 6 ACPs; Octane R=2·T/C=10·T; faucet L1 list now DFK/Beam/Dispatch/Echo/PLYR; icm-contracts archived → icm-services; inflation-projection figure is secondary-source only
- Corrections applied to dev-questions/001 Q5 and curriculum module 7
- Report: raw/avalanche-fuji/2026-11-02-verify-report-avalanche-fuji-brief.md
- Wiki compilation for Part B/C protocol articles may now proceed against brief #1

## [2026-11-02] compile | 8 avalanche articles from verified brief #1
- wiki/avalanche/primary-network-architecture.md
- wiki/avalanche/l1s-after-etna.md
- wiki/avalanche/dynamic-gas.md
- wiki/avalanche/wallets-sponsorship.md
- wiki/avalanche/icm-crosschain.md
- wiki/avalanche/upgrade-timeline.md
- wiki/avalanche/fuji-testnet.md
- wiki/avalanche/tempo-myth.md
- All 7 verify corrections applied; UNVERIFIABLE items handled: Helicon inflation projection (~0.5–1 ppt) omitted; Tempo tech vocabulary (Reth/Simplex/TIP-20/~0.6s/Mar 2026) and third-party faucet specifics included but explicitly marked unconfirmed
- Curriculum modules 5–10, 12, 13 marked ✅ in curriculum/overview.md

## [2026-11-02] compile | 4 ecosystem articles from verified brief #2
- wiki/ecosystem/use-cases-2026.md
- wiki/ecosystem/perps-hyperliquid.md
- wiki/ecosystem/memecoins-launchpads.md
- wiki/ecosystem/competitive-scoreboard.md
- Corrections applied (verify pass 2026-11-02): Hyperliquid FY2025 written as ≈$2.7–3.0T — the brief's "~$633B FY2025" was REFUTED and never appears as an annual figure ($633B taught only as Q1 2026 volume); DeFi TVL 2026 peak corrected to $127.2B (Jan 18, 2026; "~$115B" traced to a Jan 1 misread, not taught); Avalanche TVL $584.0M rank #12 (not $587.1M/#13); L1 count headlined ~81 active + 528 ever created — the unsupported "~175 active (Apr 2025)" omitted entirely; FIFA Collect 1M users dated Sept 17, 2026 (not Oct) and marked platform-reported vs 85K+ on-chain addresses; BUIDL/USYC #1 reframed as flip-flopping through 2026 (BUIDL ~$2.8B reclaim ~Aug 31, 2026; USYC $2.41B led mid-Oct, BUIDL ~$2.25B); pump.fun 2025 revenue written as $620–664M with the DefiLlama revision note; stablecoin total $294.2B API / $295.5B cited; Hyperliquid 56% end-2025 share kept with the incentive-wash-volume caveat and open-interest (~59–63%) as cleaner metric; Solana Q1 2026 app revenue $292M (99Bitcoins) vs ~$342M (Messari) methodology note; AVAX refreshed to $8.62/$3.83B; Aave exploit detailed per verify (Apr 18, 2026, ~$292–293M, $26.4B→~$17.9B→~$14B); GENIUS Act signed July 18, 2025
- UNCERTAIN items marked, not taught as fact: Hyperliquid $2.6B RWA-perp open interest (late-2026 X post); NYSE tokenization testing (original article date uncertain); Avalanche $131.2M weekly tokenized-stock inflows ("reportedly")
- Curriculum modules 3 and 11 marked ✅ in curriculum/overview.md

## [2026-11-02] compile | 5 foundations articles from verified brief #3
- wiki/foundations/blockchain-mental-model.md
- wiki/foundations/btc-eth-anchors.md
- wiki/foundations/consensus-zk-vocabulary.md
- wiki/foundations/evm-token-standards.md
- wiki/foundations/defi-rwa-primer.md
- All verify corrections applied (verify pass 2026-11-02): (1) 2,048 ETH validator max balance attributed to Pectra (May 2025, EIP-7251), NOT Shanghai — Shanghai/Capella (Apr 12, 2023) noted as withdrawals-only — btc-eth-anchors; (2) tokenized treasuries written as $14.32B across 119 products with 7D APY 3.66% (rwa.xyz pull Oct 30–Nov 2, 2026, trail $15.65B/101 → $14.90B/117 → $14.32B/119); the brief's stale $9–10B figure omitted entirely and BUIDL no longer taught as largest — leadership USDY $2.4B / USYC $2.2B / BUIDL $2.1B, Ondo largest platform ~$3.1B — defi-rwa-primer; (3) stablecoin peak corrected to $316.35B on May 20, 2026 (the brief's ~$322B never appears), total $298.2B Nov 2 with USDT $179.3B = 60.13% — defi-rwa-primer; (4) validator count ~881k (Sept 30, 2026; 863–868k in Oct), down from 1.1M via Pectra consolidation, replacing "~870k" — btc-eth-anchors; (5) next halving ~mid-April 2028 (est. Apr 8–14, block 1,050,000 → 1.5625 BTC) replacing "~March–April 2028", and MAX_MONEY citation fixed to src/consensus/amount.h (nSubsidyHalvingInterval kept in src/chainparams.cpp) — btc-eth-anchors; (6) Scroll kept as ZK-rollup example WITH decline caveat (TVL −98.5% to $8.65M, Phemex delisted Oct 21, 2026, permissioned-network transition), Starknet post-quantum L1 noted as research-only — consensus-zk-vocabulary; (7) standard named EIP-7702 "Set Code for EOAs" (Final, Core) with "ERC-7702" flagged as colloquial, Pectra activation May 7, 2025 (epoch 364032, 10:05 UTC) — evm-token-standards; (8) ~13-minute finality presented as derived arithmetic (2 × ~6.4 min), corroborated by the staking FAQ's "deposits recognized in around 13 minutes" — btc-eth-anchors and consensus-zk-vocabulary
- Supporting-Module-3 article (defi-rwa-primer) kept complementary to ecosystem/use-cases-2026.md: mechanisms here, usage map there; same-day snapshot differences (treasuries $14.32B/119 here vs $14.9–15.1B/109 there) are dated pulls from different briefs, left as-is
- Curriculum modules 0, 1, 2, 4 marked ✅ in curriculum/overview.md (module 3 already ✅ from brief #2) — Part A fully teachable
