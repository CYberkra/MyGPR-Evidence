# AT-BG-004B Multi-Scene Comparison Report

## Artifact Role
synthetic_background_suppression_multi_scene_diagnostic_comparison

## Input Artifacts
- `autotune/AT-BG-003_GX008_scene001_background_suppression_diagnostic/`
- `autotune/AT-BG-004A_GX008_scene002_background_suppression_diagnostic/`

## Parent Paired Artifacts
- `gprmax/GX-008_scene001_flat_dry_sand_pec_shallow_paired_diagnostic/` (dry sand)
- `gprmax/GX-008_scene002_flat_damp_sand_pec_shallow_paired_diagnostic/` (damp sand)

## Candidate Methods
- mean background subtraction
- median background subtraction
- SVD background suppression

## Per-Scene Selected Results
- scene_001: selected_trial_id=trial_003, method=mean_background_subtraction, params={'mode': 'moving_window_mean', 'window_size': 5, 'axis': 'trace'}, metrics={'mae': 0.029371318842451328, 'mse': 0.00880796154825314, 'rmse': 0.09385074079757251, 'psnr': 16.370642559430287}, warnings=[]
- scene_002: selected_trial_id=trial_003, method=mean_background_subtraction, params={'mode': 'moving_window_mean', 'window_size': 5, 'axis': 'trace'}, metrics={'mae': 0.011964291100524606, 'mse': 0.0013645776488880094, 'rmse': 0.036940190157713174, 'psnr': 15.05181790956213}, warnings=[]

## Cross-Scene Consistency Analysis
- selected method matches: True
- selected parameters match: True
- both scenes selected trial_003 under current scoring: True
- top-ranked candidates are similar in both scenes under the current 17-trial grid.
- warning pattern: both selected trials have no warnings.
- damp-sand scene did not change selected method/parameter under the current diagnostic setup.

## Conservative Interpretation
This is a two-scene diagnostic comparison and a preliminary consistency observation. Under current scoring and candidate grid, scene_001 and scene_002 selected the same trial. This supports further testing on more GX-008 scenes.

## Claim Boundary
- synthetic paired GX-008 scene_001 and scene_002 only
- background suppression diagnostic only
- fixed-workflow parameter recommendation slice
- not full AutoTune
- not production scoring
- not field validation
- not no-prior truth correctness
- not AutoTune superiority evidence
- not paper-candidate benchmark

## Recommended Next Task
- GX-008-EXPAND-001: add additional target/material/depth scenes
- or AT-BG-005-REPORT-VISUALS: generate non-array preview comparison figures
- or UI-BG-AUTOTUNE-PANEL-SPEC: later frontend panel spec only
