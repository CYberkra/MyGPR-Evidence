# AT-002 Native Benchmark AutoTune Ablation

## Dataset And Scope
- Scenario: `pipe_demo_longline_v1`
- Shape: `[2037, 90]`
- Source evidence: `gprmax/GX-003_audited_native_gprmax_benchmark/`
- Source commit: `ee502475d5f456f9df77e0f4336d34211b0173e9`
- Ground truth available: `True`
- Metric type: `ground_truth`

AT-002 uses GX-003 native gprMax-to-CSV provenance to diagnose which processing stages help or hurt before any AutoTune scoring redesign.
Ground truth metrics and heuristic QC are stored separately. Ground truth is not used as AutoTune search input.

## Claim Boundary
- This is a per-stage ablation diagnostic, not a claim that AutoTune globally beats manual processing.
- Motion compensation, processing_engine behavior, and AutoTune scoring are frozen for this task.
- If a branch has sanity warnings or an invalid reason, manual-vs-auto claims must be treated as inconclusive.

## Stage-Level Ranking
- Metric used: `truth_score`
- Winner: `inconclusive`
- Loser: `inconclusive`
- Diagnostic winner including invalid branches: `only_frequency_filter_1d_auto_tuned`
- Diagnostic loser including invalid branches: `only_background_suppression_auto_tuned`

| Branch | Valid | truth_score | target preservation | background reduction | false positive | heuristic target ratio | Invalid reason |
|---|---:|---:|---:|---:|---:|---:|---|
| expert_manual | False | 2.0020 | 0.0005 | 0.9984 | 0.4014 | 7.8911 | zero-time/effective signal energy nearly disappeared |
| safe_default | False | 2.0020 | 0.0005 | 0.9984 | 0.4014 | 7.8911 | zero-time/effective signal energy nearly disappeared |
| auto_tuned | False | 1.7173 | 0.0003 | 0.9986 | 0.5111 | 135.9166 | zero-time/effective signal energy nearly disappeared |
| only_dewow_auto_tuned | False | 2.0093 | 0.0001 | 0.9998 | 0.4004 | 1.0868 | zero-time/effective signal energy nearly disappeared |
| only_frequency_filter_1d_auto_tuned | False | 2.0295 | 0.0005 | 0.9984 | 0.4006 | 11.2452 | zero-time/effective signal energy nearly disappeared |
| only_background_suppression_auto_tuned | False | 1.7169 | 0.0007 | 0.9961 | 0.5124 | 10.9107 | zero-time/effective signal energy nearly disappeared |
| only_gain_auto_tuned | False | 2.0020 | 0.0005 | 0.9984 | 0.4014 | 212.6982 | zero-time/effective signal energy nearly disappeared |

## Selected Auto Parameters
### auto_tuned
```json
{"dewow": {"best_score": -0.48414465115364763, "recommended_params": {"_low_energy_guard": true, "window": 18}, "risk_flags": ["low_selection_confidence", "multiple_near_optima"], "trial_count": 16}, "energy_decay_gain": {"best_score": 1.1007115005699672, "recommended_params": {"max_gain": 12.0, "smoothing_samples": 15, "strength": 1.2}, "risk_flags": ["low_selection_confidence", "best_params_at_edge"], "trial_count": 64}, "frequency_filter_1d": {"best_score": 3.3479136167729884, "recommended_params": {"filter_type": "bandpass", "high_freq_mhz": 2500.0, "low_freq_mhz": 5.0, "taper_ratio": 0.12}, "risk_flags": ["best_params_at_edge"], "trial_count": 8}, "set_zero_time": {"best_score": 0.0, "recommended_params": {"new_zero_time": 0.01179327168374842}, "risk_flags": ["low_selection_confidence", "multiple_near_optima", "best_params_at_edge"], "trial_count": 22}, "subtracting_average_2D": {"best_score": -3.074586411766034, "recommended_params": {"ntraces": 57}, "risk_flags": ["low_selection_confidence", "multiple_near_optima"], "trial_count": 17}}
```

### only_dewow_auto_tuned
```json
{"dewow": {"best_score": -0.49852068635900104, "recommended_params": {"_low_energy_guard": true, "window": 14}, "risk_flags": ["low_selection_confidence", "multiple_near_optima", "best_params_at_edge"], "trial_count": 16}}
```

### only_frequency_filter_1d_auto_tuned
```json
{"frequency_filter_1d": {"best_score": 3.2531572345742052, "recommended_params": {"filter_type": "bandpass", "high_freq_mhz": 2500.0, "low_freq_mhz": 150.0, "taper_ratio": 0.04}, "risk_flags": ["best_params_at_edge"], "trial_count": 8}}
```

### only_background_suppression_auto_tuned
```json
{"subtracting_average_2D": {"best_score": -3.072591079113673, "recommended_params": {"ntraces": 57}, "risk_flags": ["low_selection_confidence", "multiple_near_optima"], "trial_count": 17}}
```

### only_gain_auto_tuned
```json
{"energy_decay_gain": {"best_score": 1.2083692629379361, "recommended_params": {"max_gain": 12.0, "smoothing_samples": 15, "strength": 1.2}, "risk_flags": ["low_selection_confidence", "multiple_near_optima", "best_params_at_edge"], "trial_count": 64}}
```

