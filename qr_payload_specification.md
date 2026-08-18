# QR Payload Format Specification

## Overview

The ECAS QR payload contains the information required for
certificate identification and Schnorr-based zero-knowledge
proof verification.

## Payload Prefix

The QR payload uses the following predefined prefix:

ECAS-CERT:

## Payload Structure

After decoding and deobfuscation, the QR payload is represented
as a JSON structure containing the following fields:

| Field | Description | Encoding |
|---|---|---|
| `cert_id` | Certificate identifier | String |
| `unique_id` | Unique certificate identifier | String |
| `R` | Schnorr commitment | Base64 |
| `e` | Schnorr challenge | Hexadecimal |
| `s` | Schnorr response | Hexadecimal |

## Example

```json
{
  "cert_id": "CERT-DEMO-001",
  "unique_id": "UID-DEMO-001",
  "R": "<Base64-encoded commitment>",
  "e": "<hexadecimal challenge>",
  "s": "<hexadecimal response>"
}

Processing

The QR payload is processed in the following sequence:

QR code is scanned.
The encoded payload is Base64 decoded.
XOR deobfuscation is applied.
The ECAS-CERT: prefix is validated.
The resulting JSON structure is parsed.
The certificate identifier and unique identifier are extracted.
The Schnorr proof components (R, e, and s) are extracted.
The proof is verified using the issuer's public key and
NIST P-256 curve parameters.
Cryptographic Parameters
Curve: NIST P-256 (secp256r1)
Hash function: SHA-256
ZKP protocol: Schnorr
ZKP commitment: R = kG
Nonce: 32-byte randomly generated value
