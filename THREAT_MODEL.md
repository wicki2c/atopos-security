# Atopos Threat Model

## Purpose
This document defines the threat model and security boundaries for Atopos. It is intended to help reviewers understand what the system aims to protect, what adversaries are considered, and what is explicitly out of scope.

## Assets
- Message plaintext
- Room secrets / key material (client-side)
- Message integrity (tamper resistance)
- Metadata minimisation where feasible

## Trust boundaries
- Client devices are trusted to hold keys and perform encryption/decryption.
- The service backend is not trusted with message plaintext and is designed not to possess decryption keys.
- Relays/transports may be untrusted and may observe timing and routing metadata depending on configuration.

## Adversaries considered
### Passive network observer
May observe traffic timing and volumes. Risk varies by routing mode and padding/cover strategies.

### Malicious relay
May attempt traffic correlation or disruption. Cannot decrypt ciphertext without key material.

### Server compromise
Attacker obtains server-side data and may attempt to extract secrets. The system is designed not to store message decryption keys server-side.

### Coercion / compelled disclosure
A user may be compelled to reveal content. Deniability features aim to reduce harm but do not guarantee protection in all coercion scenarios.

## Out of scope
- Endpoint compromise (malware on client device, compromised browser)
- Malicious participant recording content (screenshots, copy/paste, external recording)
- Guaranteed anonymity against a global passive adversary
- Formal cryptographic proofs beyond standard assumptions

## Residual risks
- Traffic analysis may still be possible depending on adversary capability and routing configuration.
- Infrastructure logs outside application control (e.g., some reverse-proxy layers) may exist and are not always measurable by the application.
- User operational security (device security, sharing room links) is critical.

## References
- [Security whitepaper](./WHITEPAPER.md)
- [Transparency report](./TRANSPARENCY_REPORT.md)
- [Disclosure policy](./DISCLOSURE_POLICY.md)
