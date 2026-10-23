# ASP.NET Core + React Product — Camillia workspace template

A Camillia Community Hub workspace template for teams building a web product on an
ASP.NET Core 10 Web API with a React, Vite and TypeScript single-page frontend.

## What's inside

The `workspace/` directory is the template's `.workspace` contract tree:

```
workspace/
  README.md                     workspace overview and agent navigation guide
  rules/
    backend.md                  ASP.NET Core rules: API design, EF Core, async
    frontend.md                 React/TypeScript rules: hooks, strict mode, API client
    security.md                 authentication, tenant isolation, secrets
  conventions/
    naming.md                   C#/TypeScript naming, branch names
    testing.md                  xUnit, Vitest, Playwright conventions
    commits.md                  conventional commits and PR rules
  repositories/
    backend.md                  backend descriptor: layout, dotnet commands
    frontend.md                 frontend descriptor: layout, npm scripts
  business/
    glossary.md                 domain vocabulary skeleton
    rules.md                    numbered business rules skeleton
  architecture/
    components.md               system components and responsibilities
    decisions/README.md         ADR format and decision log
    decisions/0001-asp-net-core-plus-react-spa.md
  technical/constraints/
    versions.md                 pinned toolchain versions
    hosting.md                  container and hosting constraints
  ui/
    map.md                      routes, pages and access map
```

## How to use

Install from the Camillia Community Hub, then create a workspace from this
template. Camillia installs the `workspace/` tree as the new workspace's
`.workspace` contract: the agent reads these rules, conventions, repository
descriptors and docs skeletons before every task. After installation, replace the
`<Product>` placeholders, point the repository descriptors at your real repos and
adjust the pinned versions to your stack.

## License

MIT — see [LICENSE](LICENSE).
