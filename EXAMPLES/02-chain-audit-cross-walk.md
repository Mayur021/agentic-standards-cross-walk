# Example 2 — Chain Audit / Delegation Preservation Across Substrates

The structural axis of multi-hop delegation preservation — preserving the originating principal + all intermediate authorizations + all scope narrowings as an immutable record — recurs across the standards landscape.

## The axis

**Chain audit / delegation preservation** = multi-hop agent delegation must preserve the originating principal and every intermediate authorization and scope narrowing as an immutable record that prevents re-attribution and structurally enforces worst-case chain rules.

**Architectural axes mapped:** A3 (Chain) primarily; A6 (Immutability) secondary
**Harm categories mitigated:** H8 (Information Integrity), H9 (Information Security), H12 (Value Chain and Component Integration)

## Cross-walk table

| Substrate | Vocabulary used | Status qualifier |
|---|---|---|
| CSA NHI v1.0 four-element attribution language (para 222) | "delegator / agent / intent / actions" — anchored verbatim in v1.0 Working Draft at paragraph 222 (joint Mallikarjunarao Sunke + Mayur) | Anchored in CSA NHI v1.0 Working Draft (joint peer-review contribution; in editorial closure) |
| CSA NHI v2.0 (forthcoming) six-property schema property 5 | "Parent-chain binding" (jointly Mallikarjunarao Sunke + Mayur chain-id binding R8) | NOT in v1.0; targeted for v2.0 inclusion (joint Mayur + Mallikarjunarao Sunke) |
| CSA NHI v2.0 (forthcoming) six-property schema property 6 | "Immutability of originating principal as schema property" (Mallikarjunarao Sunke) | NOT in v1.0; targeted for v2.0 inclusion (joint Mayur + Mallikarjunarao Sunke) |
| IETF RFC 8693 | "Actor claims" in OAuth token exchange | Published RFC |
| CoSAI WS4 PR #116 Layer 5 | "Delegation Chain Preservation (RFC 8693 token exchange + actor claims)" | WIP |
| CoSAI WS4 #99 Agent Credentials RFC | "Delegation chain" sub-section in 8-co-author RFC | Accepted 2026-06-04; 4-week draft window |
| A2A Protocol v1.0.1 | "Delegation chain" in AgentCard with JWS + JCS signature verification | Published 28 May 2026 |
| Atlas Framework | "ML Lifecycle Provenance" | arXiv 2502.19567 (Feb 2025) |
| agentrust-io (public reference) | "VADP scope-narrowing in artifact #8" | Public WS4 #99 reference (pre-launch private until 2026-06-23) |
| CSA Agentic Trust Framework I-3 | "Ownership Chain" | Public Review Draft v0.9.1 |
| CSA NIST AI RMF Agentic Profile AG-MS.3 | "Delegation Chain Integrity" | CSA Labs draft March 2026 |
| OWASP AISVS C9.2.7 | "worst-case classification governing across a multi-step chain" | Proposed for v1.01 (merged 2026-05-27 into research/ directory) |
| CSAI Foundation AARM (Errico) | "tamper-evident receipts" recording the action chain | arXiv 2602.09433 |
| W3C VC Data Model 2.0 | `validFrom` / `validUntil` + `proof` mechanism preserving issuer chain | W3C Recommendation 15 May 2025 |

## What the cross-walk reveals

1. **Multiple substrates** name the chain audit axis under different vocabularies. The CSA NHI v1.0 four-element attribution language at para 222 (Mallikarjunarao + Mayur joint peer-review contribution) is the anchored v1.0 primitive; the full six-property formalization including parent-chain binding (joint with chain-id binding R8 Mayur) is targeted for v2.0; RFC 8693 actor claims are the foundational protocol primitive.
2. **Composability gap** — RFC 8693 is published; CSA NHI v1.0 anchors the four-element attribution subset at para 222 (in editorial closure); the full six-property chain audit schema is targeted for CSA NHI v2.0 inclusion; CoSAI WS4 #99 is accepted but in 4-week draft; agentrust-io VADP is pre-launch private. The full composition is not yet expressible from public references alone.
3. **AISVS C9.2.7** (Proposed for v1.01) is the worst-case chain rule that operationalizes the audit primitive for runtime enforcement — without it, the schema exists but the runtime gate does not.
4. **A2A v1.0.1** (May 2026) is the first agent-to-agent protocol with native delegation chain + signature verification; cross-walk to CoSAI WS4 #99 is the natural integration path.

## Open contribution slots

- Promote the full CSA NHI six-property chain audit schema (chain-id binding, originating-principal immutability, audit telemetry surface; Mayur + Mallikarjunarao Sunke joint work) to CSA NHI v2.0; v1.0 anchors the four-element attribution language at paragraph 222
- Add a worst-case chain rule reference to A2A AgentCard delegation chain extension
- File IETF Internet-Draft for full six-property chain audit schema (CSA NHI v2.0 hook; Q3-Q4 2026; WIMSE-adjacent)
- Add chain audit cross-walk to CSA AICM v1.0 STA (Supply Chain Management & Transparency) domain
- Extend SPDX 3.1+ AIAgent (PR #1257) with `delegationChainBinding` property

## Citation

When citing this example:

> Cross-Walking the Agentic Standards Landscape, Example 2 (Chain Audit Across Substrates). Mayur Agnihotri + Mallikarjunarao Sunke joint anchor on CSA NHI v1.0 four-element attribution at para 222 + v2.0-targeted six-property formalization, 2026-06-11 (re-baselined 2026-06-15). https://github.com/Mayur021/agentic-standards-cross-walk/blob/main/EXAMPLES/02-chain-audit-cross-walk.md
