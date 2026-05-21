# AT-013 Multi-scene Relative Policy Validation

- Source commit: `a423072be4c2a9ae29708aef18e165d4c2cd053d`
- Included scenes: `['GX-003', 'GX-004', 'GX-005', 'GX-006']`
- Gate status: `blocked`

## Primary lane
- set_zero_time excluded/fixed-zero
- dewow excluded from primary lane
- AT-011 relative candidate policy unchanged
- energy_decay_gain conservative lane

## Scene summary
- GX-003: best `local` ntraces=`9` (trace_count=90, candidates=6)
- GX-004: best `local` ntraces=`5` (trace_count=105, candidates=6)
- GX-005: best `local` ntraces=`5` (trace_count=105, candidates=6)
- GX-006: best `local` ntraces=`9` (trace_count=105, candidates=6)

## Gate evaluation
- status: `blocked`
- risk_flags: `['synthetic_thin2d_scene_limit']`
- Thin 2D limitations remain and no field-performance claim is made.
- No overall AutoTune superiority claim is made.
