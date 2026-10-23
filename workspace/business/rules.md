# Business rules

- BR-1 Every piece of data belongs to exactly one tenant; no cross-tenant reads.
- BR-2 An order may be cancelled only while it is `Draft` or `Confirmed`; after
  fulfillment a cancellation becomes a return instead.
- BR-3 Order totals are computed server-side from order lines; a client-sent total
  is never trusted.
- BR-4 Only `Owner` and `Admin` roles may invite members or change roles.
- BR-5 Every state change of an order writes an audit event with actor, timestamp
  and previous state.
- BR-6 Deleting an account anonymizes personal data but keeps the audit trail.
