# Repository: frontend

| | |
| --- | --- |
| Name | `frontend` |
| Stack | React 19, Vite 7, TypeScript 5.9 (strict), TanStack Query, react-hook-form + zod |
| Package manager | npm on Node 22 |

## Layout

```
frontend/
  src/
    app/        router.tsx, providers
    api/        generated API client (do not edit by hand)
    features/   one folder per domain feature: components, hooks, schemas
    ui/         design-system components
    test/       MSW handlers, test setup
    types/      hand-written shared types
  e2e/          Playwright specs
```

## Commands

| Task | Command |
| --- | --- |
| Install dependencies | `npm ci` |
| Dev server (http://localhost:5173) | `npm run dev` |
| Regenerate the API client | `npm run api:generate` |
| Lint | `npm run lint` |
| Type check | `npm run typecheck` |
| Unit tests | `npm run test` |
| Coverage | `npm run test:coverage` |
| Production build | `npm run build` |
| E2E tests | `npm run e2e` |

Quick check before pushing:
`npm run lint && npm run typecheck && npm run test && npm run build`.
