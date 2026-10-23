# Naming conventions

## C# / backend

- PascalCase for types, methods, properties and public fields; camelCase for
  parameters and locals; `_camelCase` for private fields.
- Interfaces start with `I`; their single production implementation drops it
  (`IOrderRepository` / `OrderRepository`).
- Async methods end in `Async`.
- Files are named after the primary type they contain.
- Test projects are `<ProjectUnderTest>.Tests`; test classes `<ClassUnderTest>Tests`;
  test methods `Method_State_Expectation`.

## TypeScript / frontend

- PascalCase for components and their files (`OrderList.tsx`); camelCase for hooks
  (`useOrders.ts`), utilities and variables.
- One component per file; co-locate its `*.module.css` and `*.test.tsx`.
- API types come from the generated client; hand-written shared types live in
  `src/types/`.

## Branches and pull requests

- Branches: `<type>/<task-id>-<short-slug>`, e.g. `feat/1234-order-export`.
- PR titles follow conventional commits (see `conventions/commits.md`).
