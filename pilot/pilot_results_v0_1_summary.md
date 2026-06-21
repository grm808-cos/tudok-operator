# Initial 20-Prompt Pilot Result

Version: v0.1 initial repository pilot  
Date: 2026-06-21  
Status: preliminary, single-model, single-evaluator demonstration

## Purpose

This file documents a small initial pilot run for the public TUDOK Operator repository. The goal is to show how the C/K/I/D rubric, diagnostic flags, and recommended actions can be recorded in a structured pilot file.

This is **not** a full validation study. It is a first demonstration run designed to make the repository more testable and to prepare for independent validation.

## Configuration

| Item | Configuration |
|---|---|
| Prompt count | 20 |
| Generator | ChatGPT current session |
| Evaluator | E1, single evaluator |
| Segmentation | one compact candidate output per prompt |
| Domains | general decision support, education, public-policy communication, governance/compliance, document summary, health/legal/financial boundary examples |
| IRR | not available in this initial run |
| Robustness | not tested in this initial run |

## Summary statistics

| Metric | Value |
|---|---:|
| Mean TUDOK | 0.849 |
| Minimum TUDOK | 0.650 |
| Maximum TUDOK | 0.933 |
| Outputs with TUDOK >= 0.80 | 15 |
| Outputs with 0.60 <= TUDOK < 0.80 | 5 |
| Outputs with TUDOK < 0.60 | 0 |

## Interpretation

The initial run shows that the protocol can record differentiated scores across prompt types and risk contexts. Lower scores appeared mainly in public-policy persuasion, partial-source, and evidence-gap prompts. Higher scores appeared when the output explicitly stated uncertainty, requested external checking, or refused unsupported certainty.

## Important limitations

- This is a preliminary single-model, single-evaluator run.
- It does not provide interrater reliability.
- It does not compare multiple models.
- It does not test prompt paraphrase robustness.
- It must not be interpreted as empirical validation of the TUDOK Operator.

## Next validation step

A stronger mini-pilot should include:

1. 30-50 prompts;
2. 2-3 models or model versions;
3. at least 2 independent evaluators;
4. Mean Absolute Disagreement or another IRR metric;
5. robustness testing on 5-10 prompt paraphrases;
6. comparison with at least one factuality or hallucination evaluation method.

The structured CSV result for this initial run is available at:

[`pilot_results_v0_1_initial_20prompts.csv`](pilot_results_v0_1_initial_20prompts.csv)
