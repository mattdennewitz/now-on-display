# Now on Display

A research collection of U.S. commercial, nonprofit, artist-run, and cooperative art galleries, plus art museums in the **United States, European Union member countries, and United Kingdom**. Research snapshots were collected on **November 15, 2026**.

**This is an extensive starting collection, not a census.** The original gallery directory represents all 50 U.S. states, Washington, DC, and Puerto Rico, with one U.S. city assigned per organization. The museum extension has its own country-aware schema and records separately named public museum institutions or venues.

## Start here

| File | Contents |
| --- | --- |
| [`us-art-galleries.csv`](us-art-galleries.csv) | Main directory: 758 gallery organizations, sorted by footprint tier. |
| [`us-art-galleries-sources.csv`](us-art-galleries-sources.csv) | 999 gallery-specific evidence records, including source URLs, checked date, and activity evidence. |
| [`art-museums.csv`](art-museums.csv) | 740 art museums across the U.S., all 27 EU member countries, and UK, with country codes and explicit operating status. |
| [`art-museums-sources.csv`](art-museums-sources.csv) | 1,378 museum-specific activity, location, identity, and official-website evidence records. |
| [`museum-research/scope.json`](museum-research/scope.json) | Explicit country allowlist, museum schema, geographic exclusions, and operating-status definitions. |
| [`museum-research/summary.json`](museum-research/summary.json) | Museum totals, country coverage, operating statuses, and evidence-basis counts. |
| [`museum-research/`](museum-research/) | Regional museum extracts, evidence, exclusions, and retained raw retrievals. |
| [`gallery-research/additional-directory-candidates.csv`](gallery-research/additional-directory-candidates.csv) | 61 additional, **unverified** directory candidates from Artnet, Artforum Artguide, and Artsy. These have not been added to the main directory. |
| [`gallery-research/coverage-findings.json`](gallery-research/coverage-findings.json) | Coverage audit, underrepresented markets, and four confirmed omitted galleries. These omissions are documented but have not yet been merged into the main directory. |
| [`gallery-research/`](gallery-research/) | All retained research data, intermediate extracts, source responses, and compressed batch exports. |

The original gallery CSV has exactly these columns:

```csv
Gallery Name,Size Tier,City & State,Official Website URL
```

The website column contains official gallery URLs, not directory-profile URLs. The separate candidate CSV intentionally contains directory-profile URLs and explicit unverified status; do not treat it as an active-gallery directory.

## Gallery footprint tiers

| Size Tier | Organizations | Classification |
| --- | ---: | --- |
| Large / Blue-Chip | 33 | Major multi-location or internationally recognized galleries. |
| Medium / Mid-Tier | 443 | Established regional galleries, ADAA members, or recognized exhibition institutions. |
| Small / Boutique | 282 | Independent, artist-run, cooperative, and neighborhood galleries. |

Tiers are qualitative research judgments, not audited measurements of revenue, staffing, floor area, or market share. The main CSV places major multinational galleries first, followed by the remaining tier blocks with principally alphabetical ordering.

## Museum collection

The museum extension is separate from the gallery files; it does not relabel museums as commercial galleries or apply gallery-market size tiers to them.

```csv
Museum Name,City,State / Region,Country,Country Code,Official Website URL,Operating Status
```

Countries use English names and ISO 3166-1 alpha-2 codes, including `US` for the United States and `GB` for the United Kingdom. The allowlist consists of the U.S., the 27 current EU member countries, and the UK. Switzerland, Norway, Iceland, Vatican City, Canada, and Mexico are outside this museum scope. Jersey, Guernsey, the Isle of Man, and British Overseas Territories are not treated as part of the UK.

U.S. regions use state or territory abbreviations; UK regions identify England, Scotland, Wales, or Northern Ireland. EU regions may be blank when not verified. Different museums can legitimately share an official domain, especially national networks, universities, and municipal operators; they are not collapsed by domain alone. Separately named venues are retained without duplicating an indistinguishable umbrella institution.

Included institutions cover fine, modern/contemporary, photography, sculpture, decorative/design, university, and artist-house art museums, plus established noncollecting public art institutions with museum-like exhibition programs. Mixed museums qualify where a substantive public art collection or identifiable art-museum program is supported; history-, archaeology-, science-, and natural-history-only institutions do not qualify.

### Operating status and activity evidence

- **Active**: a current public program, collection-access arrangement, or maintained visitor operation is supported. This is not a claim that the doors are open at every moment.
- **Active (offsite)**: the normal building is closed, but substantive current public exhibitions or collection displays continue at identified temporary/offsite venues.
- **Active (seasonal)**: an operating museum has a documented annual closed season and continuing or announced visitor program.
- **Active (partial opening)**: meaningful public art access continues while a significant portion of the museum is closed.
- **Active (temporary closure)**: a short, explicitly documented installation/event closure has a stated return to public operation.

