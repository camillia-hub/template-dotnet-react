# Hosting constraints

- Everything runs as Linux containers on the {{ orgName }} Kubernetes cluster. Base
  images: `mcr.microsoft.com/dotnet/aspnet:10.0-alpine` for the API; `node:22-alpine`
  (build stage) and `nginx:alpine` (runtime stage) for the frontend. Containers run
  rootless.
- The API listens on port 8080 behind the ingress, which terminates TLS.
- The frontend is a static build served by nginx; it holds no server-side secrets.
  Only the public API base URL is injected at container start.
- Runtime configuration comes from environment variables only; no mounted config
  files containing secrets. Secret values are injected by the platform vault.
- Outbound calls from the API go only to services listed in
  `architecture/components.md`.
