# SynapsePay
![SynapsePay logo](assets/logo.png)

Instant on-chain micropayments so AI agents can pay each other per API call.

## Overview

SynapsePay is a Solana-based payment rail that lets autonomous AI agents discover, call, and pay one another for data or compute in real time using streaming USDC payments. A simple registry and escrow program lets any agent monetize an endpoint in minutes, with no human billing setup required.

## Problem

AI agents increasingly need to transact with each other, buying data, compute, or tools from other agents. Existing payment rails are too slow, too expensive, or require manual invoicing and human-managed billing, which breaks real-time autonomous workflows.

## Solution

SynapsePay provides a Solana program that lets agents register paid endpoints, auto-negotiate price, and settle per-call payments via streaming/escrowed USDC transactions, with on-chain receipts for every call.

## Features (MVP)

- Agent registry program for listing paid API endpoints with price per call
- Escrow + streaming payment program (Anchor) for per-call USDC settlement
- SDK that wraps HTTP calls with automatic Solana payment + verification
- Demo: two AI agents (one buyer, one seller) autonomously negotiating and paying
- Dashboard showing live agent-to-agent payment flows

## Tech stack

- Anchor, Rust (on-chain programs)
- Solana Pay
- USDC (SPL token)
- Helius RPC
- TypeScript (SDK, demo, dashboard)
- LangChain / agent framework (demo agents)

## How it works

```
Seller Agent --register endpoint+price--> Registry Program (Solana)
Buyer Agent --discover + negotiate-------> Registry Program
Buyer Agent --call via SDK--------------> Seller Endpoint
                 |
                 v
        SDK wraps call with
        Solana Pay USDC payment
                 |
                 v
        Escrow/Streaming Program --settle per call--> On-chain receipt
                 |
                 v
            Dashboard (live view)
```

An agent lists a paid API endpoint and its price per call in the on-chain registry. Another agent discovers it, negotiates price, and calls it through the SynapsePay SDK. The SDK automatically wraps the HTTP call with a Solana Pay USDC payment into escrow. The escrow/streaming program verifies the payment and releases USDC per call, recording an on-chain receipt. A dashboard visualizes these agent-to-agent payment flows live.

## Roadmap

- Add reputation/trust scoring for agents based on payment history
- Support multi-token and cross-chain settlement via bridges
- Partner with agent frameworks (LangChain, CrewAI) for native SDK integration

## Pitch

- Slides: [docs/pitch.pdf](docs/pitch.pdf)
- Script: [docs/pitch-script.md](docs/pitch-script.md)

## Team

- Name / role - placeholder
- Name / role - placeholder
- Name / role - placeholder

Built for the Colosseum hackathon.

---

🎬 Pitch video: [docs/pitch-video.mp4](docs/pitch-video.mp4)


## Prototype

Live prototype: https://s25k1030pq-max.github.io/synapsepay/

The source is [docs/index.html](docs/index.html) (served with GitHub Pages from the /docs folder). All data is simulated.
