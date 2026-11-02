# Verification Report — 2026-11-02 Avalanche/Fuji Ecosystem Brief

**Verify hop:** independent fresh-context agent, 2026-11-02. Method: primary sources fetched live (build.avax.network docs, github.com/avalanche-foundation/ACPs raw files, github.com/ava-labs release notes & configs, status.avax.network, paradigm.xyz, tempo.xyz).

| # | Claim | Verdict | Corrected value | Primary source |
|---|---|---|---|---|
| 1 | Fuji C-Chain ID **43113 (0xA869)**; mainnet **43114 (0xA86A)** | **VERIFIED** | — | build.avax.network/docs/primary-network |
| 2 | Fuji RPC `api.avax-test.network/ext/bc/C/rpc` | **VERIFIED** | — | same docs page |
| 3 | Testnet explorer is **explorer-test.avax.network/c-chain** (current official name) | **VERIFIED** | — | same docs page |
| 4 | `subnets.avax.network` (mainnet L1 explorer) / `subnets-test.avax.network` (testnet) | **VERIFIED** | — | faucet config.json EXPLORER fields |
| 5 | Snowtrace Etherscan version sunset Oct 2023, replaced by Avascan-run | **VERIFIED** | Announced Oct 30, 2023; shut down Nov 30, 2023 | finance.yahoo.com/news/top-avalanche-block-explorer-snowtrace-114300897.html |
| 6 | Faucet drip = **2 AVAX** (config `DRIP_AMOUNT: 2`, DECIMALS 18) | **VERIFIED** | — | raw.githubusercontent.com/ava-labs/avalanche-faucet/main/config.json |
| 7 | Rate limit **1 drip / address / 24h** (MAX_LIMIT 1, WINDOW_SIZE 1440 min) | **VERIFIED** | — | same config.json |
| 8 | Faucet serves WAGMI, DFK, Dexalot testnet L1s | **CORRECTED** | Current config lists DFK, Beam, Dispatch, Echo, PLYR, Kite, etc. — **WAGMI & Dexalot chains are gone** (Dexalot only as an ERC-20 drip) | faucet config.json |
| 9 | Etna mainnet **Dec 16, 2024** (12 PM ET) | **VERIFIED** | — | github.com/ava-labs/avalanchego/releases/tag/v1.12.0 |
| 10 | Etna bundled **7 ACPs** | **CORRECTED** | v1.12.0 schedules **6**: ACP-77, 103, 118, 125, 131, 151 | v1.12.0 release notes |
| 11 | ACP-77: L1 validator fee **512 nAVAX/s ≈ 1.33 AVAX/month** below target T | **VERIFIED** (verbatim in ACP-77) | — | github.com/avalanche-foundation/ACPs/ACPs/77-reinventing-subnets |
| 12 | ACP-125: base fee **25 → 1 nAVAX**, Activated | **VERIFIED** | — | …/ACPs/125-basefee-reduction |
| 13 | ACP-131 Cancun EIPs in Etna | **VERIFIED** | — | v1.12.0 release notes |
| 14 | Primary Network validator minimum **still 2,000 AVAX** | **VERIFIED** | — | build.avax.network/docs/primary-network |
| 15 | Octane (ACP-176) Fuji **Mar 13, 2025** / mainnet **Apr 8, 2025** | **VERIFIED** | v1.13.0-fuji + v1.13.0 ("Fortuna") confirm both dates | …/releases/tag/v1.13.0-fuji, /v1.13.0 |
| 16 | Octane: replaces static **15M gas/10s** target; validators vote on target | **VERIFIED** | — | …/ACPs/176-dynamic-evm-gas-limit…/README |
| 17 | Octane "**gas limit = 2× target**" | **CORRECTED** | ACP-176 sets capacity-add rate **R = 2·T** and max block capacity **C = 10·T**; "2×" describes R, not the gas limit | ACP-176 README |
| 18 | Granite Fuji **Oct 29, 2025** / mainnet **Nov 19, 2025**; ACP-181/204/226 | **VERIFIED** | — | …/releases/tag/v1.14.0-fuji and /v1.14.0 |
| 19 | Helicon Fuji **Jul 28, 2026** / mainnet **Sep 22, 2026, 15:00 UTC**; v1.15.0-fuji no C-Chain state sync post-activation | **VERIFIED** (all three details verbatim) | — | build.avax.network/docs/primary-network/helicon-upgrade |
| 20 | Helicon contents: ACP-194 Continuous Execution (Coreth → new VM); ACP-236 auto-renewal; ACP-267 uptime **80→90%**; ACP-273 min stake **48h mainnet / 12h Fuji**; ACP-285 **10%→7.5%** ramped over 90 days | **VERIFIED** (six ACPs total; all parameters match docs) | — | Helicon docs page |
| 21 | ACP-283 contents "UNCERTAIN" | **CORRECTED — now findable** | **ACP-283 = Dynamic Minimum Gas Price**: C-Chain minimum gas price becomes dynamic, set by stake-weighted validator preference | Helicon docs table + …/ACPs/283-dynamic-minimum-gas-price |
| 22 | ACP-285 inflation-reduction "~0.5–1 ppt" projection | **UNVERIFIABLE** from primary docs | Docs confirm only the 7.5%/90-day ramp; the projection is a secondary-source estimate | Helicon docs |
| 23 | C-Chain minimum base fee **is 1 nAVAX** today | **CORRECTED** | 1 nAVAX was true only Dec 2024–Mar 2025. ACP-176 (Octane) set the floor at **M = 1e-18 AVAX**; Helicon's ACP-283 makes it dynamic per validator preference | ACP-176 README (M = 1*10⁻¹⁸ AVAX); Helicon docs; ACPs discussion #178 |
| 24 | Nothing newer than Helicon activated as of Nov 2, 2026 | **VERIFIED** (consistent: Helicon is the latest upgrade page; ACP repo tops out at 285) | — | build.avax.network/docs/primary-network/helicon-upgrade |
| 25 | Tempo = Stripe/Paradigm payments L1, announced **Sep 4, 2025**, Matt Huang CEO, independent company | **VERIFIED** | — | paradigm.xyz/writing/tempo-payments-first-blockchain |
| 26 | **"No Avalanche connection"** for Tempo; no Avalanche feature named "tempo" | **VERIFIED** (best-effort negative) | Paradigm post and tempo.xyz contain zero Avalanche references; websearch outage prevented exhaustive search | paradigm.xyz; tempo.xyz |
| 27 | Tempo tech details: Reth, Simplex, TIP-20, ~0.6s finality, mainnet Mar 2026 | **UNVERIFIABLE** here | tempo.xyz confirms it's live and Stripe/Paradigm-incubated but fetched pages don't state these specifics | tempo.xyz |
| 28 | Core free gas since **Mar 25, 2025** | **VERIFIED** (weak) | The Block article blocked (403, no archive); cited URL slug embeds 2025-03-25, corroborating the date | theblock.co URL slug |
| 29 | ACP-209 (EIP-7702-style) **Proposed, not activated**, adapted for Continuous Execution | **VERIFIED** verbatim | — | …/ACPs/209-eip7702-style-account-abstraction |
| 30 | `avalanche-evm-gasless-transaction` repo (ERC-2771) under ava-labs | **VERIFIED** | — | github.com/ava-labs/avalanche-evm-gasless-transaction |
| 31 | No official "ARC" repo from Avalanche Foundation; ACPs are the standard; ARC-20 = Metal Blockchain (Avalanche fork) | **VERIFIED** (best-effort negative) | avalanche-foundation hosts only the ACPs repo; MetalBlockchain org's metalgo is forked from ava-labs/avalanchego | github.com/avalanche-foundation/ACPs; github.com/MetalBlockchain |
| 32 | AWM branded **ICM**; **Teleporter** contract framework; **ICTT** for token transfer | **VERIFIED** | Nuance: github.com/ava-labs/teleporter redirects to **icm-contracts**, which was **archived Dec 3, 2025** and moved entirely to **ava-labs/icm-services** | github.com/ava-labs/icm-contracts |
| 33 | status.avax.network for network status | **VERIFIED** | — | status.avax.network |
| 34 | Core faucet URL core.app/tools/testnet-faucet | **VERIFIED** (URL live) | — | core.app/tools/testnet-faucet |
| 35 | QuickNode faucet requires small mainnet balance; thirdweb 0.01 AVAX/day | **UNVERIFIABLE** this session | URLs plausible; couldn't load pages | — |

