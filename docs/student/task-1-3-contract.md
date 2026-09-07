# Task 1.3 contract

Only these paths are student-editable for this Task:

- `src/adapters/queue/redis_streams.py` (trace-context injection/extraction)
- `src/worker/runtime.py` (starting the worker span as a child of the extracted context)
- `src/worker/metrics.py` (removing the unbound metric label, fixing the unit bug)
- `submission.yaml`

All other files, including `src/domain/contracts.py`, are protected. If your fix genuinely requires a
change there, stop and ask your instructor before proceeding — do not assume it's permitted.

Run `poe verify` before submitting. Both `poe telemetry-repair` and `poe answers` must pass.

## Answer and assessment contract

Use `evidence-pack.json` and `evidence-guide.md` in this directory for the graded
structured analysis. The public check verifies shape, permitted changes, runtime behavior, and any
published arithmetic checks. Protected automated answer checks establish semantic
correctness against the public fixed pack. They do not add a held-out scenario.
Preserve actual local experiment evidence for the one final instructor defense and
label it separately from supplied reference data. No separate instructor Task-answer
grade is required; the final defense assesses empirical reasoning and judgment.
