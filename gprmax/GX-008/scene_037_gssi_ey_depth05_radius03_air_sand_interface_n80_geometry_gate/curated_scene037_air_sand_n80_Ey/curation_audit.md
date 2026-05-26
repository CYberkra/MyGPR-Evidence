# GX-008-EVIDENCE-003 Scene_037 Curation Audit

## 1. Task ID
`GX-008-EVIDENCE-003-SCENE037-CURATED-PACKAGING`

## 2. Source Repo / Commit Verification
- Repo: `https://github.com/CYberkra/MyGPR`
- Branch: `main`
- Commit: `707ee62b9fbcb0f5ffc8ada71f0fd530886934b2`

## 3. Evidence Repo Commit Before Curation
- Repo: `https://github.com/CYberkra/MyGPR-Evidence`
- Branch: `main`
- Base commit before curation: `a7d91eb253dfe36a82b42eef0d723e07cf86d246`

## 4. Files Copied into Curated Folder
Required:
- paired_preview_panel.png
- target_response_full_percentile_1_99.png
- target_response_crop_best_candidate.png
- target_response_symmetric_absmax.png
- target_response_surface_muted_display_only.png
- target_response_trace_normalized_display_only.png
- central_trace_A_scan_raw_bg_target.png
- trace_30_35_40_45_A_scan_overlay.png
- trace_35_40_41_45_49_A_scan_overlay.png
- paired_metrics.json
- paired_report_summary.json
- paired_validation_summary.json
- paired_target_response_report.md

Optional (present and copied):
- raw_full_percentile_1_99.png
- background_full_percentile_1_99.png
- raw_preview.png
- background_preview.png
- target_response_preview.png
- target_response_crop_0p5_99p5.png
- target_response_crop_5_95.png

Added metadata/docs:
- curated_manifest.json
- README.md
- curation_audit.md

## 5. Files Deliberately Excluded
- `.out`
- `.h5`
- `.vti`
- `.vtk`
- `.vtu`
- `.npy`
- large raw simulation outputs
- temporary scratch logs

## 6. Metrics Copied from paired_metrics.json
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

## 7. Visual Figure Recommendations
- Primary figure: `target_response_crop_best_candidate.png`
- Process/context figure: `paired_preview_panel.png`
- Waveform support figure: `trace_35_40_41_45_49_A_scan_overlay.png`

## 8. Claim Boundary
- Synthetic paired diagnostic result only.
- Not exact CLT-GPR replication.
- Not finalized paper benchmark.
- Not field validation.
- Not AutoTune evaluation.
- Not a target correctness claim without ROI/ground-truth review.

## 9. Final Evidence Commit Hash After Push
`fa9b233 (to be confirmed after push)`
