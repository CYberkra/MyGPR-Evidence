# YS-001 YingShan Line9 H5 and Field CSV Data Audit

## Executive Summary
- This artifact is data-audit/package-preparation only, not ground-truth validation.
- H5 exists: `True`, size: `504001912` bytes, SHA256: `46b4ff7f7f95c532e45703ae68c2983846f5b9a95e586405465908115f6916f4`.
- Field CSV exists: `True`, size: `68794423` bytes, SHA256: `655f72f99de4cbcb22b1b9be64dc8ebdf2f156accbe9b27729c6862f6b1e172d`.
- H5 likely role: `unknown_or_custom_h5`.
- H5 preview generated: `True`; Field preview generated: `True`; H5-vs-field comparison feasible: `True`.

## H5 Structure Audit
- Root attributes count: `10`
- Group count: `0`
- Dataset count: `1`
- Selected radar-like dataset: `/data`
- Orientation note: `interpreted_as_samples_x_traces_tentative`
- Selection rationale: `selected /data by dataset-name/2D-priority heuristic`

## Field CSV Audit
- Raw numeric shape: `[1191378, 5]`
- Reconstructed B-scan shape: `[501, 2378]`
- Dtype: `float64`
- NaN/Inf (amplitude): `0` / `0`
- Min/Max (amplitude): `-0.068787515` / `0.075539112`
- Percentiles p01/p05/p50/p95/p99: `-0.027182563979999973`, `-0.00420281115`, `-2.06e-07`, `0.003964094399999991`, `0.03010738303999987`
- Orientation note: `samples_x_traces_from_header_reshape`
- Decay RMS shallow/middle/deep: `0.01359389716453538` / `0.00011200764801672363` / `2.6890359497711024e-05`
- Deep/Shallow ratio: `0.0019781199734145625`; dB drop: `-54.074947437670275`

## H5 vs Field Basic Comparison
- Comparison feasible at basic shape/decay/visual level only.
- No physical alignment or underground-structure correctness claim.

## Missing-data Checklist (from senior)
- model.in
- gprMax version
- material settings
- geometry explanation
- source/receiver settings
- trace spacing
- time window
- whether unified_geometry.h5 is native gprMax output or postprocessed file
- screenshot provenance
- known target/layer annotation
- real field Line9 survey metadata

## Claim Boundary
- No AutoTune run in this task.
- No scoring/algorithm modification in this task.
- No field-correctness claim; no screenshot-as-ground-truth claim.
