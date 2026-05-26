# GX-008 Scene_037 Curated Paired Evidence (Air/Sand Interface, GSSI Ey, N80)

## 1. Artifact Title
GX-008-EVIDENCE-003 Scene_037 Curated Packaging

## 2. Scene ID
`scene_037_gssi_ey_depth05_radius03_air_sand_interface_n80_geometry_gate`

## 3. Source Commit
`707ee62b9fbcb0f5ffc8ada71f0fd530886934b2` (MyGPR `main`)

## 4. Geometry Summary
- Domain: `1.0 x 0.15 x 0.40 m`
- Grid: `0.002 x 0.002 x 0.002 m`
- Dry sand: `z=0.000..0.260 m`
- Air/free-space: `z=0.260..0.400 m`
- Soil surface: `z=0.260 m`
- Antenna skid bottom: `z=0.310 m`
- Antenna standoff: `0.050 m`
- Target: PEC cylinder along y
- Target center: `x=0.50 m, z=0.180 m`
- Target radius: `0.03 m`
- Target cover depth: `0.05 m`
- Trace count: `80` (target center trace 1-based: `41`)

## 5. Run Summary
- Raw with target: completed (`80/80`)
- Background only: completed (`80/80`)
- Pairing: `target_response = raw_with_target - background_only`

## 6. Selected Component
- Component: `Ey`
- Receiver path: `rxs/rx1/Ey`

## 7. Shape Summary
- Raw: `[3636, 80]`
- Background: `[3636, 80]`
- Target response: `[3636, 80]`

## 8. Metrics Summary
- raw_energy: `116247.83200056886`
- background_energy: `112964.74818742435`
- target_response_energy: `3554.8169202461177`
- target_to_raw_energy_ratio: `0.03057964057539346`
- target_to_background_energy_ratio: `0.03146837378283868`
- mean_abs_target_response: `0.01726872011216153`
- max_abs_target_response: `2.3664356414228678`
- raw_background_rmse: `0.110548203304583`
- raw_background_psnr: `33.08998897357791`
- roi_energy_ratio: `0.9979606645548237`

## 9. Figure List
Primary paired figures:
- `paired_preview_panel.png`
- `target_response_full_percentile_1_99.png`
- `target_response_crop_best_candidate.png`
- `target_response_symmetric_absmax.png`
- `target_response_surface_muted_display_only.png`
- `target_response_trace_normalized_display_only.png`

A-scan support figures:
- `central_trace_A_scan_raw_bg_target.png`
- `trace_30_35_40_45_A_scan_overlay.png`
- `trace_35_40_41_45_49_A_scan_overlay.png`

Optional context figures:
- `raw_full_percentile_1_99.png`
- `background_full_percentile_1_99.png`
- `raw_preview.png`
- `background_preview.png`
- `target_response_preview.png`
- `target_response_crop_0p5_99p5.png`
- `target_response_crop_5_95.png`

## 10. Visual Interpretation
The scene_037 paired target_response shows a clear centered hyperbola-like response after subtracting the background-only simulation from the raw-with-target simulation. The strongest response is centered near the designed target-center trace, supporting the use of this artifact as a synthetic paired diagnostic candidate. The result should not be treated as an exact paper replication or field validation result.

## 11. Claim Boundary
- Synthetic paired diagnostic result only.
- Not exact CLT-GPR replication.
- Not finalized paper benchmark.
- Not field validation.
- Not AutoTune evaluation.
- Not a target correctness claim without ROI/ground-truth review.

## 12. Recommended Usage in Report
- Primary figure: `target_response_crop_best_candidate.png`
- Process/context figure: `paired_preview_panel.png`
- Waveform support: `trace_35_40_41_45_49_A_scan_overlay.png`

## 13. Known Limitations
- Synthetic single-scene diagnostic only.
- ROI interpretation depends on scene-defined geometry.
- No direct quantitative field-data equivalence in this artifact.

## 14. Do-Not-Claim
- Do not claim exact CLT-GPR replication.
- Do not claim final paper benchmark.
- Do not claim real field validation.
- Do not claim AutoTune superiority.
- Do not claim target correctness beyond the synthetic geometry definition.
- Do not compare quantitatively with field data unless a separate validation protocol is added.
