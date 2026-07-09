# Wandr — Personal Travel Decision Engine

> Stop searching. Start exploring.

Wandr is a startup-ready travel planning and discovery platform that helps users decide where to travel and plan their journeys intelligently.

## What it does

| Feature | Description |
|---------|-------------|
| **Discover places** | 3-question wizard → ranked destination recommendations |
| **Plan my journey** | Destination input → full itinerary with places, food, accommodation |
| **Trip optimizer** | Detects spare days → suggests nearby destinations |
| **Smart filters** | Amazon-style filters (transport, stay, category, crowd) |
| **Bucket list** | Save, prioritise, and track dream destinations |
| **Visited tracker** | Mark visited, rate, and track explorer progress |
| **Travel personality** | Auto-detected from behaviour (Road Trip Explorer, Nature Lover, etc.) |
| **Explorer progress** | Karnataka 35% complete — gamified travel tracking |

## Tech stack

- **Frontend** — Next.js 14, TypeScript, Tailwind CSS, React Query, Framer Motion
- **Backend** — NestJS, Drizzle ORM, PostgreSQL (Neon), Redis cache
- **Auth** — JWT + Google OAuth + email/password
- **Storage** — Cloudflare R2
- **Hosting** — Vercel + Railway + Neon

## Quick start

```bash
# See DEPLOYMENT.md for full setup guide
cd backend && npm install && npm run db:push && npx tsx src/common/seed.ts && npm run start:dev
cd frontend && npm install && npm run dev
```

## Recommendation engine

Seven-factor weighted scoring system:

| Factor | Weight | Description |
|--------|--------|-------------|
| Budget | 20% | How well destination budget matches user budget |
| Time | 15% | Whether destination fits available days |
| Group | 15% | Destination suitability for travel group type |
| Weather | 15% | Current weather suitability |
| Season | 10% | Whether it's the best season to visit |
| Distance | 10% | Proximity from user's home city |
| Preferences | 15% | Match with user's favourite categories + history |

Designed to be swapped with an ML model without changing the API contract.

## Roadmap

- **v1** (MVP) — Discover + Plan + Optimizer + Auth + Profile
- **v2** — Real-time weather API, Google Maps embed, mobile app
- **v3** — AI recommendations (replace rule engine), collaborative trips, social sharing

## License

MIT
