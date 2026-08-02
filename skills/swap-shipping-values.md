---
name: Swap Shipping customs-correct values and labels
description: Turn a Shipment Intent into a customs-correct Compliance Pack and create or cancel carrier shipping labels, with signed orderCreated/labelUpdated webhooks.
api: Swap Shipping / Swap Values API
base_url: https://api-gateway.swap-os.com/shipping/v1/public
auth: x-api-key header + storeId in the request body
operations:
  - retrieve-invoices
  - create-a-shipping-label
  - cancel-a-shipping-label
source: https://docs.api-swap-os.com/products/shipping/
---

# Swap Shipping customs-correct values and labels

Use this skill to make sure declared values, HS codes, and commercial-invoice fields are correct **before** a carrier label is created.

## Auth
Send `x-api-key` and include `storeId` in the request body. Sandbox host is `https://sandbox-apigw.swap-os.com/shipping/v1/public`.

## Steps
1. **Build a Shipment Intent** — items, origin, destination. Prices may reflect checkout totals; Swap normalizes them into customs-compliant declared values.
2. **Retrieve values (pull)** — `retrieve-invoices` returns the enriched Compliance Pack (declared values, HS codes, CI fields) for an order. Or receive the same payload via the **orderCreated** webhook (push) — pick pull or push per order, never both.
3. **Create label** — `create-a-shipping-label` for the order using the enriched values.
4. **Cancel label** — `cancel-a-shipping-label` when needed.

## Webhooks
- **orderCreated** and **labelUpdated** deliveries are signed with **HMAC-SHA256 (Base64)** in the `x-swap-signature-sha256` header. Verify every signature before processing and discard failures. The signing secret is shown once at webhook creation.
- Delivery is at-least-once — make handlers idempotent. See `asyncapi/swap-webhooks.yml`.
