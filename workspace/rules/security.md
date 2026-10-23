# Security rules

Apply to every repository in this workspace.

- Secrets never enter source control: no connection strings, tokens or passwords in
  code, config, tests or docs. Local secrets use user-secrets (backend) or
  `.env.local` (frontend); deployed secrets come from the platform vault.
- Every API endpoint requires authentication unless it is explicitly listed as
  public in `architecture/components.md`. Authorization is enforced in the
  application service, not only by a controller attribute.
- Tenant isolation is a hard rule: a request may only touch data of the caller's
  tenant. Cross-tenant tooling requires an ADR.
- Log structured events; never log payloads containing personal data or
  credentials.
- Dependencies with known high-severity vulnerabilities are upgraded before the
  task is considered done.
