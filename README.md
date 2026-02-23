# atopos-security
> This repository contains official Atopos security documentation and
> publish-safe evidence artifacts. Documentation is licensed under
> CC BY 4.0. See LICENSE and SECURITY_NOTICE.md.

This repository contains public security documentation and publish-safe evidence artifacts for **Atopos**.

## What’s included
- Security whitepaper
- Threat model
- Transparency report
- Disclosure policy (responsible vulnerability reporting)
- Claims matrix and security tests
- Evidence artifacts generated from production runs (publish-safe)

## Evidence
Evidence artifacts are published under:
- `evidence/latest/`

These artifacts are designed to support review of specific claims (see `SECURITY_CLAIMS_MATRIX.md`) without publishing secrets, hostnames, IPs, raw logs, or environment values.

## Scope / limitations
Atopos is designed so the service does not possess message decryption keys.
This does **not** protect against:
- endpoint compromise,
- malicious participants,
- screenshots/copying.

## Responsible disclosure
See `DISCLOSURE_POLICY.md`.
