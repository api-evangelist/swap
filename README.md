# Swap

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

Swap (Swap Commerce, Inc.) is an agentic commerce platform that helps merchants sell, ship, and scale globally, powering 700+ brands across AI-led product discovery, cross-border checkout, fulfillment, and returns on a shared per-store data layer. Swap exposes six independent public API surfaces: the Agentic Storefront API (conversational discovery, chat, virtual try-on, and checkout), the Global API (cross-border classify, shipping rates, tax and duty calculation, and order reporting), the Protect API (package-protection order enrollment and claims), the Returns API (reverse logistics and quality control), the Shipping API / Swap Values API (customs-correct declared values and commercial-invoice enrichment for any carrier label stack), and the TLC API (guaranteed total landed cost and HS-code classification). Every surface authenticates with a per-API, per-environment API key plus a store identifier, and several ship JWT- or HMAC-signed webhooks.

**Areas:** Company · E-Commerce · Cross-Border · Customs · Shipping · Returns · Tax · Duties · Agentic Commerce · Checkout · Package Protection · Landed Cost

## Swap on APIs.io

Everything profiled for Swap is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/swap/](https://apis.io/providers/swap/)** — or go straight to one of the APIs or properties below.

### APIs (6)

- [Swap Agentic Storefront API](https://apis.io/apis/swap/swap-agentic-storefront-api/) — Public Gateway API for the Agentic Storefront product: conversational discovery and chat, catalog/collection browsing, cart and checkout sessions, virtual…
- [Swap Global API](https://apis.io/apis/swap/swap-global-api/) — Public API for Swap Global: the cross-border checkout flow of classify (HS codes) then optional shipping rates, calculate (taxes and duties), and order…
- [Swap Protect API](https://apis.io/apis/swap/swap-protect-api/) — Public API for the Swap Protect product: enroll protected orders and manage claim activity (create/update orders, retrieve claims, send claim messages,…
- [Swap Returns API](https://apis.io/apis/swap/swap-returns-api/) — Public API for Swap Returns reverse logistics: list external returns (V1 and V2) and update quality-control status, with per-store JWT-signed webhooks for…
- [Swap Shipping API](https://apis.io/apis/swap/swap-shipping-api/) — Public Shipping / Swap Values API: enrich a Shipment Intent into a customs-correct Compliance Pack (declared values, HS codes, commercial-invoice fields),…
- [Swap TLC API](https://apis.io/apis/swap/swap-tlc-api/) — Public Total Landed Cost API: compute guaranteed landed cost (duties, taxes, import fees) for single or bulk cross-border shipments, request HS-code…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Swap Webhooks](https://apis.io/asyncapis/swap/swap-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [swap](https://apis.io/servers/swap/swap/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Swap Authentication](https://apis.io/security/swap/swap-authentication/)
- [Swap Domain Security](https://apis.io/security/swap/swap-domain-security/)
- [Swap Trust Center](https://apis.io/security/swap/swap-trust-center/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.swap-commerce.com/)
- [Documentation](https://docs.api-swap-os.com/)
- [Getting started](https://docs.api-swap-os.com/quickstart/make-first-request/)
- [API reference](https://docs.api-swap-os.com/products/choosing-an-api/)
- [Sign up](https://www.swap-commerce.com/book-a-demo)
- [Blog](https://www.swap-commerce.com/blog)
- [Compliance](https://www.swap-commerce.com/security-compliance)
- [Trust centre](https://www.swap-commerce.com/security-compliance)
- [Terms of service](https://www.swap-commerce.com/terms-conditions)
- [Privacy policy](https://www.swap-commerce.com/privacy-policy)
- [GitHub](https://github.com/swap-commerce)

## API Evangelist rating

**Kin Score 47.5** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 39.0 |
| Contract governance | 18.2 |
| Operational transparency | 26.3 |
| Developer ergonomics | 66.1 |
| Access clarity | 50.0 |

**Agent readiness 26.8** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | — |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 26.8** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/swap/](https://apis.io/providers/swap/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Swap: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/swap/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
