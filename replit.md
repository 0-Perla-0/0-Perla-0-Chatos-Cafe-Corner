# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Hosts the **Chato's Cafecito Canino** SPA.

## Artifacts

- **chatos-cafecito** (`/`) — Vanilla HTML/CSS/JS single-page app for Chato's Cafecito Canino. Inspired by neko-hi.com, with pastel-pink palette, Quicksand typography, multi-language selector (ES/EN/FR/PT/IT/DE/JA/ZH/KO/RU/AR), Google Maps embed, service hours table, full menu (humans + pets) and academic footer with the CUCEI logo.
  - `index.html` — page markup with `data-i18n` keys.
  - `public/style.css` — pastel pink/cream/dark-grey theme.
  - `public/script.js` — translations dictionary + language switcher + smooth scroll + reveal-on-scroll.
  - `public/logo_cucei_1.webp` — CUCEI logo used in the footer.
- **api-server** — Express 5 API (not used by the SPA but kept available).
- **mockup-sandbox** — design canvas (not used).

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally
- `pnpm --filter @workspace/chatos-cafecito run dev` — run the SPA locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