## Sanity Warnings
- `expert_manual`: dewow: edge_preservation collapsed; dewow: ground-truth target energy preservation is very low; dewow: local_saliency_preservation collapsed; dewow: target_band_fidelity is very low; dewow: zero-time/effective signal energy nearly disappeared; energy_decay_gain: ground-truth target energy preservation is very low; frequency_filter_1d: ground-truth target energy preservation is very low; frequency_filter_1d: target_band_fidelity is very low; subtracting_average_2D: edge_preservation collapsed; subtracting_average_2D: ground-truth target energy preservation is very low; subtracting_average_2D: local_saliency_preservation collapsed; subtracting_average_2D: zero-time/effective signal energy nearly disappeared
- `safe_default`: dewow: edge_preservation collapsed; dewow: ground-truth target energy preservation is very low; dewow: local_saliency_preservation collapsed; dewow: target_band_fidelity is very low; dewow: zero-time/effective signal energy nearly disappeared; energy_decay_gain: ground-truth target energy preservation is very low; frequency_filter_1d: ground-truth target energy preservation is very low; frequency_filter_1d: target_band_fidelity is very low; subtracting_average_2D: edge_preservation collapsed; subtracting_average_2D: ground-truth target energy preservation is very low; subtracting_average_2D: local_saliency_preservation collapsed; subtracting_average_2D: zero-time/effective signal energy nearly disappeared
- `auto_tuned`: dewow: edge_preservation collapsed; dewow: ground-truth target energy preservation is very low; dewow: local_saliency_preservation collapsed; dewow: zero-time/effective signal energy nearly disappeared; energy_decay_gain: ground-truth target energy preservation is very low; frequency_filter_1d: ground-truth target energy preservation is very low; frequency_filter_1d: target_band_fidelity is very low; subtracting_average_2D: edge_preservation collapsed; subtracting_average_2D: ground-truth target energy preservation is very low; subtracting_average_2D: local_saliency_preservation collapsed; subtracting_average_2D: zero-time/effective signal energy nearly disappeared
- `only_dewow_auto_tuned`: dewow: edge_preservation collapsed; dewow: ground-truth target energy preservation is very low; dewow: local_saliency_preservation collapsed; dewow: target_band_fidelity is very low; dewow: zero-time/effective signal energy nearly disappeared; energy_decay_gain: ground-truth target energy preservation is very low; frequency_filter_1d: ground-truth target energy preservation is very low; frequency_filter_1d: target_band_fidelity is very low; subtracting_average_2D: edge_preservation collapsed; subtracting_average_2D: ground-truth target energy preservation is very low; subtracting_average_2D: local_saliency_preservation collapsed; subtracting_average_2D: zero-time/effective signal energy nearly disappeared
- `only_frequency_filter_1d_auto_tuned`: dewow: edge_preservation collapsed; dewow: ground-truth target energy preservation is very low; dewow: local_saliency_preservation collapsed; dewow: target_band_fidelity is very low; dewow: zero-time/effective signal energy nearly disappeared; energy_decay_gain: ground-truth target energy preservation is very low; frequency_filter_1d: ground-truth target energy preservation is very low; frequency_filter_1d: target_band_fidelity is very low; subtracting_average_2D: edge_preservation collapsed; subtracting_average_2D: ground-truth target energy preservation is very low; subtracting_average_2D: local_saliency_preservation collapsed; subtracting_average_2D: zero-time/effective signal energy nearly disappeared
- `only_background_suppression_auto_tuned`: dewow: edge_preservation collapsed; dewow: ground-truth target energy preservation is very low; dewow: local_saliency_preservation collapsed; dewow: target_band_fidelity is very low; dewow: zero-time/effective signal energy nearly disappeared; energy_decay_gain: ground-truth target energy preservation is very low; frequency_filter_1d: ground-truth target energy preservation is very low; frequency_filter_1d: target_band_fidelity is very low; subtracting_average_2D: edge_preservation collapsed; subtracting_average_2D: ground-truth target energy preservation is very low; subtracting_average_2D: local_saliency_preservation collapsed; subtracting_average_2D: zero-time/effective signal energy nearly disappeared
- `only_gain_auto_tuned`: dewow: edge_preservation collapsed; dewow: ground-truth target energy preservation is very low; dewow: local_saliency_preservation collapsed; dewow: target_band_fidelity is very low; dewow: zero-time/effective signal energy nearly disappeared; energy_decay_gain: ground-truth target energy preservation is very low; frequency_filter_1d: ground-truth target energy preservation is very low; frequency_filter_1d: target_band_fidelity is very low; subtracting_average_2D: edge_preservation collapsed; subtracting_average_2D: ground-truth target energy preservation is very low; subtracting_average_2D: local_saliency_preservation collapsed; subtracting_average_2D: zero-time/effective signal energy nearly disappeared

## Interpretation
- Result is inconclusive because no valid scored branch was available.
- The diagnostic ranking still records metric highs/lows, but those cannot be used as stage winners until sanity failures are resolved.

## Limitations
- AT-002 diagnoses stage-level behavior on one native gprMax benchmark; it is not a global AutoTune redesign.
- AutoTune scoring is unchanged; ground truth is used only after selection for validation and evidence.
- pipe_demo_longline_v1 is paper-usable for limited native gprMax claims, not field-data generalization.

## Known Risks
- A stage can improve heuristic QC while degrading ground-truth target preservation.
- Manual-vs-auto conclusions are invalid if branch sanity warnings indicate early signal loss.
- One 90-trace pipe scenario is insufficient to redesign scoring without more scenes.
