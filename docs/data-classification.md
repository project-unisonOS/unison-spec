# Data Classification

- **Public**: public docs/site content. No auth required.
- **Internal**: source code, configs, non-prod artifacts. Restrict to org contributors.
- **Sensitive**: user profiles/context graphs, consent state, telemetry with identifiers. Encrypt at rest, mTLS in transit; policy/consent checks before access; limited retention.
- **Highly-sensitive**: credentials/tokens, model API keys, actuation commands, VPN configs, consent/intents tied to identity. Store only in Vault/Secret Manager; shortest TTL; strong authN/Z + step-up; restricted logging (metadata only).

Handling rules:
- Tag resources with classification; enforce at read/write via policy.
- Redact PII and secrets in logs; prefer hashes/truncation.
- Use signed artifacts (images/policy bundles) and mTLS for sensitive/highly-sensitive flows.
- Default-local processing; avoid sending sensitive data to external providers unless explicitly consented and policy allows.
