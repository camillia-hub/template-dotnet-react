# System components

```
+-----------+   HTTPS/JSON   +--------------------+   SQL   +------------+
| frontend  | -------------> | backend (API)      | ------> | PostgreSQL |
| React SPA | <------------- | ASP.NET Core 10    |         | 16         |
+-----------+                +---------+----------+         +------------+
                                       |
                                       v
                              +----------------+
                              | Object storage |  (attachments, exports)
                              +----------------+
```

| Component | Repository | Responsibility |
| --- | --- | --- |
| frontend | `frontend` | SPA served as static assets; talks only to the API. |
| backend | `backend` | All business logic, authorization and data access. |
| PostgreSQL | managed service | System of record; owned exclusively by the backend. |
| Object storage | managed service | Binary attachments via short-lived signed URLs issued by the backend. |

Public endpoints (no authentication) are only: `GET /health`, plus the login and
password-reset endpoints. Everything else requires a valid session token.
