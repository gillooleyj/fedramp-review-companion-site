# Internal review workflow and review sheet analysis

Prepared 4 November 2026 from the supplied internal SOP and workbook. This analysis explains what those artifacts actually instruct a reviewer to do. It does not establish that every copied rule, internal convention, or spreadsheet formula reflects the currently effective public requirements.

The most important finding is that the SOP deliberately stops short of teaching package analysis. Its “Phase 2 — Review” introduction says the steps concern document handling, group decisions, and handoffs, and are not intended to explain how to analyze a package or interpret Rules and KSIs. The missing training therefore needs to connect the public rule to the provider's implementation, evidence, assessment, and agency implications. The workbook provides useful prompts for that reasoning but does not supply the reasoning itself.

## Sources and status

- Internal SOP (source retained offline): front matter identifies **DRAFT**, version **0.1**, effective date **TBD**, process owner **TBD**. Its revision history also includes 0.03 dated 15 October 2026, 0.02 dated 7 October, and 0.01 dated 25 September. Do not describe this as a finalized or approved policy solely because it is the current supplied copy.
- Review sheet template (source retained offline): local Excel export of a Google Sheets workflow. It contains Google-specific functions, cached output, and instructions for Apps Script menus. This review did not execute its scripts, recalculate it in Google Sheets, or change it.
- SOP references below name the original headings. `P` references are paragraph positions in the extracted OOXML, retained in the local extraction for precise checking, not printed section or page numbers.

## The roles are distinct

The **provider** supplies package materials and responds to FedRAMP. The **Intake Team** checks whether the package is usable for review and prepares the review infrastructure. The **Review Team** evaluates the package, discusses concerns, and develops feedback. The **Vanguard Lead** guides the review and routes escalation. The **Security Director**, with the Program/FedRAMP Director as appropriate, provides escalation decisions and final approval. These responsibilities appear under “Roles & Responsibilities” (P24–42).

An independent assessor is a different actor from a FedRAMP program reviewer. The workbook explicitly warns that the ASF auditor must not automatically be entered as the FedRAMP independent assessor merely because the firm is FedRAMP recognized or has performed other FedRAMP assessments (`Summary!B26` note). `MakeCertReport!C29:C34` describes IV&V as optional for Class A and mandatory for the other classes supported by those instructions. The public rules should resolve the applicable class and assessment obligations.

## Workflow described by the SOP

| Stage | What the supplied SOP directs | Review purpose |
| --- | --- | --- |
| Intake and access | Verify Marketplace identity and FedRAMP ID; request trust-center access; scan for significant files; download and organize materials; create the review folders and sheet; run the SDR Checker. | Establish that the review team can obtain and navigate the package. |
| Completeness | Check documents and SDR content, identify missing Rules/KSIs, and manually inspect a handful of 3–7 Rules/KSIs. Return the package for correction if the information is insufficient to perform review. | Establish reviewability. Passing this gate is not a determination that claims are correct. |
| Assignment | Assign a team, request access, begin review, and hold an internal kickoff. Assign Rules/KSIs and MRR work, agree collaboration methods, and set a schedule. | Ensure that the work has owners and coverage. |
| Walkthrough | For B/C/D, prepare an agenda and meet with provider and assessor. | Understand the offering and how to navigate the trust center. The detailed walkthrough section is unfinished. |
| Individual review | Perform Rules/KSI and MRR review, complete the other review questions, document concerns, and communicate with the team. | Produce a reasoned review record. |
| Conclave | Discuss all concerns, determine next steps, discuss recurring themes and strengths, and finalize external comments. | Turn individual observations into team dispositions. |
| Resolution and escalation | Route escalations through Vanguard Lead; consolidate pre-cert actions for provider response; consolidate post-cert actions for the report; conduct the security-inbox check. | Resolve prerequisites and identify follow-up and agency implications. |
| Recommendation | Team lead prepares and refines the certification report, obtains Vanguard review, then recommends certification to the directors. | Present an approval recommendation and an intelligible record of the review. |
| Certification | Finalize report, save PDF, generate SHA-256 hash, notify provider, and update FRODO/Marketplace. | Publish and preserve the approved outcome through the authorized process. |

Sources: SOP “Phase 1 — Intake” (P59–126); “Phase 2 — Review” (P129–224); “Phase 3 — Certification” (P228–249); “Intake Team Conducts SDR Completeness Check” (P472–504).

