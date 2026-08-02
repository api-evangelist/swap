---
name: Swap TLC guaranteed landed cost
description: Classify goods and compute a guaranteed total landed cost (duties, taxes, import fees) for a cross-border shipment, then report shipped or void.
api: Swap TLC API
base_url: https://prod-tlc.api-swap-os.com/tax-duty/v1
auth: x-api-key header (TLC-scoped, environment-specific)
operations:
  - tlc-controller-request-classification
  - tlc-controller-create-transaction
  - tlc-controller-create-bulk-transaction
  - tlc-controller-report-shipped
  - tlc-controller-void-transaction
source: https://docs.api-swap-os.com/products/tlc/
---

# Swap TLC guaranteed landed cost

Use this skill to get a referenceable, guaranteed landed-cost result for a cross-border shipment with the standalone TLC API.

## Auth
Send `x-api-key: <your-tlc-api-key>` on every call. Sandbox host is `https://sandbox-tlc.api-swap-os.com/tax-duty/v1`; a sandbox key will not work in production.

## Steps
1. **Classify (optional)** — `tlc-controller-request-classification`: send a description (plus optional image URL, category, summary) and get an HS code with a human-readable description.
2. **Compute** — `tlc-controller-create-transaction` for one shipment (or `tlc-controller-create-bulk-transaction` for many). Provide origin/destination addresses, currency, and shipment details; receive duties, taxes, and import fees as distinct components.
3. **Report shipped** — `tlc-controller-report-shipped` (`POST /shipped`): record one or more shipments made against the transaction.
4. **Void** — `tlc-controller-void-transaction` (`PATCH /void`): record that a transaction was voided.

## Rules
- **No idempotency-key header on TLC.** `POST /shipped` and `PATCH /void` are not guaranteed to deduplicate repeated calls for the same calculation — guard against double submission yourself.
- Choose Global **or** TLC on a given merchant flow, not both.
- See `conventions/swap-conventions.yml` and `changelog/swap-changelog.yml`.
