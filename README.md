# Freshteam (freshteam)

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

Freshteam is the HR and applicant tracking (ATS) product from Freshworks, covering recruiting, applicant tracking, employee information management (HRIS), onboarding, and time-off. It exposes a documented REST API on an account-specific base (`https://{domain}.freshteam.com/api`) with token authentication over Employees, Job Postings, Applicants, Interviews, Time-off, and organization structure (Departments, Branches, Teams).

> **Product status - end of life.** Freshworks has announced the discontinuation of Freshteam. New subscriptions and renewals are halted starting **March 7, 2026**, and existing customers retain access - and therefore API access - only through the end of their subscription term (reported through approximately **April 2027**). Freshworks is consolidating non-IT team use cases into Freshservice for Business Teams. The Freshteam REST API remains documented and usable for current customers during this sunset window, but is **not available to new signups**. This entry documents the API honestly as an existing but discontinuing product.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/freshteam/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/freshteam/refs/heads/main/apis.yml)

## Access Model

- **Base URL:** `https://{domain}.freshteam.com/api`, where `{domain}` is your Freshteam account subdomain.
- **Authentication:** An account API token generated in the Freshteam UI under **profile icon > API Settings > Your API Key**, sent as `Authorization: Bearer YOUR_API_TOKEN`. Freshworks documents this under an OAuth 2.0 heading, but in practice the credential is a long-lived static account key.
- **Pagination:** List endpoints default to 50 objects per page; page with `page`, `sort`, and `sort_type` query parameters and read `total-objects`, `total-pages`, and `link` response headers.
- **Rate limits:** Per-minute limits scale with plan and headcount - Free (no limit), Trial (10/min), Growth and Pro (MAX(50, employees)/min), Enterprise (MAX(100, 2x employees)/min). Responses carry `x-ratelimit-total`, `x-ratelimit-remaining`, and `x-ratelimit-used-currentrequest`.

## Tags

- Human Resources
- HRIS
- Applicant Tracking
- ATS
- Recruiting
- Employee Management
- Onboarding
- Time Off
- HR Software
- End of Life

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Freshteam Employees API

List, create, retrieve, and update employee records, manage custom employee fields, send portal invites, and read organization structure - branches, departments, sub-departments, business units, teams, levels, and roles. This is the HRIS core of Freshteam.

- **Human URL:** [https://developers.freshteam.com/api/](https://developers.freshteam.com/api/)
- **Base URL:** `https://{domain}.freshteam.com/api`

### Freshteam Time-off API

Create, list, and retrieve time-off (leave) requests, approve or cancel them, and read the configured time-off types. Lets HR systems automate leave workflows against employee balances.

- **Human URL:** [https://developers.freshteam.com/api/](https://developers.freshteam.com/api/)
- **Base URL:** `https://{domain}.freshteam.com/api`

### Freshteam Job Postings API

List and retrieve job postings and their custom fields. Powers careers sites, job boards, and recruiting integrations that syndicate open roles managed in the Freshteam applicant tracking system.

- **Human URL:** [https://developers.freshteam.com/api/](https://developers.freshteam.com/api/)
- **Base URL:** `https://{domain}.freshteam.com/api`

### Freshteam Applicants API

Create applicants (candidates) against a job posting and manage candidate sources. The ATS surface for pushing inbound applications and tracking where candidates come from into Freshteam's recruiting pipeline.

- **Human URL:** [https://developers.freshteam.com/api/](https://developers.freshteam.com/api/)
- **Base URL:** `https://{domain}.freshteam.com/api`

### Freshteam Onboarding API

Create and retrieve new-hire records to drive pre-boarding and onboarding workflows - converting an accepted candidate into an incoming employee before their start date.

- **Human URL:** [https://developers.freshteam.com/api/](https://developers.freshteam.com/api/)
- **Base URL:** `https://{domain}.freshteam.com/api`

## Artifacts

- [OpenAPI](openapi/freshteam-openapi.yml) — modeled from the public Freshteam API reference
- [Postman Collection](collections/freshteam.postman_collection.json)
- [Open Collection](collections/freshteam.opencollection.json)
- [Authentication](authentication/freshteam-authentication.yml)
- [Plans / Pricing](plans/freshteam-plans-pricing.yml)
- [Rate Limits](rate-limits/freshteam-rate-limits.yml)
- [FinOps](finops/freshteam-finops.yml)
- [Review](review.yml)

## Common Properties

- [Authentication](authentication/freshteam-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/freshworks-inc)
- [Website](https://www.freshworks.com/hrms/)
- [Documentation](https://developers.freshteam.com/api/)
- [Plans](plans/freshteam-plans-pricing.yml)
- [Rate Limits](rate-limits/freshteam-rate-limits.yml)
- [FinOps](finops/freshteam-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
