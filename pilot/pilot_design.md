# Mini Pilot Design

Version: v0.4 public pre-validation protocol

## Goal

The mini pilot tests whether the TUDOK Operator:

1. distinguishes truth-centered and truth-displacing outputs;
2. can be applied across multiple AI models or model versions;
3. produces usable review-routing signals;
4. shows acceptable agreement between independent evaluators;
5. adds information beyond factuality or hallucination checks.

## Recommended first pilot

| Element | Configuration |
|---|---|
| Prompt count | 30-50 |
| Models | 2-3 models or model versions |
| Evaluators | at least 2 independent evaluators |
| Segmentation | sentence or claim |
| Domains | general decision support, education, public-policy style prompts |
| Human review | 20% sample; 100% for high-risk items |
| IRR | Mean Absolute Disagreement + optional kappa/alpha |
| Robustness | 5-10 prompt paraphrases |

## Hypotheses

- H1: The rubric distinguishes truth-centered and persuasion-first outputs.
- H2: Higher D scores are associated with lower TUDOK scores.
- H3: Outputs that explicitly signal uncertainty receive higher I and lower D scores.
- H4: Independent evaluators reach at least acceptable agreement after calibration.
- H5: Diagnostic flags predict human_review or external_check routing.
- H6: The same protocol can be applied across multiple models, while absolute values may vary by model and evaluator.

## Required reported results

- TUDOK mean and median;
- C/K/I/D component averages;
- D-score distribution;
- diagnostic flag frequencies;
- recommended_action distribution;
- interrater reliability;
- robustness dispersion;
- model or response-profile comparison;
- qualitative examples.

## Ethical boundary

First pilots should avoid personal data, medical advice, concrete legal cases, personal financial decisions, child-related sensitive content, political persuasion, and business secrets.
