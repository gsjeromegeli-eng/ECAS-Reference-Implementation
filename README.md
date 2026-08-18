# ECAS Reference Implementation

This repository provides supplementary research materials for the study:

**Enhanced QR Code-Based Certificate Authentication Model Utilizing
Elliptic Curve Cryptography (ECC), Zero-Knowledge Proof (ZKP),
and Multi-Factor Authentication (MFA)**

## Purpose

This repository provides supplementary materials to support the
reproducibility and further evaluation of the proposed certificate
authentication model.

## Repository Contents

### Simulated Certificate

`simulated_certificate.pdf`

A synthetic certificate containing a QR code generated using the
proposed system. The certificate uses simulated information and
does not contain real student or graduate records. The certificate
design is an example certificate only created using Canva.

### QR Payload Specification

`qr_payload_specification.md`

Describes the structure and encoding of the QR-code payload used
by the system, including the certificate identifier, unique
identifier, and Schnorr ZKP proof components.

### Reference Source Code

`source_code/`

Contains selected source-code components demonstrating the
cryptographic and verification mechanisms used in the proposed
system, including ECC/ECDSA, Schnorr-based ZKP, QR payload
processing, and OTP generation and validation.

The source code is provided as a sanitized reference implementation
and does not contain production credentials, private keys, or
confidential institutional information.

## Cryptographic Parameters

- ECC curve: NIST P-256 (secp256r1)
- Digital signature: ECDSA
- Hash function: SHA-256
- ZKP: Schnorr protocol
- ZKP nonce: 32-byte random nonce generated using a CSPRNG
- OTP: Random 6-digit numeric OTP
- OTP validity: 5 minutes

## QR Payload

The QR payload uses the `ECAS-CERT:` prefix and contains the
certificate identifier, unique identifier, and Schnorr ZKP proof
components (`R`, `e`, and `s`).

The payload is processed using Base64 decoding and XOR
deobfuscation before the JSON structure is parsed.

## Academic Use

The materials are provided for academic and research purposes,
including reproducibility, verification, and further development
of the proposed authentication model.

## Citation

Please cite the corresponding conference paper when using these
materials in academic work.

## Disclaimer

The certificate and associated data included in this repository
are simulated and are intended only for research and demonstration
purposes.
