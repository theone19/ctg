# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev          # start dev server (Vite, hot reload)
npm run build        # type-check + production build (runs in parallel)
npm run build-only   # vite build only, no type-check
npm run type-check   # vue-tsc type check only
npm run preview      # preview production build locally
```

## Stack

- **Vue 3** with Composition API (`<script setup>`)
- **Vite 8** — dev server and bundler
- **Vue Router 5** — history-mode routing, defined in `src/router/index.ts`
- **Pinia 3** — state management, stores in `src/stores/`
- **TypeScript 6** — split tsconfig: `tsconfig.app.json` for src, `tsconfig.node.json` for vite config

## Path alias

`@` resolves to `src/` — use `@/components/Foo.vue`, `@/stores/bar`, etc.

## Conventions

- Stores use the **setup store** style (`defineStore('id', () => { ... })`), not the options API style.
- New routes go in `src/router/index.ts`. Lazy-load views with `() => import('../views/FooView.vue')` for code splitting.
- Global styles live in `src/assets/`; `main.css` imports `base.css`.
