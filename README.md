# Justsay

**Crypto that does what you say.**

Sayso is a conversational crypto assistant built for the UXmaxx Hackathon (Universal Accounts Track). Instead of picking networks, bridging assets, or holding the right gas token on every chain, users just type or speak what they want — Sayso handles the rest through a single Universal Account.

> "Send $50 to Alice." "Swap my USDC for ETH." "Consolidate my stablecoins."
> No chain selection. No bridging. No jargon.

## The problem

Multi-chain UX is broken. Before making a single transaction, a user has to know which network they're on, hold the right native token for gas, manually bridge funds, and understand terms like EOA, gas, and bridging just to move money.

## The solution

Sayso removes the interface entirely. A natural-language command is parsed into a structured intent, shown back to the user in plain English for confirmation, then executed via Particle Network's Universal Accounts SDK in **EIP-7702 mode** — the user's existing wallet address becomes a chain-abstracted account in place. One login, one balance, any chain, any asset. No new address, no migration, no smart-account deployment.

## How it works

```
User types/speaks a command
        ↓
Backend parses it into a structured intent (LLM)
        ↓
Frontend shows a plain-English confirmation card
        ↓
On confirm → executed via Universal Account (EIP-7702)
        ↓
Done — no manual chain switching
```

## Project structure

```
sayso/
├── frontend/     Next.js app — command bar, confirmation card, execution UI
├── backend/      Intent parsing + execution API
└── pitch/        Hackathon pitch deck
```

See each folder's own README for setup details.

## Tech stack

- **Frontend:** Next.js, React, Tailwind
- **Backend:** Node.js, Express, TypeScript
- **Chain abstraction:** Particle Network Universal Accounts SDK (EIP-7702)
- **Intent parsing:** LLM-based (Featherless AI / OpenAI / Anthropic)

## Running locally

```bash
# Backend
cd backend
npm install
npm run dev     

# Frontend
cd frontend
npm install
npm run dev        
```

## Judging criteria alignment

| Criteria | How Sayso addresses it |
|---|---|
| UX excellence (40%) | Natural language replaces manual chain/network/bridge selection entirely |
| Universal Accounts + EIP-7702 (30%) | Chain abstraction via EIP-7702 is the core mechanism, not an add-on |
| Adoption potential (20%) | Usable by anyone who can type or talk — no crypto literacy required |
| Technical quality/polish (10%) | Working intent-parsing pipeline + Universal Account execution flow |

## Status

Hackathon build — intent parsing and execution are currently mocked to keep the demo runnable with no API keys. See `backend/src/intent/parser.ts` and `backend/src/execution/universalAccount.ts` for where the real LLM and Particle SDK calls plug in.

## License

MIT
