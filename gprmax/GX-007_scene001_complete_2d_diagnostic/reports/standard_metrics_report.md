# Standard Metrics Report

- artifact_id: `GX-007_scene001_complete_2d_diagnostic`
- scene_id: `scene_001_single_shallow_pipe`
- source_commit: `370f2b02dc5cf9d8ade05d6ab6fbfd46d1d26f13`
- metrics_schema: `synthetic_paired_metrics_v1`
- backend: `CPU`

## Shapes
- raw_shape: `[936, 21]`
- background_shape: `[936, 21]`
- target_response_shape: `[936, 21]`

## Key Metrics
- raw_energy: `5370261.437874472`
- background_energy: `5369559.7853927845`
- target_response_energy: `701.6566087774397`
- target_to_background_energy_ratio: `0.00013067302289588223`
- target_to_raw_energy_ratio: `0.00013065594978838732`
- raw_background_mae: `0.06523294634353208`
- raw_background_mse: `0.035696815669874274`
- raw_background_rmse: `0.1889360094578963`
- raw_background_psnr: `55.64670820075655`
- sparsity_or_concentration_proxy: `25.83948928418988`

## Files
- `tables/standard_paired_metrics.json`
- `tables/standard_paired_metrics_summary.json`

## Claim Boundary
- metrics apply to synthetic paired data only
- not valid as no-prior field ground truth
- not AutoTune evaluation by itself
- not AutoTune superiority evidence
