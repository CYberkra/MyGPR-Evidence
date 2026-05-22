# AT-019 YingShan Line9 Full AutoTune Diagnostics

## Executive summary
- Full AutoTune pipeline status: completed
- First warning/failure stage: None
- Dewow window=256 is expected to clamp to 250 for 501-sample data; this is constraint warning, not algorithm crash when run continues.
- Background stage diagnostics generated across subtracting/median/running-average/svd methods.
- No-prior high-risk policy implies UI should block aggressive auto recommendation paths and require manual review.

## Data summary
- Field CSV: `C:\Users\17844\Desktop\02_Preprocessed_Standard\2025-09_营山\Line9origin(36).csv`
- Parsed shape: `(501, 2378)`
- ROI: none (no-prior field diagnostics)

## Claim boundary
- Field diagnostic only; no ground-truth validation.
- No target detection claim.
- No underground correctness claim.
- No AutoTune superiority claim.
- No preset promotion.