# GX-006 Native Benchmark Report

## Status
- Scenario ID: `gx006_layered_complex_background_v1`
- Generation status: `complete`
- Source repo: `https://github.com/CYberkra/MyGPR`
- Source branch: `codex/research-gprmax-autotune`
- Source commit: `a423072be4c2a9ae29708aef18e165d4c2cd053d`
- gprMax version: `3.1.6`

## Purpose
- Layered complex-background

## Native Run Environment And Commands
- gprMax environment: `E:/gprMax/gprMax-v.3.1.7/.venv/Scripts/python.exe`
- Run command: `E:\gprMax\gprMax-v.3.1.7\.venv\Scripts\python.exe -m gprMax model.in -n 105`
- Merge command: `E:\gprMax\gprMax-v.3.1.7\.venv\Scripts\python.exe -m tools.outputfiles_merge <basefilename> --remove-files`
- Conversion command: `python scripts/gprmax_benchmark/prepare_native_gprmax_package.py --model-in ... --out ... --receiver rx1 --component Ez --scenario-id gx006_layered_complex_background_v1`

## Geometry / Material / Acquisition Summary
- Domain: `1.20 x 0.60 x 0.002 m`
- Grid: `dx=dy=dz=0.002 m`
- Source/receiver step: `0.01 m`
- Trace count: `105`
- Sample count: `5089`
- Time window: `24.006383839438286 ns`
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
- model hash: `0b5f25b1e4a5b5c855be13abf65065f65e5dfd531bcbb0c47a6b6b05084ae89f`
- native output hash: `ed37f9daaa0e06ecc9646a454781188b140cb573e51717e81493ecd70d7c3fed`
- converted CSV hash: `78bc1d6639a14d4247348580b34e4c584052d52f096d10c43c635bf4179c1acd`

## Notes On Model Sanity Fixes
- `##title` was corrected to `#title` for valid gprMax syntax.
- Tx/Rx x-start positions were shifted inward (`0.09/0.13 m`) to keep the 105-trace path away from the x-boundary.
- GX-004 `#hertzian_dipole` line was fixed to include waveform name `my_ricker`.

## Limitations
- Thin 2D z-dimension approximation is used and must be disclosed in downstream claims.
- Synthetic scene benchmark does not validate field-flight performance.
- This package completion task does not run AutoTune validation.

## Explicit Non-Claims
- Layer-interface suppression is not automatically an improvement in GX-006.
- No preset promotion or AutoTune superiority claim is made in this task.
