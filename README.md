# LinusBio

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

LinusBio (Linus Biotechnology Inc.) is a New York-based precision-medicine company spun out of the Mount Sinai Institute for Exposomic Research that commercializes "temporal exposomics sequencing" — a robotics, laser-ablation and mass-spectrometry platform that reads a single strand of hair like growth rings to reconstruct hundreds of time-resolved measurements of a person's chemical and biological exposures, then runs them through an AI pipeline to produce biomarkers. Its clinical product ClearStrand-ASD (formerly StrandDx-ASD) is an FDA Breakthrough Device-designated laboratory developed test run in a CLIA-certified lab to help rule out autism spectrum disorder in children from one month to ten years of age, and its consumer product Traced is a $299 at-home environmental exposure test measuring 15 elements across a 30-day timeline. LinusBio publishes no developer program, no OpenAPI and no public REST API; its only machine-callable surface is the Shopify-hosted Universal Commerce Protocol (UCP) MCP endpoint on the traced.life storefront, through which an agent can search the catalog, build a cart and open a checkout for the Traced test under a buyer-approval rule.

**Areas:** Company · Health · Diagnostics · Precision Medicine · Biotechnology · Exposomics · Life Sciences · Autism · Commerce · Agents

## LinusBio on APIs.io

Everything profiled for LinusBio is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/linusbio/](https://apis.io/providers/linusbio/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [Traced UCP Commerce (MCP)](https://apis.io/apis/linusbio/linusbio-traced-ucp-commerce/) — The agent-callable commerce surface for LinusBio's Traced environmental exposure test, served from the traced.life storefront. It implements the Universal…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Traced UCP Commerce MCP Server](https://apis.io/servers/linusbio/traced-ucp-commerce-mcp-server/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Linusbio Authentication](https://apis.io/security/linusbio/linusbio-authentication/)
- [Linusbio Domain Security](https://apis.io/security/linusbio/linusbio-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Linusbio Scopes](https://apis.io/scopes/linusbio/linusbio-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Linusbio Plans Pricing](https://apis.io/plans/linusbio/linusbio-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Linusbio Rate Limits](https://apis.io/rate-limits/linusbio/linusbio-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.linusbio.com/)
- [Documentation](https://traced.life/agents.md)
- [Getting started](https://traced.life/agents.md)
- [Pricing](https://traced.life/products/test)
- [Support](https://www.clearstrandasd.com/support/contact-us)
- [Blog](https://www.linusbio.com/news)
- [Terms of service](https://traced.life/policies/terms-of-service)
- [Privacy policy](https://traced.life/policies/privacy-policy)

## API Evangelist rating

**Kin Score 32.5** — thin · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 0.0 |
| Contract governance | 18.2 |
| Operational transparency | 21.1 |
| Developer ergonomics | 42.3 |
| Access clarity | 39.5 |

**Agent readiness 24.1** — agent-aware

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
| Protected Resource Metadata | verified |
| Dynamic Client Registration | — |
| Agentic Commerce | platform (partial credit) |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 36.7** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/linusbio/](https://apis.io/providers/linusbio/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for LinusBio: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/linusbio/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
