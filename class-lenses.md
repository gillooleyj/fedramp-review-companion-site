# Published-rule lenses for Classes A–C

Verified November 4, 2026 against selected live official CR26 pages. This is a focused training lens for the 20x Program path, not an exhaustive applicability engine. Source rule text, conditions, definitions and effective dates govern. Review questions are suggested techniques, not additional requirements.

## What changes by class

| Topic | Class A | Class B | Class C |
| --- | --- | --- | --- |
| Assessment foundation | Approved external framework plus FedRAMP overlay | Independent assessment of applicable rules and KSIs | Independent assessment of applicable rules and KSIs |
| Separate recognized-assessor package IV&V | MAY | Required initial assessment; annual rule/KSI coverage | Required initial assessment; annual rule/KSI coverage |
| Automated methods per KSI | Do not import B/C minimum counts | SHOULD: at least one | MUST: at least two |
| Historical KSI metrics | MAY | SHOULD: 30-day and available annual summaries | MUST: summaries plus available daily history and persistent-validation status |
| Quarterly review meeting | MAY under the optional Class A rules | SHOULD | MUST |

Sources: [Class A certification](https://www.fedramp.gov/2026/reference/20x/a/fedramp-certification/), [Class A related rules](https://www.fedramp.gov/2026/reference/20x/a/related/), [Class B certification](https://www.fedramp.gov/2026/reference/20x/b/fedramp-certification/), [Class B SDR](https://www.fedramp.gov/2026/reference/20x/b/security-decision-record/), [Class C certification](https://www.fedramp.gov/2026/reference/20x/c/fedramp-certification/), [Class C SDR](https://www.fedramp.gov/2026/reference/20x/c/security-decision-record/), [Class B continuous monitoring](https://www.fedramp.gov/2026/reference/20x/b/collaborative-continuous-monitoring/), [Class C continuous monitoring](https://www.fedramp.gov/2026/reference/20x/c/collaborative-continuous-monitoring/).

Class B’s historical-metrics force changed from MUST to SHOULD on October 8, 2026. Class A’s mandatory overlay explicitly added SDR-CSX-KSI on October 31. Initial applications lacking the full metric period must be considered under the published mechanism/agreement note; do not turn unavailable historical data into an automatic adverse finding. SHOULD departures still require documented decisions under the [official definition](https://www.fedramp.gov/2026/definitions/#should).

The accompanying `class-lenses.json` contains 12 focused checks per class. Every check separates the published requirement summary from a suggested review question and links to the governing page. It does not enumerate every rule, decide conditional applicability, or declare compliance.

## Evidence fields in the SDR

The live [SDR JSON Schema, version 1.1.1](https://www.fedramp.gov/schemas/fedramp-security-decision-record-schema-2026-06-24.json) defines `frrImplementation`, `frrValidation`, and `frrAssessment` as arrays of text statements that may use Markdown. It does **not** define a dedicated `frrEvidence` property. A rule’s evidence references may therefore appear inside those narratives or additional provider fields.

KSI entries have a dedicated `ksiEvidence` array. Its evidence objects support a description, type, URI location, inline evidence text and update date. Narrative fields may still mention other artifacts. Empty structured evidence fields alone do not prove the absence of evidence elsewhere. Conversely, a filename or URL in prose does not establish that the actual artifact was supplied, opened, verified or supports the claim.

A readable viewer can present text, headings, lists and evidence references while retaining exact field names and source pointers. It must distinguish narrative extraction from schema validation and technical evaluation.

## Scope and timing

The lenses concern published class distinctions as observed on the verification date. They do not replace the separate type/path/stage applicability checks. Live pages distinguish initial-obtaining dates from ongoing-maintenance transition/grace conditions. Confirm those conditions for the actual review.

For B/C, annual rule assessment and annual KSI inclusion are stated in IVV-CSO-FIA and IVV-CSX-AIA. See [Class B IV&V](https://www.fedramp.gov/2026/reference/20x/b/independent-verification-and-validation/) and [Class C IV&V](https://www.fedramp.gov/2026/reference/20x/c/independent-verification-and-validation/). Initial assessment freshness is a different check. A three-month assessment window should not be mistaken for a requirement to reassess the whole offering every three months.
