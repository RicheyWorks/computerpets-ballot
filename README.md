# Ballot

**Feature Voting App** — Lets token and NFT holders vote on the ComputerPets development roadmap.

Part of the [ComputerPets](https://github.com/RicheyWorks/computerpets) ecosystem. Index: [computerpets-ecosystem](https://github.com/RicheyWorks/computerpets-ecosystem).

> Status: **design scaffold**. This repository ships the contract, README, and layout so implementation can start without renaming the organ later.

## Why it exists

Holders propose. Weight comes from verified pets + optional VOTE credits. Steam-only players still get a capped voice so the chain does not own the game.

The flagship overlay already puts a living sticker on the real desktop (Rui first, 210 kinds). Ballot does not replace that. It is one organ.

## Stack

TypeScript · React 19 · snapshot-style votes · NFT / Steam weight · Ledger VOTE asset

GroupId / namespace: `com.enterprisepet.ballot`  
Default listen: `8080`

## Talks to

- computerpets-minter
- computerpets-ledger
- computerpets-steamgate
- computerpets-console

## Contract

### Data

`Proposal(id, body, deadline) · Weight(nftCount, steamCap) · Ballot(choice, weight)`

### Surface

- GET /v1/proposals — open / closed
- POST /v1/proposals — holder + steam identity
- POST /v1/vote — weighted, one ballot per proposal

### Failure doctrine

Sybil NFT wash → snapshot block, not live balance. Unverified voter → 401. After deadline → read-only.

## Layout

```
computerpets-ballot/
  README.md           this file
  LICENSE             MIT
  docs/CONTRACT.md    the same contract, frozen for implementers
  src/                implementation lands here
```

## Run (Windows)

PowerShell, from this folder, after the flagship helpers (Git, Node LTS 22+, JDK 21 as needed):

```powershell
cd app; npm install; npm run dev
```

You do not need this service to meet Rui. The [flagship start-here](https://github.com/RicheyWorks/computerpets/blob/main/docs/START-HERE.md) is still the first pet.

## Ecosystem

| Organ | Repo |
| --- | --- |
| Flagship desktop + Spring | [RicheyWorks/computerpets](https://github.com/RicheyWorks/computerpets) |
| This organ | [RicheyWorks/computerpets-ballot](https://github.com/RicheyWorks/computerpets-ballot) |
| Full map | [RicheyWorks/computerpets-ecosystem](https://github.com/RicheyWorks/computerpets-ecosystem) |

## License

MIT. See [LICENSE](LICENSE).

---

*Two hundred ten living kinds. Keep them so a line does not go quiet.*
