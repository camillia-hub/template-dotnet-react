# Product workspace: ASP.NET Core API + React SPA

This workspace builds and evolves **{{ projectName }}**, a web product made of:

- `backend` — an ASP.NET Core 10 Web API (see `repositories/backend.md`).
- `frontend` — a React 19 + Vite + TypeScript single-page app (see
  `repositories/frontend.md`).

## How the agent should navigate this workspace

Read in this order before your first task:

1. `rules/` — mandatory rules. `backend.md` and `frontend.md` are stack-specific,
   `security.md` always applies. Rules win over conventions when they conflict.
2. `conventions/` — how code is named, tested and committed.
3. `repositories/` — one descriptor per repository: layout plus build and test
   commands. Run the quick checks listed there before you call a change done.
4. `business/` — the domain vocabulary (`glossary.md`) and the numbered business
   rules (`rules.md`) the product enforces. Use these exact terms in code and in
   explanations.
5. `architecture/components.md` — what the system is made of and who owns what.
   `architecture/decisions/` logs ADRs; add one when you change something
   structural.
6. `technical/constraints/` — pinned versions and hosting limits you may not
   exceed.
7. `ui/map.md` — the routes and screens of the frontend; keep it in sync when you
   add, move or remove a page.

When a task teaches you a durable fact about the domain, record it in
`business/glossary.md` or `business/rules.md` — not only in the task paper.
