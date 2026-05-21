# YS-002 YingShan Line9 model.in and Geometry Binding Audit

## Executive Summary
- This artifact binds `impulse2.in` with `unified_geometry.h5` and `Line9origin(36).csv` at provenance/metadata level only.
- geometry_binding_status: `plausible`
- Reason: `model references geometry h5 path but consistency is partial`
- No AutoTune run, no gprMax rerun, no field-correctness claim.

## model.in Parse Summary
- model.in size: `563` bytes
- model.in SHA256: `5e2281f6ea0c406019bd98e91d09603a5e94953b16047380a74c77868fd62bc5`
- domain: `[17.5, 2.0, 0.002]`
- dx_dy_dz: `[0.005, 0.005, 0.002]`
- time_window: `3e-08` s
- source: `hertzian_dipole` @ `[0.0, 1.8, 0.0]`
- receiver: `[0.5, 1.8, 0.0]`
- src_steps / rx_steps: `[0.1, 0.0, 0.0]` / `[0.1, 0.0, 0.0]`
- geometry_objects_read: `0 0 0 F:\gprMax-master\user_models\gprMax-Matlab-SFCW-radars-signal-processing-simulation-main\NC9Line\ex_h5\png_color.h5 F:\gprMax-master\user_models\gprMax-Matlab-SFCW-radars-signal-processing-simulation-main\NC9Line\ex_h5\materials.txt`
- geometry_view: `0 0 0 17.500 2.000 0.002 0.005 0.005 0.002 impulse n`

## Geometry Binding
- references unified_geometry.h5 filename directly: `False`
- inferred h5 geometry role: `likely_geometry_or_material_index_grid_not_receiver_timeseries`
- consistency match checks: `['grid_spacing_match']`
- consistency mismatch checks: `['grid_counts_mismatch_domain_and_dxdyz']`

## Model vs Field Metadata Comparison
- field B-scan shape: `[501, 2378]` (samples x traces)
- field time window: `700.0` ns
- field trace interval: `0.09093` m
- model time window: `29.999999999999996` ns
- model src step: `0.1` m
- model trace count approx: `175`
- This is metadata-level comparison only; no physical alignment claim.

## Screenshot Provenance Note
- Screenshots are treated as informal visual context, not ground truth.
- geometry_view command in impulse2.in gives a plausible model/profile preview link, but provenance is incomplete.

## Missing-data Checklist
- native gprMax receiver output file (.out or _merged.out)
- exact gprMax version used by the senior
- whether impulse2.in was the exact model used for the screenshots
- whether unified_geometry.h5 was generated from this exact model run
- whether there are target/layer annotations
- whether field Line9 has survey metadata and coordinate metadata
- whether simulation and field share trace origin/direction/distance scale
- whether there is any ground truth from drilling/excavation/geological profile

## Claim Boundary
- No AutoTune run in this task.
- No scoring/algorithm modifications.
- No field-performance or underground-correctness claim.
