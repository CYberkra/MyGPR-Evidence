# GX-007 Scene001 Conversion/Pairing Evidence Report

## 1. Summary

- conversion: success
- pairing: success
- preview: success
- source commit: `69a9f5bbcb9d697c59d8c5d49012eae727906917`
- output shape warning: `936 x 1` (single-trace-like, not representative 2D B-scan benchmark)

## 2. Source Outputs

- raw run manifest: `gprmax/GX-007_scene001_conversion_pairing/logs/raw_run_manifest.json`
- background run manifest: `gprmax/GX-007_scene001_conversion_pairing/logs/background_run_manifest.json`
- raw log files:
  - `gprmax/GX-007_scene001_conversion_pairing/logs/raw_stdout.log`
  - `gprmax/GX-007_scene001_conversion_pairing/logs/raw_stderr.log`
- background log files:
  - `gprmax/GX-007_scene001_conversion_pairing/logs/background_stdout.log`
  - `gprmax/GX-007_scene001_conversion_pairing/logs/background_stderr.log`

No `.out`/`.h5`/`.vti` native simulation binaries are committed in this artifact package.

## 3. Conversion Result

- converter used: `scripts/gprmax_campaign_convert_scene001.py`
- extracted arrays:
  - raw: `arrays/raw_bscan.npy`, `arrays/raw_bscan.csv`
  - background: `arrays/background_bscan.npy`, `arrays/background_bscan.csv`
- raw shape: `[936, 1]`
- background shape: `[936, 1]`
- dtype: `float32` (NPY payload)

## 4. Pairing Result

- target_response generated: yes
- outputs:
  - `arrays/target_response.npy`
  - `arrays/target_response.csv`
  - `tables/paired_validation_summary.json`
  - `tables/paired_metrics.json`

Key metrics (from `paired_metrics.json`):

- `raw_energy`: `255703.86933204762`
- `background_energy`: `255693.32561147978`
- `target_response_energy`: `10.543924899213927`
- `target_to_background_energy_ratio`: `4.12366058988774e-05`

## 5. Preview Result

- preview PNGs:
  - `figures/raw_preview.png`
  - `figures/background_preview.png`
  - `figures/target_response_preview.png`
  - `figures/paired_preview_panel.png`
- lightweight reports:
  - `reports/paired_target_response_report.md`
  - `reports/paired_report_summary.json`

## 6. Claim Boundary

This artifact is **GX-007 scene_001 minimal synthetic conversion/pairing evidence** only.

- It is **not** real UAV-GPR field validation.
- It is **not** AutoTune evaluation.
- It is **not** a paper-candidate final result.
- Because shape is `936 x 1`, it is **not** yet a representative 2D B-scan benchmark.
- ROI remains placeholder until explicit review and update.

## 7. Next Steps

- `GX-007-ROI-001`: if preview is usable, update ROI from placeholder.
- `GX-007-SCENE001-BSCAN-FIX`: if `936 x 1` is insufficient, adjust scan/output config to generate representative B-scan dimensions.
- `GX-007-SCENE002-RUN-001`: proceed only after deciding scene_001 shape acceptability.
