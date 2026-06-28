# Changelog

Notable changes to this project. Newest first.

## [0.1.0] - 2026-06-28
- First release of the **FlowProof for n8n** community node (`n8n-nodes-flowproof`).
- Two operations: **Check** (full diagnostic) and **Verify** (pass/fail verdict to gate a deploy).
- Runs entirely inside n8n — no API, no network, no credentials leave the instance. A CI parity test asserts it agrees with the FlowProof reference engine on every fixture.
