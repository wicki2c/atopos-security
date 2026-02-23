# Atopos Security Whitepaper

## Executive summary

Atopos is an encrypted, ephemeral communication system designed so that:

- Decryption keys are generated and held client-side.
- The server stores only ciphertext and opaque identifiers.
- URL fragments containing room secrets never reach the server.
- In higher privacy modes, message envelopes are padded to fixed sizes.
- Optional routing modes include direct transport and privacy-enhancing routes (e.g., Tor or mixnet), depending on configuration.

Security properties are based on architectural constraints, not on “trust us” assurances.

## Architecture overview

### Client
- Derives room key locally.
- Encrypts content before transmission.
- Decrypts content only with local key material.

### Server
- Accepts encrypted envelopes.
- Stores ciphertext only.
- Does not possess the decryption key and is not able to decrypt stored ciphertext.

### Relays / routing
- Carry ciphertext between participants.
- May observe timing or transport metadata depending on the routing mode and threat model.
- Cannot decrypt content without client-held key material.

## Key properties

### 1) Server does not possess decryption keys
Atopos is designed so that the service does not have access to message decryption keys. Message content is encrypted client-side and stored/transmitted as ciphertext.

### 2) Room secrets remain client-side
Room secrets are represented in a way that does not require sending them to the server (e.g., via URL fragment mechanisms). The system is structured such that the server does not need to receive the room secret in order to operate.

### 3) Ciphertext-only storage
The server is intended to store opaque ciphertext and non-sensitive operational fields required for delivery and accounting. It is not designed to store message plaintext or room secrets.

### 4) Log redaction and minimisation
Atopos is designed to avoid logging message plaintext or room secrets. Logging is intended to be bounded and redacted where necessary.

### 5) Envelope size invariants (privacy modes)
In higher privacy modes, envelopes are padded to fixed sizes to reduce message length inference from ciphertext size. This does not eliminate all traffic analysis risks but aims to reduce leakage related to message length.

### 6) Routing verification (transport modes)
Atopos supports multiple routing modes based on configuration. Transport mode selection affects what a network observer may infer (e.g., IP-level metadata), and should be evaluated against the threat model.

## Server compromise analysis

If the server is compromised, an attacker may obtain:
- encrypted blobs (ciphertext),
- opaque identifiers and operational metadata,
- timing information related to delivery.

A server compromise does not automatically grant access to:
- room secrets,
- client key material,
- plaintext message content.

Without client-held key material, decrypting correctly implemented modern ciphertext is considered computationally infeasible under standard cryptographic assumptions.

## Limitations and non-goals

Atopos does not claim to:
- protect against a compromised client device,
- prevent malicious participants from leaking content,
- eliminate all traffic analysis,
- provide guaranteed anonymity against a global passive adversary.

Atopos prioritises conservative, reviewable claims.

## Further reading
- [Threat model](./THREAT_MODEL.md)
- [Transparency report](./TRANSPARENCY_REPORT.md)
- [Disclosure policy](./DISCLOSURE_POLICY.md)
- Evidence artifacts: [`evidence/latest/`](./evidence/latest/)
