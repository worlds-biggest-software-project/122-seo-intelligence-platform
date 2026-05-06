# SEO Intelligence Platform

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source SEO platform that unifies keyword research, content gap analysis, rank tracking, and on-page audits — and extends them into the era of LLM-powered search.

The SEO Intelligence Platform combines technical site auditing, backlink and keyword analysis, and SERP rank tracking in a single deployable package. It is built for in-house SEO teams, agencies, and engineering-led growth groups who need data sovereignty and intelligent prioritisation rather than another expensive proprietary dashboard.

---

## Why SEO Intelligence Platform?

- **Incumbents are expensive and fragmented.** Semrush ($139.95–$499.95/mo), Ahrefs ($129–$449/mo), and enterprise platforms like BrightEdge and Conductor (tens of thousands per year) force teams to choose between price, depth, and breadth.
- **No credible open-source alternative exists.** Agencies and enterprises with data-sovereignty requirements have no self-hostable SEO suite combining rank tracking, content gap analysis, and on-page audit.
- **Audits overwhelm rather than guide.** Tools surface hundreds of issues without intelligent triage; non-technical stakeholders cannot tell what matters.
- **GEO/AEO is unaddressed.** Existing tools track Google rankings only; LLM-powered search engines (Perplexity, ChatGPT, Google AI Overviews) are reshaping discovery and no incumbent tracks citation behaviour there.
- **Consolidation is reducing buyer choice.** Adobe's pending acquisition of Semrush (announced November 2025) signals SEO being absorbed into broader experience clouds, narrowing standalone options.

---

## Key Features

### Keyword & Competitor Research

- Keyword research with search volume, keyword difficulty, and competition scoring
- Competitor domain comparison across keyword and backlink profiles
- Content gap analysis across keyword and backlink data
- Traffic value estimation via PPC cost extrapolation from rankings
- SERP feature tracking (featured snippets, knowledge panels, local pack)

### Technical & On-Page Auditing

- Site crawler detecting 50+ common technical issues (4xx/5xx errors, redirects, redirect chains, duplicates, missing meta)
- On-page audit covering title and description length, heading structure, and Schema.org / JSON-LD validation
- Security audit for mixed content and missing security headers
- JavaScript rendering with real-time crawl results
- Multi-user-agent crawling (Googlebot, Bingbot variants) with robots.txt (RFC 9309) and Sitemaps Protocol validation
- Core Web Vitals monitoring (LCP, INP, CLS)

### Backlink & Rank Tracking

- Backlink analysis covering referring domains, anchor text, and authority scoring
- Backlink index with frequent (daily minimum) updates
- SERP rank tracking across geographies and devices
- Internal linking analysis with visualisation

### Reporting & Integrations

- Automated reporting with scheduling and CSV/JSON export
- Google Search Console API integration for click-through and crawl data
- Google Ads keyword volume integration
- REST API for programmatic crawl triggering and custom reporting

---

## AI-Native Advantage

LLM-based severity ranking turns hundreds of raw audit findings into a prioritised list with plain-language business-impact explanations for non-technical stakeholders. AI-generated opportunity briefs translate keyword and content-gap data into actionable recommendations rather than leaving interpretation to analysts. The platform extends into Generative Engine Optimisation (GEO) and Answer Engine Optimisation (AEO) — tracking how content is cited inside LLM-powered search engines, a category entirely unaddressed by current tools.

---

## Tech Stack & Deployment

The platform is designed to be self-hosted or deployed as a managed cloud instance, with data sovereignty as a core requirement for enterprise and agency deployments. It integrates with Google Search Console and Google Ads APIs, validates against open standards including robots.txt (RFC 9309), the Sitemaps Protocol, and Schema.org / JSON-LD, and reports against Core Web Vitals (LCP, INP, CLS). A REST API supports programmatic crawl triggering and CI/CD-friendly automation.

---

## Market Context

The global SEO software market was estimated at $74.6 billion in 2024 and is projected to reach $154.6 billion by 2030 (CAGR ~13.5%); the broader SEO services market is forecast at $171 billion by 2030 (MarkNtel Advisors, Precedence Research, Grand View Research). Pricing spans £199/yr desktop tools (Screaming Frog) to enterprise platforms costing tens of thousands per year (BrightEdge, Conductor). Primary buyers are in-house SEO specialists and managers, content marketers, digital agencies, e-commerce growth teams, technical SEOs, and CMOs at mid-market SaaS companies.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
