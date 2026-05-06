# Standards & API Reference

> Project: SEO Intelligence Platform · Generated: 2026-05-06

## Industry Standards & Specifications

### IETF Standards

**RFC 9309 — Robots Exclusion Protocol**
- URL: https://datatracker.ietf.org/doc/html/rfc9309
- Formalised in September 2022, RFC 9309 is the official IETF standard for robots.txt — the protocol governing which pages web crawlers are permitted to access. It defines syntax, caching behaviour (5–24 hour TTL), error handling, and wildcard pattern matching rules. Every SEO crawler component must implement RFC 9309 to responsibly honour crawl directives. An extension working draft (REPext, late 2024) builds on RFC 9309 by exploring page-level crawl controls via HTTP response headers and HTML meta tags.

**RFC 6749 — OAuth 2.0 Authorization Framework**
- URL: https://www.rfc-editor.org/rfc/rfc6749
- The foundational OAuth 2.0 specification defining four grant types (authorization code, implicit, resource owner password credentials, client credentials) and the four roles (resource owner, client, authorization server, resource server). All Google API integrations — including Google Search Console and Google Ads APIs — require OAuth 2.0 with the Authorization Code flow. Modern implementations should also incorporate RFC 7636 (PKCE) to prevent code interception attacks.

**RFC 7636 — Proof Key for Code Exchange (PKCE)**
- URL: https://datatracker.ietf.org/doc/html/rfc7636
- An extension to the OAuth 2.0 Authorization Code flow that prevents authorization code interception attacks, now mandated for all public client types. Required when implementing user-delegated OAuth flows for Google Search Console and Google Ads API integration.

**RFC 8288 — Web Linking**
- URL: https://datatracker.ietf.org/doc/html/rfc8288
- Defines the link relation types used in HTTP `Link` headers and HTML `<link>` elements. Relevant for canonical URL handling, pagination link elements (`rel=canonical`, `rel=prev`, `rel=next`), and hreflang link attributes — all of which are audited by technical SEO crawlers.

### W3C Standards

**Web Content Accessibility Guidelines (WCAG) 2.2**
- URL: https://www.w3.org/TR/WCAG22/
- Published October 2023 (updated December 2024); also ratified as ISO/IEC 40500:2025. WCAG 2.2 adds 9 success criteria over WCAG 2.1, focusing on cognitive disabilities, visual impairments, and mobile usability. SEO audit platforms increasingly flag WCAG compliance issues because Google's ranking signals reward semantic HTML, meaningful alt text, and logical navigation — all shared requirements between accessibility and SEO. Sites achieving WCAG compliance report up to 12% uplift in organic traffic.

**W3C Web Performance Working Group — Core Web Vitals**
- URL: https://web.dev/articles/vitals
- Google's Core Web Vitals (standardised through the W3C Web Performance Working Group) comprise three user-centric performance metrics now used as ranking signals: Largest Contentful Paint (LCP, target ≤ 2.5 s), Interaction to Next Paint (INP, target ≤ 200 ms, replaced FID in March 2024), and Cumulative Layout Shift (CLS, target < 0.1). Every on-page audit and technical SEO tool must measure and report these metrics.

### Data Model & API Specifications

**Sitemaps Protocol**
- URL: https://www.sitemaps.org/protocol.html
- The de facto XML sitemap standard (sitemaps.org), supported by Google, Bing, and all major search engines. Defines the XML schema for `<urlset>`, `<url>`, `<loc>`, `<lastmod>`, `<changefreq>`, and `<priority>` elements. Technical SEO auditors validate sitemap structure, coverage, and consistency with crawled URLs. RFC 9309 deliberately leaves sitemaps as an extension to the robots exclusion protocol.

**Schema.org / JSON-LD**
- URL: https://schema.org/
- A collaborative vocabulary (backed by Google, Bing, Yahoo, and Yandex) with 800+ entity types, used to annotate web pages with machine-readable structured data. As of 2024, over 45 million web domains mark up pages using Schema.org vocabulary. JSON-LD (JavaScript Object Notation for Linked Data) is the W3C-recommended encoding format and the only format Google recommends for new implementations. In 2026, JSON-LD schema markup bridges traditional SEO and generative engine optimisation (GEO), enabling visibility in Google AI Overviews, ChatGPT, and Perplexity. Key types for SEO audit tools: Article, Product, FAQPage, HowTo, BreadcrumbList, LocalBusiness, Organization.

**OpenAPI Specification 3.1**
- URL: https://spec.openapis.org/oas/v3.1.0
- The industry-standard machine-readable REST API description format (formerly Swagger). Ahrefs API v3 exposes an OpenAPI-compatible specification for all 105 endpoints across Site Explorer, Keywords Explorer, Rank Tracker, and Site Audit. An SEO intelligence platform should expose its own API surface via an OpenAPI 3.1 spec to enable integrations, client SDK generation, and developer tooling.

**hreflang Attribute Specification**
- URL: https://developers.google.com/search/docs/specialty/international/localized-versions
- The Google and Bing specification for the `hreflang` attribute, used to signal language and regional targeting for international sites. Incorrect hreflang implementation is one of the most common and high-impact technical SEO issues; audit tooling must validate hreflang tag syntax, reciprocal linking, and language/region code correctness.

