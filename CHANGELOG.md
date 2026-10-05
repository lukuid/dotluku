# Changelog

## 1.1.0
- Added the `verification` record type: a non-chain-advancing external verification record for external registry, marketplace, authority, customs, and compliance checks against existing evidence
- Defined explicit record classification: native chain-advancing records (`scan`, `environment`, `biometric`), device-attested auxiliary records (`attachment`, `location`, `custody`), and external verification records (`verification`)
- Defined the response-preservation rule requiring the exact original provider response bytes to be stored as a content-addressed attachment, with `response.data` as a non-authoritative parsed convenience representation
- Defined the extensible, non-Boolean `status` model, generic `scheme`/`provider` model, optional `collector_attestation`, and `recorded` / `authority_verified` / `authority_verified_and_collector_attested` assurance levels
- Clarified that archive seals in `seals.json` sign only the archive-level manifest commitment and never carry record-level verification results
- Added the External Verification (`verification`) Record Check to the forensic verification workflow

## 1.0.0
- Initial public release of the `.luku` forensic evidence specification
- Defined archive structure, block integrity model, native and auxiliary record types
- Added trusted time model, evidence interpretation rules, and verifier workflow
