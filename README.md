# Claude.md — Nuxt.js Project Instructions

## Project Overview
This is a **Nuxt 4** application using **Vue 3 (Composition API)**.
The project is private and intended for internal development.

Primary goals:
- Clean, maintainable code
- Clear separation between UI, data, and server logic
- Practical, production-ready solutions (not demos)

---

## Tech Stack
- Nuxt: v4.x
- Vue: v3.x (Composition API only)
- UI: @nuxt/ui
- Styling: Tailwind CSS v4
- Content: @nuxt/content v3
- Database: SQLite (better-sqlite3)
- Module system: ES Modules (`type: module`)

---

## General Rules
- Prefer **clarity over cleverness**
- Follow **Nuxt conventions** unless explicitly instructed otherwise
- Avoid unnecessary abstractions
- Do not introduce new dependencies unless clearly justified
- Assume this project is **long-lived**, not a prototype

---

## Vue & Nuxt Rules
- Use **Composition API** only
- Use `<script setup>` syntax
- Do NOT use Options API
- Prefer `defineProps`, `defineEmits`, and composables
- Use `useFetch`, `useAsyncData`, or server routes appropriately
- Do not access the database directly from client-side code

---

## File & Directory Conventions
- Pages go in `/pages`
- Reusable components go in `/components`
- Composables go in `/composables`
- Server logic goes in `/server`
- Database access must live in `/server/*`
- Content files belong in `/content`

---

## Project Initialization

```bash
pnpm create nuxt@latest kh-intern
cd kh-intern
pnpm approve-builds
pnpm add vue @nuxt/ui
pnpm add --save-dev tailwindcss
pnpm install
pnpm dev
```
