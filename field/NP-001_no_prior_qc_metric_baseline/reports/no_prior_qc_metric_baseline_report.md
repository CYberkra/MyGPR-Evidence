# NP-001 No-prior QC Metric Design and Baseline

## Executive summary
- NP-001 defines no-prior raw QC metrics on the DS-002 selected three lines.
- No AutoTune, no gprMax, no processing pipeline was run.
- All three lines are parseable and reconstructable.
- All three lines currently trigger `high_risk` no-prior warnings.

## Semantics clarification
- `suitable_for_safe_auto_recommendation = no` means software should **not** auto-recommend aggressive processing.
- `suitable_for_no_prior_qc_stress_baseline = yes` means these lines are valid stress-test inputs for warning-system baseline evaluation.
- High-risk warnings do **not** mean the data are unusable; they mean conservative display-first workflow and manual review are required.

## Per-line findings (concise)
- YingShan Line9origin(36).csv: no_prior_processing_caution=high_risk; shallow_dominance=high_risk; weak_deep_signal=high_risk; trace_instability=ok
- YaAn 测线21-1_功率30dbm_高度11m.csv: no_prior_processing_caution=high_risk; shallow_dominance=high_risk; weak_deep_signal=high_risk; trace_instability=ok
- YaAn 测线21-1_功率36dbm_高度11m.csv: no_prior_processing_caution=high_risk; shallow_dominance=high_risk; weak_deep_signal=high_risk; trace_instability=ok

## Recommended initial policy
- conservative_display_only
- avoid_aggressive_background_suppression
- avoid_amplitude_claims
- require_manual_review

## Claim boundary
- no target detection claim
- no underground correctness claim
- no AutoTune performance claim
- heuristic thresholds only

## Next recommended task
- NP-002 no-prior processing safety pilot on the same three lines.
