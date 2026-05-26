# GX-008 Scene_037 Report Package (Air/Sand Interface, N80, Ey)

## 1. Package title
GX-008-EVIDENCE-005 Scene_037 Report Package

## 2. Source commit
- MyGPR source commit: `707ee62b9fbcb0f5ffc8ada71f0fd530886934b2`

## 3. Evidence commit base
- MyGPR-Evidence base commit: `f0e24b832d915f3fc431d043e52d5c11a4a27008`

## 4. Directory contents
- `figure_01_main_target_response.png`
- `figure_02_paired_process.png`
- `figure_03_ascan_support.png`
- `figure_04_background_sanity.png`
- `figure_05_full_target_response_context.png`
- `captions.md`
- `report_text_zh.md`
- `report_text_en.md`
- `package_manifest.json`
- `README.md`

## 5. Figure usage guide
- Main figure: `figure_01_main_target_response.png`
- Process figure: `figure_02_paired_process.png`
- A-scan support: `figure_03_ascan_support.png`
- Background sanity: `figure_04_background_sanity.png`
- Full context: `figure_05_full_target_response_context.png`

## 6. Report text usage guide
- Chinese narrative template: `report_text_zh.md`
- English narrative template: `report_text_en.md`
- Locked captions for all figures: `captions.md`

## 7. Metrics summary
- raw_shape: `[3636, 80]`
- background_shape: `[3636, 80]`
- target_response_shape: `[3636, 80]`
- target_response_energy: `3554.8169202461177`
- target_to_raw_energy_ratio: `0.03057964057539346`
- target_to_background_energy_ratio: `0.03146837378283868`
- raw_background_psnr: `33.08998897357791`
- roi_energy_ratio: `0.9979606645548237`

## 8. Claim boundary
- synthetic paired diagnostic result only
- not exact CLT-GPR replication
- not finalized paper benchmark
- not field validation
- not AutoTune evaluation
- not a target correctness claim without ROI/ground-truth review

## 9. Do-not-claim section
Do not claim:
- exact CLT-GPR dataset replication
- final paper benchmark completion
- field validation
- AutoTune superiority or effectiveness proof
- ROI energy ratio as proof of detection correctness
- equivalence to real GPR field data

## 10. Recommended next task
GX-008-MODEL-AUDIT-001-SCENE037-GEOMETRY-AND-CLAIM-REVIEW
