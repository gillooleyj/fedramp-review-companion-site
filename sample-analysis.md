# Fictional review exercises

Prepared November 4, 2026. All scenarios below are newly constructed teaching examples. Names, numbers, dates, file labels and results are invented. These examples do not describe or evaluate a particular provider package and are not official templates or complete certification submissions.

The purpose is to practice a repeatable reasoning chain: **applicable requirement → claim → evidence → method → result → justified conclusion → targeted follow-up**. Check the published class-specific rule before treating any question as a requirement.

## Exercise 1 — Class A: the claim is more specific than the audit result

**Scenario.** A fictional service states that every privileged user must use a phishing-resistant authentication method. Its external audit report describes tests of multifactor authentication for a sample of administrative applications. The tested control and result do not identify the factor type. The SDR names a separate policy export but does not identify its date or location.

**What is established.** The audit result supports the particular multifactor control, population and period the auditor tested. It may be relevant evidence, but the excerpt alone does not establish the more specific factor claim.

**What remains unknown.** Which users and systems are covered? What authentication methods are permitted, including recovery and exception paths? Where is the configuration evidence that supports the more specific assertion?

**Review question.** “Please identify the dated configuration or test evidence supporting the phishing-resistant authentication assertion, including its population and exceptions. Explain which part of the external audit result substantiates that assertion and which part is supported separately.”

**Possible working note.** “External audit evidence supports a related control. The more specific claim remains unsubstantiated from the cited passage. Request clarification; do not infer that the measure is absent.”

