# Open Call for Independent Validation

The C/K/I/D rubric, baseline protocol, evaluator prompt, and reporting schema of the TUDOK Operator published in this repository may be publicly tested for research, educational, and independent validation purposes, with appropriate citation.

## Purpose

The purpose is to ensure that auditing truth-priority does not remain closed, unverifiable, or the privilege of only high-cost services. Research groups, auditors, AI-governance experts, and institutions are invited to test the protocol on their own AI outputs.

## What Should Be Tested?

- Does the C/K/I/D rubric work across multiple models?
- How large is the disagreement between evaluators?
- Which diagnostic flags appear most frequently?
- Does TUDOK provide an additional signal alongside factuality or hallucination measurements?
- Can it be used for review-routing purposes?
- How stable is the TUDOK value under prompt paraphrasing or evaluator replacement?

## Minimum Recommended Pilot

- 30-50 prompts
- 2-3 models or model versions
- at least 2 independent evaluators
- Mean Absolute Disagreement or another IRR metric
- distribution of diagnostic flags and recommended_action values

## Important Limitation

Use of the public protocol does not constitute certification, official qualification, or industrial compliance confirmation. TUDOK is a calibration and audit-preparation instrument that should be interpreted together with external fact-checking, expert review, and domain-specific validation.
