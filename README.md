# Atopos Security

This repository contains public security documentation and publish-safe evidence artifacts for **Atopos**.

## What’s included
- [Security whitepaper](./WHITEPAPER.md)
- [Threat model](./THREAT_MODEL.md)
- [Transparency report](./TRANSPARENCY_REPORT.md)
- [Disclosure policy](./DISCLOSURE_POLICY.md)
- Evidence artifacts (publish-safe): [`evidence/latest/`](./evidence/latest/)

## Latest evidence (publish-safe)
- [Evidence summary](./evidence/latest/EVIDENCE_SUMMARY.md)

## Scope / limitations
Atopos is designed so the service does **not possess message decryption keys** by design.  
This does **not** protect against:
- endpoint compromise,
- malicious participants,
- screenshots/copying.

## Responsible disclosure
See [DISCLOSURE_POLICY.md](./DISCLOSURE_POLICY.md).

## License
Documentation in this repo is licensed under CC BY 4.0. See [LICENSE](./LICENSE) and [SECURITY_NOTICE.md](./SECURITY_NOTICE.md).
