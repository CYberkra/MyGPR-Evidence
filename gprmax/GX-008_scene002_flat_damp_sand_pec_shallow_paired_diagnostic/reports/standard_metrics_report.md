# GX-008 Scene 002 Standard Metrics Report

## Artifact
- artifact_id: `GX-008_scene002_flat_damp_sand_pec_shallow_paired_diagnostic`
- scene_id: `scene_002_flat_damp_sand_pec_shallow`
- metrics_schema: `synthetic_paired_metrics_v1`
- source_commit: `12848a580aa0b8086576ecb946a7beef138349de`

## Input Shapes
- raw: `[936, 41]`
- background: `[936, 41]`
- target_response: `[936, 41]`

## Key Metrics
- raw_background_mae: `0.011964291100674148`
- raw_background_mse: `0.0013645776489623431`
- raw_background_rmse: `0.03694019015871931`
- raw_background_psnr: `69.89623294940046`
- target_to_background_energy_ratio: `5.033107187430459e-06`
- target_to_raw_energy_ratio: `5.033081874553658e-06`

## Warnings
[]

## Claim Boundary
- metrics apply to synthetic paired data only
- not valid as no-prior field ground truth
- not AutoTune evaluation by itself
- not AutoTune superiority evidence
