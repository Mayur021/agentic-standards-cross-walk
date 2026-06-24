# Example 1 — Action-Class Authority Across Substrates

> **AISVS citation note (updated 2026-06-24)**: The AISVS controls in the rows below shipped in OWASP AISVS v1.0 (released June 2026), in the Orchestration and Agentic Security chapter. C9.2.3 is the reversibility classification (Level 2), C9.2.4 is runtime enforcement by class (Level 2), and C9.2.10 is the worst-case-across-chain rule (Level 3). Verified against the released v1.0.

The structural axis of action-class authority recurs across the standards landscape under multiple vocabularies. This worked example shows the same axis expressed in 12 different substrates.

## The axis

**Action-class authority** = the property of an agentic system whereby each authorized action carries a declared class (read-only / reversible / external-reversible / irreversible) gated at the verb-layer of the runtime, evaluated against a manifest declaration rather than the agent's runtime claim.

**Architectural axes mapped:** A2 (Authority) primarily; A4 (Blast radius) secondary
**Harm categories mitigated:** H1 (CBRN), H4 (Data Privacy), H9 (Information Security), H12 (Value Chain)

## Cross-walk table

| Substrate | Vocabulary used | Status qualifier |
|---|---|---|
| OWASP AISVS C9.2.3 | "trusted reversibility classification" | Shipped in v1.0 |
| OWASP AISVS C9.2.10 | "worst-case chain rule + blast-radius independent axis" | Shipped in v1.0 |
| CSA Agentic Trust Framework I-5 | "Capability Manifest" | Public Review Draft v0.9.1 |
| CSA Agentic Trust Framework S-2 | "Action Boundaries" | Public Review Draft v0.9.1 |
| CSA NIST AI RMF Agentic Profile AG-MP.1 | "Tool Risk Classification (consequence scope, reversibility, auth, compositional risk)" | CSA Labs draft March 2026 |
| Singapore IMDA MGF Agentic AI v1.5 component 2 + 5 | "Instructions + Tools" | Published 20 May 2026 (v1.5) |
| OWASP LLM Top 10 LLM06 | "Excessive Agency" (mitigations: minimize functionality + permissions + autonomy) | v2 Published 2025 |
| OWASP ASI Sprint 1 ASI03 | "Identity & Privilege Abuse" | Sprint 1 draft |
| OWASP AST10 AST03 | "Over-Privileged Skills" | Incubator, v1.0-2026 |
| SPDX 3.1-RC1 PR #1257 | "agentTrustLevel + agentPermissionScope" | Open PR |
| CoSAI WS4 PR #117 ADLC-AD-A03 | "Reversibility taxonomy alignment per AISVS C9.2.3" | PR comment 2026-06-10 |
| CSAI Foundation AARM (Errico) | "actions classify as forbidden / context-dependent deny / context-dependent allow" | arXiv 2602.09433; CSAI Foundation flagship 2026-04-29 |
| Orchestration Layer Regulation | "regulation should shift to orchestration layer" | arXiv 2604.22819 (April 2026) |

## What the cross-walk reveals

1. **Twelve substrates** name the same axis under twelve different vocabularies.
2. **No single substrate** captures the full axis — the reversibility classification (AISVS C9.2.3) and the worst-case chain rule (AISVS C9.2.10) compose; CSA ATF I-5 + S-2 also compose; IMDA Instructions + Tools compose. The axis is structurally composite.
3. **Status differential** — some are Published (LLM Top 10 v2, IMDA v1.5); some are Shipped (AISVS C9.2.3/9.2.10); some are Public Review Draft (CSA ATF); some are Open PR (SPDX 3.1-RC1 #1257); some are arXiv preprint (AARM, Orchestration Regulation). Citation discipline applies in every direction.
4. **Convergence opportunity** — the unified vocabulary "action-class authority" is the integrating term. Adoption of this term in any single substrate's next revision creates cross-walk gravity for the others.

## Open contribution slots

- Add a unified-vocabulary appendix to any of the substrates above that lacks it
- Extend SPDX 3.1+ AIPackage with action-class as a declared property using PR #1267 additionalInformation pattern
- Add the cross-walk explicitly to CSA AICM v1.0 control catalog
- File IETF Internet-Draft `draft-agnihotri-action-class-authority-00` (Q3-Q4 2026)

See [COSAI-FOCUSED-CROSSWALK.md](../COSAI-FOCUSED-CROSSWALK.md) "Open contribution slots" section for the full slot list.

## Citation

When citing this example:

> Cross-Walking the Agentic Standards Landscape, Example 1 (Action-Class Authority Across Substrates). Mayur Agnihotri, 2026-06-11. https://github.com/Mayur021/agentic-standards-cross-walk/blob/main/EXAMPLES/01-action-class-authority-cross-walk.md
