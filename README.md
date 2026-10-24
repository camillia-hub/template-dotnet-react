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

Two payload areas have special meaning to the product rather than to the
workspace tree: `template.json` declares the expected repositories (see
[Template contract](#template-contract)), and `repos/` carries the seed
content the wizard applies to them (`api`, `web`).

## How to use

Install from the Camillia Community Hub, then create a workspace from this
template. Camillia installs the `workspace/` tree as the new workspace's
`.workspace` contract: the agent reads these rules, conventions, repository
descriptors and docs skeletons before every task. Where the workspace files
carry `{{ projectName }}` or `{{ orgName }}` tokens, they are substituted with
your project and organization names when the template is applied — no manual
placeholder hunt. After installation, point the repository descriptors at your
real repos and adjust the pinned versions to your stack.

## Template contract

`template.json` declares the repositories this product is made of; the
workspace wizard walks each one and offers to **create** a fresh repo at your
git provider or **load** an existing one:

| Key | Label | Description | Required | Override default |
|---|---|---|---|---|
| `api` | API service | ASP.NET Core Web API backend | yes | no |
| `web` | Web frontend | React + Vite SPA frontend | yes | no |

Seed content for each repo lives under `repos/<key>/` (a starter README and
`.gitignore`). Applying a seed to a repo that already has content requires the
"authorize content override" choice in the wizard; before anything is
overwritten the current branch heads are tagged
`camillia-backup/template-<yyyyMMdd-HHmmss>`, so existing work is never lost.

Replacement tokens — `{{ orgName }}`, `{{ projectName }}` and `{{ projectId }}`
— are substituted across all workspace-bound files at apply time. See the
[extension guidelines](https://github.com/camillia-hub/extension-guidelines)
for the full template contract.

## License

MIT — see [LICENSE](LICENSE).
