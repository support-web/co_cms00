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

## システムの使い方（日本語）
このリポジトリはモノレポ構成のため、ローカル環境を整えてから各アプリを起動します。

1. 前提ツールを用意する
   - Node.js 18 以上、pnpm 8 以上をインストールします。
   - Docker が使える場合は、`infra/docker/docker-compose.yml` のサービス（PostgreSQL/Redis/MinIO）を立ち上げると便利です。
     ```bash
     cd infra/docker
     docker compose up -d
     ```
2. 依存関係をインストールする
   ```bash
   pnpm install
   ```
3. 各アプリを開発モードで起動する
   - Turborepo 経由で一括起動（スクリプト整備後に有効化予定）
     ```bash
     pnpm turbo run dev
     ```
   - または個別に実行（各アプリの `package.json` にスクリプトを追加後）
     ```bash
     pnpm --filter admin dev   # 管理画面
     pnpm --filter web dev     # 公開サイト
     pnpm --filter api dev     # API サーバー
     ```
4. 設計・要件の確認
   - 製品の詳細要件は `docs/仕様書.md` にまとまっています。開発前に参照してください。

> 現時点ではスケルトンのみで、各アプリの実装やスクリプトはこれから追加されます。