The SOP starts the FedRAMP 30-day clock at application and stops it when certification status is updated in FRODO. It separately starts the Review Team Clock at “Under Review.” It does **not** explain pause/resume rules, define every clock calculation, or give the Review Team Clock's stop condition. Those details should not be invented from ticket status names. The SOP calls for queue and review updates at least weekly (P125 and P171).

## What to check at intake

The SOP's “Appendix: Package Checklists” (P525–563) calls for an accessible trust center without an NDA or vendor terms barrier, a correct FedRAMP ID in the CPO, and human- and machine-readable SDRs that are complete. It expects all applicable MUST and SHOULD Rules/KSIs, meaningful implementation status, explanation and planned timeframes where implementation is partial or absent, and concrete references to evidence.

For Class A, its examples favor a specific mapping such as an ASF section, page, or control over a generic “See SOC report.” Referenced artifacts must be available. If a FedRAMP-specific optional independent assessment was conducted, the checklist calls for per-practice assessment summaries and an overall CPO assessment summary. It also identifies ASF materials, CPO, incident examples with differing rule forces, and OCR. The SOP says to check ASF freshness and seek a bridge letter when the SOC 2 report is old. The current public rule remains the authority for exact timing and accepted materials.

The paragraph introducing “Class A tell-tale signs of too low quality to review” (P487–492) lists positive attributes such as direct ASF mappings and sufficient implementation detail, without consistently saying “missing.” Read this as an ambiguous draft checklist, not as a rule that having mappings is itself a defect.

The automated intake check is narrower than substantive review. The note at `Intake Report!C1` documents this logic:

- For FRR items reported Not Implemented, the check can pass if an implementation field is present.
- For other FRR statuses, it looks for implementation and validation fields.
- For KSI items reported Not Implemented, an implementation field can similarly satisfy the check.
- For other KSI statuses, it looks for implementation, validation, tests, and evidence.
- Missing entries fail, blank status is noted, and assessment presence is display-only.

That is a field-presence check. It does not establish that the implementation exists, the validation is persuasive, the evidence is current, or a mandatory independent assessment is sufficient.

## How the workbook encodes substantive reasoning

The active `Review Sheet` uses row 5 for headers and rows 6–422 for the supplied review entries. Interpret columns as a sequence of questions, rather than a checklist whose filled cells prove security.

| Column | Header | How to use it |
| --- | --- | --- |
| A–E | Class Filter; Rule ID; Rule Name; Rule Statement & Notes; Rule Force | Confirm the applicable class, requirement identity, exact text, and force against the selected current rule version. |
| F | Provider Status | Preserve what the provider claims. Missing, undefined, and unexpected values are distinct from Not Implemented. |
| G | Reviewer Assigned | Identify who owns the review. Meta rules may be assigned to all reviewers. |
| H | Status for Not Fully Implemented | Clarify whether implementation is unknown, planned, in progress, or claimed inapplicable, and record the rationale. |
| I | Evidence of Implementation | Identify evidence or ASF mappings for Class A; evidence provision for B/C. A reference must be inspected before it can support a conclusion. |
| J | Automated V&V — Num Methods | Record method count for the related automation requirements. Counting alone does not judge whether methods test different failure modes or cover the relevant population. |
| K | Appropriate Method(s) — Automated V&V + IA V&V | Judge whether provider and assessor methods actually test the practice. The note explicitly makes this optional for Class A. |
| L | Rule Intent Met | Make the outcome judgment; explain partial, negative, or inapplicable results. The note describes N/A as particularly suitable when an optional MAY rule was not adopted. |
| M | Sufficient Info? | Ask whether the information supports an agency customer's risk-based decision, including explanation of measures, persistent cycles, verification, and validation where required. |
| N | Reviewer Status | Select “OK, nothing additional” or “Concern.” This is the reviewer's triage result, separate from provider status. |
| O | Internal Notes & Comments | The note says this **must** be populated for a Concern. Preserve the basis and evidence location. |
| P | External Likes | Record specific strengths worth communicating to the provider. |
| Q | Next Steps | Record the team disposition from the Conclave. |
| R–S | Internal Notes; Internal Escalation Outcome | Record discussion and any leadership determination. |
| T | External Action/Feedback to share w/ Provider | State the requested correction or clarification in language the provider can act on. |
| U | External Actions for & Impact to Agencies | Explain agency-relevant implications, including risks that may coexist with an OK program-review result. |
| V | Class/RuleID | Composite identifier for the class-specific entry. |

