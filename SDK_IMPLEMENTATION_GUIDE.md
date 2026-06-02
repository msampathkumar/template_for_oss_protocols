# SDK Development & Conformance Guidelines

This document outlines the required standards and guidelines for developing language-specific SDKs and reference implementations for **[Protocol Name]**. 

To ensure a unified developer experience and interoperability across the ecosystem, all official and community-supported SDKs should adhere to the following principles.

## 1. Architectural Guidelines

When building an SDK for **[Protocol Name]**, keep the following design principles in mind:

* **Separate Transport from Protocol:** The core state machine, schema validation, and payload formatting should be strictly separated from the transport layer (e.g., HTTP, WebSockets, stdio). This allows developers to swap out network protocols without rewriting the core logic.
* **Idiomatic Implementation:** While the protocol behavior must be identical across languages, the API surface should feel native to the target language (e.g., using `async/await` in Python/TS, Goroutines in Go, or Traits in Rust).
* **Fail Fast on Validation:** SDKs must validate incoming and outgoing payloads against the official schemas *before* processing them or sending them over the wire.

## 2. Conformance Testing

If your SDK claims to support **[Protocol Name]**, it must pass the official Conformance Test Suite. This ensures that System A (built in Python) can seamlessly talk to System B (built in TypeScript).

### The Test Suite
[Insert instructions here on how to run the conformance suite, e.g., "We provide a Dockerized conformance runner that acts as a dummy server/client."]

### Required Test Categories
Every SDK must implement automated tests covering:
* **Schema Validation:** Ensure both valid and malformed JSON/Data payloads are correctly accepted or rejected.
* **State Machine Verification:** Ensure the SDK handles unexpected lifecycle events (e.g., receiving a `Disconnect` signal before `Handshake` is complete) gracefully.
* **Error Handling:** Verify that the SDK standardizes error codes exactly as defined in the protocol specification.

## 3. Cross-Language & Cross-Version Compatibility

Because **[Protocol Name]** is language-agnostic, implementations must not rely on language-specific quirks (e.g., assuming JSON keys are naturally ordered, or mishandling large integers).

### Version Negotiation
SDKs must gracefully handle version mismatches:
1. **Handshake:** Every connection must begin with a version handshake.
2. **Backwards Compatibility:** SDKs should ideally support the current major version `vX.Y` and the immediate prior major version `v(X-1).Y`.
3. **Graceful Degradation:** If an SDK receives a payload with fields from a newer minor version, it must ignore the unknown fields rather than crashing, as per our [Extensibility/Deprecation Policy](#).

## 4. New SDK Checklist

If you are building a new SDK for the protocol, please ensure you complete the following steps before officially releasing it or submitting it for community adoption:

- [ ] **Define/Review Confirmation Tests Repository.** (Understand the required test suite and expected outputs).
- [ ] **Create your SDK repo.** (Set up your independent repository following our architectural guidelines).
- [ ] **Run Confirmation Tests to share report as defined in Confirmation Tests Repository.** (Execute the test suite against your implementation and publish the passing results).

### Interoperability CI
All official SDKs must rune a regular(daily/weekly) test matrix CI pipeline. This pipeline should aim to ensure 100% cross-language compatibility on the latest `main` branch.

---
> **Want to build an SDK?**
> Please open an Issue proposing the new language SDK before starting work to ensure it aligns with the current roadmap and avoids duplicated effort!

Build to share ❤️ Happy coding! 
