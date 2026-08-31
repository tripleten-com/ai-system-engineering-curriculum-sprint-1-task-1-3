# Task 1.3 contract

Only these paths are student-editable for this Task:

- `src/adapters/queue/redis_streams.py` (trace-context injection/extraction)
- `src/worker/runtime.py` (starting the worker span as a child of the extracted context)
- `src/worker/metrics.py` (removing the unbound metric label, fixing the unit bug)
- `submission.yaml`

All other files, including `src/domain/contracts.py`, are protected. If your fix genuinely requires a
change there, stop and ask your instructor before proceeding — do not assume it's permitted.

Run `poe verify` before submitting. Both `poe telemetry-repair` and `poe answers` must pass.
