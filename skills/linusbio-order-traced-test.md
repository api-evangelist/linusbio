---
name: order-traced-exposure-test
description: >-
  Buy LinusBio's Traced environmental exposure test on behalf of a user through the
  traced.life Universal Commerce Protocol MCP endpoint, stopping at the buyer-approval gate
  that the store requires before payment.
generated: '2026-08-25'
method: generated
source: >-
  Grounded in the 13 tools returned by an anonymous tools/list against
  https://traced.life/api/ucp/mcp on 2026-08-25 (saved verbatim to
  mcp/linusbio-traced-mcp-tools-list.json) and the flow published by the provider at
  https://traced.life/agents.md. No tool name, parameter or rule in this skill is invented.
api: linusbio-traced-ucp-commerce
endpoint: https://traced.life/api/ucp/mcp
operations:
  - search_catalog
  - lookup_catalog
  - get_product
  - create_cart
  - update_cart
  - get_cart
  - cancel_cart
  - create_checkout
  - update_checkout
  - get_checkout
  - complete_checkout
  - cancel_checkout
  - get_order
---

# Order the Traced environmental exposure test

LinusBio sells the Traced™ at-home environmental exposure test ($299 USD, 15 elements across a
30-day timeline) from a Shopify storefront at `https://traced.life`. The store implements the
Universal Commerce Protocol (UCP) `2026-04-08` over MCP, so an agent can complete every step of
a purchase except the payment itself.

**Endpoint:** `POST https://traced.life/api/ucp/mcp`
**Content-Type:** `application/json` · **Accept:** `application/json, text/event-stream`
**Auth:** none. `tools/list` and catalog reads answer anonymously.

## Before you start

Confirm the store's capabilities are still what this skill assumes:

```
GET https://traced.life/.well-known/ucp
```

Read `ucp.version` and the `services["dev.ucp.shopping"]` entry. If the version has moved past
`2026-04-08`, re-run `tools/list` and re-read the input schemas rather than trusting the
parameter names below.

## Required on every call

Every tool's `inputSchema` requires a `meta` object carrying your UCP agent profile:

```json
{ "meta": { "ucp-agent": { "profile": "https://your-agent.example/ucp-profile" } } }
```

Calls without it will not validate.

## Steps

1. **Find the product.** Call `search_catalog` with the buyer's intent (e.g. "environmental
   exposure test"), or `lookup_catalog` if you already hold a product or variant identifier.
   Use `get_product` to pull the full detail for a single identifier before quoting anything.
2. **Read the price correctly.** Every amount comes back in ISO 4217 **minor units** paired
   with a currency code — `{"amount": 29900, "currency": "USD"}` is **$299.00**. Divide by 100
   for two-decimal currencies before you show a number to the buyer. Quoting the raw integer
   is the single most likely way to get this wrong.
3. **Build a cart.** `create_cart` with the chosen variant, then `update_cart` for quantity or
   line changes and `get_cart` to read back state. If the buyer changes their mind at this
   stage, `cancel_cart` — nothing has been charged.
4. **Open a checkout.** `create_checkout` from the cart. `get_checkout` returns line items,
   totals, discounts and taxes.
5. **Fulfilment details.** `update_checkout` to set the shipping address and shipping method.
   The store's UCP profile declares `allows_multi_destination.shipping: false` — one
   destination per order, and only the `shipping` method combination is allowed.
6. **Stop and ask.** The store's published rules are explicit: *"Checkout requires human
   approval. Agents must not complete payment without explicit buyer consent."* Present the
   final total and get contemporaneous approval from the human. Do not automate past this
   point. If you cannot get approval at the moment of payment, route the purchase through the
   Shop skill (`https://shop.app/SKILL.md`) instead, as the provider recommends.
7. **Complete.** `complete_checkout` after approval. Pass an `meta.idempotency-key` string —
   it is the only idempotency control on this surface, and it is what stops a retried or
   duplicated completion from charging the buyer twice. The response carries the order ID and
   the Thank You Page URL, or errors encountered inline.
8. **Confirm.** `get_order` with the returned order ID to read back the completed order.

## Reversing a mistake

| What happened | How to undo it | Window |
|---|---|---|
| Cart built, nothing charged | `cancel_cart` | Any time before checkout completes |
| Checkout open, payment not taken | `cancel_checkout` | Any time before `complete_checkout` succeeds |
| Order placed, payment authorized | **No agent tool exists.** The buyer must contact Traced support for a refund | **48 hours** from payment authorization, per `https://traced.life/policies/refund-policy` |

Tell the buyer about the 48-hour window *before* they approve payment. Once
`complete_checkout` returns an order ID you cannot take it back yourself.

## Rate limits and failures

The MCP endpoint is rate-limited per IP. Back off on `429`. No numeric limit, window or
`RateLimit-*` header is published, so treat the ceiling as unknown and retry conservatively.
Errors arrive as JSON-RPC 2.0 error objects; there is no RFC 9457 problem catalog and no
published error-code reference.

## What this surface is not

This is a commerce endpoint only. It sells a test kit. It exposes **no** exposomics data, no
laboratory results, no specimen tracking and no patient records. Test results are delivered
through a telehealth provider and the LinusBio patient portal, neither of which has any public
API. Do not tell a user you can retrieve their results through this endpoint.
