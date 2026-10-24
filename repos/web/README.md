# {{ projectName }} — Web

React 19 + Vite + TypeScript single-page frontend for **{{ projectName }}**.
Talks to the API service (`api` repository).

## Layout

- `src/` — routes, components, API client
- `tests/` — Vitest unit tests, Playwright end-to-end specs

## Commands

```bash
npm install
npm run dev
npm run build
npm test
```

The workspace contract (`repositories/frontend.md`) lists the build rules and
the quick checks the agent runs before calling a change done.
