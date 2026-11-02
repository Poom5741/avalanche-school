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
