# Wiki Log

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
