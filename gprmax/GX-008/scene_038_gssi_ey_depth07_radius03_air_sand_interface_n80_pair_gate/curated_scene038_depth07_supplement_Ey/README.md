# GX-008 Scene_038 Depth Sensitivity Supplement (Ey)

## 1) Title
Scene_038 depth07 air/sand-interface n80 paired result supplementary artifact.

## 2) Scene ID
`scene_038_gssi_ey_depth07_radius03_air_sand_interface_n80_pair_gate`

## 3) Source Commit
MyGPR source commit: `32fc97003bd0333776e757381e48082875ab1508`

## 4) Relation to Scene_037
This artifact is a supplement to primary scene:
`scene_037_gssi_ey_depth05_radius03_air_sand_interface_n80_geometry_gate`.
It does not replace scene_037 as PRIMARY_ACTIVE.

## 5) Single-variable Change
- cover depth: `0.05 m -> 0.07 m`
- target center z: `0.18 m -> 0.16 m`
- target top z: `0.21 m -> 0.19 m`
- target lower z: `0.15 m -> 0.13 m`

## 6) Unchanged Conditions
- air/sand interface
- dry sand material
- GSSI-like 1.5 GHz antenna
- Ey receiver component
- n80 scan
- target x center
- radius03
- PEC target
- paired subtraction: `target_response = raw_with_target - background_only`

## 7) Run/Output Summary
- raw shape: `[3636, 80]`
- background shape: `[3636, 80]`
- target_response shape: `[3636, 80]`
- component: `Ey` (`rxs/rx1/Ey`)

## 8) Metrics Summary
- raw_energy: `116912.25021293758`
- background_energy: `112964.74818742435`
- target_response_energy: `2957.0023831295566`
- target_to_raw_energy_ratio: `0.02529249396657608`
- target_to_background_energy_ratio: `0.02617632872711295`
- mean_abs_target_response: `0.016448358605592208`
- max_abs_target_response: `2.029122680425644`
- raw_background_rmse: `0.10082515689665042`
- raw_background_psnr: `33.88964461481177`
- roi_energy_ratio: `0.9995248194699562`

## 9) Figure List
- `paired_preview_panel.png`
- `target_response_full_percentile_1_99.png`
- `target_response_crop_best_candidate.png`
- `target_response_symmetric_absmax.png`
- `target_response_surface_muted_display_only.png`
- `target_response_trace_normalized_display_only.png`
- `central_trace_A_scan_raw_bg_target.png`
- `trace_35_40_41_45_49_A_scan_overlay.png`
- `background_full_percentile_1_99.png`
- `raw_full_percentile_1_99.png`

## 10) Visual Interpretation
Scene_038 is a depth07 single-variable sensitivity supplement based on scene_037. It moves the PEC cylinder target 2 cm deeper, changing cover depth from 0.05 m to 0.07 m while preserving the air/sand interface, GSSI-like antenna, Ey component, n80 scan, target radius, and paired subtraction protocol. The paired target_response remains clear and centered near trace 41, supporting the robustness of the scene_037-style synthetic paired diagnostic workflow under a modest target-depth increase. It does not replace scene_037 as the primary active model.

## 11) Claim Boundary
- single-variable synthetic depth sensitivity supplement only
- does not replace scene_037 as primary active scene
- not exact CLT-GPR replication
- not finalized paper benchmark
- not field validation
- not AutoTune evaluation
- not a target correctness claim without ROI/ground-truth review

## 12) Do-not-claim
Do not claim:
- scene_038 replaces scene_037 as primary active model
- exact CLT-GPR replication
- final paper benchmark
- field validation
- AutoTune evaluation or superiority
- real-world target detection accuracy
- ROI energy ratio proves detection correctness
- display-only images are amplitude-preserving evidence

## 13) Recommended Usage
Use as supplementary depth-sensitivity evidence in report/thesis sections where scene_037 remains the primary synthetic paired diagnostic artifact.
