# MFCMS (Mobile First CMS)

This repository hosts a monorepo for building a mobile-first CMS platform described in `docs/仕様書.md`.
The project is organized for pnpm + Turborepo with separate applications for admin, public web, and API services.

## Repository structure
- `apps/admin` – Admin console (Next.js planned)
- `apps/web` – Public web renderer (Next.js planned)
- `apps/api` – API service (NestJS/Fastify planned)
- `packages/ui` – Shared UI library
- `packages/sdk` – API SDK client
- `packages/blocks` – Block definitions/renderers
- `packages/config` – Shared configuration (ESLint/TS config, etc.)
- `infra/docker` – Local development docker-compose
- `infra/migrations` – Database migrations
- `docs` – Specifications and design docs

## Getting started
1. Install pnpm (v8+) and Node.js (v18+).
2. Run `pnpm install` to install workspace dependencies (once package manifests are added).
3. Use `pnpm turbo run dev` (to be defined) to start individual apps.

Refer to `docs/仕様書.md` for the full product requirements.
