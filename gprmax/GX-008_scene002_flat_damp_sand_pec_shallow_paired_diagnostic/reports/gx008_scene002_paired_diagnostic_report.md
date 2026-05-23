# GX-008 Scene 002 Paired Diagnostic Report

## Artifact Role
synthetic_complete_2d_paired_diagnostic

## Source Commit
- source repo: https://github.com/CYberkra/MyGPR
- source branch: `main`
- source commit: `12848a580aa0b8086576ecb946a7beef138349de`

## Scene Description
- campaign: `GX-008_paired_synthetic_mini_benchmark`
- scene: `scene_002_flat_damp_sand_pec_shallow`
- pair formula: `target_response = raw - background`

## Material Summary
- background: damp_sand_like (GX-008 synthetic scene config)
- target: PEC cylinder (shallow target, paired removed in background run)

## Run Backend
- final backend: GPU via `scripts/run_gprmax_gpu_env.bat`
- gprMax runtime: `E:\gprMax\gprMax-v.3.1.7\.venv\Scripts\python.exe`
- gpu device: `0`

## Run and Shape Summary
- requested_num_runs: `41`
- actual_raw_trace_count: `41`
- actual_background_trace_count: `41`
- raw shape: `[936, 41]`
- background shape: `[936, 41]`
- target_response shape: `[936, 41]`

## Included Files
- manifests/evidence_manifest.json
- reports/gx008_scene002_paired_diagnostic_report.md
- reports/paired_target_response_report.md
- reports/paired_report_summary.json
- tables/convert_summary_41.json
- tables/paired_metrics.json
- tables/paired_validation_summary.json
- arrays/raw_bscan.csv
- arrays/background_bscan.csv
- arrays/target_response.csv
- figures/raw_preview.png
- figures/background_preview.png
- figures/target_response_preview.png
- figures/paired_preview_panel.png
- logs/raw_run_manifest.json
- logs/background_run_manifest.json
- logs/raw_stdout.log
- logs/raw_stderr.log
- logs/background_stdout.log
- logs/background_stderr.log

## Excluded Native Outputs
This curated package excludes native gprMax outputs and bulky intermediates:
- `.out`
- `.h5`
- `.vti`
- `.vtk`
- `.vtu`
- `.npy`

## Recommended Use
- backend conversion/pairing/preview reproducibility checks
- synthetic paired diagnostic inspection
- fixed-scene processing sanity reference

## Do-Not-Use-As
- field validation evidence
- AutoTune evaluation evidence
- AutoTune superiority evidence
- paper-candidate benchmark
- full CLT-GPR dataset replication

## Claim Boundary
- synthetic GX-008 scene_002 only
- small-scale complete 2D paired diagnostic artifact
- paper-inspired mini benchmark scene, not full benchmark completion
- not field validation
- not AutoTune evaluation
- not AutoTune superiority evidence
- not paper-candidate benchmark
- not representative CLT-GPR-style dataset replication
