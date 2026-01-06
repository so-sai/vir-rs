# VIR-rs Specification v0.1 – Proof of Core Invariants

**Status**: DRAFT (Canonical)
**Date**: 2026-01-06
**Context**: Post-Sovereign AI Safety Protocol. A compile-time and runtime framework for enforcing the Three Core Invariants.

## 1. Objective
To provide a reference implementation in Rust that enforces IVA (Agency), IAA (Accountability), and IER (Entropy Resistance).

## 2. Design Principles
- **Unrepresentability**: Invalid states must be impossible to represent.
- **Fail-Fast**: Invariant III (Entropy Resistance) is checked first.
- **Ownership = Accountability**: Proofs are linear types (consumed on use).
- **Supply Chain Hardening**: All dependencies pinned.

## 3. Core Type System
RawAction<T> --verify()--> Result<AlignedAction<T>, AlignmentError>
                                  |
                                  +--execute(proof)--> Result<Executed<T>>

## 4. Security Standards (Jan 2026)
- **Rust**: 2024 Edition
- **Hashing**: BLAKE3 1.8.2
- **Signatures**: ed25519-dalek 2.2.0
- **Hardening**: forbid unsafe, deny warnings, panic=abort

---
Reality remains the final arbiter.
