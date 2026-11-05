# How to read the package scorecard

Use the [Review Companion](reviewer.html) to answer three questions: **What did I receive? How far can I follow each claim? What should I inspect next?** The counts describe the files you select. They do not predict certification or assign a percentage to security effectiveness.

Start with the current **Certification Package Overview (CPO)**, **Security Decision Record (SDR)**, **Ongoing Certification Report (OCR)** and the supporting artifacts you have. Select the class from the package. The practice counts come from two kinds of SDR entries: FedRAMP rules (FRRs) and Key Security Indicators (KSIs). If the folder includes historical copies, compare them deliberately or select just the current files before reporting counts.

## Try it on the fictional example

1. Choose **Class A** and **Load fictional teaching example**. Four JSON files open: an SDR, a CPO, an intentionally incomplete OCR, and a test record.
2. Check document structure. The SDR and CPO match their bundled schemas; the OCR excerpt lacks its reporting period. The test record is ordinary evidence JSON, so it is outside these three schema checks. Report this as **2 of 3 checked documents matched**, not “half the package passed.”
3. Look for the **AFC-CSO-ACK** row. Follow its validation pointer to the named receipt test. The selected test record reports an acknowledgment for **one external sender route**. It supports that bounded observation; it says nothing about internal senders or recovery routing. An additional filename cited by the assessor has no selected match.
4. Compare **MAS-CSO-IIR**. The provider describes an inventory but says it has not yet been tested. A populated field is not an observed test result. Ask for the applicable scope, method and result, or the documented basis for an alternative.
5. Open a practice, record your working disposition **and its basis**, then return to the scorecard. A disposition requesting clarification is review work; it does not count as evidence supporting the claim. Export review notes separately if you need to resume.

Use **Download scorecard (.txt)** to keep a snapshot of the counts, input files and practice-level traces. This report can contain package filenames and evidence references. Save it alongside the package. To continue editing your notes later, use **Export review notes** instead.

## What each count means

| Measure | Population | How to use it |
| --- | --- | --- |
| Files selected | The JSON documents and supporting files you chose | Use the controlling version of each document. Extract archives first. Other file types contribute filenames or paths; their contents are not inspected. A real or example OCR can be appropriate for an initial submission. |
| JSON structure | Recognized CPO, SDR and OCR documents with a supported schema | Find the first structural issue in each checked file. Unknown types and unsupported declarations are listed separately. A schema match does not prove the document has substantively addressed a rule. |
| Indicators found | Distinct KSI identifiers in each SDR versus the selected class roster | A: 7 named in the mandatory overlay. B: 41 compared, with 5 expressly optional indicators separate. C: 46 listed. Presence means an ID was found, even if the entry says the measure was not adopted. Revisions are compared separately. |
| Implementation, provider validation and independent assessment text | Submitted FRR and KSI practice objects | Measure each field separately. Common explicit absences, empty fields, bare status labels and citation-only fields do not count as explanatory text. A narrative may describe a failure, a plan, or a justified alternative. Read it. |
| Traceable practice rows | All submitted FRR and KSI practice objects | The chain count requires a recognizable ID, implementation text, validation text, and a matched local target or embedded evidence **in the same row**. The target can address just one part of the row. Other citations may remain unresolved. |
| Reviewer work recorded | Practice rows in this selection and class | A source-linked working disposition with a written basis records human review progress. Read that basis and distinguish support, clarification and escalation. Use the team process for final disposition. |

There is no overall grade. A row can match the schema, name the right indicator, contain all three narratives and still cite a test of the wrong population. Conversely, a demonstration to an assessor or evidence in a controlled repository can be legitimate even when it cannot be opened from the selected files. **“No local match” is a follow-up, not a finding.**

## Follow a reference

Start with the **file, practice ID and JSON pointer**. A filename in a narrative is a citation. A unique selected file is a candidate to inspect; two files with the same cited basename leave a choice to resolve. Select a folder when possible to preserve relative paths. Embedded KSI evidence text can be inspected at its pointer. External URLs are not fetched. The tool cannot discover a citation written in an unsupported notation or prove that it found every relevant file.

An evidence index can provide an intermediate step. For example, a narrative may cite `EVD-TEST-01`. If a selected JSON record explicitly pairs that identifier in `evidenceId` or `evidenceID` with `evidenceLocation` or `evidenceText`, the tool can show the cited ID, the index file and pointer, and the final target. Duplicate definitions and competing targets stay unresolved. This is a supported provider convention, not a required FedRAMP manifest format.

The SDR and OCR can also name their CPO using `certificationPackageOverviewUri`. The scorecard compares these declared targets and looks for a selected CPO with the same URL filename. A shared URL helps reconcile the documents. A filename match cannot establish the identity or version of the document at that URL; check the offering, scope and revision yourself.

For each promising chain, ask: **What was supposed to happen, what was actually observed, for which resources and period, and with what exceptions?** In the review sheet, record the evidence locator in I, method/count and appropriateness in J/K, rule intent and information sufficiency separately in L/M, then disposition and rationale in N/O. Team discussion and next steps belong in the team's fields. No count fills in those judgments for you.

## Rule and version basis

- [FRC-CSO-PKG and FRC-CSO-JSN](https://www.fedramp.gov/2026/providers/20x/rules/fedramp-certification/) distinguish package information from machine-readable format requirements. The scorecard does not infer the full applicable package inventory from filenames.
- [SDR-CSO-FRR and SDR-CSX-KSI](https://www.fedramp.gov/2026/providers/20x/rules/security-decision-record/) explain why reviewers trace the practice, its measures, verification, validation, independent work where applicable, and supporting material. Check the applicable class and path before treating an absence as a concern.
- [IVV-CSO-SEI, IVV-CSO-SEE, IVV-IAS-VIM and IVV-IAS-VEF](https://www.fedramp.gov/2026/reference/20x/c/independent-verification-and-validation/) distinguish evidence of implementation from evidence of effectiveness. Class A uses its [alternative framework and overlay](https://www.fedramp.gov/2026/reference/20x/a/fedramp-certification/); separate FedRAMP package IV&V is optional. For Classes B/C, check independent work separately. Counting test descriptions cannot establish the number or adequacy of automated methods.
- The [Class B](https://www.fedramp.gov/2026/reference/20x/b/key-security-indicators/) and [Class C](https://www.fedramp.gov/2026/reference/20x/c/key-security-indicators/) KSI rosters and the Class A overlay were checked November 4, 2026. The [pinned reference edition](https://github.com/FedRAMP/2026-markdown/tree/888be032e1290ec6bc7a01b7de4acc4da885575b/reference/20x) identifies the comparison set. There is no denominator for **all applicable FRRs** in this tool.
- Offline structure checks use snapshots from the [official schema catalog](https://www.fedramp.gov/schemas/) checked November 4, 2026: CPO 0.2.0, SDR 1.1.1, OCR 0.2.1 and Common Definitions 0.4.2. An undeclared type is inferred from document fields. Confirm that the edition matches your review; a disagreement with this snapshot may be a version question.
