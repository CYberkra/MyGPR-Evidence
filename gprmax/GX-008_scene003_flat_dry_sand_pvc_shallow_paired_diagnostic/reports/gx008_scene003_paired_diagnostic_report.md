# GX-008 Scene003 Paired Diagnostic Report

## Artifact role
- synthetic_complete_2d_paired_diagnostic

## Source commit
- 25b491d3e254f7ed9f07159e8d555eb448994c8e

## Scene description
- scene_003_flat_dry_sand_pvc_shallow
- target material variation from PEC baseline to PVC under dry-sand shallow setup.

## Material summary
- Soil: dry_sand_like (eps_r=3.0, sigma=0.001)
- Target: pvc_like (draft dielectric)

## PVC material caveat
- pvc_like is draft parameterization; citation/validation lock is pending and this artifact must be interpreted with that caveat.

## Run backend
- GPU via scripts/run_gprmax_gpu_env.bat
- gprmax python: E:\gprMax\gprMax-v.3.1.7\.venv\Scripts\python.exe

## Run counts and shapes
- requested_num_runs: 41
- actual raw traces: 41
- actual background traces: 41
- raw shape: [936, 41]
- background shape: [936, 41]
- target_response shape: [936, 41]

## Pairing formula
- target_response = raw - background

## Why scene_003 matters
- isolates target material effect (PEC -> PVC) while keeping dry-sand shallow context.
- supports later checks for weak-target over-suppression risk in background suppression diagnostics.

## Included files
- manifests/evidence_manifest.json
- reports/paired_target_response_report.md
- reports/paired_report_summary.json
- tables/convert_summary_41.json
- tables/pair_preview_generic_41.json
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

## Excluded native outputs
- .out, .h5, .vti, .vtk, .vtu, .npy

## Claim boundary
- synthetic scene_003 only
- not field validation
- not AutoTune evaluation
- not AutoTune superiority evidence
- not paper-candidate benchmark

## Recommended use
- synthetic paired diagnostic reference for scene_003 PVC shallow variation.

## Do-not-use-as
- field-ground-truth validation
- AutoTune superiority claim
- full benchmark completion claim
