# AT-019 YingShan Line9 Full AutoTune Diagnostics

## Executive summary
- Full AutoTune pipeline status: completed
- First warning/failure stage: None
- Dewow window=256 is expected to clamp to 250 for 501-sample data; this is constraint warning, not algorithm crash when run continues.
- Background stage diagnostics generated across subtracting/median/running-average/svd methods.
- No-prior high-risk policy implies UI should block aggressive auto recommendation paths and require manual review.
- Source commit: `d0337f97116c1d012770ce1ab6f07fd6a68a913d`

## Data summary
- Field CSV: `C:\Users\17844\Desktop\02_Preprocessed_Standard\2025-09_营山\Line9origin(36).csv`
- Parsed shape: `(501, 2378)`
- ROI: none (no-prior field diagnostics)

## Dewow finding
- Full AutoTune completed; dewow did not hard-fail.
- For 501 samples, candidate window `256` is expected to be constrained to `250` (`n_samples//2`) as a non-blocking constraint behavior.
- Best dewow candidate in the diagnostics table is `window=26`.
- This indicates the dewow issue is warning UX / candidate-constraint communication, not a dewow algorithm failure.

## Background suppression finding
- Background stage selected `subtracting_average_2D` with `ntraces=676` in this run.
- The selected score is negative in diagnostics.
- Risk signals show weak structure preservation in selected output:
  - `local_saliency_preservation` around `0.32`
  - `edge_preservation` around `0.36`
  - `peak_ratio` around `0.14`
- This suggests scoring-vs-safety alignment risk for no-prior field data, and should not become an automatic aggressive recommendation.

## No-prior interpretation
- `no_prior_level = high_risk`.
- Diagnostic run is allowed for analysis/evidence generation.
- UI automatic aggressive recommendation should remain blocked and manual review should remain required.
- No target detection or underground correctness claim is allowed.

## Next recommended task
- AT-020: Background scoring / no-prior safety what-if diagnostics (diagnostics-first, no immediate scoring change).

## Claim boundary
- Field diagnostic only; no ground-truth validation.
- No target detection claim.
- No underground correctness claim.
- No AutoTune superiority claim.
- No preset promotion.
