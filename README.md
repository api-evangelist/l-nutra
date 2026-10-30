# L-Nutra

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

L-Nutra, Inc. is a Los Angeles based nutri-technology company founded on the fasting-mimicking diet (FMD) research of Dr. Valter Longo at the USC Longevity Institute. It develops and sells clinically studied nutrition programs — the ProLon 5-Day Fasting Mimicking Diet, Fast Bar and related longevity nutrition products — direct to consumers, to healthcare providers, and through an employer and health-plan channel. L-Nutra is not a developer-platform company and publishes no developer portal, OpenAPI description or API reference of its own. Its machine-readable surface is the agentic-commerce layer of its three Shopify storefronts (prolonlife.com, l-nutrahealth.com and l-nutraprofessional.com): each serves an llms.txt / agents.md agent instruction document, a Universal Commerce Protocol (UCP) discovery profile at /.well-known/ucp, an anonymous MCP endpoint at /api/ucp/mcp exposing thirteen catalog, cart, checkout and order tools, a Shopify Storefront MCP endpoint at /api/mcp, and Shopify customer-account OpenID Connect discovery documents.

**Areas:** Company · Nutrition · Health · Longevity · Consumer Products · E-Commerce · Agentic Commerce · Universal Commerce Protocol · MCP · Shopify

## L-Nutra on APIs.io

Everything profiled for L-Nutra is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/l-nutra/](https://apis.io/providers/l-nutra/)** — or go straight to one of the APIs or properties below.

### APIs (3)

- [ProLon Life Agentic Commerce (UCP/MCP)](https://apis.io/apis/l-nutra/prolon-life-agentic-commerce-ucpmcp/) — The agent-facing commerce surface of L-Nutra's direct-to-consumer ProLon storefront. An anonymous MCP endpoint at https://prolonlife.com/api/ucp/mcp…
- [L-Nutra Health Agentic Commerce (UCP/MCP)](https://apis.io/apis/l-nutra/l-nutra-health-agentic-commerce-ucpmcp/) — The agent-facing commerce surface of L-Nutra Health, the employer / health-plan channel storefront. An anonymous MCP endpoint at…
- [ProLon Professional Agentic Commerce (UCP/MCP)](https://apis.io/apis/l-nutra/prolon-professional-agentic-commerce-ucpmcp/) — The agent-facing commerce surface of L-Nutra Professional, the practitioner ordering storefront. An anonymous MCP endpoint at…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [l-nutra-mcp.yml](https://apis.io/servers/l-nutra/l-nutra-mcp-yml/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [L Nutra Authentication](https://apis.io/security/l-nutra/l-nutra-authentication/)
- [L Nutra Domain Security](https://apis.io/security/l-nutra/l-nutra-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [L Nutra Scopes](https://apis.io/scopes/l-nutra/l-nutra-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [L Nutra Plans Pricing](https://apis.io/plans/l-nutra/l-nutra-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [L Nutra Rate Limits](https://apis.io/rate-limits/l-nutra/l-nutra-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://prolonlife.com/)
- [Documentation](https://prolonlife.com/agents.md)
- [Pricing](https://prolonlife.com/collections/all)
- [Sign up](https://prolonlife.com/account/login)
- [Support](https://prolonlife.com/pages/faqs)
- [Blog](https://prolonlife.com/blogs/stories)
- [Terms of service](https://prolonlife.com/policies/terms-of-service)
- [Privacy policy](https://prolonlife.com/policies/privacy-policy)

## API Evangelist rating

**Kin Score 27.5** — thin · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.7 |
| Contract quality | 0.0 |
| Contract governance | 18.2 |
| Operational transparency | 0.0 |
| Developer ergonomics | 30.4 |
| Access clarity | 44.7 |

**Agent readiness 20.5** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | platform (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | platform (partial credit) |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 32.8** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/l-nutra/](https://apis.io/providers/l-nutra/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for L-Nutra: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/l-nutra/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
