# The TUDOK Operator

## Model-agnostic calibration index for truth-priority in AI-assisted decision-making

**Version:** v0.4 EN public pre-validation draft  
**Status:** pre-validation / pilot-ready / expert-review oriented

## Abstract

Artificial intelligence systems increasingly support decision-making, communication, research, education, and institutional processes. In these contexts, it is not sufficient for an AI output to be coherent, persuasive, or user-friendly; it must also be examined in terms of whether it preserves the priority of truth. The TUDOK Operator is presented as a model-agnostic calibration index that estimates whether truth-priority is preserved in a given output according to a fixed evaluation protocol. The method decomposes the output into interpretable segments and evaluates them according to four components: semantic coherence, internal consistency, contextual truth-alignment, and distortion pressure. The result is a TUDOK value in the [0,1] range, accompanied by diagnostic flags and a recommended_action field. TUDOK is not a truth-verification engine, not a moral arbiter, and not a compliance certification mechanism, but a truth-priority calibration and audit-preparation instrument.

## 1. Introduction

AI systems today no longer merely provide information; they interpret, summarize, rank, recommend, and prepare decisions. Users often cannot see when an answer is a fact, when it is an estimate, when it is a rhetorical simplification, and when it is an uncertain claim.

Formal coherence and the priority of truth are not the same. An answer may be fluent, friendly, and persuasive while its claims are insufficiently sourced, overly confident, or organized within a distorting narrative. This is not only a hallucination problem: the subordination of truth may occur even when there is no obvious factual error.

## 2. What Is TUDOK?

The TUDOK Operator is an output-level calibration index. It estimates whether truth remains the primary organizing principle in the examined output.

TUDOK does not measure the quantity of knowledge. It measures a truth-priority state.

## 3. What TUDOK Is Not

TUDOK is not:

- an objective truth-verification engine;
- a moral arbiter;
- a compliance certification;
- a safety filter;
- a replacement for factuality benchmarks;
- a replacement for domain-expert review.

## 4. TUDOK and Factuality

**Factuality:** Is the claim true?  
**TUDOK:** Has truth remained the primary organizing principle?

A response may receive a high TUDOK value if it signals uncertainty and requests verification, even if one detail is factually incorrect. Another response may be partially factually correct but receive a low TUDOK value if it asserts excessive certainty or excludes the need for review.

## 5. Formal Definition

Let `X` denote the space of interpretable outputs. The TUDOK Operator is:

```text
TUDOK: X -> [0,1]
```

The segments of an output are:

```text
x = {x_1, x_2, ..., x_n}
```

Components:

- `C(x_i)` = semantic coherence
- `K(x_i)` = internal consistency
- `I(x_i)` = contextual truth-alignment
- `D(x_i)` = distortion pressure

Raw segment score:

```text
s_i = C_i + K_i + I_i - D_i
```

Normalized TUDOK:

```text
TUDOK = max(0, MeanRawScore) / 3
```

## 6. Minimal Pipeline

1. Input selection
2. Fixing the segmentation rule
3. C/K/I/D scoring
4. Computing MeanRawScore
5. Normalization
6. Diagnostic flags
7. Recommended action
8. Robustness and sensitivity analysis

## 7. Next Research Step

The next step is a 30-50 prompt mini pilot on real model outputs, with at least two independent evaluators and an inter-rater reliability report.
