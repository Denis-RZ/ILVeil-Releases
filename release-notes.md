# ILVeil v2.0.0

## Included

- Windows x64 desktop build (requires the [.NET 9 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/9.0) -- see "Distribution change" below)
- built-in Help assets
- activation UI
- managed protection workflow
- Native AOT publish workflow
- self-protected: this build is itself hardened with ILVeil's own managed protection pipeline

## What's New Since v1.0.0

- Key-method virtualization ([ILVeilVirtualize]) now covers real control flow -- if/else, ternaries, and loops with direct relational conditions (`if (x < y)`, `for (...)`) -- instead of only straight-line int/bool logic.
- Each virtualized method's bytecode now uses its own independent opcode mapping, so recovering one method's mapping no longer helps decode another.
- A stack/control-flow verifier now runs before a method is virtualized, so anything with an inconsistent or unsupported stack shape safely falls back to the existing hardening path instead of being guessed at.
- General protection-pipeline hardening: masked dispatcher state constants, additional string-decode variants, and payload-storage hardening for virtualized methods.

## Distribution Change

Previous releases shipped a single self-contained `.exe` (portable, no separate .NET install required). v2.0.0 ships as a framework-dependent Windows x64 build instead, so it requires the **.NET 9 Desktop Runtime** to be installed. This changed because ILVeil's own self-protection step cannot yet safely process a self-contained single-file bundle -- shipping this release self-protected (matching how ILVeil is meant to be used) took priority over the portable packaging format. Restoring a self-protected, self-contained package is tracked as future work.

## Licensing

This build runs as the Free edition by default (no `product-license.json` bundled). For commercial Pro licensing or evaluation requests, contact [dengwebdev@gmail.com](mailto:dengwebdev@gmail.com).

## Integrity

See `releases/SHA256SUMS.txt` for the published package checksum.
