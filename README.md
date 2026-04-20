# HabitForge

HabitForge is a full-stack, gamified habit-tracking app built with Next.js.
It turns consistency into a game loop with XP, levels, streaks, achievements, charts, social sharing, and a freemium model.

## Tech Stack

- Next.js 16 (App Router + Route Handlers)
- TypeScript
- Tailwind CSS 4
- Prisma ORM
- Neon Postgres
- Chart.js + react-chartjs-2
- Zod validation

## Core Features

- Custom habit creation (daily/weekly, targets, descriptions, colors)
- Progress tracking (streaks, completion stats, charts)
- Gamification (XP, levels, achievements)
- Social accountability (opt-in leaderboard)
- Freemium model (premium analytics, CSV export, resources)

## Setup (Neon)

1. Install dependencies:

```bash
npm install
```

2. Copy env template:

```bash
cp .env.example .env
```

3. Put your Neon URLs in `.env`:

- `DATABASE_URL`: Neon pooled URL (`-pooler` host)
- `DIRECT_URL`: Neon direct URL (non-pooler host)

4. Generate Prisma client:

```bash
npm run prisma:generate
```

5. Create/apply schema in your Neon database (first time):

```bash
npm run prisma:migrate -- --name init
```

6. Run app:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

## Vercel Deployment

Set these environment variables in Vercel project settings:

- `DATABASE_URL`
- `DIRECT_URL`

Use this command in CI/deploy step after code is deployed:

```bash
npm run prisma:deploy
```

## Prisma Scripts

- `npm run prisma:generate`
- `npm run prisma:migrate`
- `npm run prisma:deploy`
- `npm run prisma:push`
- `npm run prisma:studio`

## API Routes

- `GET /api/users`
- `POST /api/users`
- `GET /api/users/[userId]/dashboard`
- `GET /api/users/[userId]/habits`
- `POST /api/users/[userId]/habits`
- `PATCH /api/users/[userId]/habits/[habitId]`
- `DELETE /api/users/[userId]/habits/[habitId]`
- `POST /api/users/[userId]/habits/[habitId]/complete`
- `PATCH /api/users/[userId]/subscription`
- `PATCH /api/users/[userId]/share`
- `GET /api/users/[userId]/premium/analytics`
- `GET /api/users/[userId]/premium/resources`
- `GET /api/users/[userId]/premium/export`
- `GET /api/leaderboard`
