# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project State

This is a greenfield project. No framework, build tooling, or source files have been added yet. The only scaffolding present is:

- `.env` — Supabase connection credentials (`VITE_SUPABASE_URL`, `VITE_SUPABASE_SUPABASE_ANON_KEY`)
- `package-lock.json` — empty lock file (no dependencies installed)
- `robots.txt` — allows all crawlers
- `placeholder.svg` — a wordmark SVG asset

## Stack Constraints

- **Database**: Supabase (already provisioned — do not create a new instance)
- **Frontend server**: Vite
- **Environment variables** use the `VITE_` prefix, consumed via `import.meta.env`
- The anon key env var name is `VITE_SUPABASE_SUPABASE_ANON_KEY` (note the double "SUPABASE")

## Commands

Once a `package.json` is created and dependencies are installed, standard Vite commands apply:

```bash
npm install          # install dependencies
npm run dev          # start dev server
npm run build        # production build
npm run preview      # preview production build
```

## Database

Migrations are managed via the `mcp__supabase__apply_migration` tool. All tables must have RLS enabled. No migrations have been applied yet.
