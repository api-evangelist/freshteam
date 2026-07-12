# Freshteam (freshteam)

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
