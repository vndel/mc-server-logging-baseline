# Minecraft Server Logging Baseline

Logging conventions for Paper and Velocity services that preserve diagnostic value while limiting sensitive data exposure. Logging policy should be configured per plugin and reviewed after upgrades.

## Baseline
- Use UTC timestamps and include service identity, version, and environment in structured records.
- Keep error context and correlation identifiers; avoid logging passwords, tokens, session secrets, or full connection headers.
- Do not collect player chat or persistent IP history by default.
- Redact UUIDs and addresses before sharing diagnostic bundles publicly.
- Set access controls and retention periods based on operational purpose.
- Rate-limit repetitive failures without hiding the initial cause or recovery transition.

Validate redaction with synthetic fixtures before enabling centralized ingestion. This repository does not prescribe a legal retention period.

## Files
- `policy.yml`: example field and retention policy.
- `incident-log-checklist.md`: safe collection checklist.