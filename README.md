# MAS Group — B2B Operations Platform

[![Quality Gate](https://github.com/kamiljan11/mas-group/actions/workflows/quality.yml/badge.svg)](https://github.com/kamiljan11/mas-group/actions/workflows/quality.yml)

**Live:** [maskalkulator.lovable.app](https://maskalkulator.lovable.app) · **Status:** production · **Built & operated by** [Kamil Jan](https://kamiljan.com)

A custom B2B operations platform running across MAS Group's verticals — **auto parts, print and logistics** — in Iceland.

## What it does
- Per-product-line **pricing calculators**
- **Quote-to-order pipeline** with 13-stage tracking
- **Commission management** for the sales team
- Role-based access for clients, sales reps and admins
- Automated logistics workflow (orders → SMS updates → customs → delivery) with Twilio/email integrations

## Stack
React · TypeScript · Supabase · Vercel · Google Apps Script · Twilio · n8n

## What this repository is

This is a **public reference repo, not the application** — there is no `package.json`, no
`src/`, nothing to `npm install` or run. The platform's source is private (see
[Source](#source) below). What lives here is the documentation trail: what the platform does,
why it's split this way, and how to tell if it's still alive. See
[`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) and
[`docs/adr/0001-public-repo-is-a-reference-not-the-source.md`](docs/adr/0001-public-repo-is-a-reference-not-the-source.md).

## Checking it's alive

```bash
curl -I https://maskalkulator.lovable.app   # 200 = up (the platform itself; www.masgroup.is is the company site, not this app)
```

CI (`.github/workflows/quality.yml`) runs a secrets scan and Semgrep on this repo's own
content; the npm-based steps (lint/typecheck/test/build) no-op here (`if: hashFiles('package.json') != ''`)
because there's no application code in this repo to run them on.

## Source
Application source: [`maskalkulator`](https://github.com/kamiljan11/maskalkulator) — proprietary operational code; access may be restricted. This repository is the public write-up — the product is live at [maskalkulator.lovable.app](https://maskalkulator.lovable.app).

## Licence

See [`LICENSE`](LICENSE) — proprietary, published for reference only.
