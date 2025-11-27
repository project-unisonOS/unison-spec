# Unison Specification

This repo defines the stable contracts for the Unison system.

Scope:
- System architecture and module boundaries.
- Message formats between modules.
- Accessibility and safety requirements.
- Version compatibility between modules.

Any module in the platform must conform to these contracts. CI will block merges if it does not.

## Status
Core contracts (active) — source of truth for schemas; keep in sync with service implementations.

## Testing
Validate changes by running JSON schema validators or contract checks in dependent services; formal test harness TBD.
