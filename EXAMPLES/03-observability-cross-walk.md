# Example 3 — Observability / Trace Audit Across Substrates

The structural axis of observability — every agent action and gate decision producing a cryptographically integrity-protected structured trace consumable by humans and downstream systems — recurs across the standards landscape.

## The axis

**Observability / trace audit** = every action and gate decision in an agentic system produces a structured trace record with cryptographic integrity protection, append-only audit semantics, and downstream consumption interfaces.

**Architectural axes mapped:** A7 (Observability) primarily; A6 (Immutability) and A3 (Chain) secondary
**Harm categories mitigated:** All 12 H-categories (observability is cross-cutting)

## Cross-walk table

| Substrate | Vocabulary used | Status qualifier |
|---|---|---|
| OWASP AOS (Agent Observability Standard) v0.1 | "Event interaction model (Observed Agent ↔ Guardian Agent) + AgBOM extending CycloneDX/SWID/SPDX" | Public Preview |
| CoSAI WS4 PR #116 Layer 6 | "Observable Trust (OpenTelemetry + runtime trace context)" | WIP |
| CSAI Foundation AARM (Errico) | "Tamper-evident receipts" recording the full action sequence | arXiv 2602.09433 |
| CSA Agentic Trust Framework B-1 + B-2 | "Structured Logging + Action Attribution" | Public Review Draft v0.9.1 |
| CSA NIST AI RMF Agentic Profile AG-MS.1 | "Behavioral Telemetry" | CSA Labs draft March 2026 |
| SPDX 3.0.1 AIPackage modelExplainability | "modelExplainability" property | Stable |
| EQTY Lab Lineage Explorer (public demo) | "vLLM provenance visualization" | Public demo at CoSAI WS1 |
| agentrust-io TRACE (public reference) | "GatewayClaim append-only Merkle registry" | Public reference via CoSAI WS4 #99 (pre-launch private until 2026-06-23) |
| CSA AAGATE Janus Shadow-Monitor Agent | "Pre-execution behavioral assessment" | arXiv 2510.25863 (Dec 2025) |
| C2PA (Content Provenance and Authenticity) | Cryptographic provenance for AI-generated content | C2PA spec (Coalition for Content Provenance and Authenticity) |
| OpenTelemetry trace context | "Trace context propagation" | OpenTelemetry standard |
| OWASP AISVS C13 | "Monitoring, Logging & Anomaly Detection" chapter | v1.0 release 2026-06-24 |
| CSA OpenClaw "behavioral monitoring/anomaly detection" | One of 8 control domains | Published 2026 |
| OCSF (Open Cybersecurity Schema Framework) | Trace + event schema for cyber defenders | CoSAI WS2 telemetry framework cites OCSF |
| CoSAI WS2 Telemetry framework | AI stack telemetry schema (OCSF-aligned) | Merged 5/5 (PR #114) |

## What the cross-walk reveals

1. **Fifteen substrates** touch the observability axis. OWASP AOS is the most operationally complete (event model + AgBOM); CoSAI WS4 Layer 6 is the architectural anchor; AARM tamper-evident receipts are the cryptographic primitive.
2. **AgBOM (OWASP AOS)** explicitly extends CycloneDX + SWID + SPDX — a built-in cross-walk into the BOM-layer family.
3. **Cross-walk gravity** — OCSF (Open Cybersecurity Schema Framework) is the existing cyber-defender trace schema; OWASP AOS + CoSAI WS2 telemetry framework both align to it. This is the convergence point where agentic observability meets cyber observability.
4. **AISVS C13** is the verification-controls layer of observability — what every system must verify. It composes with AOS (the trace format), C2PA (the content provenance), and AARM (the runtime receipts).

## Open contribution slots

- File AgBOM ↔ SPDX 3.1+ AIAgent cross-walk PR (after SPDX silent-observer norms satisfied, Week 6+)
- Add observability cross-walk row to CSA AICM v1.0 LOG (Log and Monitoring) domain
- Add cryptographic-integrity requirement to OWASP AOS receipt schema (SACP receipts per Issue #75)
- File IETF Internet-Draft on cross-walk between OCSF + AgBOM + AARM tamper-evident receipts (post-Q4 2026 IETF action-class authority I-D)
- Extend EQTY Lab Lineage Explorer to ingest OWASP AOS events (substrate-16 public-demo collaboration path)

## Citation

When citing this example:

> Cross-Walking the Agentic Standards Landscape, Example 3 (Observability Across Substrates). Mayur Agnihotri, 2026-06-11. https://github.com/Mayur021/agentic-standards-cross-walk/blob/main/EXAMPLES/03-observability-cross-walk.md
