# SimToolBox

A collection of interconnected financial simulation tools for learning, testing, and demonstrating modern payment and banking infrastructure.

## Overview

SimToolBox is an ecosystem of simulators that model real-world financial systems. These projects work together to create a complete payment processing environment—from customer banking, through payment networks, to merchant storefronts and digital wallets.

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│    BSIM     │     │    NSIM     │     │    SSIM     │
│   Banking   │◄───►│   Network   │◄───►│    Store    │
│  Simulator  │     │  Simulator  │     │  Simulator  │
└─────────────┘     └─────────────┘     └─────────────┘
       ▲                   ▲                   ▲
       │                   │                   │
       └───────────┬───────┴───────────────────┘
                   │
            ┌─────────────┐
            │    WSIM     │
            │   Wallet    │
            │  Simulator  │
            └─────────────┘
```

## Projects

| Project | Description | Repository |
|---------|-------------|------------|
| **BSIM** | Full-stack banking simulator with accounts, credit cards, WebAuthn authentication, and Open Banking APIs | [bsim](https://github.com/jordancrombie/bsim) |
| **NSIM** | Payment network middleware that routes transactions between merchants and banks | [nsim](https://github.com/jordancrombie/nsim) |
| **SSIM** | E-commerce store simulator with product catalog, checkout, and payment lifecycle management | [ssim](https://github.com/jordancrombie/ssim) |
| **WSIM** | Digital wallet simulator (like Apple Pay) for aggregating cards from multiple banks | [wsim](https://github.com/jordancrombie/wsim) |

## How They Work Together

1. **BSIM (Bank)** - Users create accounts, manage funds, and issue credit cards. Provides OAuth 2.0/OIDC for authentication across the ecosystem.

2. **WSIM (Wallet)** - Users enroll their BSIM cards into a digital wallet for convenient payments without re-authenticating.

3. **SSIM (Store)** - Merchants sell products. Customers authenticate via BSIM or pay with WSIM wallet credentials.

4. **NSIM (Network)** - Routes payment authorizations from SSIM to BSIM, handles captures, refunds, and webhooks—acting like Visa/Mastercard networks.

## Use Cases

- **Learning**: Understand how modern payment systems interconnect
- **Testing**: Develop and test payment integrations in a safe sandbox
- **Demonstration**: Showcase OAuth flows, WebAuthn, and payment processing
- **Prototyping**: Build new financial applications against realistic APIs

## Getting Started

Each project has its own setup instructions. We recommend starting in this order:

1. **[BSIM](https://github.com/jordancrombie/bsim)** - Set up the banking backend first (provides authentication)
2. **[NSIM](https://github.com/jordancrombie/nsim)** - Deploy the payment network
3. **[SSIM](https://github.com/jordancrombie/ssim)** - Launch the store simulator
4. **[WSIM](https://github.com/jordancrombie/wsim)** - Add wallet capabilities (optional)

## Tech Stack

All projects share a common technical foundation:

- **Backend**: Node.js, Express, TypeScript
- **Frontend**: Next.js, React, Tailwind CSS
- **Database**: PostgreSQL with Prisma ORM
- **Auth**: OAuth 2.0/OIDC, WebAuthn/Passkeys, JWT
- **Infrastructure**: Docker, Docker Compose

## License

See individual project repositories for license information.
