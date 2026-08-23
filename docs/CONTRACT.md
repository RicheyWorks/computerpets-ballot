# Ballot contract

Do not implement against folklore. Implement against this file.

## Identity

- Product: **Ballot**
- Repo: `computerpets-ballot`
- Category: Community
- Idea: Feature Voting App
- Port / surface: `8080`

## Must

- Stay canon with 210 species. No illegal hybrids. No swapped voices.
- Treat the desktop overlay as the main quest. This organ is optional until wired.
- Fail soft: the overlay keeps walking if this service is down, unless this *is* the overlay.
- No PII in public artifacts (Steam id, wallet, home path, webcam frames).

## Data

Proposal(id, body, deadline) · Weight(nftCount, steamCap) · Ballot(choice, weight)

## Surface

- GET /v1/proposals — open / closed
- POST /v1/proposals — holder + steam identity
- POST /v1/vote — weighted, one ballot per proposal

## Neighbors

- computerpets-minter
- computerpets-ledger
- computerpets-steamgate
- computerpets-console

## Failure doctrine

Sybil NFT wash → snapshot block, not live balance. Unverified voter → 401. After deadline → read-only.

## Stack

TypeScript · React 19 · snapshot-style votes · NFT / Steam weight · Ledger VOTE asset
