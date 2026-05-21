# DS-001 Local YingShan / YaAn Field Dataset Inventory

## Executive Summary
- Scope: local dataset inventory and raw QC only.
- Root: `C:\Users\17844\Desktop\02_Preprocessed_Standard`
- Files scanned: 215172
- CSV candidates: 215169
- H5/HDF5 files: 1
- .in files: 1
- .out files: 0
- Usable CSV B-scan count: 0
- Preview images generated: 0

## Claim Boundary
- This artifact is inventory/QC only.
- No AutoTune run.
- No algorithm/scoring change.
- No underground correctness claim.

## Outputs
- `tables/file_inventory.csv`
- `tables/csv_field_line_summary.csv`
- `tables/h5_file_summary.csv`
- `tables/gprmax_model_asset_summary.csv`
- `tables/field_decay_summary.csv`
- `tables/dataset_selection_recommendations.csv`

## Next-step recommendation
- Prioritize datasets listed in `tables/dataset_selection_recommendations.csv` for controlled no-prior QC and simulation-vs-field provenance binding.


## Deterministic Line9 Extraction
- Added deterministic extraction for `Line9origin(36).csv` using known SFCW contract (col4 amplitude, 501 samples, 2378 traces).