### Security & Authentication Standards

**OAuth 2.0 (RFC 6749) with PKCE (RFC 7636)**
- Already covered above; mandatory for all delegated API access to Google services.

**API Key Authentication**
- Semrush and DataForSEO use API key authentication (key passed as a query parameter or HTTP header). An SEO intelligence platform integrating third-party data sources must securely manage and rotate API keys, preferably using a secrets manager.

**OWASP API Security Top 10**
- URL: https://owasp.org/www-project-api-security/
- The OWASP API Security Top 10 (updated 2023) identifies the most critical API security risks including broken object-level authorization, excessive data exposure, and injection. Relevant to any SEO platform that exposes a developer API over user-controlled data (keyword lists, site crawl results, competitor profiles).

### MCP Server Specifications

The Model Context Protocol (MCP) is an emerging open standard for exposing tools and data sources to LLM agents. An AI-native SEO intelligence platform could expose SEO data via an MCP server to allow AI agents (e.g., Claude, GPT-4) to query keyword data, run technical audits, and retrieve competitor intelligence programmatically. Ahrefs has published an open-source MCP server skill repository (github.com/ahrefs/ahrefs-api-skills). Moz has a community MCP wrapper (github.com/metehan777/moz-mcp). This is an early-stage but strategically important integration surface.

---

## Similar Products — Developer Documentation & APIs

### Google Search Console API

- **Description:** The primary authoritative source for search performance data — impressions, clicks, CTR, and average position for queries and pages. The only API that provides first-party index coverage and crawl data directly from Google.
- **API Documentation:** https://developers.google.com/webmaster-tools/v1/
- **SDKs/Libraries:** Google API Client Libraries (Python, Java, Node.js, Go, PHP, Ruby) via https://developers.google.com/discovery/libraries; community Python wrapper: https://github.com/joshcarty/google-searchconsole
- **Developer Guide:** https://developers.google.com/webmaster-tools/v1/how-tos/authorizing
- **Standards:** REST/JSON; OpenSearch 1.1 data model; Google Discovery Document format
- **Authentication:** OAuth 2.0 (Authorization Code + PKCE); requires Google API Console project and OAuth 2.0 credentials

### Google Ads API (Keyword Planner)

- **Description:** Exposes the KeywordPlanIdeaService for generating keyword ideas and retrieving historical search volume, competition, and CPC metrics at scale — the same data that powers Google's Keyword Planner UI. Requires a Google Ads manager account and developer token.
- **API Documentation:** https://developers.google.com/google-ads/api/docs/keyword-planning/overview
- **SDKs/Libraries:** Google Ads API client libraries for Python, Java, Ruby, PHP, .NET, Perl — https://developers.google.com/google-ads/api/docs/client-libs
- **Developer Guide:** https://developers.google.com/google-ads/api/docs/keyword-planning/generate-keyword-ideas
- **Standards:** REST/JSON and gRPC (protobuf); OpenAPI-compatible discovery
- **Authentication:** OAuth 2.0; developer token + manager account required

### Semrush API

- **Description:** Commercial REST API exposing Semrush's 25+ billion keyword database, domain analytics, backlink data, site audit, and competitor intelligence. API v4 introduces OAuth 2.0 and a unified response format across all products.
- **API Documentation:** https://developer.semrush.com/api/
- **SDKs/Libraries:** No official SDKs; community wrappers available; full endpoint reference at https://developer.semrush.com/api/introduction/semrush-api-overview/
- **Developer Guide:** https://developer.semrush.com/api/get-started/api-access/
- **Standards:** REST/JSON; HTTP GET requests; API v4 uses OAuth 2.0; earlier versions use API key as query parameter
- **Authentication:** API key (v3 and earlier); OAuth 2.0 (v4)
- **Notes:** API units (credits) consumed per request; Semrush acquisition by Adobe announced November 2025 — API continuity uncertain post-acquisition.

### Ahrefs API v3

- **Description:** RESTful API providing programmatic access to Ahrefs' 35 trillion backlink index, keyword research, rank tracker, site audit, and brand radar. OpenAPI-compatible specification available. API v2 discontinued November 1, 2025.
- **API Documentation:** https://docs.ahrefs.com/docs/api/reference/introduction
- **SDKs/Libraries:** Ahrefs API Skills (MCP-compatible): https://github.com/ahrefs/ahrefs-api-skills; community SDK links at https://docs.ahrefs.com/
- **Developer Guide:** https://docs.ahrefs.com/ahrefs-connect/docs/api-guide
- **Standards:** REST/JSON; OpenAPI-compatible spec for all 105 methods; rate limit 60 requests/minute (HTTP 429 on excess)
- **Authentication:** API token (Bearer header)
- **Notes:** Ahrefs Connect programme required for API access; bootstrapped and independently held; no pending acquisitions.

### Moz Links API