Source: `Review Sheet!A5:V5` and the header notes. `Dropdown Lists!F2:F3` defines the two reviewer statuses. `Dropdown Lists!L2:L5` defines the next-step options: OK, post-cert action/feedback, pre-cert action/feedback, and internal escalation.

The note at `Review Sheet!E5` describes MUST as required, SHOULD as expected unless justified with rationale and implications, and MAY as optional. That note is an internal shorthand. Use the current public rules' definitions when interpreting the obligation. A blank Rule Force on a KSI row does not make the KSI optional; determine applicability from the governing certification rules.

The distinction between `L` and `M` is valuable. A reviewer may believe an outcome is plausible while still lacking enough information for agencies to understand its scope and limitations. Conversely, the package may be transparent and complete about a partially implemented measure. Preserve both judgments.

## How supporting sheets fit together

- **Summary:** provider identity, class (`C14`), ASF and assessment dates (`B18:C31`), hosting/platform information (`B33:M38`), review team and completion (`B40:C42`), and collected findings (`B44:P53`). The note at `D14` says class becomes locked after creation because changing it can affect entered review data.
- **Intake Report:** human/machine-readable document checks (`A3:D14`), freshness inputs (`E3:J7`), and detailed checker output beginning at row 15. Treat it as completeness and usability triage.
- **ASF Exceptions:** source control and location, auditor finding, provider response, relevance, and FedRAMP summary (`A2:G2`). This prevents a broad ASF opinion from hiding exceptions that matter for this offering.
- **Scorecard (A):** ASF mapping/coverage, implementation, optional adoption, exceptions, and agency risks. The sheet is hidden in this supplied export.
- **Scorecard (BC):** implementation summaries, automation, and internal “surety” scoring. `Z47` describes that score as a combination of completeness, accuracy, intent, and sufficiency. These are internal summaries, not independent evidence or an automatic certification decision.
- **MakeCertReport:** instructions at `A1` require checking inputs and reviewing/editing the generated report. Additional reviewer narrative belongs in `D33`, `D37`, `D40`, `D42:D44`; source-fed feedback appears in `E45:E47`. Generated prose requires comparison with the underlying findings.

There are 21 worksheets, including hidden helper and legacy sheets. The active review list has 40 Class A rows, 188 Class B rows, and 189 Class C rows. These are counts of rows in this template, **not** counts of all applicable official requirements. The Class C list includes a duplicate described below.

## Material limitations in the supplied artifacts

These are observed issues in the supplied local files. They were not repaired and have not been confirmed against the live Google Sheets version.

1. **The SOP leaves the analytical method unspecified.** Phase 2 explicitly disclaims teaching it. MRR review is assigned but MRR is not defined or explained in the abbreviations appendix. The B/C checklist section and walkthrough detail are incomplete. No criteria explain exactly when a concern becomes pre-cert, post-cert, or escalation.
2. **The SOP's status summary does not fully match its main workflow.** The appendix uses old step numbers and transitions such as “Under Review → Certified,” while the body includes “Pending Certification Decision.” Use the operational owner's current workflow to resolve the conflict.
3. **The workbook has an exact duplicate Class C practice.** `Review Sheet!B421:B422` both contain `KSI-SVC-VRI`, with the same class, title, and statement. Totals derived from row counts can count it twice. Confirm whether the live template already corrects it before using counts as coverage evidence.
4. **The template includes a cell error.** `Review Sheet!G100` has a stored `#REF!` value in Reviewer Assigned. `MakeCertReport!B21` has a stored `#VALUE!`. These observations concern the supplied export; no native recalculation was performed.
5. **Cached generated prose is unsafe as evidence.** `MakeCertReport!E44` already claims successful tests and satisfactory performance while `Review Sheet!F2` shows 0/40 reviewed and provider identity is unfilled. `Summary!O53:P53` also contains example/generated findings despite blank current review inputs. Treat that prose as stale template output until regenerated and checked against actual notes.
6. **Freshness formulas deserve validation before operational reliance.** `Intake Report!I5` is labeled for SDR freshness but gates on `G6/H6` before testing `G5`; it uses TODAY rather than the submission date. `I6` tests the report end date against TODAY minus 12 months, while `I7` compares bridge date to submission date with an absolute seven-day difference. These are literal formula observations, not findings that the public rule itself is wrong. The intended dates, reference date, and direction of comparison need confirmation.
7. **Some instructions refer to old columns or tabs.** `Summary!B2` refers to “Class A Review,” but the visible review tab is “Review Sheet.” The note at `Review Sheet!Q5` directs writing specifics in Q, though Q is the categorical next-step field and T is the external narrative. It also names “Not a reviewer concern,” which is absent from the current next-step list. Follow the actual current headers and resolve ambiguous instructions with the template owner.
8. **The local Excel export cannot reproduce the whole Google workflow.** Google AI, IMPORTRANGE, FILTER/CHOOSECOLS exports, Apps Script menus, and authenticated external data are not validated merely by reading this file. Counts and cached prose are not proof that those services executed successfully.

