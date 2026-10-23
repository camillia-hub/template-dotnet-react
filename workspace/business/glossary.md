# Business glossary

Use these terms in code, APIs and conversations. Add a row when the domain gains a
concept; never invent synonyms.

| Term | Definition |
| --- | --- |
| Tenant | A customer organization. All data is isolated per tenant. |
| Account | A user login belonging to exactly one tenant. |
| Member | An account with access to the product; carries a role. |
| Role | `Owner`, `Admin`, `Member` or `Viewer`; decides permissions (see `business/rules.md`). |
| Order | The central aggregate of the product: a customer request to be fulfilled. |
| Order line | One item of an order: product reference, quantity, agreed price. |
| Fulfillment | The delivery process of an order, tracked as a state machine. |
| Audit event | An immutable record of a business-relevant change. |
