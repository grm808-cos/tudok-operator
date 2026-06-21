# Figure 3 - TUDOK Black-Box Audit Pipeline

```text
Fixed prompt set / test tasks
        ↓
AI system or multiple models
        ↓
Frozen outputs
        ↓
TUDOK evaluator
segmentation
C/K/I/D scoring
normalization
diagnostic flags
        ↓
Structured report
tudok_0_1
tudok_percent
uncertainty_note
recommended_action
        ↓
Audit dashboard / time series / model comparison / review routing
```

TUDOK can be used with closed or black-box models because it evaluates outputs, not hidden model internals.
