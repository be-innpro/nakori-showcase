# Nakori.Life

> **"AI does. You live." — A voice-first super-app for the 80M Brazilians AI has ignored.**
> A be-innpro product. Submitted to the **START Rise Challenge 2026**.

[![Status](https://img.shields.io/badge/status-MVP%20%C2%B7%2091.9%25%20built-blue)]()
[![License](https://img.shields.io/badge/license-Proprietary-orange)]()
[![Stack](https://img.shields.io/badge/stack-PWA%20%E2%80%A2%20Node%2020%20%E2%80%A2%20Fastify-success)]()

---

## What it is

Nakori.Life is a **voice-first AI super-app** for Brazilian socio-economic classes C and D — 80 million people who can't afford paid AI products and aren't served well by global, English-trained assistants.

Three integrated experiences in one app:

1. **Nakori AI** — voice-first copilot with 55 Brazilian-Portuguese journey templates (tax, credit, health, legal, financial)
2. **Nakori Shop** — contextual marketplace with affiliate revenue (Amazon, Hotmart, Shopee)
3. **Nakori Life** — AI-guided journeys for finance, health, and career
4. **Wallet Satoshi + Steep** — Bitcoin/RWA wallet for the unbanked, with smart-contract referral incentives

## Problem

Brazilian classes C and D — 80 million people — are systematically excluded from the AI revolution:

- **78% prefer speaking** to typing — but AI products are chat-first
- **130M audio messages/day** are sent on WhatsApp; voice is the native interface
- **Low digital literacy** rules out complex UX
- **Disposable income €50–€200/month** rules out paid AI subscriptions
- **No bank account** for ~30% — rules out credit-card-based AI
- **Low English fluency** rules out unlocalised global assistants

Nakori.Life delivers intelligence in their language, on their device, at their price point.

## Architecture

```
                ┌──────────────────────────────────────────────────┐
                │                Nakori PWA (Android-first)        │
                │  ┌─────────────────────────────────────────────┐ │
                │  │     Voice-first UI (Whisper PT-BR ASR)      │ │
                │  └─────────────────────────────────────────────┘ │
                │     │                                            │
                │     ▼                                            │
                │  ┌──────────────────────────────────────────────┐│
                │  │  Intent Detection · 55 BR-PT Templates       ││
                │  │  (tax · credit · health · legal · financial) ││
                │  └──────────────────────────────────────────────┘│
                │     │              │              │              │
                │     ▼              ▼              ▼              │
                │  ┌──────┐      ┌──────┐      ┌────────────┐      │
                │  │Nakori│      │Nakori│      │Wallet      │      │
                │  │AI    │      │Shop  │      │Satoshi/RWA │      │
                │  └──────┘      └──────┘      └────────────┘      │
                │     │              │              │              │
                │     ▼              ▼              ▼              │
                │  ┌──────────────────────────────────────────────┐│
                │  │   Backend (Fastify · Node 20 · MongoDB)      ││
                │  │   Firebase Auth · Groq Whisper · OpenRouter  ││
                │  └──────────────────────────────────────────────┘│
                │     │                                            │
                │     ▼                                            │
                │  ┌──────────────────────────────────────────────┐│
                │  │   Smart Contracts (SolVM Base / Arbitrum)    ││
                │  │   Referral · Affiliate split · Yield (Steep) ││
                │  └──────────────────────────────────────────────┘│
                └──────────────────────────────────────────────────┘
```

## Voice-first UX (the differentiator)

Most AI apps are chat-first. Nakori inverts the order:

1. **User speaks** (Whisper PT-BR transcription, ~200 ms latency)
2. **Intent classifier** routes to one of 55 BR-PT templates
3. **Template** assembles a structured query (tax form, credit application, health check-in, ...)
4. **LLM** generates the answer + a marketplace recommendation if relevant
5. **TTS** speaks back the answer (optional; user can read it)
6. **Share button** posts the answer to WhatsApp with `✦ nakori.app` signature → viral K-factor 1.3

## Tech stack

| Layer | Technology |
|---|---|
| **Frontend** | Next.js 15 PWA · React Native (mobile, post-MVP) |
| **Backend** | Fastify · Node 20 |
| **Storage** | MongoDB · Firebase Auth |
| **Voice** | Groq Whisper PT-BR |
| **LLM Routing** | OpenRouter / Groq (subscription-tier aware) |
| **Wallet** | Smart contracts on SolVM Base / Arbitrum |
| **Distribution** | Native Play Store (0% fee) → iOS month 6+ |

## Monetisation (6 streams)

| Stream | Mechanism |
|---|---|
| **Subscription** (40%) | Freemium → Starter → Pro → Elite (€0.50–€3/month) |
| **Referral** (20%) | 10% recurring share for 12 months on referred users |
| **Marketplace affiliate** (15%) | Amazon / Hotmart / Shopee splits (70/30) |
| **Wallet fees** (10%) | On-chain transaction routing |
| **Yield share (RWA)** (10%) | Steep DeFi yield split |
| **Brand integrations** (5%) | Native journey sponsorship |

## Computational footprint

- **Today**: ~16 production containers; CPU-bound (Whisper inference offloaded to Groq).
- **At 10× scale**: dedicated GPU after **60K MAU** — margin shifts from 79% to 85%+, and PT-BR fine-tuning becomes feasible. SINES-class infrastructure unlocks unit economics that pure SaaS can't deliver at €0.50/month price points.
- **Voice traffic peaks**: Brazilian evenings (19h–23h GMT-3) require burst capacity — exactly what liquid-cooled, multi-tenant GPU infra is designed for.

## Distribution & growth

- **Zero-cost launch**: viral via WhatsApp (`✦ nakori.app` signature on every shared answer)
- **K-factor 1.3** validated in PMF experiments
- **Native Play Store** (0% Google fee for our pricing tier)
- **Micro-influencers CPA-only** (no fixed marketing spend)
- **Gate week 4**: D7 retention ≥ 20% before scaling spend

## Stage & evidence

- **MVP, 91.9% built** · final QA in progress
- **55 Brazilian-Portuguese journey templates** ready
- **OCR + Whisper PT-BR** integrated
- **Wallet Satoshi + Steep** smart contracts deployed on testnet
- **PMF experiments** documented; D7 ≥ 20% confirmed in beta cohort

## Trajectory

| Milestone | Target |
|---|---|
| **Month 2** | Break-even |
| **Month 6** | 18K MAU · R$48K MRR |
| **Month 12** | 90K MAU · R$241K MRR · 79% margin |
| **2027+** | Expansion to lusophone markets (Portugal, Angola, Mozambique, Cabo Verde) |

## About be-innpro

be-innpro builds **sovereign agentic AI for Europe and the lusophone world** — a unified stack of three production products (Datumlens, ORMAI, Nakori.Life) on one orchestration core. Founded in Lisbon by **José Maria Duque (CEO)** and **Neilsen Alves Seixas (CTO)**.

Website: [https://be-innpro.com](https://be-innpro.com)

## Status of this repository

This repository hosts a **public showcase only** — architecture, screenshots, README. The Nakori source code is **not public** while we finalise IP protection. Beta access is invitation-only; contact us to join the waitlist.

## Contact

- **CEO & Founder** — José Maria Duque — `jose@be-innpro.com`
- **CTO & Co-Founder** — Neilsen Alves Seixas — `neilsen.seixas@be-innpro.com`

---

© 2026 be-innpro. All rights reserved. Nakori.Life, Datumlens, ORMAI, and FORJA Process are protected by pending intellectual-property filings.
