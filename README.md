# dotluku

The canonical specification repository for the `.luku` forensic evidence format.

`.luku` is a portable, offline-verifiable cryptographic evidence container designed for signed device-originated records, append-only archive integrity, and long-term trust validation.

> License: The specification text in this repository is licensed under Creative Commons Attribution 4.0 International (`SPDX: CC-BY-4.0`). See [LICENSE](LICENSE).

## Specification

- Current stable version: 1.0.0
- Read the Spec: [LUKU.md](LUKU.md)

## What this repository contains

This repository defines:

- the `.luku` archive structure
- record formats and canonical serialization rules
- verification workflow
- block integrity model
- evidence interpretation boundaries
- inline record examples within the versioned specification files

## Reference implementations

Reference tooling and implementations are available separately:

- [LukuID SDK](https://github.com/lukuid/sdk)
- [LukuID CLI](https://github.com/lukuid/cli)

## Compatibility

Implementations MUST follow this specification to be considered `.luku`-compatible.

## License

The specification text in this repository is licensed under CC BY 4.0 (`SPDX: CC-BY-4.0`). See [LICENSE](LICENSE).
