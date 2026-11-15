# Now on Display

A research directory of commercial, nonprofit, artist-run, and cooperative art galleries in the United States. Research snapshots were collected on **November 15, 2026**.

**This is an extensive starting directory, not a nationwide census.** All 50 states, Washington, DC, and Puerto Rico are represented, but coverage within each jurisdiction is uneven. Each organization is assigned one U.S. city; this is not a branch-location inventory.

## Start here

| File | Contents |
| --- | --- |
| [`us-art-galleries.csv`](us-art-galleries.csv) | Main directory: 758 gallery organizations, sorted by footprint tier. |
| [`us-art-galleries-sources.csv`](us-art-galleries-sources.csv) | 999 gallery-specific evidence records, including source URLs, checked date, and activity evidence. |
| [`gallery-research/additional-directory-candidates.csv`](gallery-research/additional-directory-candidates.csv) | 61 additional, **unverified** directory candidates from Artnet, Artforum Artguide, and Artsy. These have not been added to the main directory. |
| [`gallery-research/coverage-findings.json`](gallery-research/coverage-findings.json) | Coverage audit, underrepresented markets, and four confirmed omitted galleries. These omissions are documented but have not yet been merged into the main directory. |
| [`gallery-research/`](gallery-research/) | All retained research data, intermediate extracts, source responses, and compressed batch exports. |

The main CSV has exactly these columns:

```csv
Gallery Name,Size Tier,City & State,Official Website URL
```

The website column contains official gallery URLs, not directory-profile URLs. The separate candidate CSV intentionally contains directory-profile URLs and explicit unverified status; do not treat it as an active-gallery directory.

## Footprint tiers

| Size Tier | Organizations | Classification |
| --- | ---: | --- |
| Large / Blue-Chip | 33 | Major multi-location or internationally recognized galleries. |
| Medium / Mid-Tier | 443 | Established regional galleries, ADAA members, or recognized exhibition institutions. |
| Small / Boutique | 282 | Independent, artist-run, cooperative, and neighborhood galleries. |

Tiers are qualitative research judgments, not audited measurements of revenue, staffing, floor area, or market share. The main CSV places major multinational galleries first, followed by the remaining tier blocks with principally alphabetical ordering.

## Method and inclusion criteria

1. Discover galleries through dealer associations, regional gallery associations, exhibition guides, fair exhibitor lists, and official sites.
2. Extract gallery identities, U.S. locations, and official website links.
3. Review published activity evidence: dated exhibitions or fair participation, named current programs, current association listings, public gallery hours, and operating exhibition/showroom information.
4. Exclude confirmed closures, uncertain archive-only entries, museums without an identified qualifying gallery operation, framing-only businesses, and individual artist portfolios without an established gallery operation.
5. Merge organizations across source lists and known renamings; assign one U.S. city and a footprint tier.
6. Keep raw evidence, exclusions, and unverified candidates separate from the main export.

Framing businesses are included only where an active fine-art gallery program was supported. SAM Gallery is included as the Seattle Art Museum's separately identified art-sales and exhibition gallery, not as a general museum listing. Nonprofit organizations are included for their exhibition-gallery programs, not merely because they fund or support artists.

### Context.dev skill / tooling provenance

Research was requested using the **Context.dev skill** and was performed with the mounted [Context.dev](https://context.dev/) MCP integration. The tools actually used were:

- `context/web-search` for discovery and query-relevant source passages;
- `context/web-scrape` for official sites, directories, Markdown, and structured extraction;
- `context/submit-batch`, `context/get-batch`, and `context/get-batch-results` for bulk retrieval;
- `context/get-usage` for credit-budget checks;
- `context/submit-feedback` to report a transport failure.

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

Artnet, Artforum, and Artsy were subsequently sampled for additional candidates; they were not exhaustively harvested. Their listings alone do not establish current operation, a permanent U.S. location, or eligibility for the main directory.

## Complete retained data archive

This repository preserves **79 data files**: 61 JSON files, 11 compressed NDJSON exports, five CSV files, and two text captures. Intermediate and duplicate-format captures are intentionally retained rather than discarded during repository packaging.

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

## Coverage and verification limits

- New York state accounts for 43.5% of the main directory. ADAA, NADA, and the NYC exhibition guide supplied 60.2% of row origins.
- Several states have only one assigned gallery. Some important markets have no assigned rows, even though galleries operate there.
- University galleries, municipal exhibition spaces, neighborhood cooperatives, regional art-walk districts, and galleries outside the sampled networks were not systematically enumerated.
- Published evidence varies in strength. A dated current exhibition is stronger than an undated operating page or current association listing. No telephone confirmation was performed.
- Some galleries operate seasonally, by appointment, between installations, offsite, or through temporary exhibitions. The files are research snapshots, not a live business-status guarantee.
- Known omissions and new candidates remain separate from the 758-row export. Website changes, renamed businesses, shared domains, and multiple locations require further identity review.
- No national completeness percentage can be inferred from these files.

The main export was checked for the exact four-column schema, tier ordering, populated fields, HTTP(S) website URLs, exact duplicate rows, all-state representation, and evidence coverage for every row. Those are data-integrity checks, not independent confirmation of every gallery's business status.

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
