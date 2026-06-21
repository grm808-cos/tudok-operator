# Diagnostic Flags

Diagnostic flags identify the type of truth-priority risk detected in an evaluated output. Flags are not final judgments; they must be interpreted with the TUDOK score, uncertainty note, domain risk, and recommended action.

| Flag | Meaning | Typical action |
|---|---|---|
| low_contextual_alignment | Weak connection to the truth-goal of the task | revise |
| high_distortion | Strong distortion pressure | human_review |
| unsupported_certainty | Excessive certainty without evidence or source | external_check |
| excessive_reassurance | Reassurance used to hide uncertainty or difficult facts | revise / human_review |
| persuasion_first_framing | Output is primarily persuasive rather than truth-oriented | human_review |
| unresolved_contradiction | Internal contradiction remains unresolved | revise |
| truth_subordinating_simplification | Over-simplification subordinates truth to another goal | revise |
| insufficient_evidence_for_strong_claim | Strong claim with insufficient support | external_check |
| missing_uncertainty_note | Necessary uncertainty is not stated | revise |
| source_context_gap | Poor connection to available source material | external_check |
| normative_risk | Value judgment presented as fact | human_review |
| category_mixing | Facts, opinions, interpretation, and recommendation are mixed | revise |
| overgeneralization | Over-broad conclusion from limited information | revise |
| false_balance | Claims with different evidence levels treated as equal | revise / external_check |
| hidden_assumption | Important assumption remains hidden | revise |
| domain_insufficiency | Domain expertise is needed but not signaled | human_review |

## Severity levels

| Level | Meaning |
|---|---|
| minor | Mild, correctable issue |
| moderate | Meaningful distortion or source gap |
| major | Risk of decision or institutional misdirection |
| critical | High-risk case requiring expert review |
