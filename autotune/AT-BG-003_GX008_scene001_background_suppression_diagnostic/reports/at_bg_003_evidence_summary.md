# AT-BG-003 Evidence Summary

- artifact_role: `synthetic_background_suppression_autotune_diagnostic`
- parent_artifact: `gprmax/GX-008_scene001_flat_dry_sand_pec_shallow_paired_diagnostic/`
- source_commit: `817bf55f1e9cb3ed91da96693964b4492aa75d5a`
- scene_id: `scene_001_flat_dry_sand_pec_shallow`
- input_shape: `[936, 41]`
- input_arrays:
  - `raw_bscan.csv`
  - `target_response.csv`

## Candidate Methods

- `mean_background_subtraction`
- `median_background_subtraction`
- `svd_background_suppression`

## Candidate Grid

- mean: global + moving window `[5, 9, 15, 21, 31, 41]`
- median: global + moving window `[5, 9, 15, 21, 31, 41]`
- svd: `remove_rank` `[1, 2, 3]`

## Trial Results

- trial_count: `17`
- selected_trial_id: `trial_003`
- selected_method: `mean_background_subtraction`
- selected_params: `{"mode":"moving_window_mean","window_size":5,"axis":"trace"}`

Top candidates (from `trial_table.json`):

1. `trial_003`: mean moving window 5, mae=0.029371318842451328, rmse=0.09385074079757251, psnr=16.370642559430287
2. `trial_001`: mean global, mae=0.029371318842451418
3. `trial_004`: mean moving window 9, mae=0.02937131884245153

## Output Files Included

- `manifests/evidence_manifest.json`
- `manifests/background_suppression_autotune_manifest.json`
- `reports/background_suppression_autotune_report.md`
- `reports/at_bg_003_evidence_summary.md`
- `tables/trial_table.json`
- `tables/trial_table.csv`
- `tables/selected_parameters.json`

## Files Excluded

- gprMax native outputs (`.out`, `.h5`, `.vti`, `.vtk`, `.vtu`)
- `.npy` arrays
- processed candidate arrays
- unrelated `scratch/` content outside selected files
- unrelated DS-001 dirty files

## Claim Boundary

- synthetic paired diagnostic only (GX-008 scene_001)
- background suppression scope only
- not full AutoTune
- not production scoring
- not field validation
- not no-prior truth correctness evidence
- not AutoTune superiority evidence

## Recommended Next Task

- `AT-BG-004-REVIEW-PIPELINE`: wire trial_table + selected_parameters into read-only evidence viewer/report aggregation (still no production scoring change).
