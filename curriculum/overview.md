# Curriculum — avalanche-school

Goal: the learner becomes a **Technical Translator** — able to correctly answer developer/community questions about what Avalanche offers and how it compares to the rest of the industry.

Three parts. Modules marked ✅ have compiled wiki content ready to teach. Modules marked ⏳ have research collected but await their verify pass / wiki compilation — teach only the outline until then.

Track progress locally in `curriculum/progress.md` (gitignored). Record: module, session date, checkpoint score, dev-drill results, where you stopped.

---

## Part A — Blockchain foundations (industry-wide)

| # | Module | Teaches | Status |
|---|---|---|---|
| 0 | Blockchain mental model | Blocks, transactions, accounts/keys/wallets, what gas pays for, why consensus matters — all by analogy, no CS theory | ✅ |
| 1 | BTC & ETH — the two anchors | What each is famous for, PoW vs PoS in plain language, why every comparison starts here | ✅ |
| 2 | Modern consensus + ZK (vocabulary level) | PoS variants, rollups, validity proofs — names and one-line meanings only, zero math | ✅ |
| 3 | What people actually build & trade | DeFi (DEX/lending), RWA/tokenized treasuries, perps & Hyperliquid, memecoins & pump.fun, stablecoins/payments, gaming — the real 2025–2026 usage map | ✅ |
| 4 | EVM + token standards | What "EVM-compatible" means; ERC-20/721/1155/4337 and why devs say these constantly | ✅ |

## Part B — Avalanche in depth

| # | Module | Teaches | Status |
|---|---|---|---|
| 5 | Architecture | Primary Network, C/P/X-Chain roles, validators & staking (incl. Helicon changes: 90% uptime, 48h min stake) | ✅ |
| 6 | L1s after Etna | Subnets → Avalanche L1s, Validator Manager contracts, ~1.33 AVAX/month continuous fee, the >99% cost drop | ✅ |
| 7 | Gas in the dynamic era | Fee floor history 25→1 nAVAX (ACP-125) → dynamic floor 1e-18 (ACP-176/ACP-283), dynamic fees, custom gas tokens on L1s, fee burn | ✅ |
| 8 | Wallets & sponsorship | Core (free C-Chain gas since Mar 2025), MetaMask/Chainlist, passkeys (ACP-204), account abstraction, ACP-209 pending | ✅ |
| 9 | Cross-chain: ICM | Avalanche Interchain Messaging (ex-Warp), Teleporter, ICTT token transfers — no external bridge needed | ✅ |
| 10 | Reading upgrades like a pro | The Etna → Octane → Granite → Helicon timeline; what an ACP is, where to read proposals and release notes | ✅ |

## Part C — Avalanche and the world

| # | Module | Teaches | Status |
|---|---|---|---|
| 11 | "Is it keeping up?" | Avalanche vs Solana vs Ethereum+L2s vs Hyperliquid vs Tempo — with dated numbers (TVL, stablecoins, app revenue) and both the criticisms and the institutional counter-narrative | ✅ |
| 12 | Myth-busting | Tempo ≠ Avalanche; "ARC" standards don't exist (ACPs do); subnets are gone (L1s now); ARC-20 belongs to Metal Blockchain | ✅ |
| 13 | Fuji + answering devs for real | Fuji testnet practically: chain IDs 43113/43114, faucets, explorers, why upgrades rehearse on Fuji first — then live drills from `dev-questions/` | ✅ |

---

## Source documents

- `raw/avalanche-fuji/2026-11-02-avalanche-fuji-ecosystem-brief.md` — protocol facts (verify pass: in progress)
- `raw/use-cases/2026-11-02-crypto-use-cases-competitive-brief.md` — usage & competitive data (verify pass: in progress)

Wiki articles are compiled from these after verification. `wiki/index.md` tracks article ↔ module mapping.
