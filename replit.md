# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

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
- **Auth**: Clerk (Google + email via Replit-managed Clerk)

## Artifacts

- **linktree** (`/`) — LinkBio link-in-bio platform (React + Vite)
- **api-server** (`/api`) — Express API backend

## LinkBio Features

A premium link-in-bio platform (Linktree alternative) with:
- Burgundy (#800020) glassmorphism design
- Google & email authentication via Clerk
- Profile editor: avatar upload, bio, username, display name
- Custom background image upload
- Multiple social media links with drag-to-reorder
- Theme customization: primary color, button style, font family
- Live phone-frame preview while editing
- Public shareable profile page at `/p/:username`
- Mobile-first responsive design

## Database Schema

- `profiles` — user profiles (userId, username, displayName, bio, avatarUrl, backgroundUrl, theme JSON)
- `links` — user links (profileId, title, url, platform, isActive, sortOrder)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
