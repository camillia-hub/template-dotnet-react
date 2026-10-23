# Version constraints

| Component | Pinned version | Notes |
| --- | --- | --- |
| .NET | 10 (SDK 10.0.x) | `global.json` pins the SDK with `latestPatch` roll-forward. |
| C# | 14 | Nullable reference types and implicit usings enabled everywhere. |
| EF Core | 10.x | Moves with the .NET major version. |
| Node.js | 22 LTS | Set in `frontend/.nvmrc` and in CI. |
| TypeScript | 5.9.x | `strict: true`; no downgrades. |
| React | 19.x | Function components only. |
| Vite | 7.x | Dev server on port 5173. |
| PostgreSQL | 16 | Same major version locally (Testcontainers), in staging and in production. |

Upgrades are dedicated chores, one ecosystem at a time, merged only with the full
test suite green.