- **Description:** JSON-RPC 2.0 API providing access to Moz's backlink database and Domain Authority / Page Authority metrics. Method names follow a structured namespace pattern (e.g., `link.fetch`, `keyword.generate`).
- **API Documentation:** https://moz.com/api (official); reference guide: https://developer-support.majestic.com/ (Majestic) — Moz docs at https://mza.bundledseo.com/api/docs/guides/getting-started
- **SDKs/Libraries:** Community JavaScript wrapper: https://github.com/avamia/moz-api
- **Developer Guide:** https://moz.com/api/
- **Standards:** JSON-RPC 2.0 via HTTP POST to universal endpoint https://api.moz.com/jsonrpc
- **Authentication:** API key + secret (HMAC-signed requests)

### Majestic API

- **Description:** REST API providing access to the world's largest commercial backlink database, with a Fresh Index (updated multiple times daily) and Historic Index (5+ years). Exposes link discovery dates, anchor text, crawl history, redirect status, and Trust Flow / Citation Flow metrics.
- **API Documentation:** https://developer-support.majestic.com/api/
- **SDKs/Libraries:** PHP library: https://github.com/nticaric/majestic-seo-api; official connector library at https://majestic.com/support/tools/for-developers
- **Developer Guide:** https://developer-support.majestic.com/
- **Standards:** REST; resource unit system (Analysis Units, Retrieval Units, Index Item Units) for quota management
- **Authentication:** API key

### DataForSEO API v3

- **Description:** Wholesale SEO data API providing SERP results, keyword data, backlink data, on-page audit, and rank tracking across Google, Bing, Yahoo, Baidu, YouTube, and more. Significantly cheaper than Semrush/Ahrefs at $0.0006/query. Live and Standard (asynchronous task) delivery methods available.
- **API Documentation:** https://docs.dataforseo.com/v3/
- **SDKs/Libraries:** Multiple community SDKs; official documentation at https://dataforseo.com/apis
- **Developer Guide:** https://dataforseo.com/apis/serp-api
- **Standards:** REST/JSON; supports webhooks/callbacks for asynchronous tasks; batch requests supported
- **Authentication:** HTTP Basic Authentication (login + password)
- **Notes:** Used as a data backend by multiple SEO SaaS platforms. Supports Google AI Overviews / AI Mode search insights (2025+).

### Google PageSpeed Insights API

- **Description:** Measures Core Web Vitals (LCP, INP, CLS) and overall performance scores for any URL using both lab data (Lighthouse) and real-user field data (Chrome UX Report / CrUX, aggregated over 28 days). Integrated into Screaming Frog v23.0 and most enterprise SEO platforms.
- **API Documentation:** https://developers.google.com/speed/docs/insights/v5/about
- **SDKs/Libraries:** Uses Google API Client Libraries; also callable directly via REST GET
- **Developer Guide:** https://developers.google.com/speed/docs/insights/v5/get-started
- **Standards:** REST/JSON; returns scores per Lighthouse 12 audit categories
- **Authentication:** API key (no OAuth required for public URLs)

### Screaming Frog SEO Spider REST API

- **Description:** Desktop and cloud crawler with a command-line and REST interface for triggering programmatic crawls, extracting results, and integrating third-party API data (Ahrefs, Moz, GA4, GSC, PageSpeed Insights) during crawl. Version 23.0 (October 2025) added Ahrefs v3 API update and Lighthouse/PSI integration.
- **API Documentation:** https://www.screamingfrog.co.uk/seo-spider/user-guide/general-settings/#api-access
- **SDKs/Libraries:** No official SDK; scriptable via custom JavaScript extraction rules and command-line flags
- **Developer Guide:** https://www.lupagedigital.com/blog/screaming-frog-api/
- **Standards:** REST; CSV/JSON/XLSX export; supports custom JavaScript execution within crawl context
- **Authentication:** Licence key; API integrations use per-service credentials (OAuth for Google, API key for Ahrefs/Moz)

---

## Notes

- **GEO/AEO tooling (emerging):** Tracking brand and content visibility in AI-generated search results (Google AI Overviews, ChatGPT, Perplexity, Gemini) is a rapidly growing category in 2025–2026. Leading platforms include Scrunch, Adobe LLM Optimizer (launched October 2025), Profound, AthenaHQ, and Semrush AI Visibility Toolkit (September 2025). No stable API standards exist yet for this category; tools rely on LLM probing (sampling AI engine responses programmatically) rather than official APIs, as Google, OpenAI, and Perplexity do not expose ranking or citation data through public APIs.

- **Bing Search API deprecation:** Microsoft announced the retirement of the Bing Web Search API and Custom Search API effective August 11, 2026. New integrations targeting Bing SERP data should use DataForSEO or SerpApi as intermediaries rather than the native Bing Search API.

- **REPext (crawl controls evolution):** The IETF late-2024 working draft REPext extends RFC 9309 by exploring page-level crawl directives via HTTP response headers, beyond robots.txt. This is not yet standardised and not widely implemented, but relevant to forward-looking audit tooling.

- **MCP as an integration surface:** The Model Context Protocol is an emerging standard (backed by Anthropic, Microsoft, and others) that could become the primary integration surface for AI-native SEO tools exposing data to LLM agents. SEO data sources (keyword databases, backlink graphs, crawl results) are natural MCP tool/resource candidates.
