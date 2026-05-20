# GX-006 Layered Complex Background

## Status
- Artifact ID: `GX-006`
- Scenario ID: `gx006_layered_complex_background_v1`
- Generation status: `pending_native_output`
- Source repo: `https://github.com/CYberkra/MyGPR`
- Source branch: `codex/research-gprmax-autotune`
- Source commit: `a423072be4c2a9ae29708aef18e165d4c2cd053d`

## Scenario Purpose
Background-structure preservation benchmark under layered clutter.

## Model Geometry And Materials
- Domain 1.20x0.60x0.002 m, dx=dy=dz=0.002 m, thin 2D z-dimension.
- Time window: `24.0 ns`
- Trace spacing: `0.01 m`
- Planned trace count: `105`
- Materials: `layer_top(er=6.0,sigma=0.005); layer_mid(er=9.0,sigma=0.01); layer_deep(er=12.0,sigma=0.02); target_fill(er=5.5,sigma=0.003)`

## Source / Receiver Configuration
- Tx start (0.12,0.30,0), Rx start (0.16,0.30,0), src/rx step 0.01 m along +x.

## Target / Layer Summary
- Layered interfaces plus optional medium-depth target.

## ROI And Negative-Control Setup
- ROI table: `tables/roi_definitions.csv`
- Ground-truth manifest: `manifests/ground_truth.json`
- Negative-control ROIs are mandatory and included.

## Generated Files In This Task
- `model/model.in`
- `manifests/benchmark_manifest.json`
- `manifests/pending_native_output.json`
- `manifests/ground_truth.json`
- `tables/roi_definitions.csv`
- `tables/metadata_summary.csv`

## Missing Files (Pending Native Output)
- `native/native.out` or `native/*_merged.out`
- `converted/data.csv`
- `figures/raw_bscan_preview.png`
- `figures/roi_overlay.png`

## Required Next Commands
1. `gprMax model/model.in`
2. `python scripts/gprmax_benchmark/prepare_native_gprmax_package.py --model-in model/model.in --out <native_out_or_merged_out> --output-dir <local_package_dir> --receiver rx1 --component Ez --scenario-id gx006_layered_complex_background_v1 --ground-truth manifests/ground_truth.json`
3. `python scripts/gprmax_benchmark/audit_gprmax_package.py --package <local_package_dir> --output-json <local_package_dir>/gprmax_package_audit.json`

## Limitations
- Native gprMax output is not generated in this task, so no converted CSV or B-scan figure is provided yet.
- Thin 2D z-dimension approximation is used; report this limitation in every downstream benchmark claim.
- Synthetic scene evidence does not validate field-flight performance.

## Explicit Non-Claims
- Layer-interface suppression is not automatically an improvement.
- This task does not run AutoTune validation and does not promote any preset.