Closed buildings without a supported current museum program, permanently closed institutions, and not-yet-open replacements are excluded. Closure dates, temporary locations, seasonal notices, and evidence conflicts belong in the source ledger and regional evidence records; do not use this snapshot as live opening-hours advice.

Evidence distinguishes dated official programs from undated current visiting/collection information and explicitly labeled search-index fallbacks. The regional six-column CSVs retain their extraction schema; the combined root museum CSV adds operating status from their evidence records. The country restriction applies to the curated museum dataset: raw source directories can mention out-of-scope institutions that were not included.


## Gallery method and inclusion criteria

1. Discover galleries through dealer associations, regional gallery associations, exhibition guides, fair exhibitor lists, and official sites.
2. Extract gallery identities, U.S. locations, and official website links.
3. Review published activity evidence: dated exhibitions or fair participation, named current programs, current association listings, public gallery hours, and operating exhibition/showroom information.
4. Exclude confirmed closures, uncertain archive-only entries, museums without an identified qualifying gallery operation, framing-only businesses, and individual artist portfolios without an established gallery operation.
5. Merge organizations across source lists and known renamings; assign one U.S. city and a footprint tier.
6. Keep raw evidence, exclusions, and unverified candidates separate from the main export.

Framing businesses are included only where an active fine-art gallery program was supported. SAM Gallery is included as the Seattle Art Museum's separately identified art-sales and exhibition gallery, not as a general museum listing. Nonprofit organizations are included for their exhibition-gallery programs, not merely because they fund or support artists.

### Context.dev skill / tooling provenance

