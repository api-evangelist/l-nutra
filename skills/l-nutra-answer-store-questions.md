---
name: answer-store-questions
description: >-
  Answer a buyer's questions about ProLon products, shipping, returns and store policy using the
  read-only surfaces of L-Nutra's storefronts, without starting a transaction.
api: ProLon Life Agentic Commerce (UCP/MCP)
endpoint: https://prolonlife.com/api/mcp
operations:
  - search_shop_policies_and_faqs
  - search_catalog
  - get_product_details
  - get_product
  - lookup_catalog
generated: '2026-08-23'
method: generated
source: >-
  live tools/list of https://prolonlife.com/api/mcp and https://prolonlife.com/api/ucp/mcp,
  plus the read-only paths documented in https://prolonlife.com/llms.txt
---

# Answer questions about the ProLon store

L-Nutra runs **two** MCP endpoints per storefront and they do not carry the same tools. Pick the
right one or you will not find what you are looking for.

| Endpoint | Use it for |
|---|---|
| `https://prolonlife.com/api/mcp` (Shopify Storefront MCP) | `search_shop_policies_and_faqs` — the **only** way to query policy and FAQ text through MCP. Also `search_catalog`, `get_cart`, `update_cart`, `get_product_details`. |
| `https://prolonlife.com/api/ucp/mcp` (UCP) | `search_catalog`, `lookup_catalog`, `get_product` — richer catalog reads, plus the whole cart/checkout/order surface. |

**Divergence to know about:** on `l-nutrahealth.com` and `l-nutraprofessional.com` the
`/api/mcp` endpoint exposes `search_shop_policies_and_faqs` **and nothing else**. The catalog and
cart tools are enabled on `prolonlife.com` alone. Their `/api/ucp/mcp` endpoints carry the full
thirteen tools on all three hosts.

## Steps

1. **Policy, shipping, returns, FAQ questions.** Call `search_shop_policies_and_faqs` on
   `/api/mcp` with the buyer's question. If you need the full text rather than a snippet, GET the
   policy page directly — `/policies/refund-policy`, `/policies/shipping-policy`,
   `/policies/terms-of-service`, `/policies/privacy-policy`.
2. **Product questions.** Call `search_catalog` with the buyer's intent, then `get_product`
   (UCP) or `get_product_details` (Storefront MCP) for variants, exact pricing and real-time
   availability. `lookup_catalog` resolves several product or variant IDs in one request.
3. **Quote prices correctly.** Amounts are integers in ISO 4217 minor units paired with a currency
   code. Divide by 100 for USD and EUR before speaking a price aloud.
4. **Do not start a transaction.** `create_cart` and everything downstream of it belongs to the
   purchase skill. Reading is free and anonymous; buying needs human approval.

## Caveats

- `l-nutraprofessional.com` serves no `/policies/*` documents at all — its returns, shipping and
  terms are not published anywhere machine-readable. Do not answer a policy question about the
  professional storefront from the consumer store's policy; say the policy is not published.
- ProLon is a food product with published contraindications. The refund policy states the
  information is educational and not intended to diagnose, treat, cure or prevent any disease, and
  that the program may not be appropriate for people who are pregnant or nursing, under 18 or over
  70 without physician approval, or who have certain medical conditions or allergies. Do not give
  medical advice; point the buyer at the product's own safety information and their clinician.
- The corporate site `l-nutra.com` returned HTTP 500 on every page on 2026-08-23. Do not cite it as
  a source; use the storefronts.
