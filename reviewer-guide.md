# How to review a FedRAMP 20x package

A practical learning guide for a new FedRAMP program reviewer · November 4, 2026

**The task is to establish a defensible connection between the applicable requirement, the provider's security measures, evidence that those measures operate, and a conclusion an agency can understand.** Reading the JSON is the beginning. The review asks whether the information supports the claims, explains remaining uncertainty, and supports the team's certification recommendation.

This guide combines the internal SOP and workbook, official CR26 material, and newly constructed fictional teaching scenarios. It is training guidance, not a new FedRAMP policy or a certification decision. The original files have not been changed.

## Start here

1. Read “The reasoning behind the review” and “One practice, end to end” below.
2. Open the [local Review Companion](reviewer.html) and load the fictional teaching example. Follow KSI-IAM-APM through implementation, validation and assessment.
3. Read the [fictional review exercises](sample-analysis.html). Practice distinguishing an implementation claim, its supporting evidence, and a reviewer conclusion.
4. Use the [SOP and workbook map](internal-workflow-analysis.html) alongside your actual review sheet.
5. Read the [official-source research](official-research.html) before relying on a rule or class-specific expectation. Confirm the current version for the review you are assigned.

## The reasoning behind the review

The provider describes its security decisions and implementation. Verification establishes whether the described measures exist. Validation establishes whether they produce the intended security outcome. Independent assessment evaluates those measures and their effectiveness. The FedRAMP review then examines the package and assessment information, resolves questions, and develops a program decision record. These roles overlap in subject matter, but they are not interchangeable.

