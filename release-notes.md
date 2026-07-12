# ILVeil v2.0.0

Major protection and product-integration release.

## Included

- portable self-contained Windows x64 desktop build
- built-in Help assets
- activation UI
- managed protection profiles, VM auto-selection, string/control-flow/rename protection, and runtime guards
- Native AOT publish workflow
- Application Guard SDK with ECDSA-signed application capabilities
- derived-value and checkpoint-bound feature flows
- encrypted embedded resources, including flow-bound decryption
- Application License Issuer with DPAPI-protected private keys
- in-product Guard integration states, guide, starter-package export, and post-protection verification

## Compatibility and scope

Normal binary protection does not require source changes. Application Guard is optional and requires source integration for strong value/flow binding. The integrity marker remains audit-only and is explicitly reported as not runtime-enforced.

## Integrity

See `releases/SHA256SUMS.txt` for the published package checksum.
