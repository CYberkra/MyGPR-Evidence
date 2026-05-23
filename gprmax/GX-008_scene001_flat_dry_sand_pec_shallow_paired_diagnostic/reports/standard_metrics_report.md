# Standard Metrics Report

- artifact_id: `GX-008_scene001_flat_dry_sand_pec_shallow_paired_diagnostic`
- scene_id: `scene_001_flat_dry_sand_pec_shallow`
- source_commit: `370f2b02dc5cf9d8ade05d6ab6fbfd46d1d26f13`
- metrics_schema: `synthetic_paired_metrics_v1`
- backend: `GPU via scripts/run_gprmax_gpu_env.bat`

## Shapes
- raw_shape: `[936, 41]`
- background_shape: `[936, 41]`
- target_response_shape: `[936, 41]`

## Key Metrics
- raw_energy: `10614805.214989502`
- background_energy: `10614467.199356852`
- target_response_energy: `338.01433237576254`
- target_to_background_energy_ratio: `3.184468198236492e-05`
- target_to_raw_energy_ratio: `3.1843667926985774e-05`
- raw_background_mae: `0.029371318842239945`
- raw_background_mse: `0.008807961548294191`
- raw_background_rmse: `0.09385074079779121`
- raw_background_psnr: `62.31984542204228`
- sparsity_or_concentration_proxy: `21.040031474746858`

## Files
- `tables/standard_paired_metrics.json`
- `tables/standard_paired_metrics_summary.json`

## Claim Boundary
- metrics apply to synthetic paired data only
- not valid as no-prior field ground truth
- not AutoTune evaluation by itself
- not AutoTune superiority evidence
