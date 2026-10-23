# Repository: backend

| | |
| --- | --- |
| Name | `backend` |
| Stack | ASP.NET Core 10 Web API, C# 14, EF Core 10, PostgreSQL 16 |
| Solution | `Product.sln` at the repository root |

## Layout

```
backend/
  src/
    Product.Api/             controllers, Program.cs, configuration
    Product.Application/     use cases, validators, DTOs
    Product.Domain/          entities, domain services, repository interfaces
    Product.Infrastructure/  EF Core, AppDbContext, repositories, integrations
  tests/
    Product.UnitTests/
    Product.IntegrationTests/
```

## Commands

| Task | Command |
| --- | --- |
| Restore and build | `dotnet build` |
| Run the API locally | `dotnet run --project src/Product.Api` |
| Unit and integration tests | `dotnet test` |
| Add a migration | `dotnet ef migrations add <Name> --project src/Product.Infrastructure --startup-project src/Product.Api` |
| Apply migrations locally | `dotnet ef database update --project src/Product.Infrastructure --startup-project src/Product.Api` |
| OpenAPI document | served at `/openapi/v1.json` when the API runs |

Quick check before pushing: `dotnet build` (warning-free) and `dotnet test`.