## A practical reading path

1. Read the SOP's “Purpose,” “Roles & Responsibilities,” and the first paragraph of “Phase 2 — Review.” Identify your assigned role and the decision you are preparing for the team.
2. Open `Summary!C14` and confirm the package class. Read the current public certification and class-specific requirements before using the copied worksheet statements. Note the selected rule version and assessment period.
3. Read the CPO and package navigation information to understand the offering, boundary, trust center, assessment basis, and evidence locations. Compare these with `Summary!B5:M38`.
4. Read the header notes in `Review Sheet!F5:U5`, then trace one assigned practice from its rule text through the SDR to its referenced evidence and assessment result. Complete the individual-review fields before applying the same method to the rest of your assignments.
5. Review relevant ASF exceptions for Class A, or the applicable independent assessment information for B/C. Bring substantiated concerns and unresolved questions to the Conclave. After team disposition, check that the provider feedback and agency implications are correctly carried into the report.

## Recommended working method for a new reviewer

The following is proposed training guidance, not an additional FedRAMP requirement.

For each assigned practice, write a compact evidence chain: **applicable requirement → provider claim → concrete implementation → evidence location and period → verification/validation method and result → limitations → reviewer conclusion → team disposition**. Keep the provider's words and the reviewer's inference distinguishable.

Read the complete applicable practice and surrounding governing rules before examining a claimed implementation. Identify the subject, scope, frequency, reporting or access obligation, and any conditional applicability. Then test whether the package addresses those elements for the actual offering and boundary under review. A policy can establish intended behavior; a relevant operational result, configuration, test record, or assessment may be needed to demonstrate that behavior occurs.

When evidence is thin, ask a specific question that would change the judgment. For example: “The SDR describes a scheduled review but does not identify the covered resource population or latest result. Please identify the population and provide the latest result with the review period and exceptions.” This is more actionable than “provide more evidence.” The required evidence depth still depends on class and the governing rule.

For the Conclave, separate four questions: Is this a rule/application uncertainty requiring internal interpretation? Is information missing? Is there demonstrated implementation or validation weakness? Is there an agency-use limitation that needs clear communication? Do not let “Concern” silently become “noncompliant,” and do not let “OK” silently become “suitable for every agency use.” The workbook's independent provider, reviewer, next-step, and agency-impact fields support that separation.

## Implications for a JSON reviewer

A useful assistant should recreate the evidence chain and workbook distinctions, with an explicit selected rule version and class. It should show the source JSON pointer, linked artifact location, implementation status, rationale, frequency, method, result, and assessment statement together. Missing fields and unresolved references should remain distinct from substantive adverse findings.

Automated checks can identify absent practice IDs, duplicates, malformed statuses, broken internal references, inconsistent dates, mismatched class IDs, and divergence between claimed status and narrative. Human review must decide whether methods are appropriate, evidence is representative, the intended outcome is met, a SHOULD deviation is justified, or an issue warrants pre-cert action. A score or green schema check must not be displayed as a certification decision.

Retain source snapshots and reviewer notes separately. Keep dispositions editable and attributable to the team. Export observations keyed by class and practice ID into the existing workbook fields. Avoid relying on row number alone, because template changes and the observed duplicate make that fragile.