The original gallery research was requested using the **Context.dev skill** and was performed with the mounted [Context.dev](https://context.dev/) MCP integration. The museum extension also uses this integration, supplemented by official museum networks, direct public-page reads, and local data processing. The tools actually used were:

- `context/web-search` for discovery and query-relevant source passages;
- `context/web-scrape` for official sites, directories, Markdown, and structured extraction;
- `context/submit-batch`, `context/get-batch`, and `context/get-batch-results` for bulk retrieval;
- `context/get-usage` for credit-budget checks;
- `context/submit-feedback` to report transport and extraction failures.

Provenance clarification: **no separately installed Context.dev skill package or skill version was available in the session**; the installed-skill listing was empty. The reference to the Context.dev skill records the requested workflow, not a claim that a standalone skill package was installed or executed. Actual extraction used Context.dev's available MCP tools, supplemented by direct public-page reads and local CSV/JSON processing.

No further Context calls are needed to read or analyze the saved files. Fresh verification or additional collection may require new requests and credits.

## Principal discovery sources

- [Art Dealers Association of America: member galleries](https://artdealers.org/member-galleries)
- [New Art Dealers Alliance: gallery members](https://www.newartdealers.org/members)
- [Two Coats of Paint: November 2026 NYC gallery guide](https://twocoatsofpaint.com/2026/11/nyc-selected-gallery-guide-november-2026.html)
- [Seattle Art Fair: 2026 galleries](https://seattleartfair.com/2026-galleries/)
- [EXPO CHICAGO: 2026 gallery announcement](https://www.expochicago.com/news/announcing-galleries-2026)
- [Scottsdale Gallery Association](https://scottsdalegalleries.com/about/map/)
- [Charleston Gallery Association](https://www.charlestongalleryassociation.com/galleries)
- Jackson Hole Chamber of Commerce's 2026/2027 Gallery Guide, linked in the regional evidence records
- [Artforum Artguide](https://artguide.artforum.com/)
- [Artnet's fine-art gallery directory](https://www.artnet.com/galleries/fine-art/)
- [Artsy's gallery directory](https://www.artsy.net/galleries)
- Official gallery sites and additional local sources recorded in the evidence files
- [Association of Art Museum Directors: members](https://aamd.org/our-members/members)
- [Art UK: current partner collections](https://artuk.org/for-collections/current-partner-collections)
- [Art Fund: museum and exhibition discovery](https://www.artfund.org/explore)
- [European Union: current member countries](https://european-union.europa.eu/principles-countries-history/eu-countries_en)
- Official museum visit, collection, exhibition, and closure-notice pages recorded in the museum evidence files

Artnet, Artforum, and Artsy were subsequently sampled for additional candidates; they were not exhaustively harvested. Their listings alone do not establish current operation, a permanent U.S. location, or eligibility for the main directory.

## Retained gallery research archive

The original gallery archive preserves **79 data files**: 61 JSON files, 11 compressed NDJSON exports, five CSV files, and two text captures. Intermediate and duplicate-format captures are intentionally retained rather than discarded during repository packaging. The museum extension is additional and does not change these original files.

### Curated and intermediate datasets

- `gallery-research/parent-records.json`: main-research records before integrating regional, nonprofit, and Northwest additions.
- `gallery-research/combined-records.json`: the 758 combined records, including evidence and source-origin metadata.
- `gallery-research/combined-candidates.json`, `nada-candidates.json`, and `nyc-guide-candidates.json`: intermediate candidate lists; not independently validated directories.
- `gallery-research/adaa-roster.json` and `adaa-profiles.json`: association roster and profile extracts.
- `gallery-research/nonprofit.csv` and `nonprofit-evidence.json`: nonprofit research slice and evidence.
- `gallery-research/regional.csv` and `regional-evidence.json`: regional research slice and evidence.
- `gallery-research/excluded-candidates.json`: excluded or insufficiently supported candidates; exclusion does not always mean confirmed closure.

### Source and batch captures

- `official-site-evidence.json`, `followup-evidence.json`, `fair-evidence.json`, and `northwest-evidence.json`: retrieved page evidence.
- `activity-part*.ndjson.gz`, `followup-part*.ndjson.gz`, `fair-part*.ndjson.gz`, and `northwest-part*.ndjson.gz`: original compressed Context batch exports.
- Batch submission/status files, `adaa-profile-page*.json`, `adaa-roster-response.json`, and `*-full.json`: retrieval metadata and original or expanded response captures.
- `adaa-full.txt`, `nada-full.txt`, `nyc-november-guide*.json`, `expo2026.json`, and `seattle2026.json`: source-directory and exhibition-guide captures.
- `coverage-*.json`, `major-gaps.json`, `international-gaps.json`, `uncertain-status.json`, `iowa-gap.json`, and `indiana-gap.json`: targeted discovery and coverage-audit evidence.
- `artforum-santafe-directory-check.json`, `artnet-directory-check.json`, `artnet-full-directory-check.json`, and `artsy-directory-check.json`: subsequent directory-access samples.

Raw responses have heterogeneous schemas: some are complete source objects, some wrap tool text, and some preserve documented clipping or loading placeholders. A successful response or present file is not proof that every page field was captured. Prefer the curated CSV and gallery-specific evidence when evaluating an individual entry. Some transient partial wrappers and redundant download copies were removed during research before repository packaging; all retained generated data files are included here.

## Retained museum research archive

`museum-research/us/`, `eu-west/`, `eu-south-east/`, and `uk/` preserve each regional museum CSV, evidence records, exclusions, source extracts, batch submissions/status responses, and compressed retrieval exports. `museum-research/scope.json` documents the country boundary, and `museum-research/summary.json` summarizes the combined museum dataset.

All retained generated museum data are committed, including failed/partial retrieval evidence needed to explain exclusions or verification limits. Expiring batch download links are supplemented by local compressed exports. Museum records were checked for the agreed schema, country/name-code consistency, eligible geography, explicit operating status, duplicate identities, source coverage, and the requested Art Institute of Chicago, Whitney, and MoMA entries.


## Gallery coverage and verification limits

- New York state accounts for 43.5% of the main directory. ADAA, NADA, and the NYC exhibition guide supplied 60.2% of row origins.
- Several states have only one assigned gallery. Some important markets have no assigned rows, even though galleries operate there.
- University galleries, municipal exhibition spaces, neighborhood cooperatives, regional art-walk districts, and galleries outside the sampled networks were not systematically enumerated.
- Published evidence varies in strength. A dated current exhibition is stronger than an undated operating page or current association listing. No telephone confirmation was performed.
- Some galleries operate seasonally, by appointment, between installations, offsite, or through temporary exhibitions. The files are research snapshots, not a live business-status guarantee.
- Known omissions and new candidates remain separate from the 758-row export. Website changes, renamed businesses, shared domains, and multiple locations require further identity review.
- No national completeness percentage can be inferred from these files.

The gallery export was checked for the exact four-column schema, tier ordering, populated fields, HTTP(S) website URLs, exact duplicate rows, all-state representation, and evidence coverage for every row. Those are data-integrity checks, not independent confirmation of every gallery's business status. The museum collection is also evidence-supported rather than exhaustive, and country representation does not establish complete coverage within a country.

## Reading the data

The CSVs are UTF-8 and use standard CSV quoting. Open them in a spreadsheet or read them with Python's standard library:

```python
import csv

with open("us-art-galleries.csv", newline="", encoding="utf-8") as file:
    galleries = list(csv.DictReader(file))
```

To inspect a compressed batch export:

```python
import gzip
import json

with gzip.open(
    "gallery-research/activity-part0.ndjson.gz", "rt", encoding="utf-8"
) as file:
    records = [json.loads(line) for line in file if line.strip()]
```

## Privacy and source rights

Keep this repository private. Raw captures can contain rendered HTML, third-party page metadata, request and batch identifiers, and time-limited download URLs; they are not sanitized for public redistribution. No account credentials or Context API keys were intentionally saved. Expiring download URLs are not a durable substitute for the compressed exports preserved here.

Third-party source text, images referenced by URL, and site content remain subject to their owners' rights and terms. This repository does not grant a license to redistribute third-party material.
