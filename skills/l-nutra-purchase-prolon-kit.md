---
name: purchase-prolon-kit
description: >-
  Buy a ProLon or L-Nutra product on a buyer's behalf over the store's Universal Commerce Protocol
  MCP endpoint, stopping for explicit human approval before payment is completed.
api: ProLon Life Agentic Commerce (UCP/MCP)
endpoint: https://prolonlife.com/api/ucp/mcp
operations:
  - search_catalog
  - get_product
  - create_cart
  - update_cart
  - create_checkout
  - update_checkout
  - complete_checkout
  - cancel_checkout
  - get_order
generated: '2026-08-23'
method: generated
source: live tools/list of https://prolonlife.com/api/ucp/mcp and https://prolonlife.com/llms.txt
---

# Purchase a ProLon kit

Every tool named here was returned by a live `tools/list` on `https://prolonlife.com/api/ucp/mcp`.
The same tools exist on `https://l-nutrahealth.com/api/ucp/mcp` and
`https://l-nutraprofessional.com/api/ucp/mcp`; swap the host to buy from a different storefront.

## Before you start

- The endpoint is anonymous over HTTPS. There is no key to obtain and no account to create.
- Every call must carry `meta["ucp-agent"].profile` — a URI that describes you, the calling agent.
  It is required by the schema, but it is a self-description, not a credential.
- Prices come back as `{"amount": <integer>, "currency": "<ISO 4217>"}` in **minor units**.
  `{"amount": 2500, "currency": "USD"}` is $25.00. Convert before you quote a number to the buyer.
- Pass `context.address_country` (ISO 3166-1 alpha-2) and `context.currency` so pricing and
  availability are correct for the buyer.

## Steps

1. **Find the product.** Call `search_catalog` with the buyer's intent in `catalog.query` and their
   `catalog.context`. Use `get_product` to confirm exact pricing, variants and real-time
   availability before you quote anything.
2. **Build the cart.** Call `create_cart` with `cart.line_items[]`, where each item is
   `{ "item": { "id": "<product variant gid>" }, "quantity": <n> }`. Add `cart.buyer.email` and
   `cart.buyer.phone_number` when the buyer has given them to you. Keep the returned cart `id`.
3. **Adjust if needed.** `update_cart` changes quantities or line items. `get_cart` re-reads state.
   `cancel_cart` throws the cart away — it is free and reversible at this stage.
4. **Open a checkout.** Call `create_checkout`. Keep the returned checkout `id`.
5. **Fulfilment and payment details.** Call `update_checkout` to set the shipping address, the
   shipping method and `checkout.payment.instruments[]`. Each instrument needs `id`, `handler_id`
   and `type` (`"card"` for credit/debit, `"token"` for a wallet). The store declares a Google Pay
   handler with `handler_id` `gpay` in `/.well-known/ucp`. Re-read totals with `get_checkout` and
   show the buyer the full amount including tax and shipping.
6. **STOP. Get human approval.** The store's `robots.txt` and `llms.txt` both say agents must not
   complete checkout, payment or order placement without an explicit, contemporaneous human
   approval step. Do not proceed on a standing instruction given earlier in the session.
7. **Complete.** Call `complete_checkout` with the checkout `id` and a
   `meta["idempotency-key"]` you generate. **The key is required by the schema.** Reuse the same
   key if you have to retry — it is the only protection against double-charging on this surface.
   The response carries the order ID and the Thank You Page URL.
8. **Confirm.** Call `get_order` with the returned order id
   (`gid://shopify/Order/<n>`) and report it back to the buyer.

## Reversibility — read this before step 7

Cancellation is cheap up to the moment `complete_checkout` succeeds and expensive after it.

- Before completion: `cancel_cart` and `cancel_checkout` fully reverse the transaction.
- After completion: **there is no MCP tool that reverses an order.** Published policy is that all
  sales are final and returns are not accepted, open or unopened. An order can only be cancelled
  before it enters the fulfilment process, by contacting customer service at
  `customerservice@l-nutra.com` or 888-926-5370 (Mon-Fri, 09:00-17:00 Central). Expedited orders
  begin processing immediately and cannot be cancelled at all.
- Subscriptions must be cancelled at least 24 hours before the scheduled renewal date.
- Damaged or missing items must be reported within 14 days of delivery.

Tell the buyer that sales are final **before** they approve payment, not after.
Source: <https://prolonlife.com/policies/refund-policy>

## Errors and limits

- Errors come back as JSON-RPC 2.0 error objects, plus in-band errors on `complete_checkout`.
  There is no published error-code registry, so surface the message verbatim.
- The endpoint is rate-limited per IP with no published number and no `RateLimit-*` headers.
  Back off on HTTP 429.
