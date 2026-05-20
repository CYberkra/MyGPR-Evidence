# AT-004 ROI / Zero-Time / Dewow Triage

## Scope
- AT-002 remains `inconclusive`.
- This run does not change AutoTune scoring, motion compensation, or processing_engine behavior.
- Candidate ROI is diagnostic only and does not silently replace GX-003 ground truth.

## Dataset
- Scenario: `pipe_demo_longline_v1`
- Shape: `[2037, 90]`
- Source commit: `df5abc89ba6ee51675df745fdd465fc62930ebd6`
- GX-003 ROI: `{'time_start_idx': 760, 'time_end_idx': 883, 'dist_start_idx': 38, 'dist_end_idx': 51}`
- Candidate ROI: `{'time_start_idx': 788, 'time_end_idx': 911, 'dist_start_idx': 38, 'dist_end_idx': 51}`

## ROI Review
- GX-003 ROI local-background contrast: `133.9`
- Candidate ROI local-background contrast: `717.1`
- Corrected ROI recommended: `False`
- Overlay: `figures/input_bscan_roi_overlay.png`

## Root-Cause Classification
- ROI status: `usable_but_visual_review_required`
- Zero-time status: `problem`
- Dewow status: `parameter_domain_can_preserve_roi`
- Recommended next fix: `zero_time_defaults`
- Best dewow experiment: `zero0_dewow_window_256`
- Best dewow ROI energy ratio: `1.039`
- Safe default global energy ratio: `0.002239`

Findings:
- GX-003 ROI is not clearly invalid by local contrast alone.
- Registry default zero-time shifts a large sample interval and collapses global energy.
- At least one dewow window preserves enough tracked ROI energy for further tuning.

## Experiment Table
| Experiment | Shift samples | ROI energy ratio | Global energy ratio | ROI local contrast | Candidate local contrast | Overlay |
|---|---:|---:|---:|---:|---:|---|
| no_zero_time_no_dewow | 0 | 1 | 1 | 133.9 | 717.1 | `figures/no_zero_time_no_dewow_roi_overlay.png` |
| zero_time_fixed_0_dewow_off | 0 | 1 | 1 | 133.9 | 717.1 | `figures/zero_time_fixed_0_dewow_off_roi_overlay.png` |
| safe_default_zero_time_only | 423 | 1 | 0.002239 | 133.9 | 2.659 | `figures/safe_default_zero_time_only_roi_overlay.png` |
| zero0_dewow_window_5 | 0 | 2.308e-05 | 2.457e-05 | 38.31 | 336 | `figures/zero0_dewow_window_5_roi_overlay.png` |
| zero0_dewow_window_11 | 0 | 0.0002797 | 0.000298 | 38.24 | 331.8 | `figures/zero0_dewow_window_11_roi_overlay.png` |
| zero0_dewow_window_23 | 0 | 0.003705 | 0.003958 | 37.97 | 312.7 | `figures/zero0_dewow_window_23_roi_overlay.png` |
| zero0_dewow_window_64 | 0 | 0.1242 | 0.1353 | 36.3 | 205.7 | `figures/zero0_dewow_window_64_roi_overlay.png` |
| zero0_dewow_window_128 | 0 | 0.7317 | 0.8386 | 34.34 | 81.43 | `figures/zero0_dewow_window_128_roi_overlay.png` |
| zero0_dewow_window_256 | 0 | 1.039 | 1.114 | 33.47 | 64.96 | `figures/zero0_dewow_window_256_roi_overlay.png` |
| zero0_dewow_window_512 | 0 | 1.004 | 0.9995 | 131.9 | 457.3 | `figures/zero0_dewow_window_512_roi_overlay.png` |

## Decision Boundary
- Do not claim AutoTune improvement from this artifact.
- Do not replace GX-003 ROI without a separate benchmark/ground-truth revision.
- If fixing next, prioritize the classified target above, then rerun AT-002/AT-003.
