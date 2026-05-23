# AT-BG-004A Evidence Summary

## Artifact Role
synthetic_background_suppression_autotune_diagnostic

## Parent Artifact
- `gprmax/GX-008_scene002_flat_damp_sand_pec_shallow_paired_diagnostic/`

## Source Commit
- `12848a580aa0b8086576ecb946a7beef138349de`

## Input Arrays
- raw: `gprmax/GX-008_scene002_flat_damp_sand_pec_shallow_paired_diagnostic/arrays/raw_bscan.csv`
- target_response: `gprmax/GX-008_scene002_flat_damp_sand_pec_shallow_paired_diagnostic/arrays/target_response.csv`
- input_shape: `[936, 41]`

## Candidate Methods
- mean background subtraction
- median background subtraction
- SVD background suppression

## Candidate Grid
- default AT-BG diagnostic v1 grid (17 trials total)

## Trial Result
- trial_count: `17`
- selected_trial_id: `trial_003`
- selected_method: `mean_background_subtraction`
- selected_parameters: `{'mode': 'moving_window_mean', 'window_size': 5, 'axis': 'trace'}`

## Top Candidates Summary
- trial_003: method=mean_background_subtraction, params={'mode': 'moving_window_mean', 'window_size': 5, 'axis': 'trace'}, score(mae/rmse/psnr)=(0.011964291100524606, 0.036940190157713174, 15.05181790956213), label=recommended
- trial_001: method=mean_background_subtraction, params={'mode': 'global_mean', 'axis': 'trace'}, score(mae/rmse/psnr)=(0.011964291100524714, 0.036940190157713174, 15.05181790956213), label=acceptable_alternative
- trial_004: method=mean_background_subtraction, params={'mode': 'moving_window_mean', 'window_size': 9, 'axis': 'trace'}, score(mae/rmse/psnr)=(0.01196429110052486, 0.036940190157713174, 15.05181790956213), label=acceptable_alternative
- trial_005: method=mean_background_subtraction, params={'mode': 'moving_window_mean', 'window_size': 15, 'axis': 'trace'}, score(mae/rmse/psnr)=(0.011964291100525428, 0.036940190157713174, 15.05181790956213), label=acceptable_alternative
- trial_006: method=mean_background_subtraction, params={'mode': 'moving_window_mean', 'window_size': 21, 'axis': 'trace'}, score(mae/rmse/psnr)=(0.011964291100525586, 0.036940190157713174, 15.05181790956213), label=acceptable_alternative

## Differences from Scene 001
- same harness and candidate family (mean/median/SVD)
- this artifact uses GX-008 scene_002 (damp sand) paired input
- multi-scene comparative conclusion should be done in AT-BG-004B

## Output Files Included
- manifests/evidence_manifest.json
- manifests/background_suppression_autotune_manifest.json
- reports/background_suppression_autotune_report.md
- reports/at_bg_004a_evidence_summary.md
- tables/trial_table.json
- tables/trial_table.csv
- tables/selected_parameters.json

## Files Excluded
- processed arrays
- `.out`, `.h5`, `.vti`, `.vtk`, `.vtu`, `.npy`
- unrelated scratch directories and unrelated dirty files

## Claim Boundary
- synthetic paired diagnostic only
- background suppression only
- not full AutoTune
- not production scoring
- not field validation
- not no-prior truth correctness
- not AutoTune superiority evidence
- not paper-candidate benchmark

## Recommended Next Task
- `AT-BG-004B-MULTI-SCENE-COMPARISON`
