# GX-007 Scene001 Complete 2D Diagnostic Evidence Report

## Summary
- artifact_id: `GX-007_scene001_complete_2d_diagnostic`
- source commit: `adb8ab7c102208f1aeb2d92cc5d09c0a6fdb6606`
- artifact role: `synthetic_complete_2d_paired_diagnostic`
- final backend: `CPU`
- requested_num_runs: `21`
- actual_raw_trace_count: `21`
- actual_background_trace_count: `21`

## Shapes
- raw shape: `[936, 21]`
- background shape: `[936, 21]`
- target_response shape: `[936, 21]`

## Included Curated Files
- arrays: `raw_bscan.*`, `background_bscan.*`, `target_response.*`
- tables: `paired_validation_summary.json`, `paired_metrics.json`
- figures: `raw_preview.png`, `background_preview.png`, `target_response_preview.png`, `paired_preview_panel.png`
- reports: `paired_target_response_report.md`, `paired_report_summary.json`

## Key Metrics
- raw_energy: `5370261.438142946`
- background_energy: `5369559.785661268`
- target_response_energy: `701.656608797365`
- target_to_background_energy_ratio: `0.0001306730228930592`

## GPU Status
- GPU is optional acceleration for this pipeline.
- This curated artifact is finalized from CPU complete 2D outputs.
- A later GPU diagnostic failure log exists in the workspace run folder and is intentionally excluded from this curated artifact.

## Claim Boundary
- synthetic GX-007 scene_001 only
- small-scale complete 2D paired diagnostic
- not field validation
- not AutoTune evaluation
- not AutoTune superiority evidence
- not paper-candidate benchmark
