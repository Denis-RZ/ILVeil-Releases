# ILVeil v2.2.0

## Native VM Runtime Variant

- generated native runtime variants are specialized per protected deployment
- deployment-bound key material uses a separate sidecar and keyed runtime cache
- Native Capability Gate V2 binds the native call to the protected deployment
- CLI supports `--vm-native-runtime-variant`, `--vm-native-capability-gate-v2`, and exact native method selection
- crackme demonstration now combines managed VM hash validation with a load-bearing native envelope gate

## Verification

- Crackme tests: 17/17 passed
- Native VM Runtime Variant smoke: 11/11 passed
- protected crackme: valid serial accepted, invalid serial rejected, corrupted key material fails closed
- public demo package: `releases/ILVeil-Crackme-V2.zip`

## Included

- self-protected Windows x64 desktop build (requires the .NET 9 Desktop Runtime)
- expanded VM return shapes, instance operations, switches, and auto-selection
- Application Guard SDK with ECDSA-signed capabilities
- derived values and checkpoint-bound feature flows
- encrypted embedded resources, including flow-bound decryption
- Application License Issuer with DPAPI-protected private keys
- in-product Guard states, integration guide, starter-package export, and post-protection verification
- refreshed desktop layout and current screenshots

## Compatibility and scope

Normal binary protection does not require source changes. Application Guard is optional and requires source integration for strong value/flow binding. The integrity marker remains audit-only and is explicitly reported as not runtime-enforced.

## Integrity

See `releases/SHA256SUMS.txt` for the published package checksum.
