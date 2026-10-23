# Testing conventions

## Backend — xUnit

- Unit tests mirror the source tree in `tests/Product.UnitTests`.
- Integration tests use `WebApplicationFactory` with Testcontainers (PostgreSQL) in
  `tests/Product.IntegrationTests`; they run in CI, not on every local save.
- New business logic ships with unit tests; new endpoints ship with at least one
  integration test for the happy path and one for an authorization failure.
- Run `dotnet test` before pushing.

## Frontend — Vitest + Testing Library

- Component tests live next to the component (`*.test.tsx`) and assert behavior,
  not implementation details.
- Hooks are tested with `renderHook`; API traffic is mocked with MSW handlers in
  `src/test/mocks/`.
- Run `npm run test` before pushing; `npm run test:coverage` must keep global line
  coverage at or above 80%.

## End-to-end — Playwright

- Specs in the `e2e/` folder of the frontend repo cover the critical journeys (sign
  in, create an order, change its state). They run in CI against the ephemeral
  review environment.
