# Backend Exclusion Rationale

The current Dara Drips submission focuses on the frontend and contract architecture repositories. A backend service can be added later, but it is intentionally outside the current submission scope.

## Current focus

Dara is being split into two active workstreams for the current Wave scope:

| Repository | Current responsibility |
|------------|------------------------|
| `dara_frontend` | User-facing Ayo board experience, planned wallet-ready UI, contributor docs, and frontend UX research. |
| `dara_contract` | Soroban/Stellar research, match-record architecture, reward-flow planning, and future contract implementation notes. |

That split keeps the scope reviewable while the game model, player flows, and on-chain responsibilities are still being defined.

## Why backend is excluded for now

- The project does not yet have a stable API contract between frontend, backend, and Soroban contracts.
- Match-state ownership is still under research: some state may stay local or frontend-managed, while verified records may move to Soroban later.
- Reward and tournament flows need contract and security planning before a backend service brokers them.
- Adding a backend repository too early would create extra setup, hosting, secrets, and review surface without a clear interface.
- The current Drips scope is easier to evaluate through documentation, frontend planning, and contract architecture tasks.

## Future backend possibilities

A backend can be introduced once the frontend prototype and contract architecture produce clearer integration points. Possible backend responsibilities include:

- Matchmaking or lobby coordination for remote play.
- Player profile metadata that should not live on-chain.
- Tournament scheduling and leaderboard aggregation.
- Indexing Soroban match events for frontend display.
- Optional anti-abuse checks before reward distribution.
- Admin tooling for tournaments, disputes, or content moderation.
- API adapters that help the frontend read contract and indexer data consistently.

## When to add backend scope

Backend work should be reconsidered after the project has:

1. A documented Ayo game-state model.
2. A frontend prototype that identifies real API needs.
3. Soroban match-record and reward-flow decisions.
4. A security note describing which data belongs off-chain versus on-chain.
5. A small set of backend endpoints with clear request and response shapes.

Until then, backend tasks should remain planning notes rather than implementation requirements.

## Contributor guidance

Contributors should focus current backend-related work on documentation and interface planning. Avoid adding server code, databases, secrets, deployment files, or hosted-service assumptions unless a future issue explicitly scopes that work.