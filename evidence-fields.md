# Where evidence appears in an SDR

Checked against the live published SDR schema on November 4, 2026. This note describes schema structure and review technique; it does not determine evidence sufficiency.

## Published fields

The [published SDR schema](https://www.fedramp.gov/schemas/fedramp-security-decision-record-schema-2026-06-24.json) reports `$schemaVersion: 1.1.1`.

| JSON path | What it holds |
| --- | --- |
| `/fedRampRequirements/*/frrImplementation` | Implementation statements. |
| `/fedRampRequirements/*/frrValidation` | Provider validation statements. |
| `/fedRampRequirements/*/frrAssessment` | Independent assessment statements. |
| `/keySecurityIndicators/*/ksiImplementation`, `ksiValidation`, `ksiAssessment` | Corresponding KSI statement arrays. |
| `/keySecurityIndicators/*/ksiTests` | Test descriptions. |
| `/keySecurityIndicators/*/ksiEvidence` | Structured evidence entries. |

Statement arrays contain strings and permit Markdown. They can therefore contain artifact names, links and explanatory citations. KSI evidence entries define `evidenceType`, `evidenceDescription`, `evidenceLocation`, `evidenceText`, and `lastUpdated`. A location is a URI; text can contain evidence directly.

There is **no standard `frrEvidence` property** in this version. Provider extensions are not prohibited by these object definitions. For `securityControls`, the implementation field is `controlImplementationDescription`, not `controlImplementation`.

The KSI evidence array is required within a KSI item, but this schema sets no minimum number of entries. Schema validity therefore does not establish substantive sufficiency. The exact file should still be validated against its applicable schema.

## What a reviewer should infer

The published SDR rules require explanations, verification, validation and applicable artifacts, and require both human-readable and JSON SDR presentations. The KSI rules also address measure objectives, cycles, automation and outcomes. A schema field can organize these materials without proving that the required information has been substantively supplied. [SDR-CSO-FRR and SDR-CSX-KSI](https://www.fedramp.gov/2026/reference/20x/c/security-decision-record/).

**Suggested review practice:** search assessment, validation and implementation narratives as well as structured evidence entries. Distinguish four states: a citation is mentioned; a source is supplied or accessible; a reviewer has opened it; its contents substantiate a specific claim. A filename mentioned in `frrAssessment` proves only that the narrative mentions that filename. The actual artifact may be separate, embedded elsewhere, or unavailable in the local selection.

A readable renderer should preserve every original field and make narrative citations easier to find. A reference index is a navigation aid, not a complete or verified evidence inventory. Plain filenames, URLs and custom evidence IDs need different labels; uncertain extraction should stay visible as a heuristic.

## Implementation corrections

- Do not warn that every FRR lacks a dedicated evidence field: the standard schema does not define one.
- Limit standard `ksiEvidence` observations to KSI objects; missing and empty should be distinguished.
- Preserve provider-added fields. JSON Schema normally permits extra properties unless constrained. [JSON Schema object guidance](https://json-schema.org/understanding-json-schema/reference/object#additionalproperties).
- Read the correct security-control description field instead of manufacturing parallel FRR/KSI property names.
- Do not equate `ksiTests` descriptions with executed results, or structured evidence with validated evidence.