## Corrections to apply everywhere

1. **ACP-283 (highest value):** Replace "UNCERTAIN" — ACP-283 is the **Dynamic Minimum Gas Price** (C-Chain minimum gas price set dynamically by stake-weighted validator preference), per the Helicon docs and the ACP-283 folder.
2. **C-Chain fee floor is stale:** "Minimum base fee is 1 nAVAX" no longer holds. Since Octane (ACP-176, Mar/Apr 2025) the floor is **1e-18 AVAX**, and Helicon (ACP-283) makes the minimum dynamic. Canonical wording: 25 nAVAX → 1 nAVAX (ACP-125) → 1e-18 AVAX dynamic floor (ACP-176/ACP-283).
3. **Etna = 6 ACPs, not 7:** avalanchego v1.12.0 lists ACP-77, 103, 118, 125, 131, 151.
4. **Octane gas math:** "gas limit = 2× target" → per ACP-176, capacity added per second **R = 2·T**; max block capacity **C = 10·T**.
5. **Faucet L1 list:** WAGMI and Dexalot chains are no longer in the faucet config; cite DFK, Beam, Dispatch, Echo, PLYR.
6. **ICM repo pointer:** github.com/ava-labs/teleporter → redirects to icm-contracts (archived Dec 3, 2025) → canonical repo now **ava-labs/icm-services**.
7. **Minor wording:** Helicon's "five more ACPs = staking economics overhaul" should note ACP-283 is C-Chain gas pricing, not staking; the "~0.5–1 ppt inflation reduction" figure is secondary-source only.

Everything else load-bearing — chain IDs, RPC/explorer URLs, faucet drip & rate limit, all four upgrade dates (both networks), Helicon's five staking/execution parameters, ACP-77 fee math, ACP-125, the 2,000 AVAX minimum, ACP-209 status, Tempo's Stripe/Paradigm identity, and the ARC/ACP distinction — checked out against primary sources.
