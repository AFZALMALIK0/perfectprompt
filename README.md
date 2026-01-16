# PerfectPrompt Starter (modern prompt builder)

A full-stack **Next.js + Prisma (SQLite)** web app:
- Landing page (modern vibe)
- Sign up / Sign in
- Email or phone + password login
- OTP login via **SMS / WhatsApp / Email** (dev mode prints OTP in server logs)
- Prompt builder that turns an idea into a structured prompt
- Save & manage prompts in your account

> Inspired by prompt-generator style tools like PromptCowboy.  

---

## 1) Install

```bash
npm i
cp .env.example .env
```

## 2) Setup database

```bash
npm run prisma:migrate
```

This creates `dev.db` (SQLite) and generates Prisma client.

## 3) Run

```bash
npm run dev
```

Open http://localhost:3000

---

## OTP (SMS/WhatsApp/Email)

By default, OTP is printed in your terminal.

To enable real sending:
- Edit `src/lib/notify.ts` and plug:
  - **Twilio** for SMS + WhatsApp (recommended)
  - Resend/SendGrid/SES for email

---

## Deploy

Any Node host works (Vercel, Render, Railway, etc.)
- Set `DATABASE_URL` to a hosted database (Postgres recommended for production)
- Set a strong `JWT_SECRET`

---

## Folder highlights

- `src/app/` pages + API routes
- `src/app/api/auth/*` auth endpoints
- `src/app/api/generate` prompt builder endpoint
- `src/app/api/prompts` save prompts (CRUD)
- `prisma/schema.prisma` DB models

Enjoy 🤠
