# US car dealership email and website census, 2026

Aggregate tables from [Provena](https://www.provena-ai.com/)'s 2026 studies of US franchise car dealerships: where dealer email is received, how dealer domains authenticate mail, and what runs on dealer websites. Each table here is the downloadable form of a published study; the study page carries the full method, charts, limits and discussion.

Aggregate tables only. The underlying domain lists are not published, and nothing here identifies a person.

## Datasets

| File | Study | Coverage | Rows |
| --- | --- | --- | --- |
| [`data/dealership-email-gateway-census.csv`](data/dealership-email-gateway-census.csv) | [US franchise dealership mail gateway census, September 2026](https://www.provena-ai.com/blog/dealership-email-gateway-census) | 17,659 franchise dealership domains | 68 |
| [`data/car-dealership-cold-email-statistics.csv`](data/car-dealership-cold-email-statistics.csv) | [Car dealership email statistics index, 2026](https://www.provena-ai.com/blog/car-dealership-cold-email-statistics) | 30 statistics | 30 |
| [`data/dealership-email-authentication-census.csv`](data/dealership-email-authentication-census.csv) | [US franchise dealership email authentication census, September 2026](https://www.provena-ai.com/blog/dealership-email-authentication-census) | 8,032 franchise dealership domains receiving mail | 56 |
| [`data/dealership-website-technology-census.csv`](data/dealership-website-technology-census.csv) | [US franchise dealership website technology census, September 2026](https://www.provena-ai.com/blog/dealership-website-technology-census) | 16,948 live franchise dealership websites | 413 |

### US franchise dealership mail gateway census, September 2026

MX classification of 17,659 US franchise car dealership website domains collected from manufacturer dealer locators, with each domain's franchise brands and state. Reports the share of domains with no mail record and the distribution of receiving providers (Microsoft 365, Google Workspace, GoDaddy, Mimecast, Barracuda, Proofpoint and other gateways) overall, by brand and by state. Aggregate tables only; the domain list is not published.

- **Study:** [Dealership Email Gateway Census: 17,659 Franchise Domains](https://www.provena-ai.com/blog/dealership-email-gateway-census)
- **Method:** DNS MX resolution of every domain against public resolvers, provider classification by published mail exchange hostnames, cohorts of at least 150 dealers per brand and 100 per state
- **Period:** 2026-09; **area:** United States
- **Size:** 17,659 franchise dealership domains
- **Measures:** Share of dealer domains with no MX record; Receiving provider share among domains that accept mail; Microsoft 365 share by franchise brand; Security gateway share by franchise brand; Microsoft 365 share by state; Google Workspace share by state
- **Columns:** `table`, `category`, `domains`, `share_pct`

### Car dealership email statistics index, 2026

A curated index of 30 first-party statistics about email and US franchise car dealerships, drawn from the June 2026 outcome benchmark (43,302 sends), the September 2026 gateway census (17,659 domains) and the September 2026 authentication census (8,032 domains). Each figure records its unit (domains or contacts), source study and limits. Intended for citation.

- **Study:** [Car Dealership Cold Email Statistics 2026: 30 Numbers](https://www.provena-ai.com/blog/car-dealership-cold-email-statistics)
- **Method:** Compiled from two Provena studies: a sending-platform ledger classified by recipient MX gateway, and a DNS MX census of dealer locator domains
- **Period:** 2026-03-01/2026-09-18; **area:** United States
- **Size:** 30 statistics
- **Measures:** Gateway share of dealer domains and contacts; Reply rate by receiving gateway; Policy bounce rate by gateway; Microsoft 365 and security gateway share by brand and state; Share of negative replies caused by contact change
- **Columns:** `number`, `section`, `statistic`, `unit`, `source_study`, `source_url`

### US franchise dealership email authentication census, September 2026

SPF and DMARC records resolved for 17,636 US franchise car dealership website domains from manufacturer dealer locators, reported for the 8,032 domains that receive mail: SPF presence and all-mechanism, DMARC presence, policy (none, quarantine, reject) and reporting address, split by receiving mail provider, franchise brand and state. Aggregate tables only; the domain list is not published.

- **Study:** [Dealership Email Authentication Census: 8,032 Domains](https://www.provena-ai.com/blog/dealership-email-authentication-census)
- **Method:** DNS TXT resolution of the root and _dmarc names against public resolvers; SPF classified by its all mechanism, DMARC by its p tag; cohorts of at least 150 dealers per brand and 100 per state
- **Period:** 2026-09-18/2026-09-19; **area:** United States
- **Size:** 8,032 franchise dealership domains receiving mail
- **Measures:** SPF presence and all mechanism; DMARC presence and policy; DMARC reporting address presence; SPF without DMARC share; Enforcement by receiving provider; Enforcement by franchise brand; Enforcement by state
- **Columns:** `cohort_type`, `cohort`, `domains`, `spf_pct`, `spf_hardfail_pct`, `dmarc_pct`, `dmarc_p_none_pct`, `dmarc_enforced_pct`, `dmarc_reject_pct`, `spf_without_dmarc_pct`, `dmarc_rua_pct`

### US franchise dealership website technology census, September 2026

Website platform attribution for 16,948 live US franchise car dealership sites from manufacturer dealer locators (www CNAME chain and page fingerprints), split by franchise brand and state, plus a seeded random sample of 3,000 sites rendered in headless Chrome (1,714 readable, 40% gated against automated browsers) measuring tag managers, analytics and advertising pixels, consent tools, chat widgets, digital retailing tools and accessibility overlays, by platform. Aggregate tables only; the domain list is not published.

- **Study:** [Dealership Website Technology Census: 16,948 Dealer Sites](https://www.provena-ai.com/blog/dealership-website-technology-census)
- **Method:** DNS CNAME resolution matched to hosting vendor hostnames; HTML and rendered-DOM fingerprinting in headless Chrome with a 2.5 second post-DOMContentLoaded settle; third-party host counting; cohorts of at least 150 sites per brand, 100 per state and 60 per platform in the sample
- **Period:** 2026-09-18/2026-09-18; **area:** United States
- **Size:** 16,948 live franchise dealership websites
- **Measures:** Website platform share; Automated-browser blocking by platform; Platform by franchise brand; Platform by state; Tag manager and analytics presence; Advertising pixel presence; Consent tool presence; Meta pixel without consent tool; Meta pixel firing before consent with and without a consent tool; Chat widget presence (loaded and referenced); Digital retailing tool presence; Accessibility overlay presence; Third-party host count
- **Columns:** `table`, `cohort_type`, `cohort`, `sites`, `platform`, `platform_sites`, `platform_share_pct`

### Related study without a table here

- [Dealership cold email outcomes by receiving mail gateway, June 2026](https://www.provena-ai.com/blog/dealer-cold-email-deliverability-by-mail-gateway): Aggregate bounce and reply rates for 43,302 cold emails sent to US franchise car dealership contacts from three Google-hosted sending workspaces, grouped by the recipient domain's mail gateway (Google Workspace, Microsoft 365, Mimecast, Barracuda, Proofpoint, Sophos). Observational send ledger exported through the sending platform API on 9 June 2026; cohorts published only where large enough to prevent client inference.

## How the data was collected

Dealer website domains were taken from manufacturer dealer locators, so every domain belongs to a franchise rooftop rather than an independent lot or a listing site. Mail and authentication records were resolved against public DNS resolvers; website technology was read from the live pages. Cohorts by brand and by state are reported only above a minimum size (150 dealers per brand, 100 per state) so that small groups do not produce noisy percentages. Each study page states its own limits; read them before quoting a figure.

## Citing

Use is free, including commercial use, with attribution. Cite the study page for the figure you use, for example:

> Provena (2026). *US franchise dealership mail gateway census, September 2026*. https://www.provena-ai.com/blog/dealership-email-gateway-census

GitHub's "Cite this repository" button gives the same citation for the collection as a whole.

## Licence

[Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/). Attribute to Provena and link to the study page or to https://www.provena-ai.com/research.

## More

- All Provena research: https://www.provena-ai.com/research
- Related open dataset, which B2B articles Microsoft Copilot cites: https://github.com/danielmcgrattan2007/b2b-ai-search-citation-study
- Questions or corrections: https://www.provena-ai.com/contact
