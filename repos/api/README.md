# {{ projectName }} — API

ASP.NET Core 10 Web API backend for **{{ projectName }}**.

## Layout

- `src/` — controllers, application services, domain model, EF Core context
- `tests/` — xUnit test suite mirroring `src/`

## Commands

```bash
dotnet restore
dotnet build
dotnet test
```

The workspace contract (`repositories/backend.md`) lists the build rules and
the quick checks the agent runs before calling a change done.
