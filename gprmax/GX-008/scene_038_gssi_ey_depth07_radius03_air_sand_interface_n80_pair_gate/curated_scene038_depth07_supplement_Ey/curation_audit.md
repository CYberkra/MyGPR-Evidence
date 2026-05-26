# GX-008-EVIDENCE-006 Scene_038 Curation Audit

## 1) Task ID
`GX-008-EVIDENCE-006-SCENE038-DEPTH-SENSITIVITY-SUPPLEMENT`

## 2) Source repo/commit verification
- Source repo: `https://github.com/CYberkra/MyGPR`
- Source branch: `main`
- Source commit: `32fc97003bd0333776e757381e48082875ab1508`

## 3) Evidence repo base commit
- Base commit before curation: `cb85fdd5b36038ec723942f9372975d89bea0290`

## 4) Files copied
From scratch `D:\CDUT-UavGPR-Controller\MyGPR-Evidence\scratch\GX-008_scene038_depth07_n80_pair\paired_outputs` into:
`D:\CDUT-UavGPR-Controller\MyGPR-Evidence\gprmax\GX-008\scene_038_gssi_ey_depth07_radius03_air_sand_interface_n80_pair_gate\curated_scene038_depth07_supplement_Ey`

Copied:
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
- `paired_metrics.json`
- `paired_report_summary.json`
- `paired_validation_summary.json`
- `paired_target_response_report.md`
- `scene038_extra_metrics.json`

## 5) Files deliberately excluded
- `.out`
- `.h5`
- `.vti/.vtk/.vtu`
- `.npy`
- `.csv`
- scratch logs and bulk simulation outputs

## 6) Metrics summary
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

## 7) Visual assessment
Scene_038 paired target response remains clear and centered near the designed target-center trace after depth increase to cover depth 0.07 m.

## 8) Decision
- scene_038 passes visual review as depth sensitivity supplement
- scene_037 remains primary active model
- scene_038 can be used as supplementary figure/evidence

## 9) Claim boundary
- single-variable synthetic depth sensitivity supplement only
- does not replace scene_037 as primary active scene
- not exact CLT-GPR replication
- not finalized paper benchmark
- not field validation
- not AutoTune evaluation
- not a target correctness claim without ROI/ground-truth review

## 10) Final Evidence commit hash after push
4151fff274e9ce56a6f727be5875db8f09e6d823
