# ADR-0001: ASP.NET Core API with a React SPA

- Status: accepted
- Date: 2026-01-15

## Context

The product needs a typed, testable backend and a fast, independently deployable
user interface. The team has deep .NET and TypeScript experience.

## Decision

Build an ASP.NET Core 10 Web API as the single backend and a React + Vite +
TypeScript SPA as the single frontend. The frontend's API client is generated from
the backend OpenAPI document; there is no server-side rendering.

## Consequences

The contract between the two repositories is explicit and testable, and they deploy
independently. Pages that need search-engine visibility must live on a separate
public site — this SPA sits behind login.
