---
name: Swap Returns and quality control
description: List external returns, update quality-control status, and consume JWT-signed return lifecycle webhooks.
api: Swap Returns API
base_url: https://api-gateway.swap-os.com/returns-api
auth: X-API-Key header + swap_store_id (V2, query) / store (V1, query) / store_id (Quality Control, body)
operations:
  - get-external-returns-v-2
  - get-external-returns-v-1
  - update-quality-control
source: https://docs.api-swap-os.com/products/returns/
---

# Swap Returns and quality control

Use this skill to read returns and drive warehouse quality-control outcomes with the Swap Returns API.

## Auth
Send `X-API-Key` (Returns-scoped) plus the store identifier for the version you call: `swap_store_id` (V2), `store` (V1), or `store_id` in the body for Quality Control.

## Steps
1. **List returns** — `get-external-returns-v-2` (preferred) or `get-external-returns-v-1`. V2 returns `delivery_status` / `return_status`, `return_shipments`, `exchange_products`, `result_type`, and store-credit totals.
2. **Update quality control** — `update-quality-control` to record inspection results against a return.

## Webhooks
- **returnCreated** and **returnProcessed** are pushed per-store. Each delivery carries a **JWT (HS256)** in the top-level `jwt` body field (not an HTTP header), signed with your `whsk_<hex>` secret, expiring 300s after issue with a unique `nonce`. Verify the signature before trusting the body.
- Delivery is at-least-once and retries up to 3 times — dedupe on `nonce` / `return_id`. Prefer V2 payloads for new integrations. See `asyncapi/swap-webhooks.yml`.
