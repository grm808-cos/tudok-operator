# Figure 3 - TUDOK Audit Workflow in a Closed-Model Environment

**Publication caption:** Figure 3. The TUDOK audit workflow applicable in a closed-model environment.

The workflow evaluates observable output behavior without requiring access to model weights, training data, hidden states, or internal reasoning.

```text
1. AUDIT GOAL AND INPUT
   audit goal:
   - model evaluation
   - provider comparison
   - prompting strategy
   - compliance support

   inputs:
   - test tasks
   - frozen outputs
   - audit logs
   - reference sources

            ↓

2. OUTPUT CAPTURE
   task prompt and response identification:
   - task prompt ID
   - output ID
   - model / version
   - risk category

   segmentation into subunits:
   - statement-based segmentation
   - sentence / claim / reasoning
   - auditable units

            ↓

3. TUDOK EVALUATION
   C = coherence
   K = consistency
   I = truth- and reality-alignment
   D = distortion pressure

   s_i = C + K + I - D
   TUDOK(x) = max(0, MeanRawScore) / 3

            ↓

4. DIAGNOSTICS
   diagnostic signals:
   - weak source coverage
   - unsupported certainty
   - missing uncertainty signaling
   - normative risk

   recommended procedural step:
   - accept
   - revise
   - external verification
   - human review

   uncertainty note:
   - measurement limitations
   - evaluator observations

            ↓

5. INDICES AND TIME SERIES
   - C-index / K-index / I-index / D-index
   - TUDOK_0_1 and TUDOK %
   - trend, drift, model update, and improvement-cycle monitoring

            ↓

6. GOVERNANCE OUTPUT
   audit report:
   - summary
   - deviations
   - risks
   - recommendations

   organisational decisions:
   - review trigger
   - policy update
   - prompt improvement
   - supplier comparison

   human responsibility point:
   - expert or human review required in high-risk cases

            ↺

IMPROVEMENT CYCLE
prompt refinement / source strengthening / threshold tuning / re-measurement
```

**Boundary:** The TUDOK index is not an objective truth certificate. It is a calibration audit signal indicating truth-fidelity, reality-alignment, and distortion risk. It does not replace domain-specific or human responsibility.
