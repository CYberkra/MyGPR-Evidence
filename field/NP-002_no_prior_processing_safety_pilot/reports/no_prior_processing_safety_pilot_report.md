# NP-002 No-prior Processing Safety Pilot

## Executive summary
- NP-002 uses NP-001 high-risk warnings and the DS-002 no-prior candidate set.
- It defines safe behavior after no-prior warnings.
- No AutoTune, gprMax, or processing pipeline was run.

## Why high-risk does not mean unusable
- High-risk means automatic aggressive recommendations should be blocked.
- Data can still be visually reviewed with a warning-first workflow.
- Manual review is required before stronger parameterized processing.

## Safety decision result (line-specific)
| Site | File | Level | Initial policy | Manual review |
| --- | --- | --- | --- | --- |
| YingShan | Line9origin(36).csv | high_risk | conservative_display_only | required |
| YaAn | 测线21-1_功率30dbm_高度11m.csv | high_risk | conservative_display_only | required |
| YaAn | 测线21-1_功率36dbm_高度11m.csv | high_risk | conservative_display_only | required |

Common decision fields remain unchanged for all three lines:
- `safe_auto_recommendation_allowed = False`
- `aggressive_background_suppression_allowed = False`
- `amplitude_claim_allowed = False`
- `auto_gain_allowed = False`
- `manual_review_required = True`

## Allowed vs blocked actions
- Allowed: raw preview.
- Caution (display-only): contrast clip display, conservative energy-decay gain display, AGC display-only.
- Blocked: aggressive background suppression, dewow (pilot scope), migration, AutoTune, preset recommendation.

## User-facing wording templates
- 高风险告警提示：`当前数据触发高风险质控告警，建议先查看原始剖面并进行人工复核。`
- 阻止激进自动推荐：`系统不会自动推荐激进背景抑制或默认参数。`
- 显示增强免责声明：`以下显示增强仅用于可视化，不代表幅值保真或目标识别。`
- 无先验限制：`未提供目标区域或先验信息，因此本结果不构成地下目标判断。`
- 人工复核要求：`建议由有经验人员复核后再尝试任何参数化处理。`

## Claim boundary
- No target detection claim.
- No underground correctness claim.
- No AutoTune performance claim.
- No preset promotion.
- Display transforms are not amplitude-preserving claims.
- Thresholds are heuristic.

## Next recommended task
- NP-003 implement no-prior warning UI/spec in MyGPR.
