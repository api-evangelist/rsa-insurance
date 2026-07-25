# RSA Insurance (rsa-insurance)

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
