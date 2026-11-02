# avalanche-school

An interactive, AI-taught blockchain curriculum — from first principles to the latest state of **Avalanche** (late 2026) — designed to turn a non-technical learner into a **Technical Translator**: someone who can correctly answer developer questions like *"What does Avalanche actually offer? Gas? Wallets? Sponsorship? ERC standards? Is it keeping up with Tempo/Solana?"*

Built as an [LLM wiki](https://karpathy.bearblog.dev/llm-wiki/)-style knowledge base: `raw/` holds immutable, dated, linked source documents; `wiki/` holds compiled, evidence-grounded articles; an AI teaches from the wiki using a teach-back protocol defined in `AGENTS.md`.

## Quickstart (learner)

Open this repo with any capable AI agent (Claude Cowork, Claude Code, etc.) and say:

> Read AGENTS.md, check curriculum/progress.md if it exists, and start teaching me at my current module.

That's it. The AI handles the rest: orientation → explanation → comprehension check → teach-back → checkpoint quiz → dev-question drill. Lessons adapt to your pace and language (Thai or English — switch anytime).

## Quickstart (AI agents)

You are the teacher. **Read `AGENTS.md` first, in full.** It defines who the learner is, the lesson protocol, the grounding rules (you teach only verified facts from `wiki/`), and how to research new content when the wiki can't answer.

## Who this is for

- **Primary:** a community manager (education background, non-technical) who needs to field technical questions about Avalanche from devs and community members.
- **Also:** anyone who wants a correctness-first, jargon-aware introduction to blockchain and Avalanche's current state — the repo is public on purpose. Send the repo URL; the AI on the other end knows what to do.

## What's inside

| Path | What it is |
|---|---|
| `curriculum/overview.md` | The learning path — 3 parts, 14 modules |
| `wiki/` | The verified knowledge base (English, evidence-grounded) |
| `raw/` | Source documents: dated research briefs with inline links to primary sources |
| `dev-questions/` | The kinds of questions devs actually ask, with reference answers |
| `engagement/ideas.md` | Optional games/simulators the teaching AI can offer |
| `AGENTS.md` | The teaching protocol — the file that makes any AI a competent teacher |

## The correctness bar

Every load-bearing fact in `wiki/` must exist verbatim in a `raw/` document, and every raw research brief passes an **independent verification pass** (a fresh agent re-checks each claim against primary sources before the content is taught). Corrections are recorded, never silently rewritten. The teaching AI is forbidden from teaching numbers it cannot trace to the wiki.

## Content status

See `curriculum/overview.md` for per-module status. Modules marked `pending-verify` have research collected but are waiting for their verification pass — the teaching AI will skip or defer them until their wiki articles are compiled.

## Credits & sources

Primary sources: [build.avax.network](https://build.avax.network) docs & blog, [github.com/avalanche-foundation/ACPs](https://github.com/avalanche-foundation/ACPs), [DefiLlama](https://defillama.com), [RWA.xyz](https://www.rwa.xyz) data, and named press in each raw document. All raw documents carry dates and inline source links.

## License

MIT — take it, fork it, teach with it.
