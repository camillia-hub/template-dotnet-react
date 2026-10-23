# Commit and pull-request conventions

- Conventional Commits: `feat:`, `fix:`, `chore:`, `refactor:`, `test:`, `docs:`,
  `perf:`, optionally scoped — `feat(orders): add csv export`.
- One logical change per commit; the message explains why, not what.
- Keep PRs under roughly 400 changed lines; split larger work behind feature flags.
- Every PR links its task in the description and lists the checks the author ran
  (`dotnet test`, `npm run test`, and friends).
- Squash-merge to `main`; the merge commit keeps the conventional-commit title.
