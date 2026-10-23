# Backend rules — ASP.NET Core 10

Mandatory for every change in the `backend` repository.

## API design

- Controllers live in `src/Product.Api/Controllers`; one controller per aggregate.
  Controllers stay thin: parse, authorize, call an application service, map the
  result.
- Every endpoint returns typed results (`ActionResult<T>` or typed `Results<>`) and
  documents its error responses with `[ProducesResponseType]`.
- DTOs are request/response contracts only. Never expose EF Core entities on an
  endpoint.
- Validate input with FluentValidation validators registered in DI; never inline
  validation logic in controllers.
- API routes are versioned under `/api/v{version}/`. Breaking changes require a new
  version and a note in `architecture/decisions/`.

## Data access

- EF Core is the only data access path; no Dapper, no raw SQL outside migrations.
- Migrations are additive. A destructive migration (drop column or table) ships at
  least one release after the code stopped using it.
- Every query that touches tenant data goes through the global query filter in
  `AppDbContext`; never bypass it.

## Code quality

- Nullable reference types stay enabled; do not use `!` to silence the compiler.
- All I/O is async end to end: no `.Result`, no `.Wait()`, no `Task.Run` wrapping
  async code.
- Services are registered by interface with explicit lifetimes; never `new` up a
  service that has dependencies.
- A change is not done until `dotnet build` is warning-free and `dotnet test`
  passes.
