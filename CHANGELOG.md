# Changelog

## 1.1.0
- Added the `verification` record type: a non-chain-advancing external verification record for external registry, marketplace, authority, customs, and compliance checks against existing evidence
- Defined explicit record classification: native chain-advancing records (`scan`, `environment`, `biometric`), device-attested auxiliary records (`attachment`, `location`, `custody`), and external verification records (`verification`)
- Defined the response-preservation rule: hashing the exact original provider response bytes (`response.checksum`) is mandatory, while disclosing those bytes as a content-addressed attachment (and any parsed `response.data`) inside a given archive is an optional, privacy-preserving choice, with explicit `disclosed` / `undisclosed` / `disclosed_mismatch` response-disclosure states
- Defined the extensible, non-Boolean `status` model, generic `scheme`/`provider` model, optional `collector_attestation`, and `recorded` / `authority_verified` / `authority_verified_and_collector_attested` assurance levels
- Clarified that archive seals in `seals.json` sign only the archive-level manifest commitment and never carry record-level verification results
- Added optional, purely informational `verification.info` (self-describing scheme metadata: `name`, `description`, `version`, `documentation`) and optional `verification.result_description`, both English-only in serialized evidence and explicitly untrusted for cryptographic/trust/status/assurance purposes — schemes remain decentralized and self-describing with no central scheme registry
- Added the External Verification (`verification`) Record Check to the forensic verification workflow
- Freeze-readiness pass: scoped the device trust/time/DAC/heartbeat/counter/record-envelope model explicitly to device-originated records (native + device-attested auxiliary), clarifying that `verification` records inherit none of that model by default
- Normatively defined `verification.subject` (evidence-target subjects reusing existing record/batch/block/archive commitments, and free-form domain subjects), with no central subject registry
- Consolidated the Batch Digest Rule around one "batch binding value" concept (signature, or `response.checksum` for an unsigned `verification` record) and replaced the overclaiming backward-compatibility language with an honest statement of what pre-v1.1.0 verifiers can and cannot still check
- Fixed canonicalization example bugs: `environment`'s canonical string/structural prefix was missing `firmware`; `biometric`'s example payload was missing `id`/`uptime_us`/`firmware`; a `scan` genesis-record example and the `attachment` example's `merkle_root` handling were internally inconsistent
- Fully specified `manifest.sig` (Ed25519 detached signature over `manifest.json`'s raw bytes, self-certifying via an optional `manifest.json.exporter_public_key`) and clearly distinguished it from the mandatory ML-DSA-65 self seal, instead of leaving its algorithm/key source/verification semantics unspecified
- Strengthened the Luku-defined detached external-identity and `collector_attestation` signatures to bind `result_code`, a canonicalized `subject` commitment, and the validity interval, not just `status`; clarified that a provider-native signed artifact (JWS/COSE/etc.) remains the sole authority over what it itself covers
- Clarified that the canonical-payload colon restriction applies only to values spliced directly into a colon-delimited signed payload, not to free-form metadata such as `info.documentation`/`result_description`
- Fixed the example `verification` record's `result_description` to match the strength of its `result_code`, and corrected several "a record was signed by a device" overclaims in the Evidence Interpretation tables and workflow to account for `verification` records

## 1.0.0
- Initial public release of the `.luku` forensic evidence specification
- Defined archive structure, block integrity model, native and auxiliary record types
- Added trusted time model, evidence interpretation rules, and verifier workflow
