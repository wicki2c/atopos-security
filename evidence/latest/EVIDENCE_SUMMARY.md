# Evidence Summary (Publish-Safe)

This document summarises the most recent production validation run for Atopos.

## Run Overview

- Run date (UTC): 2026-02-22T22:37:46Z
- Run context: production
- Completeness: complete
- Overall status: pass

## Validation Results

| Check | Result |
|-------|--------|
| Fragment non-transmission | Pass |
| Database schema secret scan (schema-level) | Pass |
| Log redaction audit (bounded scan) | Pass |
| Envelope size invariant validation | Pass |
| Routing mode verification | Pass |

## Completeness Inputs

All required validation inputs were present:

- Database connection available
- Base URL reachable
- Application log paths accessible

## Notes

- This summary is publish-safe and does not include hostnames, environment values, raw logs, or infrastructure details.
- Evidence reflects application-level checks only.
- Endpoint compromise and malicious participant scenarios remain out of scope.
- External infrastructure logs (e.g., reverse proxies outside application control) are not measured by this run.

For disclosure or independent review requests, see:
- `DISCLOSURE_POLICY.md`
