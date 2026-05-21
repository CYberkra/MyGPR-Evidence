# DS-002 Field Preview Selection and No-prior QC Candidate Set

## Executive Summary
- DS-002 selects a compact representative subset from DS-001R only.
- This is raw field-data selection only; no AutoTune and no processing rerun.

## Selected Set (4-6)
| site | relative_path | selection_role | selection_reason |
|---|---|---|---|
| YingShan | Line9origin(20).csv | field_visual_QC | Site-diversity supplement with successful reconstruction |
| YaAn | 测线21-1_功率30dbm_高度11m.csv | no_prior_QC | YaAn 30dbm representative for cross-site no-prior QC |
| YaAn | 测线21-1_功率36dbm_高度11m.csv | field_visual_QC | YaAn 36dbm representative visual/decay comparison |

## YingShan Line9 comparison
- Compared Line9origin(20)/(30)/(36) using DS-001R raw previews and decay metrics.
- Recommended: **Line9origin(36)** for paper/no-prior candidate; 20/30 kept as contrast pair.

## YaAn comparison
- Included at least one 30dbm and one 36dbm line for power/height contrast.

## Decay and dynamic range summary
- See `tables/field_candidate_comparison.csv` and `figures/selected_decay_profile_comparison.png`.

## No-prior QC candidate set
- See `tables/no_prior_qc_candidate_set.csv`.

## Paper figure candidate set
- See `tables/paper_figure_candidate_set.csv`.

## Holdout/not-ready
- See `tables/holdout_or_not_ready_lines.csv`.

## Claim boundary
- No underground correctness claim.
- No AutoTune performance claim.
- No target-type claim.
- Raw preview only; selected lines are candidates, not final paper evidence.
