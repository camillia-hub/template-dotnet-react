# UI map

Single-page app in the `frontend` repository; routes are declared in
`src/app/router.tsx`. Keep this file in sync when you add, move or remove a route.

| Route | Page component | Feature folder | Access |
| --- | --- | --- | --- |
| `/login` | `LoginPage` | `features/auth` | public |
| `/` | `DashboardPage` | `features/dashboard` | member+ |
| `/orders` | `OrderListPage` | `features/orders` | member+ |
| `/orders/:orderId` | `OrderDetailsPage` | `features/orders` | member+ |
| `/orders/new` | `OrderCreatePage` | `features/orders` | admin+ |
| `/members` | `MemberListPage` | `features/members` | admin+ |
| `/settings` | `SettingsPage` | `features/settings` | owner |

Shared UI primitives (buttons, inputs, tables, dialogs) live in `src/ui/` and are
the only allowed source of styled elements.
