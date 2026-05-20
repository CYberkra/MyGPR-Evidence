# AT-005A No-Zero-Time Gain Validation

## Metadata
- Source commit: `61ad8a3ac55d9e604f802b9c8ca8ddb3474b65ad`
- Dataset: `pipe_demo_longline_v1` shape `[2037, 90]`
- Zero-time policy: `excluded`
- GX-003 ROI is used as-is; candidate ROI is not substituted.
- GX-003 metrics separate ground truth ROI diagnostics from display-oriented heuristic QC.
- Field lane, if present, is heuristic / visual QC only.
- AGC is display-oriented and non-amplitude-preserving.

## Conclusions
- Best visual gain variant: `energy_decay_gain`
- Most conservative/interpretable gain variant: `energy_decay_gain`
- AutoTune status: `improved_on_roi_contrast_metric_only_not_overall_claim`
- Field lane status: `skipped`
- 100-round loop completed: `True`

## Lane Summary
| Lane | Branch | Gain | ROI contrast | Clipping | Validity | Figure |
|---|---|---|---:|---:|---|---|
| `lane_0_raw_input` | `raw` | `none` | 133.9 | 0.001004 | `valid_with_caveats` | `figures/lane_0_raw_input.png` |
| `lane_1_background_only` | `manual` | `none` | 20.24 | 0.001004 | `valid_with_caveats` | `figures/lane_1_background_only.png` |
| `lane_2_background_energy_decay_gain` | `manual` | `energy_decay_gain` | 20.28 | 0.001004 | `valid_with_caveats` | `figures/lane_2_background_energy_decay_gain.png` |
| `lane_2b_background_sec_gain` | `manual` | `sec_gain` | 17.6 | 0.001004 | `valid_with_caveats` | `figures/lane_2b_background_sec_gain.png` |
| `lane_3_background_time_power_gain` | `manual` | `time_power_gain_local` | 17.14 | 0.001004 | `valid_with_caveats` | `figures/lane_3_background_time_power_gain.png` |
| `lane_4_background_agc_gain` | `manual` | `agcGain` | 4.025 | 0.001004 | `valid_with_caveats` | `figures/lane_4_background_agc_gain.png` |
| `lane_5_dewow256_background_energy_decay` | `diagnostic` | `energy_decay_gain` | 14.15 | 0.001004 | `valid_with_caveats` | `figures/lane_5_dewow256_background_energy_decay.png` |
| `lane_6_dewow512_background_energy_decay` | `diagnostic` | `energy_decay_gain` | 19.93 | 0.001004 | `valid_with_caveats` | `figures/lane_6_dewow512_background_energy_decay.png` |
| `lane_7_filter_background_energy_decay` | `diagnostic` | `energy_decay_gain` | 12.27 | 0.001004 | `valid_with_caveats` | `figures/lane_7_filter_background_energy_decay.png` |
| `lane_8_dewow256_filter_background_energy_decay` | `diagnostic` | `energy_decay_gain` | 9.774 | 0.001004 | `valid_with_caveats` | `figures/lane_8_dewow256_filter_background_energy_decay.png` |
| `lane_auto_background_energy_decay` | `auto_tuned` | `energy_decay_gain` | 45.25 | 0.001004 | `valid_with_caveats` | `figures/lane_auto_background_energy_decay.png` |

## Next Recommended Task
Fix the gprMax/native data-context zero-time default or lane policy first, then rerun AT-002/AT-003 with no-zero-time and safer dewow windows before changing AutoTune scoring.

## Known Risks
- Zero-time is intentionally excluded; this artifact does not repair zero-time correction.
- AGC is display-oriented and non-amplitude-preserving.
- Field lane is visual/heuristic QC only and has no ground-truth claims.
- GX-003 ROI is used as-is; candidate ROI from AT-004 is not substituted.