For example, a firewall policy describes the intended protection. A deployed configuration can substantiate that the protection is installed. A relevant traffic test can substantiate that it blocks the intended traffic. The assessor must explain what was examined and what the result supports. A reviewer still needs to know whether that test covered the actual service, relevant interfaces, exceptions and time period. See the official [IV&V rules](https://www.fedramp.gov/2026/reference/20x/c/independent-verification-and-validation/), particularly IVV-CSO-SEI, IVV-CSO-SEE, IVV-IAS-VIM and IVV-IAS-VEF.

The central question is therefore: **“What conclusion does this evidence justify, for this scope and time period?”** It is not enough that the package uses the right security terminology or contains an assessor's favorable label.

A program reviewer should understand and challenge the assessment basis without silently assuming the independent assessor's responsibilities or inventing an extra technical standard. When an uncertainty requires an authoritative interpretation or decision, use the team and escalation process.

## What each artifact is for

| Artifact | Question it should help answer | How to review it |
| --- | --- | --- |
| Certification Package Overview (CPO) | What offering is being reviewed, what is in scope, and what does the overall assessment say? | Establish identity, services, dependencies, data-sharing locations, assessor summary and outstanding issues. Reconcile those statements with the SDR. |
| Security Decision Record (SDR) | How is each applicable practice addressed and supported? | Follow implementation → validation → assessment → evidence. Treat status fields as claims until examined. |
| External framework report, especially Class A | What did an independent auditor actually cover and conclude? | Read scope, period, exceptions, complementary controls and mapped tests. A general opinion does not substantiate every more specific claim. |
| Ongoing Certification Report (OCR) | What changed or happened during the reporting period? | Reconcile operating changes, incidents, vulnerabilities and customer recommendations with the rest of the package. Separate actual reports from examples. |
| Secure Configuration Guide (SCG) | What choices and responsibilities does the customer have? | Check that security effects, defaults and customer actions are understandable and consistent with claimed protections. |
| Supporting evidence | What was observed, by whom, when and over what population? | Trace exact files or records. A link in the SDR is a reference, not proof that its target was reviewed or supports the claim. |

Source basis: official [package materials](https://www.fedramp.gov/2026/providers/20x/package/), [SDR rules](https://www.fedramp.gov/2026/providers/20x/rules/security-decision-record/), and [continuous monitoring rules](https://www.fedramp.gov/2026/providers/20x/rules/collaborative-continuous-monitoring/). The questions and review techniques in this table are a training synthesis.

## Class A, B and C review lenses

**Class A:** begin with an approved alternative security framework and the mandatory FedRAMP overlay. Review what the external assessment actually covers, its currency, exceptions, and the mapping to the offering. Then examine the required FedRAMP-specific material and KSIs. Do not require Class C's full independent assessment or automation expectations just because they would provide stronger assurance. A FedRAMP recognized assessor's optional Class A work is distinct from the external framework audit. The fact that the audit firm also performs FedRAMP work does not change the role in which it issued the report.

**Class B:** use the published Class B profile rather than assuming either Class A or Class C expectations. Review the applicable rules, KSIs, provider validation and independent assessment under Class B’s own requirements. Pay particular attention to the force and class-specific wording of automation, assessment and reporting provisions. See the [Class B reference](https://www.fedramp.gov/2026/reference/20x/b/).

**Class C:** examine the applicable rules and KSIs, provider verification/validation, independent assessment, ongoing evidence and reporting. Test whether methods and results support the asserted outcomes over the applicable population. An automation count does not establish method quality, and collection success does not establish security success.

The [published-rule A–C comparison](class-lenses.html) summarizes the key differences. The tool’s A–C lenses show a focused set of published requirements, their identifiers and force, source links, and suggested review questions. They are a learning aid, not an exhaustive applicability engine. A lens does not establish that every rule in a package applies or that every applicable rule is present.

The live Class A mandatory overlay was updated October 31, 2026 to explicitly include SDR-CSX-KSI. The supplied September Markdown snapshot predates that change. Confirm applicability in the current [certification rules](https://www.fedramp.gov/2026/providers/20x/rules/fedramp-certification/) and record the version used. The [official research](official-research.html) explains these differences and recent changes in more detail.

## One practice, end to end

This is a suggested review routine. It supplies the analytical training that the SOP explicitly leaves out.

### 1. Fix applicability before judging the implementation

Record the offering, class, certification type and path, review stage, rules version, artifact version and relevant dates. Read the whole applicable rule, including notes and cross-references. Identify its actor, required outcome, covered population, timing and conditions. Preserve the difference between MUST, SHOULD and MAY; do not promote a preferred technique into a requirement. Under the [CR26 definition of SHOULD](https://www.fedramp.gov/2026/definitions/#should), justified departures are allowed, but the decision must still be addressed in security documentation; SHOULD does not mean the reviewer can ignore the rule.

A missing row may be an actual coverage gap, a version mismatch or an inapplicable rule. A blank rule-force cell on a KSI row does not establish that the KSI is optional. Resolve the governing obligation first.

**Workbook:** A–E and the selected class in Summary. Record version issues in your notes.

### 2. Restate the provider's claim in plain language

Describe the actual mechanism, owner, environment and population. Identify dependencies, exceptions and customer actions. Ask whether the explanation would let another technically competent reviewer locate what is being claimed.

“Access is secure” is not a specific implementation. “Production administrators authenticate through policy X; recovery path Y is restricted; contractor exception Z remains” is a claim with a testable scope.

**Workbook:** F preserves provider status; H addresses status where implementation is not complete. Do not overwrite provider status with your judgment.

### 3. Trace implementation evidence

Locate the artifact. Check its identity, source, date, scope and relevance to the claimed measure. Read the actual relevant material. An evidence index establishes where something is supposed to be, not what it proves.

A policy supports intent; configuration supports a deployed setting; an operational observation may support behavior. These are useful for different questions. Neither “screenshot” nor “automated output” is a universal sufficiency label. Ask whether the evidence supports the specific proposition you are reviewing.

**Workbook:** I, with precise references and limits in O where needed.

### 4. Evaluate the validation method and observed result

Write down the property tested, data source, expected population, evaluated population, frequency, actual result and exceptions. Ask whether a failure would be visible. Distinguish a test plan from an executed result, a result from its interpretation, and missing data from an observed successful condition.

Useful questions include: Does the check inspect configuration or exercise the outcome? Are the sources independent enough to catch the relevant failure? What happens when collection fails? Are unclassified resources excluded from a favorable count? How is the sample justified? Has a later change invalidated the earlier observation?

Do not invent a numerical sampling threshold. Sampling and method expectations must come from the applicable rules and assessment context.

**Workbook:** J records relevant method counts; K judges appropriateness. A count is not the appropriateness judgment.

### 5. Read the independent assessment as an argument

Identify who assessed what, when, by which method, using what evidence, and with what exceptions. Determine whether the conclusion matches the scope and result actually described. Compare it with the provider's current status and subsequent amendments.

If the provider says “Partially Implemented” while preserved assessor text says “Pass,” retain both. Ask whether the assessor evaluated a subset, used an earlier version, applied a different criterion or has since reassessed. Do not “repair” that conflict by editing the assessor conclusion yourself.

**Workbook:** K and L, with the basis in O. Keep current observations distinct from historical conclusions.

### 6. Make two judgments, not one

First ask whether the intended outcome is met. Then ask whether the package supplies enough information for an agency to understand its risk. A measure may appear effective while its scope is poorly explained. A package may also clearly disclose a real limitation. Those are different situations and should remain visible.

**Workbook:** L is Rule Intent Met; M is Sufficient Info? N records the reviewer's OK/Concern result. O must explain a Concern under the supplied sheet's instructions. U carries agency implications.

### 7. Turn uncertainty into an answerable request

Use this structure: **observed fact → requirement or security significance → unresolved question → requested evidence or clarification → closure condition.**

Fictional example: “The SDR describes a partially deployed access restriction, while the assessor narrative concludes Pass for an earlier test of one administrative group. Please identify the population and dates covered by each statement, provide the cited result, and reconcile the current conclusion for the applicable scope. This item can be reconsidered when the scope and conclusion are consistent with attributable evidence.”

That example is a review question, not a finding of violation. Its request should be tailored to the applicable class and rule.

### 8. Bring the reasoning to the team

The supplied SOP routes concerns through the Conclave, with escalation through the Vanguard Lead and recommendation/approval handoffs. It does not provide a complete rule for deciding pre-certification versus post-certification action. Present the evidence, uncertainty, rule force and agency consequence; let the authorized team resolve the disposition.

**Workbook:** Q–U hold next steps, discussion/escalation, provider feedback and agency impact. Your initial Concern is not itself a final compliance decision.

## What a reviewer-friendly package looks like

The following are reviewability indicators, not additional FedRAMP requirements or an automatic quality score. They describe how a package can make the reviewer’s reasoning easier to reconstruct.

| Helpful practice | What it enables the reviewer to do |
| --- | --- |
| Explicit adoption decisions | Distinguish an optional practice deliberately not adopted from an applicable obligation left unaddressed. |
| Specific descriptions of mechanisms and scope | Identify what is deployed, who or what it covers, and what is excluded. |
| Precise audit citations | Find the document, control identifier, printed page, tested condition, result and audit period without guessing. |
| Visible limitations | Preserve partial implementation, non-occurrence, untested populations and unresolved questions instead of concealing them behind a favorable summary. |
| Named follow-up and timing | Understand what remains, its owner or accountable function, and the proposed completion or review date. |
| Consistent source versions | Reconcile readable and machine-readable documents and distinguish identical copies from amendments. |

Clear disclosure improves reviewability. It does not resolve a substantive concern by itself. A reviewer must still test the cited evidence against the specific claim and use the authorized team process for any disposition.

A statement such as “None” in an assessment field must be read in context: it is an explicit statement about assessment, not proof that an assessment occurred merely because the field is populated. Likewise, an auditor’s non-occurrence result can explain why operational effectiveness was not tested; it should not be converted into either a tested pass or a demonstrated failure.

The [fictional review exercises](sample-analysis.html) include positive examples of explaining an optional decision and preserving the limits of an audit result.

## Evidence quality: six questions to keep beside you

| Dimension | Practical question |
| --- | --- |
| Relevance | Does this artifact test the actual requirement or only a related practice? |
| Scope | Which resources, accounts, tenants, services and exceptions are included or excluded? |
| Time | What is the observation period, and does the evidence describe the version under review? |
| Provenance | Who produced it, from which source, and can the result be traced without changing its meaning? |
| Method | Would the check detect the failure it claims to address? What remains invisible? |
| Outcome | What happened, what failed or is unknown, and what conclusion is justified? |

This rubric is proposed training guidance. It is not an extra mandated scoring system.

## Fictional review exercises

The [teaching scenarios](sample-analysis.html) are newly constructed examples. They do not identify, quote, evaluate or describe any particular submitted provider package. Any numbers, dates, artifact names and results are invented for the exercise.

- **Class A claim versus audit scope:** a specific authentication claim is supported by a report describing a broader, less specific control. Determine what the report establishes and what remains to be substantiated.
- **Class B reference versus evidence:** an assessor paragraph names a test artifact, but that artifact is not in the files available to the reviewer. Distinguish “cited” from “supplied” and request a precise location.
- **Class C status reconciliation:** a current partial implementation statement and an earlier favorable assessment refer to different populations. Preserve both while resolving scope and chronology.
- **Measurement quality:** a successful collection job still reports adverse security results and unclassified resources. Keep collection success, security outcome and coverage separate.
- **Examples versus operating records:** a fictional incident-report example contains populated dates; those values must not become actual incident statistics.

These exercises teach reasoning. They do not establish extra evidence requirements or class-specific thresholds beyond the published rules.

## What the internal materials do—and do not—teach

The SOP is marked Draft v0.1, with effective date and process owner TBD. Its Phase 2 introduction explicitly excludes instruction in package analysis and Rules/KSI interpretation. Its strength is workflow: intake, assignment, review, discussion, resolution, recommendation and certification handoffs. It should be paired with analytical training.

The workbook already contains a useful reasoning sequence in columns I–M: evidence, method count, method appropriateness, intent and information sufficiency. It also contains separate provider, reviewer and team statuses. Preserve those distinctions.

Treat the supplied Excel export carefully: it has duplicate Class C KSI-SVC-VRI rows 421–422, stored cell errors, and cached generated report text claiming successful tests despite an unfilled review. These are observations about the local export, not a judgment about the live Google Sheets version. Do not rely on its counts or generated prose without checking the actual review inputs. The [detailed workbook analysis](internal-workflow-analysis.html) identifies exact cells and other limitations. No workbook formulas, scripts or live integrations were recalculated or repaired.

## Using the local Review Companion

Open [reviewer.html](reviewer.html) in a browser. It works without a server or internet connection. Use the fictional example first, then select one or more JSON files. Confirm which document version controls the review before drawing conclusions from historical copies or amendments.

### Read the JSON as a document

The readable view presents headings, labeled fields, paragraphs, lists and nested records instead of requiring you to read JSON punctuation. The Raw JSON view preserves the source data for comparison. **Download readable document** saves a standalone HTML rendering of the whole selected file, which can be opened or printed from a browser. It contains source content, not your review notes. JSON pointers identify where the displayed text originates. Readable formatting changes presentation, not the source content or its evidentiary meaning.

Select Class A, B or C to see focused published-rule expectations and suggested review questions. Class selection does not automatically determine applicability. The prototype does not validate official JSON Schemas, inspect PDFs, follow trust-center links, evaluate the full package, authenticate assessor conclusions, or score compliance.

### Find evidence references

The [SDR evidence-field reference](evidence-fields.html) explains the published schema. There is no standard `frrEvidence` field in version 1.1.1. An SDR can mention evidence in assessment narrative, implementation or validation explanations, dedicated evidence entries, remarks, or other supporting structures. The schema and provider’s organization determine the precise locations. For example, `frrAssessment` is assessment text and can name supporting artifacts; it is not necessarily a complete evidence inventory. A `ksiEvidence` entry can provide a more structured description and location.

The reference index helps locate URLs and artifact names mentioned in the loaded JSON and identifies the field where each mention occurs. It does not establish that the referenced material was supplied, opened, authenticated or evaluated. A filename in assessment prose is a citation. An empty dedicated evidence array does not prove that no evidence exists elsewhere. Confirm the actual artifact and its relevance before using it in a conclusion.

### Save and reopen your own notes

**Export review notes** saves a separate JSON file containing your comments and working dispositions, linked to source identifiers. **Load saved review notes** reopens a notes file previously exported by this tool. It is optional: leave it alone when starting a new review. It is not the place to open an SDR, CPO, OCR or other provider package document.

To continue a review later, reopen the same package JSON, choose the same class lens, then load the saved notes file. Notes are associated with filename, content hash where available, class lens and JSON pointer. An amended package does not silently inherit notes from an older version. If hashing is unavailable, matching lasts only for the loaded file in that tab and notes cannot automatically reconnect after a later reload.

Notes remain in the tab until exported; closing the tab without exporting loses those working notes. Loading saved notes supplements current notes and replaces an existing note for the same source entry. Exported files include your comments and source identifiers and should be handled with the package. Nothing is sent to an external service by this prototype.

## A fuller reviewer: what to build next

The next version should be based on an approved review model before adding automated judgments:

1. **Versioned applicability:** import a pinned official rules release and schema set; filter by actor, class, type, path, stage and effective dates, retaining rule force and conditional exceptions.
2. **Package provenance:** resolve current files from manifests; preserve hashes; classify operational, example, historical and analytical artifacts. Let the reviewer confirm ambiguous selections.
3. **Evidence navigation:** distinguish reference named, artifact supplied, artifact opened, and evidence evaluated. Support local PDF page citations and cross-document searches. Keep printed page numbers separate from PDF page indexes. Resolve a document through its title, trust-center resource identifier and confirmed local mapping when the URL does not expose its filename; label proposed matches for reviewer confirmation.
4. **Separate validation layers:** syntax/schema checks; applicable-ID coverage; cross-document consistency; human evidence sufficiency; authorized team disposition. Never turn one green layer into all five.
5. **Issue ledger:** retain rule/version, artifact/pointer, observation, meaning, question, owner, response, conclusion and decision date. Export to workbook fields using class plus requirement ID, not row number alone.
6. **Human-reviewed assistance:** suggestions must cite source passages, distinguish provider/assessor/reviewer voices, preserve uncertainty and permit correction. A generated answer must not overwrite evidence or become a certification verdict.

This ordering makes the tool useful as a teaching and review aid before attempting broader automation.

## Source and version boundaries

- Internal sources: supplied SOP and review-sheet v1.08; see the [workflow analysis](internal-workflow-analysis.html) for exact sections and cells.
- Local rule snapshot: generated September 14, 2026; rules SHA `58487bda77d76d9ce334304ec2e779ece7cc7d54`. It is not a verified November rules release.
- Teaching scenarios: newly constructed fictional illustrations. They are not official templates, complete packages, or evidence about an actual provider.
- Live official CR26 guidance and official blog context were consulted November 4, 2026. See [official research](official-research.html) for precise sources, updates and verification limits. Blogs explain intent and rollout; the applicable current rules govern requirements.
- No exhaustive current-rules JSON comparison, official-schema validation of every loaded package, remote evidence-access test or live-system assessment was performed for this guide.
