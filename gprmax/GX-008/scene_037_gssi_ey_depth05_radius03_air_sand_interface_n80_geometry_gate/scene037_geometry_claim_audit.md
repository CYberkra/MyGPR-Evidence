# scene_037 Geometry and Claim-Boundary Audit

## 1. Audit metadata
- task_id: `GX-008-MODEL-AUDIT-001-SCENE037-GEOMETRY-AND-CLAIM-REVIEW`
- scene_id: `scene_037_gssi_ey_depth05_radius03_air_sand_interface_n80_geometry_gate`
- evidence_commit_base: `a2161e7c1841cccbc2aa1ba4b63e8cbd38aa58bc`
- source_commit_reference: `707ee62b9fbcb0f5ffc8ada71f0fd530886934b2`
- artifact role: `synthetic paired diagnostic candidate`
- selected component: `Ey`
- pairing: `target_response = raw_with_target - background_only`

## 2. Purpose of this audit
This audit fixes the interpretation of the scene_037 model geometry and claim boundary. It is intended to prevent over-claiming and to make the model explanation consistent across the report package, captions, metrics, and future thesis/course-report text.

## 3. Model status
- scene_037 completed raw n80: `80/80`
- scene_037 completed background n80: `80/80`
- raw shape: `[3636, 80]`
- background shape: `[3636, 80]`
- target_response shape: `[3636, 80]`
- selected receiver component: `Ey / rxs/rx1/Ey`
- result has been curated into Evidence
- report package has been created
- figure/caption set has been locked

## 4. Coordinate convention and z-axis interpretation
- gprMax domain uses x, y, z coordinates.
- In scene_037, z is not described as "depth from domain top".
- The soil surface is explicitly defined at z = 0.260 m.
- Dry sand occupies z = 0.000 to 0.260 m.
- Air/free-space occupies z = 0.260 to 0.400 m.
- Target cover depth is measured relative to the soil surface, not the domain boundary.
- The target top/upper side is closer to the soil surface at z = 0.210 m.
- The target center is z = 0.180 m.
- The target lower side is z = 0.150 m.
- Therefore target cover depth = 0.260 - 0.210 = 0.050 m.
- This convention must be used consistently in report text.

## 5. Geometry table

| Item | Value |
|---|---|
| Domain | 1.0 x 0.15 x 0.40 m |
| Grid | 0.002 x 0.002 x 0.002 m |
| Time window | 14 ns |
| Mode | 3D |
| Dry sand region | z = 0.000..0.260 m |
| Air/free-space region | z = 0.260..0.400 m |
| Soil surface | z = 0.260 m |
| Antenna model | GSSI-like 1.5 GHz antenna_like_GSSI_1500 |
| Antenna input z | 0.310 m |
| Antenna standoff | 0.050 m above soil surface |
| Antenna input x path | 0.100 + (current_model_run - 1) * 0.010 |
| Trace count | 80 |
| Target center trace | 41 |
| Target type | PEC cylinder along y |
| Target x center | 0.50 m |
| Target z center | 0.180 m |
| Target radius | 0.030 m |
| Target y range | 0.002..0.148 m |
| Target top/upper z | 0.210 m |
| Target lower z | 0.150 m |
| Target cover depth | 0.050 m |
| Receiver component | Ey |

## 6. Antenna interpretation
- The scene uses `gprMax user_libs.antennas.GSSI.antenna_like_GSSI_1500`.
- The source is a Gaussian voltage source with y polarization inside the GSSI-like antenna model.
- The selected receiver component is Ey.
- The antenna input coordinate is not identical to the physical source or receiver coordinate.
- Therefore, "trace 41 aligns with target center" means the GSSI antenna input reference x equals 0.50 m, not necessarily that Tx/Rx source or receiver x equals 0.50 m.
- This distinction should be preserved in any paper/report wording.

## 7. Pairing definition
- raw_with_target contains air/sand interface, GSSI-like antenna, dry sand, and PEC cylinder.
- background_only contains the same geometry and antenna path but no PEC cylinder.
- target_response is computed as:
  `target_response = raw_with_target - background_only`
- The purpose is to suppress common antenna/interface/background responses and reveal target-related response.
- This is a synthetic paired subtraction protocol; it is not field clutter removal validation.

## 8. Output metrics
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

The ROI energy ratio is a diagnostic concentration proxy only. It must not be presented as detection accuracy, localization accuracy, or validation accuracy.

## 9. Visual interpretation
- The locked primary figure is `target_response_crop_best_candidate.png`.
- It shows a centered hyperbola-like response after paired subtraction.
- The response is located near the designed target-center trace.
- The paired process figure is `paired_preview_panel.png`.
- The A-scan support figure is `trace_35_40_41_45_49_A_scan_overlay.png`.
- Background sanity figure is `background_full_percentile_1_99.png`.
- Trace-normalized display images may be used only as display/shape continuity aids, not amplitude evidence.

## 10. Valid claims
The following claims are allowed:
- MyGPR completed a synthetic scene_037 GSSI/Ey n80 raw/background paired simulation.
- The scene includes an explicit air/sand interface.
- The scene uses a GSSI-like 1.5 GHz antenna model and Ey receiver component.
- The paired target_response image shows a centered hyperbola-like response near the designed target position.
- The result supports the gprMax pairing, conversion, visualization, and Evidence export chain.
- The artifact is suitable as a synthetic paired diagnostic candidate in a report or thesis draft.

## 11. Invalid claims
Do not claim:
- Exact CLT-GPR replication.
- Final paper benchmark.
- Field validation.
- AutoTune evaluation or superiority.
- Real-world target detection accuracy.
- ROI energy ratio proves detection correctness.
- The simulation is equivalent to field GPR data.
- The GSSI-like 1.5 GHz model represents 95 MHz UAV-GPR.

## 12. Remaining limitations
- The result is synthetic, not field data.
- It is a single-target PEC cylinder case.
- It has not yet been compared against multiple soil types or multiple targets.
- It has not been evaluated as an AutoTune benchmark.
- ROI remains diagnostic and should not be treated as ground-truth validation.
- The GSSI-like 1.5 GHz antenna is not a 95 MHz UAV-GPR antenna.
- Exact CLT-GPR replication is not claimed.
- The model is paper-aligned but not paper-identical.

## 13. Recommended report wording
The scene_037 result is used as a synthetic paired diagnostic example. The model introduces an explicit air/sand interface and uses a GSSI-like 1.5 GHz antenna model with Ey receiver output. The raw and background-only simulations were paired to compute target_response = raw_with_target - background_only. The resulting target_response image shows a centered hyperbola-like response near the designed target location. This supports the correctness of the MyGPR gprMax pairing, conversion, visualization, and evidence-export chain, but it does not constitute exact CLT-GPR replication, field validation, or AutoTune evaluation.

## 14. Final audit decision
- scene_037 is approved as the current primary GX-008 synthetic paired diagnostic candidate.
- It is approved for report package usage under the locked claim boundary.
- No immediate model modification is required before presenting this result.
- Future model changes should be opened as separate scenes only if supervisor feedback identifies a specific geometry or claim issue.

## 15. Recommended next task
`GX-008-REPORT-001-SCENE037-ONE-PAGE-SUMMARY-OR-PPT`

Purpose:
Create a one-page summary or one-slide PPT using the report package, locked figures, captions, and this geometry/claim audit.
