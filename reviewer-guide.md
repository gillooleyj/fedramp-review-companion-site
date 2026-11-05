# How to review a FedRAMP 20x package

A practical learning guide for a new FedRAMP program reviewer · November 4, 2026

**The task is to establish a defensible connection between the applicable requirement, the provider's security measures, evidence that those measures operate, and a conclusion an agency can understand.** Reading the JSON is the beginning. The review asks whether the information supports the claims, explains remaining uncertainty, and supports the team's certification recommendation.

This guide combines the internal SOP and workbook, official CR26 material, and newly constructed fictional teaching scenarios. It is training guidance, not a new FedRAMP policy or a certification decision. The original files have not been changed.

## Start here

For a first review, try the fictional example with **Class C** selected. Open **AFC-CSO-ACK**, read **Items to reconcile**, and follow the receipt test. It shows one external sender received an acknowledgment. The assessment says “Pass,” while the provider reports partial implementation and the test omits other routes. Your first task is to decide what that one test supports and record the remaining question in the sheet. [Open the Review Companion](reviewer.html)

For the step-by-step route from that observation to workbook row 235, see **Walk through a package in the Review Companion** below. The [scorecard walkthrough](scorecard-guide.html) follows the same fictional artifacts. Use the [SOP and workbook map](internal-workflow-analysis.html) for team roles and handoffs, and the [official sources](official-research.html) to check the rule edition for your assignment.

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

## Walk through a package in the Review Companion

The Companion starts with the evidence you will use to make a row entry. You can revisit package scope, the class reference or a source document while working on a practice. [Open the Review Companion](reviewer.html)

### 1. Open the current files and your review sheet

Start from the intake and kickoff decisions. Confirm that you have access to the referenced material, the correct offering, the review class, the assessment period, the controlling SDR version and your assigned practices. If you are also handling intake, use the SOP’s completeness check before starting individual review. Extract archives first. Select the package folder to keep relative file paths, or select the current JSON documents and supporting artifacts together. Check whether another SDR is a superseded version before using its claims. Attach the team's v1.08 Excel workbook under **Team review sheet (.xlsx)**. You can draft entries before attaching it. Keep your original workbook with the package.

A populated workbook must match the class you are reviewing. The blank starter opens with Class A selected in its Summary tab. For a new Class C review, confirm the class change on the copy when prompted. For a practice run, select Class C and load the fictional teaching example.

### 2. Take one practice from question to workbook entry

1. **Items to reconcile.** Read the suggested question or select your assigned practice. Check the class rule and compare the provider’s implementation, validation and independent assessment.
2. **Evidence to inspect.** Open the cited record. Identify the population, period, method, result and exceptions. Return to the same practice.
3. **Enter your review sheet findings.** Confirm the class, practice ID and row. Record what the evidence supports and what is still needed.

For example, open **AFC-CSO-ACK** in the fictional Class C exercise. The assessment reports a pass, while the provider describes partial implementation. The receipt test shows a response to one external sender, with internal sender routes and recovery untested. Under **Enter your review sheet findings**, confirm the destination is **Review Sheet, Class C, AFC-CSO-ACK**. Expand **Record the provider claim and evidence · F–K** for provider and evidence fields, then **Judge intent and information sufficiency · L–O** for your conclusions. In the unmodified v1.08 starter it is row **235**. The table shows one reviewer’s entries for this teaching case.

| Workbook cell | Example entry | Why it belongs there |
| --- | --- | --- |
| F235 · Provider status | Partially Implemented | Preserve what the provider reported. |
| I235 · Implementation evidence | Provided | You inspected the submitted test record. Put its location and limits in O. |
| L235 · Rule intent met | Partial | The test demonstrated receipt on the observed route. |
| M235 · Sufficient information | Partial | The tester identified the other paths, but supplied no results for them. |
| N235 · Reviewer status | Concern | The discrepancy needs discussion or more evidence. |
| O235 · Internal notes | Receipt test, Nov. 1, one external sender. The assessed pass covers that route. Provide results for internal senders and recovery, or explain why either falls outside this service. | A second reviewer can locate the observation, see its limit and understand what would close the question. |

