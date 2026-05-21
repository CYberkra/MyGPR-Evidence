# NP-001 No-prior QC Metric Design and Baseline

## Executive summary
- NP-001 defines no-prior raw QC metrics on DS-002 selected lines.
- No AutoTune, no processing pipeline, raw input only.

## Why no-prior QC is needed
- Non-expert users often do not have ROI/target prior.
- ROI-based validation is not always available.
- Software should still warn when data/processing risk is high.

## Metrics design
- Data integrity: parse/shape/NaN/Inf/dead traces/metadata completeness.
- Amplitude & dynamic range: robust percentiles, RMS, clipping and outlier proxies.
- Depth decay: shallow/middle/deep RMS, deep-shallow ratio, dB drop.
- Trace stability: per-trace RMS variation, anomalous/dead/noisy trace ratios.
- Artifact proxies: vertical/horizontal texture, near-surface dominance, deep noise floor.
- Warning flags: ok/caution/high_risk with heuristic thresholds.

## Per-line findings
    site                file_name data_integrity_warning amplitude_scale_warning extreme_dynamic_range_warning shallow_dominance_warning weak_deep_signal_warning trace_instability_warning possible_clipping_warning no_prior_processing_caution
YingShan      Line9origin(36).csv                     ok               high_risk                     high_risk                 high_risk                high_risk                        ok                        ok                   high_risk
    YaAn 测线21-1_功率30dbm_高度11m.csv                     ok               high_risk                     high_risk                 high_risk                high_risk                        ok                        ok                   high_risk
    YaAn 测线21-1_功率36dbm_高度11m.csv                     ok               high_risk                     high_risk                 high_risk                high_risk                        ok                        ok                   high_risk

## Recommended initial policy
    site                file_name suitable_for_no_prior_qc_baseline                                                                             recommended_initial_processing_policy                                                                                 explanation
YingShan      Line9origin(36).csv                                no conservative_display_only; avoid_aggressive_background_suppression; avoid_amplitude_claims; require_manual_review no_prior_level=high_risk; deep/shallow=0.002; trace_cov=0.033; dynamic_range_proxy=14715.49
    YaAn 测线21-1_功率30dbm_高度11m.csv                                no conservative_display_only; avoid_aggressive_background_suppression; avoid_amplitude_claims; require_manual_review  no_prior_level=high_risk; deep/shallow=0.004; trace_cov=0.019; dynamic_range_proxy=7130.05
    YaAn 测线21-1_功率36dbm_高度11m.csv                                no conservative_display_only; avoid_aggressive_background_suppression; avoid_amplitude_claims; require_manual_review  no_prior_level=high_risk; deep/shallow=0.005; trace_cov=0.020; dynamic_range_proxy=8448.03

## Warning interpretation
- `ok`: no immediate severe indicator.
- `caution`: potentially unstable for aggressive processing.
- `high_risk`: strong warning; keep conservative display-only and manual review.

## Claim boundary
- no underground correctness claim
- no target detection claim
- no AutoTune performance claim
- no preset promotion
- raw QC only
- thresholds are heuristic in this baseline

## Next recommended task
- NP-002 no-prior processing safety pilot on the same three lines.
