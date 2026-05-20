# GX-004 Native Benchmark Report

## Status
- Scenario ID: `gx004_no_target_false_positive_control_v1`
- Generation status: `complete`
- Source repo: `https://github.com/CYberkra/MyGPR`
- Source branch: `codex/research-gprmax-autotune`
- Source commit: `a423072be4c2a9ae29708aef18e165d4c2cd053d`
- gprMax version: `3.1.6`

## Purpose
- No-target false-positive control

## Native Run Environment And Commands
- gprMax environment: `E:/gprMax/gprMax-v.3.1.7/.venv/Scripts/python.exe`
- Run command: `E:\gprMax\gprMax-v.3.1.7\.venv\Scripts\python.exe -m gprMax model.in -n 105`
- Merge command: `E:\gprMax\gprMax-v.3.1.7\.venv\Scripts\python.exe -m tools.outputfiles_merge <basefilename> --remove-files`
- Conversion command: `python scripts/gprmax_benchmark/prepare_native_gprmax_package.py --model-in ... --out ... --receiver rx1 --component Ez --scenario-id gx004_no_target_false_positive_control_v1`

## Geometry / Material / Acquisition Summary
- Domain: `1.20 x 0.60 x 0.002 m`
- Grid: `dx=dy=dz=0.002 m`
- Source/receiver step: `0.01 m`
- Trace count: `105`
- Sample count: `4241`
- Time window: `20.006106084310822 ns`
- Receiver/component: `rx1/Ez`

## Generated Files
- model: `model/model.in`
- native output: `native/model_merged.out`
- converted CSV: `converted/data.csv`
- preview: `figures/raw_bscan_preview.png`
- ROI overlay: `figures/roi_overlay.png`
- benchmark manifest: `manifests/benchmark_manifest.json`
- ground truth: `manifests/ground_truth.json`
- ROI table: `tables/roi_definitions.csv`

## Hashes
- model hash: `8d2adf52e5da2c2cf639393ac2fb1ad33e7066452ff4e2aaf73c2a47372b46e6`
- native output hash: `ca3c64e6afd1504c1fd7c32a1a91fe5f9e8ed2cc06b809f9b9f94cbad1fe7d6b`
- converted CSV hash: `585d1d8be9eccc7ef50c5047b5e209a4025fa94b4139bbe280a003295138c0c7`

## Notes On Model Sanity Fixes
- `##title` was corrected to `#title` for valid gprMax syntax.
- Tx/Rx x-start positions were shifted inward (`0.09/0.13 m`) to keep the 105-trace path away from the x-boundary.
- GX-004 `#hertzian_dipole` line was fixed to include waveform name `my_ricker`.

## Limitations
- The generic package audit script is target-centric and reports a target-ROI error for this no-target control scene; this is expected and does not invalidate GX-004 design intent.
- Thin 2D z-dimension approximation is used and must be disclosed in downstream claims.
- Synthetic scene benchmark does not validate field-flight performance.
- This package completion task does not run AutoTune validation.

## Explicit Non-Claims
- No target-preservation claim is allowed for GX-004 because no true target exists.
- No preset promotion or AutoTune superiority claim is made in this task.
