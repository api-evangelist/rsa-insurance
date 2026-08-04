# RSA Insurance (rsa-insurance)

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

RSA Insurance is a British property and casualty insurer whose lineage runs back to the Sun Fire Office of 1710, making it one of the oldest general insurance brands in the United Kingdom. It writes commercial lines through intermediaries — property, liability, motor fleet, marine, construction, engineering and renewable energy, cyber, professional and financial lines, rail, and accident and health — alongside a residual personal lines book. RSA Insurance Group was acquired by Intact Financial Corporation in 2021, and on 6 October 2025 RSA and NIG formally rebranded to Intact Insurance across the UK, Ireland and Europe.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/rsa-insurance/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/rsa-insurance/refs/heads/main/apis.yml)

## Tags

- Insurance
- United Kingdom
- Property and Casualty
- Commercial Lines
- Carrier
- Broker
- Claims
- Underwriting
- Partner Gated

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

**None.** RSA Insurance publishes no public, self-serve API and operates no developer portal.

Every developer-portal candidate was probed on 2026-07-25 and none exists. `/developers`, `/developer`, `/api`, `/partners`, `/integrations` and `/brokers` all return HTTP 404 on `www.rsainsurance.co.uk`; `developer.`, `developers.`, `docs.` and `api.` resolve to a wildcard DNS address but no TLS service answers. The successor site `intactinsurance.co.uk` is no different — the same paths 404 and the same subdomains do not serve. No OpenAPI, Swagger, AsyncAPI, GraphQL schema, `.proto` or public Postman collection was found on any RSA host, so this repository has no `openapi/` directory.

### What RSA actually operates

The company's real integration surface is enumerated on its [Tools and resources](https://www.rsainsurance.co.uk/brokers-and-partners/tools-resources/) page, and every item on it is a human login:

| Tool | What it does | Access |
| --- | --- | --- |
| [RSA Connect](https://www.rsaconnect.rsagroup.co.uk/portal/UKHome.aspx) | "Connect Intermediary Website" — Claims Online, Documents Online, MID Updates | User ID + password, provisioned by email with an agency number |
| [RSA Online](https://www.rsaonline.rsagroup.com/AWE/Container.aspx?CurrentWorkflow=Logon&CurrentStep=Login) | Online trading platform for intermediated personal home and commercial products | User ID + password, brokers only |
| RSA Claims Online | Claim reference numbers, documents, current status | User ID + password, brokers only |
| Commercial Property eFNOL | Electronic first notification of loss | Public HTML web form, not an API |
| [MID2 Database](https://www.services1.rsagroup.co.uk/webappserver/midphase2public/) | Upload or change vehicle details on the Motor Insurance Database | User ID + password |
| Business and Property Protection Portal | Risk lookup, hosted by RISCAuthority | HTTP 403 to anonymous probes |
| RSAred | Risk management data portal | Host is now NXDOMAIN — a dead link on a live page |

### How machines actually reach RSA

Through the UK's intermediated plumbing, not a carrier API. Broker software houses — Acturis, Applied, Open GI, SSP and Bravo Digital Trader — and the [Polaris imarket](https://www.polaris.co.uk/products/imarket/) commercial e-trading hub, which lists Intact among its participating insurers and integrates carriers against Polaris Standards. None of that is documented publicly by RSA, and Polaris publishes no OpenAPI either.

### ACORD posture

**No ACORD reference found.** No mention of ACORD, AL3, ACORD XML, NGDS or IVANS appears anywhere on `rsainsurance.co.uk` or `intactinsurance.co.uk`. In the UK, Polaris Standards occupy the seam that ACORD occupies in North America.

### London market

No evidence was found that RSA operates a Lloyd's syndicate or participates in PPL, Whitespace, DDM/DCOM or the Blueprint Two programme. RSA is a company-market carrier writing on its own paper. Recorded as *not found* rather than *absent* — the London market's platforms are themselves broker-gated and would not be visible from an anonymous probe.

## Artifacts

The 2026-07-25 enrichment round re-probed every host and produced the record below. Most of it is a record of *absence* — which for a partner-gated carrier is the finding, not a gap.

| Artifact | What it holds |
| --- | --- |
| [authentication/rsa-insurance-authentication.yml](authentication/rsa-insurance-authentication.yml) | The published access model: four human web-portal logins, provisioned by emailing an agency number. No API keys, no OAuth, no OIDC, no mTLS, no SAML metadata. |
| [conformance/rsa-insurance-conformance.yml](conformance/rsa-insurance-conformance.yml) | Standards posture — ACORD absent, Polaris Standards *unknown* (participation implied, never stated), MID2 and ELTO genuinely conformed — plus the PRA/FCA authorisation, Solvency II SFCR, Modern Slavery and UK GDPR disclosures. No SOC 2 / ISO 27001 / PCI DSS. |
| [lifecycle/rsa-insurance-lifecycle.yml](lifecycle/rsa-insurance-lifecycle.yml) | No API versioning, deprecation policy, SLA or status page. Records the 6 October 2025 RSA-to-Intact rebrand and the host-by-host migration of the estate. |
| [security/rsa-insurance-domain-security.yml](security/rsa-insurance-domain-security.yml) | Probed TLS/HSTS/DNSSEC/CAA/SPF/DMARC. All three live hosts are HTTPS with HSTS; no DNSSEC and no CAA on either domain; `rsainsurance.co.uk` DMARC is `p=none` while `intactinsurance.co.uk` is `p=reject`. |
| [well-known/rsa-insurance-well-known.yml](well-known/rsa-insurance-well-known.yml) | Every `/.well-known/` probe on every host. Nothing is served. Deliberately *not* wired as a `WellKnown` pointer — it is a negative record. |
| [llms/rsa-insurance-llms.txt](llms/rsa-insurance-llms.txt) | Agent-facing summary telling a machine, in plain terms, that there is no API here and where the real integration seam is. |

No `openapi/`, `asyncapi/`, `mcp/`, `skills/`, `packages/`, `scopes/`, `errors/`, `sandbox/`, `cli/`, `changelog/` or `components/` directory exists, because there is nothing real to put in one. No first-party package exists on npm, PyPI or any other registry, and `github.com/rsagroup` is an unrelated neuroscience toolbox.

### Host change found this round

`www.rsaconnect.rsagroup.co.uk` now **302s to `www.connect.intactinsurance.co.uk`** — the RSA Connect intermediary portal has moved to the Intact hostname while the link on RSA's own public tools page still points at the old one. Both hosts answer HTTP 200 to *every* path, including `/openapi.json`, `/swagger.json` and `/.well-known/openid-configuration`; every one of those responses is an ASP.NET rewrite to `/ErrorPage.aspx` with the body `Security Error!.. Invalid URL or Invalid data`. They are not documents, and any future round should not mistake those 200s for a spec.

## Review

The full reviewer finding, including every probe URL with its HTTP status, is in [review.yml](review.yml).

## Links

- [RSA Insurance (legacy site)](https://www.rsainsurance.co.uk/)
- [Intact Insurance UK (successor site)](https://www.intactinsurance.co.uk/)
- [RSA and NIG are now Intact Insurance — FAQ](https://www.intactinsurance.co.uk/faqs/rsa-and-nig-are-now-intact-insurance)
- [Broker support](https://www.rsainsurance.co.uk/contact/broker-support/)
- [LinkedIn](https://www.linkedin.com/company/rsa)
- [X](https://x.com/rsagroup)
- [YouTube](https://www.youtube.com/rsainsurance)
