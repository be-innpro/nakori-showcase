# Nakori.Life

> **"AI does. You live." — A voice-first super-app for the lusophone consumer community.**
> A be-innpro product. Submitted to the **START Rise Challenge 2026**.

[![Status](https://img.shields.io/badge/status-MVP%20%C2%B7%20pre--PMF-blue)]()
[![License](https://img.shields.io/badge/license-Proprietary-orange)]()
[![Stack](https://img.shields.io/badge/stack-PWA%20%E2%80%A2%20Node%2020%20%E2%80%A2%20Fastify-success)]()

---

## What it is

Nakori.Life is a **voice-first AI super-app** for the lusophone consumer community — people whose first interaction with a smartphone is voice, who often aren't well served by global, English-trained assistants, and who need practical access to everyday services without textual friction.

Three integrated experiences in one app:

1. **Nakori AI** — voice-first copilot with a Portuguese-language journey-template library (tax, credit, health, legal, financial)
2. **Nakori Shop** — contextual marketplace with affiliate revenue
3. **Nakori Life** — AI-guided journeys for finance, health, and career
4. **Wallet (declared compliance roadmap)** — Satoshi + Steep (DeFi/RWA) on a regulatory roadmap (BCB/CVM in Brazil, MiCA in EU). **Not in V1**, conditional on regulatory partnerships.

## Target market — lusophone community

Nakori.Life addresses the lusophone consumer community in sequence, with each market chosen by scale, infrastructure readiness, and unit-economics validation:

- **Brazil first by scale** — large addressable Android base in classes C and D, voice-first context (a substantial share of WhatsApp daily traffic is audio rather than text), low fluency in English-language assistants.
- **Portugal continental and islands** — cultural and linguistic adaptation; the same technical engine, retuned for European-Portuguese variants and local journey templates.
- **PALOP markets in sequence** — Angola, Mozambique, Cabo Verde — as connectivity and unit economics validate.

The mass-market lusophone consumer is structurally underserved: low digital literacy rules out complex chat-first UX, low disposable income rules out enterprise-class subscription pricing, low banking penetration in some segments rules out standard credit-card-first onboarding, and limited fluency in English rules out unlocalised global assistants.

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
                └──────────────────────────────────────────────────┘
```

## Voice-first UX (the differentiator)

Most AI apps are chat-first. Nakori inverts the order:

1. **User speaks** (Whisper PT-BR transcription with adaptation to lusophone variants on the roadmap)
2. **Intent classifier** routes to a journey template
3. **Template** assembles a structured query (tax form, credit application, health check-in, ...)
4. **LLM** generates the answer + a marketplace recommendation if relevant
5. **TTS** speaks back the answer (optional; user can read it)
6. **Share button** posts the answer to WhatsApp with a Nakori signature → passive virality

## Tech stack

| Layer | Technology |
|---|---|
| **Frontend** | Next.js 15 PWA · React Native (mobile, post-MVP) |
| **Backend** | Fastify · Node 20 |
| **Storage** | MongoDB · Firebase Auth |
| **Voice** | Groq Whisper PT-BR (with adaptation to lusophone variants on the roadmap) |
| **LLM Routing** | OpenRouter / Groq (subscription-tier aware) |
| **Wallet (roadmap)** | Smart contracts on SolVM Base / Arbitrum — declared compliance roadmap (BCB/CVM in Brazil, MiCA in EU) |
| **Distribution** | Native app stores (Google Play first, App Store next) + own portal under construction |

## Commercial model

Nakori.life is distributed direct-to-consumer through app stores and a portal under construction. Revenue is composed of multiple complementary streams:

- **Subscription** (freemium with broad free tier; tiered paid plans for advanced features)
- **Marketplace affiliate** (70/30 split with creators)
- **Referral incentives** (recurring share for a defined period)
- **Wallet fees** (when the compliance roadmap unlocks Wallet in production)
- **Brand integrations** (native journey sponsorship, where contextually relevant)

For pricing details and waitlist access, see [be-innpro.com](https://be-innpro.com) or contact `jose@be-innpro.com`.

## Computational footprint

- **Today**: containerised stack, CPU-bound, voice inference offloaded to Groq.
- **At scale**: a dedicated GPU substrate (such as a SINES-class facility) becomes essential to keep unit economics aligned with mass-market lusophone-consumer pricing — both for inference cost and for fine-tuning Portuguese-language variants. **Brazilian-evening voice traffic peaks** (a window of high-concurrency audio interaction) require burst capacity that liquid-cooled, multi-tenant GPU infra is built for.

## Distribution & growth

- **Zero-cost launch** via app stores and viral WhatsApp sharing (Nakori signature on every shared answer)
- **Native app stores** (no aggressive distributor fee on the targeted tier)
- **CPA-only micro-influencers** (no fixed marketing spend in phase 1)
- **Validated retention gates** before scaling spend (D7-retention thresholds enforced before any paid acquisition)

## Stage

- **MVP, voice-first** · final QA in progress
- **Portuguese-language journey-template library** ready
- **OCR + Whisper PT-BR** integrated
- **PMF experiments** documented; retention gates in place

## About be-innpro

be-innpro builds **sovereign agentic AI for Europe and the lusophone world** — four layers, four commercial products: **Forja Process** (methodology), **ORMAI** (agentic cognition), **DatumLens** (B2B EU vertical), **Nakori.life** (B2C lusophone vertical) — on one unified technical core. Founded in Lisbon by **José Maria Duque (CEO)** and **Neilsen Alves Seixas (CTO)**.

Website: [https://be-innpro.com](https://be-innpro.com)

## Status of this repository

This repository hosts a **public showcase only** — architecture, screenshots, README. The Nakori source code is **not public** while we finalise IP protection. Beta access is invitation-only; contact us to join the waitlist.

## Contact

- **CEO & Founder** — José Maria Duque — `j.duque@be-innpro.com`
- **CTO & Co-Founder** — Neilsen Alves Seixas — `neilsen.seixas@be-innpro.com`

---

© 2026 be-innpro. All rights reserved. Nakori.Life, Datumlens, ORMAI, and FORJA Process are protected by pending intellectual-property filings.
