# AT-008A No-Dewow Post-Fix Native Validation

## Metadata
- Source commit: `13335f7e02834b19814ecb07aae01b6053ecc765`
- Dataset: `pipe_demo_longline_v1` shape `[2037, 90]`
- Ground truth: `available`
- Zero-time policy: `excluded`
- Dewow policy: `excluded_primary_optional_diagnostic_side_lanes`
- GX-003 ROI is used as-is.

## Core conclusion
- Primary lane excludes both `set_zero_time` and `dewow`.
- Dewow remains optional diagnostic side-lane; it is not deleted or globally invalidated.
- Primary branch validity: `all_valid_with_caveats`
- Best gain variant (primary lanes): `energy_decay_gain`
- AutoTune status: `improved_on_limited_contrast_metric_only`

## Lane summary
| Lane | Branch | Dewow policy | Gain | ROI contrast | Clipping | Validity | Figure |
|---|---|---|---|---:|---:|---|---|
| `lane_0_raw_input` | `raw` | `excluded_primary` | `none` | 133.9 | 0.001004 | `valid_with_caveats` | `figures/lane_0_raw_input.png` |
| `lane_1_background_only` | `manual` | `excluded_primary` | `none` | 20.24 | 0.001004 | `valid_with_caveats` | `figures/lane_1_background_only.png` |
| `lane_2_background_energy_decay_gain` | `manual` | `excluded_primary` | `energy_decay_gain` | 20.28 | 0.001004 | `valid_with_caveats` | `figures/lane_2_background_energy_decay_gain.png` |
| `lane_3_background_sec_gain` | `manual` | `excluded_primary` | `sec_gain` | 17.6 | 0.001004 | `valid_with_caveats` | `figures/lane_3_background_sec_gain.png` |
| `lane_4_background_time_power_gain` | `manual` | `excluded_primary` | `time_power_gain_local` | 17.14 | 0.001004 | `valid_with_caveats` | `figures/lane_4_background_time_power_gain.png` |
| `lane_5_background_agc_gain` | `manual` | `excluded_primary` | `agcGain` | 4.025 | 0.001004 | `valid_with_caveats` | `figures/lane_5_background_agc_gain.png` |
| `lane_auto_background_energy_decay` | `auto_tuned` | `excluded_primary` | `energy_decay_gain` | 45.25 | 0.001004 | `valid_with_caveats` | `figures/lane_auto_background_energy_decay.png` |
| `lane_6_dewow256_background_energy_decay` | `diagnostic` | `fixed_diagnostic_window_256` | `energy_decay_gain` | 14.15 | 0.001004 | `valid_with_caveats` | `figures/lane_6_dewow256_background_energy_decay.png` |
| `lane_7_dewow512_background_energy_decay` | `diagnostic` | `fixed_diagnostic_window_512` | `energy_decay_gain` | 19.93 | 0.001004 | `valid_with_caveats` | `figures/lane_7_dewow512_background_energy_decay.png` |

## Before / after reference
| Comparison | Before | After | Interpretation |
|---|---|---|---|
| AT-007_first_failing_step | dewow | no_dewow_primary_lane | AT-007 first failing step was dewow; AT-008A primary lane excludes dewow. |
| Best visual gain variant | energy_decay_gain | energy_decay_gain | Cross-check against AT-005A no-zero-time benchmark. |
| Primary lane validity (AT-008A) | AT-007 validity remained 0->0 | all_valid_with_caveats | Checks whether no-dewow primary lanes avoid AT-007 failure mode. |

## Known risks
- Single native gprMax scene remains insufficient for broad generalization.
- Dewow is excluded in the primary lane for this artifact; this is not a global dewow deprecation.
- AGC visual clarity cannot be treated as physical amplitude correctness.
