# AT-020 YingShan Background Safety What-if Diagnostics

## Executive summary
- AT-019 background selection (`subtracting_average_2D`, `ntraces=676`) is not safe for no-prior high-risk automatic recommendation.
- Main risk is joint: candidate space + current scoring tendency + missing hard no-prior automatic gate.
- Candidate caps reduce large-window picks, but caps alone are not fully sufficient without no-prior blocking policy.
- This artifact is diagnostics-only and does not modify production scoring.

## Data and provenance
- Source commit: `d0337f97116c1d012770ce1ab6f07fd6a68a913d`
- AT-019 base evidence commit: `c391d8b2bae93281343e118e1be124d12a90b7a7`
- Field CSV: `C:\Users\17844\Desktop\02_Preprocessed_Standard\2025-09_营山\Line9origin(36).csv`
- Shape: `(501, 2378)`
- no_prior_level: `high_risk`

## Candidate-space finding
- Candidate caps evaluated at 2%, 5%, 10%, 20%, 30%, and uncapped.
- Conservative caps (<=5%/<=10%) prevent very large-window candidates.
- Cap-only policy improves safety but still needs explicit no-prior automatic recommendation block for high-risk lines.

## Scoring what-if finding
- Variants evaluated: current, edge penalty, saliency penalty, peak penalty, large-window penalty, no-prior penalty, combined safety score.
- Combined safety score shifts ranking away from large-window candidates more consistently.
- Current score can over-favor coherence reduction relative to preservation signals for this no-prior field line.

## Method comparison
- Compared: subtracting_average_2D, median_background_2D, running_average_2D, svd_bg.
- Diagnostic preview may be allowed for all methods with clear claim boundary.
- Automatic recommendation should remain blocked under high-risk no-prior.

## No-prior decision
- High-risk no-prior data can be diagnosed.
- Automatic aggressive background recommendation should be blocked.
- Manual review is required.
- No target detection / no underground correctness claim is allowed.

## AT-021 recommendation
- Recommended first: **Option A** (UI block automatic background recommendation under no_prior_high_risk).
- Recommended second: **Option B** (no-prior candidate cap <=5% or <=10% trace ratio).
- Option C (scoring penalties) should follow A/B as controlled AT-021 implementation.

## Claim boundary
- Diagnostic only.
- No production scoring change.
- No target detection claim.
- No underground correctness claim.
- No preset promotion.
- No field-performance claim.
