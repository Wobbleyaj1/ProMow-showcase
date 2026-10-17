# ProMow

**A modern marketplace for reliable lawn care.**

ProMow connects customers with vetted lawn-care providers for simple, transparent, and trackable outdoor services. The product combines a customer booking experience with provider operations and RPG-style progression that rewards great work.

> This is a public product showcase. The implementation repository is intentionally private.

## Product vision

Make recurring lawn care as easy to book and trust as ordering a ride—while giving local providers a clear path to build reputation, skills, and earnings.

## What the product includes

### For customers

- Service-aware booking with condition details that improve price accuracy
- Property and service management for recurring or one-time visits
- Secure Stripe checkout and automatic store-credit handling
- Photo-based job context before a provider accepts a job
- Live job status updates from payment through completion
- Weather-aware postponement and rescheduling flows
- Provider profiles with tiers, skills, portfolios, and reviews
- A payment-release window with an issue-reporting escape hatch

### For providers

- Application and approval workflow with profile requirements
- Tier-gated job discovery and photo-informed claims
- Before/after photo gates for accountable service delivery
- Condition-dispute workflow when the job differs materially from its description
- XP, levels, service skills, badges, bonuses, and leaderboards
- Curated portfolios built from completed work
- Weather notifications and schedule protection

### For operations

- Admin action queue for provider approvals, disputes, and review flags
- Stripe Connect payouts with delayed release after completion
- Idempotent payment webhooks and database-enforced access controls
- Cached forecast processing for predictable schedule views
- Transactional email notifications for important booking milestones

## Service catalog

Mow · Edge · Trim · Blow · Hedge Trim · Pressure Wash Driveway · Siding Wash · Aerate · Dethatch

## High-level architecture

```text
Customer web experience ─┐
                         ├── ProMow application platform ── Supabase
Provider web experience ─┘             │                    ├─ Auth
                                       │                    ├─ Postgres
                                       │                    ├─ Storage
                                       │                    └─ Realtime
                                       ├── Stripe Connect
                                       ├── Forecast providers
                                       └── Transactional email
```

The product is designed as a TypeScript monorepo with a Next.js web application, a future Expo mobile client, shared domain types, pure business logic, a typed API client, and a shared UI layer.

## Product principles

- **Trust before transaction:** photos, condition acknowledgements, profiles, reviews, and clear status transitions reduce surprises.
- **Protection for both sides:** weather handling, disputes, cancellation rules, and payment-release timing make commitments explicit.
- **Reward quality:** provider progression is tied to completed work and service-specific experience.
- **Secure by default:** payments are processed by Stripe, secrets stay server-side, and authorization is enforced at the data layer.

## Status

ProMow is an actively developed product concept and implementation. This public repository documents the product direction and selected capabilities without exposing the private implementation.

## Links

- **Product website:** [promow.org](https://promow.org)
- **Demo:** Coming soon
- **Contact:** Open an issue in this repository for product questions or partnership inquiries

## Privacy and source availability

This repository intentionally contains no source code, infrastructure configuration, environment values, database exports, customer/provider records, or operational secrets. The implementation repository is private.

## License

The documentation and original product materials in this repository are © 2026 ProMow. All rights reserved. No license is granted to copy, modify, or redistribute the ProMow brand, product materials, or documentation without written permission.

