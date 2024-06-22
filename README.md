This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app), with Redis Upstash and Hono API that deploy in Cloudflare.

## Getting Started

First, make sure you have [Upstash](https://upstash.com/) and [Cloudflare Workers](https://workers.cloudflare.com/) account. If not go create it first.

## Setup Redis and Cloudflare Workers

- For the [Upstash](https://upstash.com/) - create redis database base on your (nearby) region. 
- And for the [`Cloudflare Workers`](https://workers.cloudflare.com/) make sure you verify your email after creating an account.

## Create wrangler file

create `wrangler.toml` file in root directory with value below:

```bash
name="countrysearchapi"
compatibility_date = "2024-06-15"

[vars]
UPSTASH_REDIS_REST_TOKEN="upstash redis token"
UPSTASH_REDIS_REST_URL="upstash redis url"
```
Make sure you have string quotes for the value

You can find the token and endpoint in the [Upstash Console](https://console.upstash.com/), in connect to database section select javascript

## Seeding Upstash Database

```bash
npm tsx src/lib/seed.ts
```

## Deploy to Cloudflare Workers

```bash
npm run deploy
```

## Run Development Server

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.