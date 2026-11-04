# FedRAMP 20x review: official source research

Research checked November 4, 2026. This is a learning aid, not an official FedRAMP determination. Rule summaries below were checked against live official rendered pages; the full current Rules JSON was not downloaded or exhaustively diffed. Suggested reviewer techniques are explicitly identified as interpretation.

## Source authority and version

Use the current CR26 rule, its defined terms, applicability, and effective dates to establish the requirement. Use current official narrative to interpret its purpose. Use the internal SOP to execute the team's workflow. Blogs explain development and intent; a pilot-era blog does not override CR26.

The supplied local corpus is a **September 14, 2026 snapshot**, not a November rules export. Its _sources.json (source retained offline) records generation at `2026-09-14T01:04:43Z`, site SHA `3db98a0406d5b27920ad4e9620296765247bb917`, and rules SHA `58487bda77d76d9ce334304ec2e779ece7cc7d54`. Its AGENTS.md (source retained offline) directs readers to canonical FedRAMP sources and separates historical communications from rules. The [live CR26 source page](https://www.fedramp.gov/2026/) links the structured rules and current guidance.

Observed differences that matter to this task:

| Live change | Why the reviewer/tool must account for it |
| --- | --- |
| October 31: FRC-CLA-MFR adds SDR-CSX-KSI to Class A's mandatory overlay. | A September-only rule catalog misses an explicit Class A KSI documentation requirement. |
| October 31: FRC-CLA-RFR removes CPO-CSF-CPM. | Do not treat the former Rev5 package maintenance reference as a current Class A recommendation. |
| October 8: SDR-CSX-KMT clarifies persistent-validation status in daily metrics and initial-certification treatment where history is unavailable. | Missing a full year is not automatically a failed initial application. |
| October 5: FRC-CSO-JSN adds public JSON web compatibility expectations. | Syntax/schema checks alone do not assess public data usability. |

Sources: [Class A certification, including changelog entries](https://www.fedramp.gov/2026/reference/20x/a/fedramp-certification/), [Class C SDR](https://www.fedramp.gov/2026/reference/20x/c/security-decision-record/), [Class C certification](https://www.fedramp.gov/2026/reference/20x/c/fedramp-certification/). This is a targeted comparison, not an exhaustive inventory of changes since September.

## The purpose of the review

FedRAMP's responsibility is to establish common rules, grant certifications, support sharing and ongoing monitoring, and rely on recognized assessors. Its public guidance expressly separates certification from a government-wide authorization to operate. The information is intended to let agencies make their own decisions. Therefore, the practical reviewer question is whether the package supplies sufficient, accurate, current information under the applicable rules—not whether one reviewer would select the service for every possible mission. [FedRAMP responsibilities](https://www.fedramp.gov/2026/responsibilities/fedramp/).

The 20x narrative emphasizes transparent security decisions, operational accountability, and automated validation. Its Phase 2 lessons identify helpful review characteristics: usable interfaces, consistent structured data, concise evidence context, clear failure criteria, assessor feedback beside provider validation, and assessor inspection of validation code. Those lessons explain effective review design; they are not independent mandatory checklist items. [FedRAMP 20x overview and pilot lessons](https://www.fedramp.gov/20x/).

KSI guidance asks providers to connect a desired security outcome to actual activities, their location in the technology or policy stack, measurement sources, timing, and gaps. It generally does not prescribe one numerical threshold or implementation for every provider. A metric should demonstrate that a capability works and reveal drift or deterioration. [KSI guidance](https://www.fedramp.gov/2026/providers/20x/key-security-indicators/).

**Reviewer interpretation:** follow this evidence chain:

`applicable rule/outcome → provider decision and objective → implemented measure → measurement/test method → observed result → independent challenge → exceptions/customer impact → current reporting`

An assertion can be complete as prose and still have a broken evidence chain. A negative result can be highly useful evidence when it accurately exposes limitations and is handled under the rules. Counting green status fields measures presentation, not assurance.

## Keep the actors separate

| Actor | What to seek in a review |
| --- | --- |
| Provider | Accountable description of the offering and security decisions; actual supporting evidence; accurate and current package; responses to assessment findings. |
| Independent assessment service | Technical verification, outcome validation, meaningful findings, and evidence of what was examined. |
| FedRAMP internal reviewer | Evaluation of the application and evidence against applicable FedRAMP expectations, identification of gaps/disputes, and an internally supported certification recommendation. |
| Agency | Service suitability for its use, customer configuration, integration, mission/data risks, and its authorization decision. |

Recognized assessors perform the bulk of verification and validation. Their role includes examining quality and completeness and recording gaps, inconsistencies, deficiencies, and potential risks. [Independent assessor responsibilities](https://www.fedramp.gov/2026/responsibilities/assessors/). The internal review role in the table is a synthesis to be reconciled with the team's SOP; the public responsibilities page is not a detailed internal workflow.

## Class A and Class C need different review logic

**Class A:** FRC-CLA-ASF requires an accepted external-framework process completed in the previous 12 months. FRC-CLA-EAM specifies the associated materials. FRC-CLA-MFR adds the FedRAMP overlay, including seven named KSIs and, since October 31, SDR-CSX-KSI. FRC-CLA-IVV makes a recognized assessor's separate verification/validation of the FedRAMP package optional. FRC-CLA-RFR and FRC-CLA-OFR remain different levels of obligation; do not silently turn them into Class C requirements. [Class A rules](https://www.fedramp.gov/2026/reference/20x/a/fedramp-certification/).

The seven named Class A KSIs are KSI-CMT-LMC, KSI-CNA-RNT, KSI-CED-RAT, KSI-IAM-AAM, KSI-IAM-APM, KSI-INR-RIR, and KSI-SVC-SIN. These identifiers are a retrieval aid; read their current actual text.

Class A's mandatory IVV-CSX-AIA means meeting the expectations of its underlying alternative security framework for persistent independent assessment. It does **not** import the Class C assessment model. Its related-rules page also separates mandatory, recommended, optional, and otherwise referenced material. [Class A related rules](https://www.fedramp.gov/2026/reference/20x/a/related/).

**Class C:** FRC-APP-FCP calls for provider verification/validation within the previous seven days; FRC-APP-FIA requires the initial recognized-assessor assessment within three months. FRC-APP-USA allows a change-focused refresh unless the prior assessment is more than nine months old. FRC-CSX-VVK requires at least two automated methods per KSI. FRC-CSX-VVR recommends automation for the rule-based SDR where applicable; FRC-CSX-MAS recommends applying all KSIs across the MAS. Preserve these different forces. [Class C certification rules](https://www.fedramp.gov/2026/reference/20x/c/fedramp-certification/).

**Reviewer interpretation:** for Class A, start with external assessment coverage, identity, dates, qualifications/exceptions, and the overlay. For Class C, establish a complete class-specific evidence model and test the automation and independent assessment. A SOC 2 report is evidence to examine, not a universal substitution for the overlay. A Class A package containing extra Class C artifacts does not itself make them mandatory.

## How to read the artifacts

### Certification Package Overview (CPO)

CPO-CSO-OVR calls for human-readable and JSON overview information, combining service description with relevant policies, scope/resources/flows, third parties, cryptography, and assessment material through the referenced rules. CPO-CSO-MTD provides identity/version context; CPO-CSO-OSA carries the overall assessment summary. Use this as the map of the service and package. [Class C CPO](https://www.fedramp.gov/2026/reference/20x/c/certification-package-overview/).

**Reviewer interpretation:** reconcile service identity, boundary, versions, assessment period, and referenced documents before reviewing isolated assertions. Check whether an overview conclusion is supported by the detailed SDR and whether limitations remain visible in both. Do not use a document's friendly title as proof it is the submitted controlling version.

### Minimum Assessment Scope (MAS)

MAS-CSO-IIR includes resources likely to handle federal customer data or affect its confidentiality, integrity, or availability. MAS-CSO-FLO covers flows and security categories. MAS-CSO-TPR requires the usage/configuration, rationale, mitigations, and compensating controls for applicable third parties. MAS-CSO-MDI includes metadata where the scope rule applies. MAS-CSO-SUP permits separately marked supplemental resources outside the certified offering. [MAS rules](https://www.fedramp.gov/2026/reference/minimum-assessment-scope/).

**Reviewer interpretation:** ask how identity, support, deployment, logs, backups, telemetry, and external resources can affect the actual offering. The question is their relationship to federal data and security, not whether they appear in an architecture picture. Avoid assuming a third party is excluded simply because its own certification is absent, or included solely because the provider uses it somewhere.

### Security Decision Record (SDR)

SDR-CSO-FRR requires implementation/risk explanations, provider verification and validation, independent verification and validation, clarifications, and applicable artifacts. SDR-CSX-KSI adds objectives, cycles, automation adequacy, and outcome evidence. SDR-CSX-KMT requires Class C historical metrics: 30-day summaries, up to a year of summary/daily data where available, including persistent-validation status. Its initial-certification note allows mechanisms plus an agreement when the service lacks the full history. [Class C SDR rules](https://www.fedramp.gov/2026/reference/20x/c/security-decision-record/).

**Reviewer interpretation:** separate the claim, implementation evidence, effect evidence, and assessor's conclusion. A URL or hash provides a locator or integrity value; neither establishes that the evidence was retrieved, relevant, authentic, or sufficient. A senior official's acceptance should be visible where the rule calls for it, but an accepted risk statement must not be treated as an automatic exception to every other obligation.

### Independent verification and validation

IVV-CSO-SEI and IVV-CSO-SEE distinguish evidence of implementation from evidence of effectiveness. IVV-IAS-VIM and IVV-IAS-VEF require the independent assessor to examine the actual measures technically, rather than rely solely on prose/screenshots. IVV-IAS-SUM provides practice-level findings for the SDR; IVV-IAS-OSA provides the overall summary for the CPO, including failures/disputes. IVV-IAS-VIP and IVV-CSO-ICP preserve the assessor's meaning when included in the package. IVV-CSO-DUS requires explanation of representative samples. IVV-CSO-FIA requires Class C assessment at least annually. [Class C IVV rules](https://www.fedramp.gov/2026/reference/20x/c/independent-verification-and-validation/).

**Reviewer interpretation:** ask what the assessor inspected, how it challenged the provider's method, which population/time window it covered, what failed, and why its conclusion follows. Two labels do not establish two effective automated methods. Repeated generic approval paragraphs should trigger a request for the underlying method and results, not an automatic adverse finding.

### Secure Configuration Guide (SCG)

SCG-CSO-RSC requires guidance for the lifecycle of top-level administrative accounts and the security implications of settings only those accounts control. SCG-CSO-AUP requires instructions for obtaining/using the guide. Public availability, secure defaults, comparison, export, API, machine-readable guidance, and release history are separately expressed recommendations. [Class C SCG rules](https://www.fedramp.gov/2026/reference/20x/c/secure-configuration-guide/).

**Reviewer interpretation:** follow one customer task from access to decommissioning. Confirm that the customer can find the setting, understand the risk, implement the recommendation, and recognize which responsibilities remain theirs. A generic security overview is not equivalent to usable configuration instructions.

### Ongoing Certification Report (OCR)

CCM-OCR-AVL specifies a report every three months covering the period since the previous summary; CCM-OCR-NRD addresses the next date. Other rules address feedback and anonymized summaries. Class C includes quarterly reviews under CCM-QTR-MTG. The initial certification package may contain a real or example OCR under FRC-CSO-PKG. [Class C CCM](https://www.fedramp.gov/2026/reference/20x/c/collaborative-continuous-monitoring/), [initial package rule](https://www.fedramp.gov/2026/reference/20x/c/fedramp-certification/).

**Reviewer interpretation:** distinguish an example report that demonstrates format/readiness from operating history. Reconcile incidents, vulnerabilities, significant changes, metric failures, and unresolved assessment issues across the package. A report saying nothing happened needs an understandable observation period and reporting basis.

## Definitions that change review outcomes

SHOULD is not a synonym for ignorable: the defined term allows valid reasons to depart but requires those decisions to be addressed in the security documentation. MAY is genuinely optional, with a recommendation to explain treatment. Persistently does not mean every second: the cycle can include intentional irregularity or interruptions, but its attributes should be understood/documented and status known. [CR26 definitions](https://www.fedramp.gov/2026/definitions/).

**Reviewer interpretation:** store requirement force, applicability, implementation decision, supporting evidence, and review disposition as different fields. Never use one blank/green/red value to represent all five.

## Reading the official communications in sequence

| Publication | What it contributes | How to use it |
| --- | --- | --- |
| [June 25, 2026 — CR26 launch](https://www.fedramp.gov/2026-06-25-propelling-change-fedramp-launches-consolidated-rules-for-2026/) | Explains the move from pilot work into stable consolidated expectations and reusable measurable evidence. | Orientation; follow actual rule dates/grace conditions for a specific package. |
| [July 30, 2026 — Certification paths](https://www.fedramp.gov/2026-07-30-fedramp-certification-paths-are-heating-up/) | Explains progressive classes and the August opening of Class A/B/C pipelines. | Understand why assurance levels differ; avoid treating the classes as identical reviews. |
| [October 8, 2026 — Foundation to implementation](https://www.fedramp.gov/2026-10-08-from-foundation-to-implementation/) | Frames 20x around existing commercial security investments and progressive assurance. | Program context and transition history, not a substitute for evidence criteria. |
| [November 2, 2026 — Memo to milestone](https://www.fedramp.gov/2026-11-02-memo-to-milestone/) | Distinguishes limited pilots from full CR26 certification and explains outcome metrics using scan results and actual release decisions. | Most directly useful recent explanation of why measured operation matters. It reports the first full Class C certification on October 29. |
| [20x overview, current page](https://www.fedramp.gov/20x/) | Consolidates principles and pilot lessons. | Read principles alongside current CR26. The page also retains older forward-looking milestone language; don't elevate those dates over current rules. |

The 2025 pilot blog series is useful development history. It should not become a second requirement catalog for full CR26 reviews.

## Suggested reviewer questions and tool checks (interpretation)

These are implementation recommendations derived from the above model, not new FedRAMP rules:

1. **Applicability first:** what class, type, path, initial/ongoing status, rule version and effective-date context apply? Show the source and force for every question.
2. **Findability:** can the reviewer locate the required artifact and identify its controlling version? Distinguish missing from supplied elsewhere and from unavailable to this reviewer.
3. **Identity and scope:** does the evidence concern this service, boundary, population, period, and customer context?
4. **Implementation:** what was actually configured/deployed/performed? A policy is one kind of evidence, not automatic proof of operation.
5. **Effect:** what measured result demonstrates the intended outcome? Ask about denominator, exclusions, zero-result meaning, failure criteria, and sampling.
6. **Automation:** where does the data originate, what logic transforms it, how are errors and stale runs detected, and what independently challenges that logic?
7. **Exceptions:** who knows, what is the customer impact, what treatment applies, and do the overview/SDR/OCR tell the same story?
8. **Decision record:** save source file and JSON pointer, rule ID, observation, evidence checked, uncertainty, exact clarification question, and disposition/reviewer/date.

A reviewer assistant can reliably help with schema validation (against the actual matching schema), missing/duplicate identifiers, references, version mismatches, date calculations, conditional applicability, evidence navigation, and reporting consistency. It can suggest missing questions. It cannot establish technical effectiveness from a narrative alone, certify a provider automatically, or silently resolve a disputed interpretation. It should never mark a rule failed merely because the provider did not use the tool author's preferred field name or file arrangement.

Before relying on a rules engine, pin and validate the current official Rules JSON/schema plus referenced artifact schemas. This research checked selected live rendered rules but did not validate every rule, every class, or every schema. A source/version manifest should travel with any generated review output.
