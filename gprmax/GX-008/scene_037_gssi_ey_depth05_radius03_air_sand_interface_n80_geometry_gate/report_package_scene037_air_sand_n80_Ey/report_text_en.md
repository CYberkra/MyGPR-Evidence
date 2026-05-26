# GX-008 scene_037 Synthetic GPR Paired Diagnostic Summary

## 1. Scene purpose
scene_037 is used to validate the MyGPR gprMax raw/background pairing, Ey component conversion, target_response computation, visualization, and evidence-export chain.

## 2. Model setup
- air/sand interface
- GSSI-like 1.5 GHz antenna
- Ey receiver component
- dry sand half-space
- air/free-space layer
- PEC cylinder target
- n80 scan
- target_response = raw_with_target - background_only

## 3. Geometry parameters
- domain: 1.0 x 0.15 x 0.40 m
- grid: 0.002 x 0.002 x 0.002 m
- dry sand: z=0.000..0.260 m
- air/free-space: z=0.260..0.400 m
- soil surface: z=0.260 m
- antenna skid bottom z=0.310 m
- antenna standoff=0.050 m
- target center x=0.50 m, z=0.180 m
- target radius=0.03 m
- target cover depth=0.05 m
- target center trace=41
- traces=80

## 4. Result summary
- raw_shape: [3636, 80]
- background_shape: [3636, 80]
- target_response_shape: [3636, 80]
- target_response_energy: 3554.8169202461177
- target_to_raw_energy_ratio: 0.03057964057539346
- target_to_background_energy_ratio: 0.03146837378283868
- raw_background_psnr: 33.08998897357791
- roi_energy_ratio: 0.9979606645548237
- The ROI energy ratio is used only as a diagnostic concentration proxy and is not a detection-accuracy metric.

## 5. Visual interpretation
`target_response_crop_best_candidate.png` shows a hyperbola-like response centered near the designed target-center trace. `paired_preview_panel.png` shows the raw/background/target_response pairing workflow. The A-scan overlay supports that response strength is highest near the center traces.

## 6. Recommended core paragraph
The GX-008 scene_037 result is used as a synthetic paired diagnostic example. The model introduces an explicit air/sand interface and uses a GSSI-like 1.5 GHz antenna model with Ey receiver output. The raw and background-only simulations were paired to compute target_response = raw_with_target - background_only. The resulting target_response image shows a centered hyperbola-like response near the designed target location. This supports the correctness of the MyGPR gprMax pairing, conversion, visualization, and evidence-export chain, but it does not constitute exact CLT-GPR replication, field validation, or AutoTune evaluation.

## 7. What can be claimed
- MyGPR has completed scene_037 synthetic raw/background pair result organization.
- A centered hyperbola-like response appears in target_response near the designed target location.
- The result supports the MyGPR synthetic paired diagnostic chain.

## 8. What must not be claimed
- Exact CLT-GPR dataset replication.
- Final paper benchmark completion.
- Real field validation.
- AutoTune effectiveness proof.
- ROI energy ratio proving detection correctness.
- Equivalence of this figure to real GPR field data.

## 9. Claim boundary
- Synthetic paired diagnostic result only.
- Not exact CLT-GPR replication.
- Not finalized paper benchmark.
- Not field validation.
- Not AutoTune evaluation.
- Not a target correctness claim without ROI/ground-truth review.
