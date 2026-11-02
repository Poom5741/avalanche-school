# A mental model of a blockchain (no CS required)

> Sources: ethereum.org, 2026 (intro to Ethereum; blocks; accounts; wallets; gas; consensus mechanisms); EIP-1559 (eips.ethereum.org); Bitcoin whitepaper, 2008; verify pass, 2026-11-02
> Raw: [brief](../../raw/foundations/2026-11-02-blockchain-foundations-brief.md); [verify report](../../raw/foundations/2026-11-02-verify-report-foundations-brief.md)
> Updated: 2026-11-02

## Overview

This is Module 0: the entire mental model of a blockchain, built from analogies with zero computer-science theory. A blockchain is a **shared ledger** that everyone holds a copy of; entries are batched into **blocks** chained together by fingerprints (**hashes**); people move value with signed **transactions**; **wallets** hold keys, not coins; **gas** pays for computation; and **consensus mechanisms** exist to solve one specific problem — the double-spend. If a learner masters only one article in Part A, it should be this one: every later module is a variation on these six ideas.

## The shared notebook: a ledger everyone holds

A blockchain is a **shared ledger** — a record of who sent what to whom. Think of a bank's transaction log, except instead of one institution keeping the private notebook, **every participant keeps their own identical copy**, and the network continuously checks that all copies agree.

The ledger is **append-only**: entries are only ever added, like a logbook written in pen — never edited or erased. You can add today's page; you cannot unwrite yesterday's.

## Pages chained by fingerprints: blocks and hashes

Entries are batched into **blocks** — think of them as pages of the logbook. Each block carries a unique fingerprint (a **hash**) of the previous block, so each page is physically chained to the one before it. A hash is a short fingerprint computed from the block's contents; if the contents change, the fingerprint no longer matches.

The consequence: tamper with an old page and every fingerprint after it breaks. Rewriting history is detectable — and computationally impractical to pull off.

## Transactions: signed instructions

A **transaction** is a signed instruction — for example, "send 1 ETH from me to Alice," or "run this program." The signature is what proves the instruction really came from the account's owner.

## Two kinds of accounts: people and programs

Ethereum has two account types:

- **EOA (Externally Owned Account)** — controlled by a private key. This is a person's wallet.
- **Contract account** — controlled by code that runs automatically when called. Nobody's hand is on the wheel; the program simply does what it was written to do.

## Keys, and the wallet myth

Each account has a **private key** — a giant random number. Think of it as the only pen that can sign in your name. From it is derived your **public key / address** — your mailbox number, safe to share.

The myth worth killing early: a "wallet" is **not a purse holding coins**. Coins always live on the shared ledger. A wallet is a **key manager** — it safely stores your private key, shows your ledger balance, and signs transactions.

Two consequences follow:

- Lose the key = lose the account. There is no password-reset desk.
- Anyone with the key *is* you.

## Gas: why nothing is free

Every Ethereum operation costs **gas** — a unit that meters computation. Users pay fees in ETH because running everyone's code costs the network real resources (compute, storage, bandwidth). If it were free, spam and infinite loops would clog the system. Gas makes abuse expensive — and it pays the validator who included your transaction.

Since EIP-1559 the fee splits in two: a **base fee** that is burned (destroyed — permanently removed by the protocol) and a **tip** (priority fee) that goes to the validator.

## The double-spend problem: why consensus exists

Digital money is just data, and data can be copied. If I hold $10, I can try to spend the same $10 twice — once with you, once with a shop. A bank solves this by keeping the one authoritative ledger: whichever transaction clears first wins.

Remove the bank, and thousands of strangers must agree on *which* of two conflicting spends came first — without any referee. This "who gets to write the next page, and in what order" problem is exactly what **consensus mechanisms** (mining or staking) solve: they make it prohibitively expensive for any single actor to rewrite the agreed history or confirm a double-spend, because doing so requires out-competing or owning a majority of the network's economic weight.

## Quick answers

- **"Where do my coins actually live?"** → On the shared ledger. Your wallet only holds the key.
- **"Why do I pay gas?"** → Because computation costs the network real resources; gas prices out abuse and pays validators. The base fee part is burned.
- **"Can old transactions be edited?"** → No — the ledger is append-only, and each block carries the previous block's fingerprint.
- **"What happens if I lose my wallet?"** → Nothing, if you still have the key. Lose the key and the account is gone.

## See Also

- [BTC & ETH: the two anchors](btc-eth-anchors.md) — who gets to write the pages in practice (PoW and PoS)
- [Consensus, rollups & ZK vocabulary](consensus-zk-vocabulary.md) — the tradeoffs of each consensus approach
- [Gas in the dynamic era](../avalanche/dynamic-gas.md) — the same gas ideas, on Avalanche's C-Chain
- [What people actually use blockchains for](../ecosystem/use-cases-2026.md) — where all these transactions actually go
