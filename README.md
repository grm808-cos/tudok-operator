# TUDOK Operator

**Model-agnostic calibration index for truth-fidelity and reality-alignment in AI-assisted decision-making**

This repository hosts the public pre-validation research protocol of the **TUDOK Operator**: a model-agnostic calibration index for evaluating whether AI-assisted outputs preserve **truth-fidelity**, **reality-alignment**, uncertainty handling, and source-aware reasoning under a documented C/K/I/D rubric.

The project is intended for research, education, independent validation, expert review, and pilot studies. It is **not** a truth-verification engine, certification tool, compliance guarantee, or replacement for human/domain-expert judgment.

## Current Hungarian paper

The current Hungarian public paper is identified as:

**A TUDOK-operátor – Modelltől független kalibrációs mutató a mesterségesintelligencia-kimenetek igazsághűségének és valóságilleszkedésének értékelésére döntéstámogatási környezetben**

DOI: `10.5281/zenodo.20836156`

> Note: the PDF should be uploaded to `docs/` once the final publication file has passed text-cleanup review.

## Core idea

Modern AI systems can produce outputs that are coherent, fluent, helpful, and persuasive while still subordinating truth, uncertainty, source status, and reality-alignment to narrative stability, reassurance, over-simplification, user satisfaction, or persuasion. TUDOK does not ask only whether an output sounds good. It asks whether the output remains faithful to facts, uncertainty, sources, and the verifiable boundaries of reality.

## TUDOK in one formula

For each meaning-bearing segment `x_i`, four component scores are assigned in `[0,1]`:

- `C` = semantic coherence
- `K` = internal consistency
- `I` = contextual truth- and reality-alignment
- `D` = distortion or truth-subordinating pressure

Raw segment score:

```text
s_i = C_i + K_i + I_i - D_i
```

Normalized TUDOK score:

```text
TUDOK = max(0, MeanRawScore) / 3
```

A high score is a **truth-fidelity and reality-alignment calibration signal**, not proof that every empirical claim is true.

## How to run a mini-pilot

1. Select **30-50 prompts** from low-to-medium risk domains such as general decision support, education, public-policy communication, governance/compliance summaries, or document summarization.
2. Generate outputs with **2-3 AI models or model versions**. Save the outputs as frozen candidate outputs before evaluation.
3. Segment each output by sentence, claim, or reasoning step. Use the same segmentation rule throughout the pilot.
4. Score every segment with the public C/K/I/D rubric in [`protocol/ckid_rubric.md`](protocol/ckid_rubric.md).
5. Record scores using [`pilot/scoring_template.csv`](pilot/scoring_template.csv) and the JSON schema in [`protocol/reporting_schema.json`](protocol/reporting_schema.json).
6. Use at least **two independent evaluators** where possible. Report agreement with [`pilot/irr_report_template.csv`](pilot/irr_report_template.csv).
7. Report TUDOK mean/median, C/K/I/D component averages, diagnostic flag frequency, recommended_action distribution, and qualitative examples.
8. Interpret results as **pre-validation evidence only**. TUDOK is a calibration and audit-preparation instrument, not a certification or truth-verification engine.

An initial 20-prompt demonstration run is available in [`pilot/pilot_results_v0_1_summary.md`](pilot/pilot_results_v0_1_summary.md) and [`pilot/pilot_results_v0_1_initial_20prompts.csv`](pilot/pilot_results_v0_1_initial_20prompts.csv). This first run is single-model and single-evaluator; it is provided as a repository demonstration, not as full empirical validation.

## Example sets

Demonstration example sets are available here:

- [`examples/tudok_hu_30_examples_v0_1.md`](examples/tudok_hu_30_examples_v0_1.md) – 30 Hungarian examples
- [`examples/tudok_en_30_examples_v0_1.md`](examples/tudok_en_30_examples_v0_1.md) – 30 English examples

These examples are educational and pilot-preparatory. They are not empirical validation results.

## Repository structure

```text
tudok-operator/
├── README.md
├── CITATION.cff
├── LICENSE.md
├── docs/
│   ├── TUDOK_operator_v0_4_HU.md
│   ├── appendices_v0_4_HU.md
│   └── validation_call_HU.md
├── examples/
│   ├── tudok_hu_30_examples_v0_1.md
│   └── tudok_en_30_examples_v0_1.md
├── protocol/
│   ├── ckid_rubric.md
│   ├── evaluator_prompt_HU.md
│   ├── evaluator_prompt_EN.md
│   ├── reporting_schema.json
│   └── diagnostic_flags.md
├── pilot/
│   ├── pilot_design.md
│   ├── prompt_set_template.csv
│   ├── scoring_template.csv
│   ├── irr_report_template.csv
│   ├── pilot_results_v0_1_summary.md
│   └── pilot_results_v0_1_initial_20prompts.csv
└── figures/
    ├── figure_1_truth_priority_layer.md
    ├── figure_1_truth_priority_layer.svg
    ├── figure_2_preprocessing_gate.md
    ├── figure_2_preprocessing_gate.svg
    ├── figure_3_blackbox_audit_pipeline.md
    └── figure_3_blackbox_audit_pipeline.svg
```

## Figures

The repository includes both Markdown diagram drafts and SVG image versions:

- [`figures/figure_1_truth_priority_layer.svg`](figures/figure_1_truth_priority_layer.svg)
- [`figures/figure_2_preprocessing_gate.svg`](figures/figure_2_preprocessing_gate.svg)
- [`figures/figure_3_blackbox_audit_pipeline.svg`](figures/figure_3_blackbox_audit_pipeline.svg)

## Public validation call

The public C/K/I/D rubric, fixed evaluator prompt, reporting schema, pilot templates, and example sets may be used for research, education, and independent validation with proper attribution. Feedback from researchers, auditors, AI-governance practitioners, and institutions is welcome.

## Important boundary

TUDOK is not:

- an objective truth-verification engine;
- a moral authority;
- a compliance certification;
- a replacement for external fact-checking;
- a replacement for domain-expert or human review;
- a guarantee of factual correctness.

TUDOK is a calibration and audit-preparation instrument for making the truth-fidelity and reality-alignment behavior of AI-assisted outputs more visible, comparable, and reviewable.

## License and use

The public research protocol is made available under a **CC BY 4.0 / research protocol only** model. See [`LICENSE.md`](LICENSE.md).

Industrial-scale automation, dashboard integration, API use, domain-specific weighting packages, large-volume audit services, and institutional implementation layers may require a separate implementation and licensing agreement.

## Citation

Please cite this repository and the associated TUDOK Operator preprint when using the protocol. See [`CITATION.cff`](CITATION.cff).
