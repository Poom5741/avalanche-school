# Engagement catalog — optional games & artifacts

The teaching AI may offer these (one per lesson max, ask first). Each is a single self-contained HTML file unless noted. Built artifacts go in `engagement/built/` (gitignored) unless the learner asks to commit.

| Idea | Teaches | When to offer | Spec sketch |
|---|---|---|---|
| **Consensus Restaurant** | Consensus vs execution (Helicon) | Learner confused after Module 5 or 10 | Click to seat customers; "waiter" (consensus) collects orders into a queue, "kitchen" (execution) cooks them in parallel. Toggle pre/post-Helicon mode to feel the difference. |
| **Chain ID Reflex** | Fuji vs mainnet config | Module 13, dev-drill prep | Timed flashcards: given RPC/explorer/chain-ID, pick "Mainnet / Fuji / Trap". Traps: 43114 vs 43113, api.avax vs api.avax-test. |
| **Faucet Quest** | Fuji practical flow | Module 13 | Step-through simulator: add Fuji to wallet → get 2 AVAX from faucet → send tx → find it on explorer. Wrong step = friendly hint. |
| **Fee Machine** | Dynamic gas (ACP-176) | Module 7 | Slider for network demand; watch base fee rise/fall around the 1 nAVAX floor and gas target move. Shows why "is gas expensive?" needs a time+context answer. |
| **Myth or Fact** | Module 12 myth-busting | End of Part C | Rapid-fire statements ("Tempo runs on Avalanche", "ARC-20 is an Avalanche standard", "L1 validators stake 2,000 AVAX") — swipe Myth/Fact, score at end, each card flips to the sourced truth. |
| **L1 Price Tag** | Etna economics | Module 6 | Before/after calculator: subnet era (2,000 AVAX stake × N validators) vs L1 era (~1.33 AVAX/month × N). Enter N, see the gap. |
| **Token Standard Sort** | ERC-20/721/1155/4337 | Module 4 | Drag cards ("fungible coin", "Bored-Ape-style NFT", "game item batch", "gasless smart wallet") into the right standard bucket. |
| **Who's the Chain?** | Competitive landscape | Module 11 | Given a fact card ("$1B cumulative revenue from memecoins", "FIFA's blockchain", "Stripe's payments L1"), pick Avalanche / Solana / Tempo / Ethereum / Hyperliquid. Sources shown on reveal. |
| **Teach-back Canvas** | Any module | Learner hesitates during teach-back | Not a game: an HTML whiteboard where the learner drags labeled blocks (actors, arrows) to assemble the flow they're about to explain. Reduces blank-page fear for non-technical learners. |
| **Upgrade Timeline Builder** | Etna→Helicon order | Module 10 | Drag four upgrade cards onto a dated timeline; each correct placement reveals its headline change. Wrong order shows what each actually changed so the learner self-corrects. |

Design rules for built artifacts: single HTML file, no network calls, uses the learner's UI language, every fact shown must come from `wiki/` with the article path shown on hover/at reveal, and difficulty adapts (wrong answers re-teach the one concept, never dump the whole lesson).
