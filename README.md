# Kubernetes Incident Response Lab

**Status: Planned**

I'm building a small asset catalog API backed by PostgreSQL to practice diagnosing container and Kubernetes failures. The catalog will use synthetic records. I'll establish a working baseline in Docker Compose, then deploy the same API image to a local Kubernetes cluster.

## Milestones

1. **Docker Compose baseline.** Run the API and PostgreSQL, seed one asset, and use `curl` to retrieve it. Explain how the API reaches the database and what confirms the request succeeded.
2. **Kubernetes baseline.** Deploy the same API image locally, configure its database connection and readiness probe, and verify that a request reaches a ready pod through the Service.
3. **Incident 1 — API starts but never becomes ready.** Introduce a bad database setting. Use pod status, events, logs, and a connectivity check to identify the cause. Restore the setting and repeat the baseline request.
4. **Incident 2 — healthy pods, no Service endpoints.** Introduce a selector mismatch. Compare the Service selector, pod labels, and EndpointSlices. Correct the mismatch and verify that requests succeed again.

## Lab notes

I'll write the configuration, run the commands, and record the evidence myself. Each incident write-up will cover the symptom, hypotheses, commands and observations, root cause, fix, and verification.

**First checkpoint:** Retrieve one seeded asset through Docker Compose and explain the request path from `curl` to PostgreSQL.
