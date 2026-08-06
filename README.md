# Akia

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Akia (The Akia Syndicate) is a San Francisco based hospitality technology company whose AI agent
platform automates the guest lifecycle for hotels and vacation rentals — guest messaging, an AI
voice agent, digital check-in through Mini Apps, guidebooks, upsells, tipping, tasks, team chat,
keyless entry, surveys, reputation management and marketing.

- Website — https://www.akia.com/
- Developer docs — https://api.akia.com/docs
- Marketplace / integrations — https://www.akia.com/marketplace
- Security & compliance — https://www.akia.com/security

## What Akia publishes

| Surface | Status |
|---|---|
| REST API v3 (v4 for mini apps + reservation search) | Documented at `api.akia.com/docs`, **partner-gated** (`partnerships@akia.com`) |
| OAuth 2.0 (RFC 6749) + 16 published scopes | Yes — `scopes/`, `authentication/` |
| `/.well-known/oauth-authorization-server` (RFC 8414) | Yes, incl. PKCE S256 + dynamic client registration |
| `/.well-known/oauth-protected-resource` (RFC 9728) | Yes — advertises the MCP endpoint |
| Remote MCP server (`https://sys.akia.ai/mcp`) | Yes, live; `tools/list` is OAuth-gated (401) |
| `llms.txt` | Yes — `llms/akia-llms.txt` |
| `security.txt` (RFC 9116) | Yes — `well-known/akia-security.txt` |
| Webhook subscriptions | Yes, in HTML — `asyncapi/akia-webhooks.yml` |
| Embeddable components (Web Chat, Embed SDK, Pixel, Mini Apps) | Yes — `components/` |

## Not published by Akia

These are recorded as absent, not as failures of this profile:

- **No OpenAPI/Swagger.** Every spec path on `api.akia.com` (`/openapi.json`, `/openapi.yaml`,
  `/swagger.json`, `/v1/openapi.json`, `/api-docs`, `/redoc`) returns the SPA login shell with
  HTTP 200. The reference is server-rendered HTML only. **No spec has been authored on Akia's
  behalf.**
- **No AsyncAPI**, and no webhook payload schemas or signature-verification scheme.
- **No error catalog** — the docs show only the success envelope `{status, status_code, data}`.
- **No status page** (`status.akia.com` does not resolve) and **no dated changelog**.
- **No deprecation policy** or Sunset/Deprecation header documentation.
- **No first-party SDKs** on npm, PyPI, RubyGems, Packagist, NuGet, Maven Central, crates.io or
  pkg.go.dev, and no public GitHub organization.
- **No A2A agent card** — `/.well-known/agent-card.json` and `/.well-known/agent.json` 404 on
  `www.akia.com` and `akia.ai`, and return an HTML SPA shell on the API hosts.
- **No idempotency key.** Create operations dedupe on a caller-supplied `extern_id`, which is a
  dedupe contract, not an idempotency contract.