**Lesson.** Match the precision of the conclusion to the precision of the evidence. Do not import the full Class C assessment model into Class A simply because more evidence would be convenient. Read the applicable [Class A certification rules](https://www.fedramp.gov/2026/reference/20x/a/fedramp-certification/) and required overlay.

## Exercise 2 — Class B: a cited file is not yet supplied evidence

**Scenario.** An SDR assessment paragraph says: “The assessor reviewed `control-test-session-04.pdf` and observed the restricted operation being denied.” The file is named in `frrAssessment`, but the reviewer’s available files contain only the SDR and an overview. A dedicated evidence listing is empty.

**What is established.** The assessment text makes an attributable claim about an examination. The reviewer can locate that claim in the SDR.

**What remains unknown.** Is the cited test record available through another repository? What did it cover? Was the observation for the current offering and version? Is the empty listing intentional because evidence is referenced in prose?

**Review question.** “Please provide the accessible location of the cited test record, its date and evaluated scope, and identify the result supporting this assessment statement. If it is already included elsewhere, give the exact document and section.”

**Possible working note.** “Artifact reference located in assessment narrative; underlying artifact not yet located in the reviewer’s available materials. Evidence availability and sufficiency remain separate questions.”

**Lesson.** Use four separate states: reference mentioned, artifact supplied, artifact inspected, conclusion supported. The reference index can help with the first; it cannot establish the other three from a name alone. Apply the [Class B IV&V rules](https://www.fedramp.gov/2026/reference/20x/b/independent-verification-and-validation/) to determine the relevant obligations.

## Exercise 3 — Class C: two statuses refer to different scopes

**Scenario.** The provider’s current record says “Partially Implemented” because a restriction covers central administrators but not delegated support roles. An assessor’s earlier paragraph says “Pass” for a test of the central administrator group. The package does not explain whether a later assessment covers the remaining roles.

**What is established.** The provider discloses incomplete implementation. The assessor states a favorable conclusion for a bounded earlier test. Neither statement should be silently rewritten to match the other.

**What remains unknown.** Did the earlier test address the complete applicable population? Does its conclusion apply to the present configuration? Is a new assessment needed, or is the apparent disagreement resolved by scope and dates?

**Review question.** “Please reconcile the current partial status and the earlier favorable assessment. Identify the population and dates covered by each, the remaining roles, and the assessor’s current conclusion for the applicable scope.”

**Possible working note.** “Provider status and assessor result preserved separately. Scope and chronology explain a possible difference, but the package has not yet reconciled the conclusion for the current population.”

**Lesson.** Status reconciliation is a reasoning task, not a rule that one favorable label wins. Preserve assessor meaning as required by the applicable [Class C IV&V rules](https://www.fedramp.gov/2026/reference/20x/c/independent-verification-and-validation/).

## Exercise 4 — Collection succeeded, but the security result did not

**Scenario.** A fictional permissions check collected 720 resource records without read errors. Its output identifies 41 adverse observations and 23 records whose ownership or scope is unresolved. The total expected resource population has not been reconciled. The job dashboard displays “Completed.”

**What is established.** The collection job completed and returned data. The check also produced adverse results and unresolved classifications.

**What remains unknown.** Is the evaluated population complete? Are the predicates appropriate for the intended security outcome? What is the treatment of unresolved records? Does “Completed” describe the job, the control result, or both?

**Review question.** “Please distinguish job completion from the security result, reconcile the evaluated population to the expected in-scope population, and explain the adverse observations and unresolved records. Identify what the check cannot detect.”

**Possible working note.** “No collection failures were reported, but the security result includes adverse observations and unknown coverage. No offering-wide compliance percentage inferred.”

**Lesson.** Do not convert collection success into security success. A denominator must be defensible before a percentage can describe coverage. A clean run can still reveal an ineffective measure. The [KSI guidance](https://www.fedramp.gov/2026/providers/20x/key-security-indicators/) provides context for connecting measurements to outcomes.

## Exercise 5 — A reporting example is not operating history

**Scenario.** A fictional provider supplies an incident-report example with populated detection and resolution timestamps to demonstrate the expected format. The narrative explicitly says no actual incident occurred. An OCR separately covers April 1–June 30 and mentions a July 12 submission event.

**What is established.** The example demonstrates how a report could be populated. The OCR defines an operating period and mentions a later administrative event.

**What remains unknown.** Is the later event clearly labeled as preparation or submission rather than in-period operation? What supports the OCR’s statement about actual incidents? Is an example allowed for the artifact and review stage in question?

**Review question.** “Confirm that the incident report is a format example and identify the operational basis for the OCR’s incident statement. Label the July submission separately from events within the April–June reporting period.”

**Possible working note.** “Example timestamps excluded from incident counts and response-time calculations. Post-period submission event needs clear labeling; no actual incident or missed deadline inferred.”

**Lesson.** Classify the artifact before extracting metrics. A valid-looking date is not proof of a real event. Use the applicable [certification package rule](https://www.fedramp.gov/2026/reference/20x/c/fedramp-certification/) and [ongoing reporting rules](https://www.fedramp.gov/2026/reference/20x/c/collaborative-continuous-monitoring/) to distinguish acceptable examples from required operating records.

## Exercise 6 — Class A: a clearly explained optional decision

**Scenario.** A fictional Class A applicant identifies a practice that the applicable published Class A rule makes optional. It records that the practice has not been adopted, gives the business and security rationale, identifies the accountable function, and states that it will reconsider the decision before pursuing a higher class. The status remains “Not Implemented.”

**What makes the explanation useful.** The reviewer can distinguish deliberate non-adoption from an unexplained omission. The decision’s scope and rationale can be checked, and a future plan is not presented as a completed implementation.

**Review question.** “Confirm that the governing rule is optional for this class, path and stage, and that no separate applicable obligation makes the underlying activity necessary. Is the stated decision consistent elsewhere in the package?”

**Possible working note.** “Optional decision and rationale are explicit. Evaluated against the applicable class; no automatic adverse finding inferred solely from the implementation-status label.”

**Lesson.** A readable package explains what it does and what it does not do. The tool should retain implementation status, rule force, decision rationale and reviewer disposition separately.

## Exercise 7 — An audit limitation preserved accurately

**Scenario.** An external auditor examined a response procedure and its tracking system. No event requiring that procedure occurred during the examination period, so the report supports a conclusion about design but does not establish operating effectiveness for actual events. A separate exercise tested a limited simulated event. The SDR identifies both sources and preserves their different scopes.

**What makes the explanation useful.** The reviewer can identify which conclusion is supported by document inspection, which is supported by a simulation, and which remains untested in actual operation. The provider does not rewrite non-occurrence as an observed successful response.

**Review question.** “What does each source establish, and does the package’s overall conclusion stay within those limits? What other evidence or reporting is relevant under the applicable rule?”

**Possible working note.** “Design examination and simulated test are distinguishable. No operating-effectiveness conclusion for actual events inferred from the absence of events.”

**Lesson.** Preserve the auditor’s qualifications when summarizing evidence. Useful disclosure can coexist with an unresolved evidence question.

## How to turn an exercise into a review note

Write five short statements:

1. **Observed fact:** what the package actually says, with its source location.
2. **Significance:** which applicable expectation or decision the observation affects.
3. **Uncertainty:** what the available information does not establish.
4. **Request:** the specific clarification, evidence location or result needed.
5. **Closure condition:** what would allow the team to reconsider the concern.

Keep provider statements, assessor conclusions and reviewer judgments distinct. The exercise is complete when another reviewer can reconstruct why the question matters and what would resolve it—not merely when every field contains text.
