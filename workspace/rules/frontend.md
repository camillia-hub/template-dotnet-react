# Frontend rules — React + Vite + TypeScript

Mandatory for every change in the `frontend` repository.

- Function components and hooks only; no class components.
- TypeScript `strict` stays on. `any` is forbidden outside test helpers; use
  `unknown` and narrow.
- Server state comes from TanStack Query; UI state from React context or component
  state. Do not add a global store library without an ADR.
- All API calls go through the generated client in `src/api/` (produced by
  `npm run api:generate` from the backend OpenAPI document). Never hand-write
  `fetch` calls against the API.
- Forms use react-hook-form with zod schemas that mirror the API contract types.
- Styling comes from the design system in `src/ui/`; no inline styles, and new CSS
  only as a component-level CSS module.
- Routes are declared in `src/app/router.tsx` and must match `ui/map.md`; update
  the map when you add, move or remove a page.
- A change is not done until `npm run lint`, `npm run typecheck`, `npm run test`
  and `npm run build` all pass.
