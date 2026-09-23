# The TUDOK Operator v2.0

## Current methodological repository reference

**Primary paper:** *The TUDOK Operator: A Model-Agnostic Calibration Measure for Assessing Truth-Fidelity and Reality-Alignment in AI Outputs for Decision-Support Contexts*  
**DOI:** 10.5281/zenodo.22916404  
**Status:** public pre-validation / pilot-ready / expert-review oriented  
**Repository role:** open validation, reproducible protocol, audit preparation, independent testing

## Purpose

TUDOK is a model-agnostic calibration methodology for examining whether AI-assisted outputs preserve **truth-fidelity**, **reality-alignment**, uncertainty handling, and source-aware reasoning under a documented C/K/I/D evaluation procedure.

It is not an objective truth-verification engine, moral authority, compliance certification, safety filter, or replacement for factual verification, domain expertise, or human responsibility.

## C/K/I/D model

For each interpretable segment:

- **C** = semantic coherence
- **K** = internal consistency
- **I** = contextual truth- and reality-alignment
- **D** = distortion pressure

```text
s_i = C_i + K_i + I_i - D_i
MeanRawScore(x) = (1/n) * sum(s_i)
TUDOK(x) = max(0, MeanRawScore(x)) / 3
TUDOK% = 100 * TUDOK(x)
```

The percentage is a calibration signal, not a percentage of factual truth.

## Architectural views

The v2.0 paper presents three architecture-independent interpretations:

1. **Figure 1 - TUDOK as a Truth-Fidelity and Reality-Alignment Calibration Layer**
2. **Figure 2 - TUDOK as a Preliminary Truth-Fidelity and Reality-Alignment Gate**
3. **Figure 3 - TUDOK Audit Workflow in a Closed-Model Environment**

These figures are governance and audit interpretations. They do not claim that every AI system is physically structured in this way.

## Closed-model audit

TUDOK can be applied without access to model weights, training data, hidden states, or internal reasoning. A controlled audit uses fixed tasks, frozen outputs, a predefined segmentation rule, a fixed C/K/I/D rubric, documented evaluator configuration, diagnostic flags, uncertainty notes, and review routing.

Possible procedural actions:

- `accept`
- `revise`
- `external_check`
- `human_review`

## Validation status

The current methodology is **pilot-ready but not fully empirically validated**. The recommended next step is a 30-50 prompt mini-pilot across 2-3 models or versions, with at least two independent evaluators and an inter-rater agreement report.

The initial 20-prompt run in this repository is a single-model, single-evaluator demonstration only.

## Open materials

The repository provides:

- C/K/I/D rubric;
- fixed evaluator prompts;
- reporting schema;
- diagnostic flags;
- task and scoring templates;
- inter-rater agreement template;
- demonstration examples;
- architectural diagrams;
- open validation call.

## Citation

Sípos, Lóránt. *The TUDOK Operator: A Model-Agnostic Calibration Measure for Assessing Truth-Fidelity and Reality-Alignment in AI Outputs for Decision-Support Contexts.* 2026. DOI: 10.5281/zenodo.22916404.