The practice counts as a recorded decision when you select **OK, nothing additional** in N, even if O is blank, or **Concern** in N and supply a reason in O. Earlier standalone Companion notes count when a working disposition and written basis are both present.

Work through the remaining fields for your assignment. G is the assignee. H records progress or rationale when implementation is incomplete. J counts distinct automated methods, and K records whether the methods are appropriate. A successful test can still leave automation or coverage unknown. P records a specific strength you would share with the provider. Q–U belong to the later team discussion, agreed actions and agency implications. Leave those decisions for the appropriate participants.

When identifiers repeat, verify the source version and destination. For example, Class C has two **KSI-SVC-VRI** lines at rows 421 and 422 in the starter. Resolve the intended row with the team before writing to either. If a submitted practice has no matching row, keep its source-linked review note and reconcile the workbook coverage separately. Also review workbook IDs for which the selected SDR has no entry. Record how the team handles each gap.

Use the queue to move to the next practice and return to unfinished ones. Field-level references may appear in implementation, validation, assessment prose such as `frrAssessment`, remarks or a dedicated `ksiEvidence` entry. Open matched JSON or an embedded excerpt in the reader. You can preview supported text files locally, or save and open a PDF or Office file on your device. Cite the page, sheet or test record in O. External links require separate inspection. [SDR evidence-field reference](evidence-fields.html)

### 3. Check the package as a whole

Open **Compare SDR identifiers with the team review sheet** to see both directions of the match. Check the scorecard for file and schema issues, class KSI coverage and references that need attention. Reconcile the offering, versions and assessment scope against the CPO, SDR and ongoing report. For Class A, inspect the alternative framework assessment and applicable overlay. For Classes B and C, confirm what the independent assessor examined and when. Bring unresolved access and scope questions to the provider and assessor walkthrough. Complete the MRR work assigned at kickoff using the scope agreed with the lead. Use the package-level checks to document source, outcome and outstanding work. Complete the team's other assigned intake, summary and reporting fields in its workbook. [How to read the scorecard](scorecard-guide.html)

### 4. Prepare the team determination

Review the outstanding questions, unfinished practices and any ambiguous workbook rows. Write your working recommendation, its basis, the conditions for closure and any implications for agencies. A partial review can be handed off with the outstanding work visible. The Conclave and approving officials make the relevant team and program decisions.

Keep the deliverables that fit your next task. **Download updated review sheet (.xlsx)** saves a copy of the attached workbook with your staged F–P edits. Review the listed cell count before downloading. Resolve any competing edits from different SDR versions or existing workbook values first. Open it in Excel so the workbook can recalculate. Verify the selected class and affected rows before using the summary or carrying entries into the team’s shared process. If the team uses a live Google Sheet, transfer the verified entries using the team’s normal process. The team handoff text gives the next reviewer your recommendation and open questions. The scorecard text records counts and references.

### Save your work and resume

Use **Export review notes** before closing the tab. Keep the JSON with the package, workbook and any downloaded copy. To resume, reopen the same class, package files and folder paths, reconnect the corresponding workbook, and restore the exported notes in step 1. Keep the original package artifacts and Excel workbook alongside the notes JSON so the Companion can reconnect the review work.

## Source and version boundaries

- Internal sources: supplied SOP and review-sheet v1.08; see the [workflow analysis](internal-workflow-analysis.html) for exact sections and cells.
- Local rule snapshot: generated September 14, 2026; rules SHA `58487bda77d76d9ce334304ec2e779ece7cc7d54`. It is not a verified November rules release.
- Teaching scenarios: newly constructed fictional illustrations. They are not official templates, complete packages, or evidence about an actual provider.
- Live official CR26 guidance and official blog context were consulted November 4, 2026. See [official research](official-research.html) for precise sources, updates and verification limits. Blogs explain intent and rollout; the applicable current rules govern requirements.
- No exhaustive current-rules JSON comparison, official-schema validation of every loaded package, remote evidence-access test or live-system assessment was performed for this guide.
