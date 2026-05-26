# GX-008 Figure Selection and Caption Lock (Scene_037)

## 1. Task metadata
- task_id: `GX-008-EVIDENCE-004-SCENE037-FIGURE-SELECTION-CAPTION-LOCK`
- evidence commit base: `79b7c75d93fe2a177d6167929d8b9d0ef6fb5785`
- source commit reference: `707ee62b9fbcb0f5ffc8ada71f0fd530886934b2`
- curated artifact path: `D:\CDUT-UavGPR-Controller\MyGPR-Evidence\gprmax\GX-008\scene_037_gssi_ey_depth05_radius03_air_sand_interface_n80_geometry_gate\curated_scene037_air_sand_n80_Ey\`
- scene id: `scene_037_gssi_ey_depth05_radius03_air_sand_interface_n80_geometry_gate`
- selected component: `Ey`
- artifact role: `synthetic paired diagnostic candidate`

## 2. Scene summary
Scene_037 is an air/sand-interface synthetic GSSI-like 1.5 GHz GPR model with a dry-sand half-space, an air/free-space layer, and a PEC cylinder target. The run uses n80 raw/background paired simulations and converts the receiver component Ey to generate target_response = raw_with_target - background_only.

Geometry:
- domain: `1.0 x 0.15 x 0.40 m`
- grid: `0.002 x 0.002 x 0.002 m`
- dry sand: `z=0.000..0.260 m`
- air/free-space: `z=0.260..0.400 m`
- soil surface: `z=0.260 m`
- antenna skid bottom `z=0.310 m`
- antenna standoff `=0.050 m`
- target: `PEC cylinder along y`
- target center `x=0.50 m, z=0.180 m`
- target radius `=0.03 m`
- target cover depth `=0.05 m`
- trace count `=80`
- target center trace `=41`
- component `=Ey`

## 3. Locked figure set

Primary figure:
- file: `target_response_crop_best_candidate.png`
- role: Main target-response figure
- use in report: main synthetic diagnostic result
- reason: shows the clearest centered hyperbola-like target_response after paired subtraction

Process figure:
- file: `paired_preview_panel.png`
- role: Raw/background/target_response process figure
- use in report: method/result pipeline figure
- reason: shows how raw and background produce target_response

Full-context figure:
- file: `target_response_full_percentile_1_99.png`
- role: Full n80 target_response context
- use in report: optional full B-scan context
- reason: shows entire trace/time window

Waveform support figure:
- file: `trace_35_40_41_45_49_A_scan_overlay.png`
- role: A-scan waveform support
- use in report: supporting evidence or appendix
- reason: shows target_response waveform behavior around target-center trace 41

Background sanity figure:
- file: `background_full_percentile_1_99.png`
- role: Background-only sanity check
- use in report: appendix or audit
- reason: shows no target-related local hyperbola in the background-only simulation

Display-only figure:
- file: `target_response_trace_normalized_display_only.png`
- role: Shape-continuity display figure
- use in report: appendix only
- reason: useful for visualizing curve continuity, but not valid for amplitude comparison

Do not use as main evidence:
- `target_response_trace_normalized_display_only.png`
  reason: trace-normalized display-only; not amplitude-preserving
- `target_response_surface_muted_display_only.png`
  reason: display-only; not raw metric evidence
- `target_response_symmetric_absmax.png`
  reason: useful display sanity check, but weaker as main figure than crop_best_candidate

## 4. Locked captions

Caption A — main result figure:
"Scene_037 synthetic air/sand-interface paired target response. The displayed B-scan is computed as target_response = raw_with_target - background_only using the Ey receiver component from a GSSI-like 1.5 GHz antenna model. The response shows a centered hyperbola-like signature near the designed target-center trace, consistent with the PEC cylinder geometry. This figure is a synthetic paired diagnostic result, not a field validation or exact paper replication."

Caption B — paired process figure:
"Raw, background-only, and paired target_response B-scans for scene_037. The raw and background-only simulations share the same air/sand-interface geometry and antenna path, while the raw model includes the PEC cylinder target. Subtracting the background-only B-scan from the raw B-scan suppresses common background and interface responses and exposes the target-related hyperbola-like response."

Caption C — A-scan support figure:
"Target_response A-scan overlays near the target-center trace. The strongest response is centered near trace 41, which corresponds to the designed x-position of the PEC cylinder. The waveform comparison supports the visual interpretation that the paired B-scan response is localized near the target-center trace."

Caption D — background sanity figure:
"Background-only B-scan for scene_037. The image mainly contains horizontal antenna/interface responses and does not show the localized hyperbola-like response observed in the paired target_response image, supporting the raw/background pairing interpretation."

## 5. Recommended report wording
The GX-008 scene_037 result is used as a synthetic paired diagnostic example. The model introduces an explicit air/sand interface and uses a GSSI-like 1.5 GHz antenna model with Ey receiver output. The raw and background-only simulations were paired to compute target_response = raw_with_target - background_only. The resulting target_response image shows a centered hyperbola-like response near the designed target location. This supports the correctness of the MyGPR gprMax pairing, conversion, visualization, and evidence-export chain, but it does not constitute exact CLT-GPR replication, field validation, or AutoTune evaluation.

## 6. Metrics to quote
- raw_shape: `[3636, 80]`
- background_shape: `[3636, 80]`
- target_response_shape: `[3636, 80]`
- target_response_energy: `3554.8169202461177`
- target_to_raw_energy_ratio: `0.03057964057539346`
- target_to_background_energy_ratio: `0.03146837378283868`
- raw_background_psnr: `33.08998897357791`
- roi_energy_ratio: `0.9979606645548237`

The ROI energy ratio is used only as a diagnostic concentration proxy and is not a detection-accuracy metric.

## 7. Claim boundary
- Synthetic paired diagnostic result only.
- Not exact CLT-GPR replication.
- Not finalized paper benchmark.
- Not field validation.
- Not AutoTune evaluation.
- Not a target correctness claim without ROI/ground-truth review.

## 8. Do-not-claim section
Do not claim:
- "MyGPR has replicated the CLT-GPR dataset."
- "The simulation proves field target-detection accuracy."
- "AutoTune improves GPR results."
- "The figure is a final benchmark."
- "The ROI energy ratio proves detection correctness."
- "The target_response figure is equivalent to real GPR field data."

## 9. Recommended next task
GX-008-EVIDENCE-005-SCENE037-REPORT-PACKAGE: build a compact report package or one-page slide using the locked figure set and captions, without modifying simulation outputs.
