# Background Suppression AutoTune Diagnostic Report

- artifact_id: `GX-008_scene001_flat_dry_sand_pec_shallow_paired_diagnostic`
- scene_id: `scene_001_flat_dry_sand_pec_shallow`
- trial_count: `17`
- scoring_rule: primary mae asc, tie rmse asc, then psnr desc, with warning penalties and optional ROI preservation penalty
- diagnostic_scope: background suppression only

## Input Paths

- raw: `D:\CDUT-UavGPR-Controller\MyGPR-Evidence\gprmax\GX-008_scene001_flat_dry_sand_pec_shallow_paired_diagnostic\arrays\raw_bscan.csv`
- target_response: `D:\CDUT-UavGPR-Controller\MyGPR-Evidence\gprmax\GX-008_scene001_flat_dry_sand_pec_shallow_paired_diagnostic\arrays\target_response.csv`
- roi_json: ``

## Candidate Grid

- mean_background_subtraction | group=mean | params={"mode": "global_mean", "axis": "trace"}
- median_background_subtraction | group=median | params={"mode": "global_median", "axis": "trace"}
- mean_background_subtraction | group=mean | params={"mode": "moving_window_mean", "window_size": 5, "axis": "trace"}
- mean_background_subtraction | group=mean | params={"mode": "moving_window_mean", "window_size": 9, "axis": "trace"}
- mean_background_subtraction | group=mean | params={"mode": "moving_window_mean", "window_size": 15, "axis": "trace"}
- mean_background_subtraction | group=mean | params={"mode": "moving_window_mean", "window_size": 21, "axis": "trace"}
- mean_background_subtraction | group=mean | params={"mode": "moving_window_mean", "window_size": 31, "axis": "trace"}
- mean_background_subtraction | group=mean | params={"mode": "moving_window_mean", "window_size": 41, "axis": "trace"}
- median_background_subtraction | group=median | params={"mode": "moving_window_median", "window_size": 5, "axis": "trace"}
- median_background_subtraction | group=median | params={"mode": "moving_window_median", "window_size": 9, "axis": "trace"}
- median_background_subtraction | group=median | params={"mode": "moving_window_median", "window_size": 15, "axis": "trace"}
- median_background_subtraction | group=median | params={"mode": "moving_window_median", "window_size": 21, "axis": "trace"}
- median_background_subtraction | group=median | params={"mode": "moving_window_median", "window_size": 31, "axis": "trace"}
- median_background_subtraction | group=median | params={"mode": "moving_window_median", "window_size": 41, "axis": "trace"}
- svd_background_suppression | group=svd | params={"remove_rank": 1}
- svd_background_suppression | group=svd | params={"remove_rank": 2}
- svd_background_suppression | group=svd | params={"remove_rank": 3}

## Top Ranked Candidates

- trial_003: method=mean_background_subtraction, params={"mode": "moving_window_mean", "window_size": 5, "axis": "trace"}, label=recommended, mae=0.029371318842451328, rmse=0.09385074079757251, psnr=16.370642559430287
- trial_001: method=mean_background_subtraction, params={"mode": "global_mean", "axis": "trace"}, label=acceptable_alternative, mae=0.029371318842451418, rmse=0.09385074079757251, psnr=16.370642559430287
- trial_004: method=mean_background_subtraction, params={"mode": "moving_window_mean", "window_size": 9, "axis": "trace"}, label=acceptable_alternative, mae=0.02937131884245153, rmse=0.0938507407975725, psnr=16.370642559430287
- trial_005: method=mean_background_subtraction, params={"mode": "moving_window_mean", "window_size": 15, "axis": "trace"}, label=acceptable_alternative, mae=0.02937131884245209, rmse=0.0938507407975725, psnr=16.370642559430287
- trial_015: method=svd_background_suppression, params={"remove_rank": 1}, label=acceptable_alternative, mae=0.029371318842452216, rmse=0.09385074079757252, psnr=16.370642559430287

## Selected Parameter

- selected_trial: `trial_003` (mean_background_subtraction) {"mode": "moving_window_mean", "window_size": 5, "axis": "trace"}

## Warnings Summary

- total_warnings: `7`

## Claim Boundary

- This harness is diagnostic-only and not production AutoTune scoring.
- This output is not AutoTune superiority evidence.
- This output is not field no-prior underground correctness evidence.
