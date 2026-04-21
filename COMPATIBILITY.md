# Compatibility

An implementation may be described as `.luku`-compatible only if it correctly implements the normative requirements of the specification.

Compatibility includes, at minimum:

- archive structure
- required file names and media type behavior
- canonical serialization rules
- record signature verification
- block integrity verification
- manifest sealing rules
- evidence interpretation boundaries where normative

## Trust compatibility

Support for custom roots or alternate trust profiles does not by itself make an implementation incompatible.

However, production-valid verification under the LukuID trust model depends on verifier trust configuration and recognized trust anchors.
