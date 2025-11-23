# TinyLink — URL Shortener



TinyLink is a simple and modern URL Shortener built using Next.js, TypeScript, Prisma, and Neon Postgres.

---

## 🌟 Key Features

🔗Create short links

🎯 Custom short codes (6–8 chars)

📈 Track clicks & last visited time

🗑 Delete short URLs

🔁 Auto-refresh dashboard every 3s

➡️ Server-side redirect /[code]

🛡 Safe URL validation (http/https)

---

## Tech Stack

1.Next.js 15+

2.TypeScript

3.Prisma ORM

4.Neon (PostgreSQL)

5.Tailwind CSS

---

## Setup

git clone https://github.com/ajayduraisamy/TinyLink.git

cd tinylink


---

## Install packages
npm install

---


##  Create .env
DATABASE_URL="your_neon_db_url"
BASE_URL="http://localhost:3000"

---
## Generate Prisma Client
npx prisma generate


---

## Run the dev server
npm run dev


---

## Prisma Schema
model Link {
  code        String   @id
  targetUrl   String
  totalClicks Int      @default(0)
  lastClicked DateTime?
  createdAt   DateTime @default(now())
}


## API Routes

{
  "targetUrl": "https://google.com",
  "code": "custom123"
}
➤ GET /api/links

Get all links

➤ GET /api/links/[code]

Fetch single link

➤ DELETE /api/links/[code]

Delete a link

➤ GET /[code]

Redirect handler

increments totalClicks

updates lastClicked


## Dashboard
Add long URL

Optional custom code

View all short links

Auto-refresh every 3 seconds

Delete button

Last clicked time + total clicks

## Demo Page
/demo
