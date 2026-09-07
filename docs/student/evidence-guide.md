# Task 1.3 evidence guide

Use [the frozen before/after evidence pack](evidence-pack.json) for graded
interpretations. Perform the required local repairs and experiments, then retain
your local evidence for the final engineering defense. Passing the answer check
does not replace the runtime checks of your implementation.

Both phases contain real synthetic HTTP requests, saved status records, Redis
entries, worker logs, Jaeger traces, metric exposition and the response to the
published dashboard query. The before phase is the seeded Task 1.3 runtime. For
the after capture, the three permitted source files were replaced in a disposable
checkout by their supplied Task 1.4 versions. Provenance includes normalized source
hashes. That describes the capture; your implementation is checked by behavior.

Compare the publisher and processing span `traceID` values and the processing
span's `CHILD_OF` reference. Check the model span's parent separately. Use the
durable exception ID to correlate HTTP, Redis, worker and saved state within each
phase. Different phases deliberately use different reading and exception IDs.

Read the metric's actual observations and application labels separately from
its name. Prometheus adds `job` and `instance`; histogram buckets add `le`.
Those do not represent per-request application dimensions. The dashboard query
response is an observed vector: distinguish an empty vector, a finite numerical
value and a query error. A finite local histogram estimate does not establish a
production SLO, nor is it an exact individual request duration.

The source excerpt explains the seeded conversion and carrier handling. In the
answer sheet, distinguish directly observed trace/query relationships from a
causal diagnosis inferred from source and runtime together. `not-established`
means the required evidence is absent. Compare HTTP outcomes, terminal states and
summaries to determine whether the captured business behavior changed.

Repair prose is not graded. The bounded diagnoses and interpretations are graded
against this pack, while `poe telemetry-repair` checks your actual HTTP-to-worker
trace parent chain, metric unit, bounded labels, dashboard query and business
behavior. Only the three source paths in the [Task contract](task-1-3-contract.md)
and `submission.yaml` are editable. The runtime histogram may be an aggregate
with no application labels, or use bounded `status`, `outcome` or `disposition`
labels from the finite states/dispositions checked by the public tests.
