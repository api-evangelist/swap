---
name: Swap Global cross-border checkout
description: Run the Swap Global classify -> rates -> calculate -> complete flow to give a shopper a guaranteed landed-cost checkout.
api: Swap Global API
base_url: https://prod-global-server.api-swap-os.com
auth: x-api-key header (Global-scoped, environment-specific) + store scope carried by the key
operations:
  - checkout-controller-classify
  - shipping-public-controller-calculate-rates
  - checkout-controller-calculate
  - orders-controller-create
source: https://docs.api-swap-os.com/products/global/checkout-flow/
---

# Swap Global cross-border checkout

Use this skill to add duty- and tax-inclusive, customs-correct pricing to a custom checkout with the Swap Global API.

## Auth
Send your Global `x-api-key` on every call. The key is scoped to one store and one environment (a sandbox key will not work in production). Global has no dedicated sandbox host — test against the production host with a sandbox dashboard account/key.

## Steps
1. **Classify** — `POST /checkout/classify` (`checkout-controller-classify`). Send the cart items; receive HS codes for customs and compliance. This is the required first step.
2. **Rates (optional)** — `POST /shipping/rates` (`shipping-public-controller-calculate-rates`) to return shipping rates for the current cart.
3. **Calculate** — `POST /checkout/calculate` (`checkout-controller-calculate`). Compute taxes and duties. Keep the returned `calculationId`.
4. **Complete** — `POST /orders` (`orders-controller-create`). Notify Swap the order was placed and link the `calculationId`.

## Rules
- The item set on `POST /orders` must match the linked calculation (same id and quantity per line) or Swap returns **422 `items_mismatch_calculation`**. Re-send only after the lines align.
- Order completion is idempotent: a duplicate returns **409** and may return the existing record with `status: "Exists"` rather than replacing the linked calculation.
- Treat HTTP status as the primary signal; log the error body, do not branch on message strings. See `errors/swap-problem-types.yml` and `conventions/swap-conventions.yml`.
