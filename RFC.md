# Cross-Walking the Agentic Standards Landscape: An Action-Class Authority Lens
## Public RFC for Community Contribution (Doc C)

**Author:** Mayur Agnihotri
**Date:** 2026-06-11
**Type:** Public RFC variant of operational cross-walk matrix
**Companion documents:** Doc 1 (operational matrix, internal) + Doc B (whitepaper v1.1 chapter)
**Status:** RFC — community contribution call open
**License:** CC BY 4.0 (proposed)
**Joint credit anchor:** Mallikarjunarao Sunke (CSA NHI 6-property chain audit schema — internal CSA IAM WG joint work; under review for v1.0)

---

## Abstract

Across four standards families (CSA, NIST, CoSAI, OWASP), one BOM-layer (SPDX), three governments (Singapore IMDA, US WhiteHouse, EU AI Act + G7), four identity protocols (MCP, A2A, WIMSE, W3C VCs+DIDs), the AGENTS.md standard, five academic substrates (Atlas / Persona Taxonomy / Orchestration Regulation / Threat Modeling / Model Openness), and adjacent industry substrates (AIUC-1, NuGuard.ai, Pitloom AIBOM), one structural axis keeps recurring: **the authority to act, declared at manifest level, gated at the verb layer, preserved across the delegation chain, audited in the trace**. This RFC presents a unified cross-walk lens for that axis across 60+ substrates, identifies where each substrate names it (under varied vocabulary), and asks the community to fill the gaps.

---

## 1. Why this RFC

The agentic-AI standards landscape has converged on a shared structural primitive — action-class authority — under multiple vocabularies: manifest-declared action class (OWASP AISVS C9.2.6 Proposed for v1.01), capability declaration (CSA ATF I-5 Capability Manifest), tool risk classification (CSA NIST AI RMF Agentic Profile AG-MP.1), action boundaries (CSA ATF S-2), permission scope (CSA NHI registry field 5), agentTrustLevel and agentPermissionScope (SPDX PR #1257), Tools and Instructions components (Singapore IMDA MGF v1.5), action attribution (CSA ATF B-2). These are the same axis under different names.

This cross-walk:
1. Names the axis explicitly (action-class authority) and the seven companion architectural axes (identity, chain, blast radius, lifecycle, immutability, observability, governance-role) it composes with;
2. Cross-walks each of 60+ substrates' schema-property level expression of the axis;
3. Maps each substrate property to both the architectural taxonomy and the NIST AI 600-1 12-risk harm taxonomy;
4. Identifies gaps where contribution slots are open;
5. Invites the community to validate, correct, extend, and contribute.

---

## 2. Scope (substrate inventory)

### CSA family (11 substrates)
CSA NHI v1 (public, May 2026, 6-field registry recommendation); CSA NHI 6-property chain audit schema (internal IAM WG joint Mayur + Mallikarjunarao Sunke, under review for v1.0); CSA Agentic Trust Framework v0.9.1 Public Review Draft (5 Core Elements / 25 requirements / 4-tier maturity); CSAI Foundation AARM (Errico arXiv 2602.09433); CSA AAGATE (arXiv 2510.25863); CSA NIST AI RMF Agentic Profile (Mar 2026 draft, 12 risk categories); CSA OpenClaw (8 control domains); CSA AICM v1.0 (243 controls / 18 domains); CSA MAESTRO (7-layer threat model); CSA AI Safety Initiative; CSA IAM WG.

### NIST family (8 substrates)
NIST AI RMF (AI 100-1, 2023); NIST AI 600-1 GenAI Profile (12-risk taxonomy, 2024); NIST IR 8596 Cyber AI Profile (Preliminary Draft Dec 2025); NIST SP 800-53 COSAiS (5 use cases, drafts in flight); NIST AI 100-2e2025 Adversarial ML (Mar 2025); NIST CSF 2.0 (Feb 2024, 6 functions); NIST CAISI AI Agent Standards Initiative (Feb 2026 launch, Q4 2026 Interoperability Profile); NIST GitHub repos (dioptra, agentic-research-evaluation-probes, AFL-agent, trojai-baseline-pruning, AIPD_TEVV).

### CoSAI family (11 substrates)
CoSAI Risk Map v1 (23 components / 35 controls / 36 risks / 10 personas / 8 lifecycle stages / 6 frameworks); CoSAI WS4 ADLC 7-phase framework (PR #117); CoSAI WS4 Identity Architecture Patterns (PR #116, WIP); CoSAI WS4 #99 Agent Credentials RFC (8 co-authors); CoSAI WS4 #113 Multimodal Agentic Security (accepted); CoSAI WS1 Supply Chain; CoSAI WS2 Defenders (Shared Responsibility + Incident Response + Telemetry); CoSAI WS3 Risk Governance (early); CoSAI TSC Security Principles for Agentic Systems; CoSAI Project CodeGuard; CoSAI Resources reference library.

### OWASP family (14 substrates)
OWASP AISVS v1.0 (release 2026-06-24, 14 chapters); AISVS C9.2.6 + C9.2.7 (Mayur PR #822 merged 2026-05-27 into research/, Proposed for v1.01); OWASP LLM Top 10 v2 (2025); OWASP Agentic Security Initiative ASI Sprint 1 Agentic Top 10; OWASP NHI Top 10 (2024); OWASP SPVS 1.0 + 1.5-AI (Mayur PR #14 + #15 + Issue #13); OWASP AOS v0.1 + AgBOM; OWASP AST10 Agentic Skills Top 10 (Incubator); OWASP AIVSS (Mayur Issue #36); OWASP secure-agent-playbook (new); OWASP Agent-Security-Regression-Harness; OWASP AI Testing Guide; OWASP AI Security & Privacy Guide; OWASP AIMM (AI Maturity Model).

### SPDX family (8 substrates)
SPDX 3.0.1 AI Profile (AIPackage); SPDX 3.0.1 Dataset Profile (DatasetPackage); SPDX 3.1-RC1 PR #1259 (dataset size — EU AI Act driver); SPDX 3.1-RC1 PR #1267 (additionalInformation extensibility); SPDX 3.1-RC1 PR #1257 (AIAgent v2); SPDX 3.1-RC1 PR #1249 (AI Prompt v2); SPDX 3.1-RC1 PR #1280 (AI chat template); SPDX 3.1-RC1 active issues (#1256, #1262, #1239, #1255, #1253, #1266).

### Government / regulatory family (5 substrates)
Singapore IMDA MGF Agentic AI v1.5 (8 components); WhiteHouse M-24-10 (Rights/Safety dual-axis + CAIO); EU AI Act Article 53(1)(d) GenAI template (enforcement 2 Aug 2026); G7 BSI SBOM for AI (7 core clusters); EU AI Act (full Act).

### Identity protocol family (11 substrates)
MCP 2025-11-25 (OAuth 2.1 + RFC 9728 + RFC 8707); A2A v1.0.1 (28 May 2026, AgentCard JWS+JCS + mTLS); WIMSE WG (7 drafts); WIMSE individual I-Ds on AI agents (4, NOT WG-adopted); W3C VC Data Model 2.0 (Recommendation 15 May 2025); W3C DID Core 1.0 (Recommendation since 2022); AGENTS.md (LF AAIF, no formal schema); OASF; Agent Trust Bench; SPIFFE/SPIRE foundational layer.

### Academic substrate (5 substrates)
Atlas Framework (arXiv 2502.19567, ML lifecycle provenance); Raymond Sheh Persona Taxonomy (arXiv 2511.15763, 4×4 grid); Orchestration Layer Regulation (arXiv 2604.22819); Threat Modeling for AI Asset-Centric (arXiv 2505.06315); Model Openness Framework (arXiv 2403.13784).

### Substrate-13 / 14 / 16 (public references only — discipline)
Anthropic Fable 5 + Mythos 5 (public refs only); agentrust-io / Imran Siddique at OPAQUE (pre-launch private until 2026-06-23; public WS4 #99 + .github profile refs); EQTY Lab / Rithikha Rajamohan + Cameron Fyfe (public CoSAI WS1 + SPDX-AI demos).

### Industry tooling (3 substrates)
AIUC-1 (Sanjeev Agarwal cluster); NuGuard.ai (Karen Bennet reference); Pitloom AIBOM (Arthit Suriyawongkul, Apache 2.0).

**Total: 89 substrate references across 12 families.** Full schema-property-level cross-walk in Doc 1 (internal operational matrix); narrative refactor in Doc B (whitepaper v1.1 chapter).

---

## 3. Unified taxonomy

The cross-walk uses two orthogonal axes.

**Axis I — Architectural 8-axis** (structural properties at design-time):
- A1 Identity / A2 Authority (action-class) / A3 Chain (delegation preservation) / A4 Blast radius / A5 Lifecycle / A6 Immutability (originating principal) / A7 Observability / A8 Governance-role (persona × responsibility).

**Axis II — Harm taxonomy** (NIST AI 600-1 GenAI Profile 12-risk, July 2024):
- H1 CBRN / H2 Confabulation / H3 Dangerous-Violent-Hateful / H4 Data Privacy / H5 Environmental / H6 Harmful Bias and Homogenization / H7 Human-AI Configuration / H8 Information Integrity / H9 Information Security / H10 Intellectual Property / H11 Obscene-Degrading-Abusive / H12 Value Chain and Component Integration.

Every substrate property maps to a subset of Axis I × Axis II.

---

## 4. Three worked examples (cross-walk in action)

### Example 1 — Action-class authority across substrates

The same axis under different names:

| Substrate | Vocabulary | Status |
|---|---|---|
| OWASP AISVS C9.2.6 | "manifest-declared reversibility classification" | Proposed for v1.01 (merged PR #822, 2026-05-27 into research/) |
| OWASP AISVS C9.2.7 | "worst-case chain rule + blast-radius independent axis" | Proposed for v1.01 (same PR) |
| CSA Agentic Trust Framework I-5 | "Capability Manifest" | Public Review Draft v0.9.1 |
| CSA Agentic Trust Framework S-2 | "Action Boundaries" | Public Review Draft v0.9.1 |
| CSA NIST AI RMF Agentic Profile AG-MP.1 | "Tool Risk Classification (consequence scope, reversibility, auth, compositional risk)" | CSA Labs draft Mar 2026 |
| Singapore IMDA component 2 + 5 | "Instructions + Tools" | v1.5 (20 May 2026) |
| OWASP LLM Top 10 LLM06 | "Excessive Agency" (mitigations: minimize functionality + permissions + autonomy) | v2 Published 2025 |
| OWASP ASI Sprint 1 ASI03 | "Identity & Privilege Abuse" | Sprint 1 draft |
| SPDX 3.1-RC1 PR #1257 | "agentTrustLevel + agentPermissionScope" | Open PR |
| CoSAI WS4 PR #117 ADLC-AD-A03 (Mayur sample) | "Reversibility taxonomy alignment" | PR comment 2026-06-10 |
| AARM (Errico) | "actions classify as forbidden / context-dependent deny / context-dependent allow" | arXiv 2602.09433 |
| Orchestration Layer Regulation | "regulation should shift to orchestration layer" | arXiv 2604.22819 |

All same axis. Architectural mapping: A2 (Authority). Harm coverage: H1 (CBRN), H4 (Data Privacy), H9 (Information Security), H12 (Value Chain).

### Example 2 — Chain audit / delegation preservation across substrates

| Substrate | Vocabulary | Status |
|---|---|---|
| CSA NHI 6-property property 5 | "Parent-chain binding" (Mallikarjunarao + Mayur chain-id binding R8) | Internal IAM WG, under review for v1.0 |
| RFC 8693 | "actor claims" in OAuth token exchange | Published RFC |
| CoSAI WS4 PR #116 Layer 5 | "Delegation Chain Preservation (RFC 8693 token exchange + actor claims)" | WIP |
| CoSAI WS4 #99 | "Delegation chain" sub-section in 8-co-author RFC | Accepted, 4-week draft window from 2026-06-04 |
| A2A v1.0.1 | "delegation chain" in AgentCard | Published 28 May 2026 |
| Atlas Framework | "ML Lifecycle Provenance" | arXiv 2502.19567 |
| agentrust-io (public ref) | "VADP scope-narrowing in artifact #8" | Public WS4 #99 reference |
| CSA Agentic Trust Framework I-3 | "Ownership Chain" | Public Review Draft v0.9.1 |

All same axis. Architectural mapping: A3 (Chain). Harm coverage: H8 (Information Integrity), H9 (Information Security), H12 (Value Chain).

### Example 3 — Observability / trace audit across substrates

| Substrate | Vocabulary | Status |
|---|---|---|
| OWASP AOS v0.1 | "Event interaction model (Observed Agent ↔ Guardian Agent) + AgBOM extending CycloneDX/SWID/SPDX" | Public Preview |
| CoSAI WS4 PR #116 Layer 6 | "Observable Trust (OpenTelemetry + runtime trace context)" | WIP |
| AARM (Errico) | "tamper-evident receipts" | arXiv 2602.09433 |
| CSA Agentic Trust Framework B-1 + B-2 | "Structured Logging + Action Attribution" | Public Review Draft v0.9.1 |
| CSA NIST AI RMF Agentic Profile AG-MS.1 | "Behavioral Telemetry" | CSA Labs draft Mar 2026 |
| SPDX 3.0.1 AIPackage modelExplainability | "modelExplainability" property | Stable |
| EQTY Lab Lineage Explorer (public demo) | "vLLM provenance visualization" | Public demo at CoSAI WS1 |
| agentrust-io TRACE (public ref) | "GatewayClaim append-only Merkle registry" | Public ref via WS4 #99 |

All same axis. Architectural mapping: A7 (Observability). Harm coverage: All H categories.

---

## 5. Open contribution slots

Where contribution is invited. Each is a substrate gap visible from the cross-walk.

### Quarter Q3 2026

- **CSA ATF v0.9.1 governance-role axis (A8)** as cross-cutting on Identity Core Element. Comment via github.com/massivescale-ai/agentic-trust-framework Public Review.
- **Raymond Sheh persona taxonomy** (arXiv 2511.15763) governance-role axis extension. Future PR adding action-class authority as cross-cutting axis (not a persona).
- **SPDX 3.1+ action-class authority dimension for AIPackage** using PR #1267 additionalInformation extensibility pattern.
- **AISVS v1.01 promotion of C9.2.6 + C9.2.7 + Issue #828** (C14.2 ↔ C9.2.6 bridge) from research/ directory into the main chapter — post v1.0 release (2026-06-24).
- **CoSAI WS4 PR #117 follow-on** with full Phase 3 Admission + Phase 4 Runtime control population.
- **OWASP SPVS 1.5-AI** CSV column gap closure (Issue #13) + V5.6.5 (PR #14) + V1.3.7 (PR #15) review and acceptance.
- **OWASP AIVSS Action-Class Authority** scoring dimension (Issue #36) advance through Calculator V4.
- **CoSAI Risk Map controls→frameworks inversion** (Issue #369, Bill Stout).
- **CSA NHI v1.0 external publication path** for the 6-property chain audit schema (internal IAM WG joint Mayur + Mallikarjunarao Sunke).
- **NIST IR 8596 v1.0** comment submission when next period opens.
- **NIST CAISI AI Agent Standards Interoperability Profile** Q4 2026 participation.

### Quarter Q4 2026 / 2027

- **IETF Internet-Draft** for action-class authority + chain audit schema (WIMSE-adjacent; could file as `draft-agnihotri-*` individual I-D).
- **NIST 800-53 COSAiS** AI-specific control overlays public comment when initial public draft posts.
- **OWASP AOS AgBOM** cross-walk to SPDX AIPackage + agentrust-io aibom (post 2026-06-23 agentrust-io public launch).
- **OWASP AST10 + CoSAI WS4** cross-walk for skill-layer agentic security.
- **W3C VC + DID** integration with action-class authority claim type.

---

## 6. Community contribution call

The community is invited to:

1. **Validate substrate completeness.** Are there standards or projects missing from the catalog? Examples we'd like: IETF SCITT, additional EU member-state guidance, Australia AI Ethics Framework, Korea AI Basic Act, Japan AI Bill, Brazil AI Act, India DPDP Act + Digital India Act drafts.

2. **Validate schema property completeness.** Within each substrate row, which properties are missing from the cross-walk? Some published substrates have properties not yet mapped to the architectural × harm matrix.

3. **Validate cross-walks.** Where is a cross-walk mapping incorrect or under-specified? If you maintain one of these standards and disagree with how its property is mapped to Axis I or Axis II, please open an issue.

4. **Validate citation qualifiers.** Where a draft standard is cited without "Proposed for", "Preliminary Draft", "I-D", "Public Review Draft", or "research/ directory" qualifier — flag the missing qualifier.

5. **Validate gap-to-contribute slots.** Which Q3/Q4/2027 slots are already in flight elsewhere that the cross-walk has missed? Which slots are no longer open because somebody filed?

6. **Validate substrate-13 / 14 / 16 discipline.** Substrates 13 (Anthropic Fable 5 + Mythos 5), 14 (agentrust-io / pre-launch private until 2026-06-23), and 16 (EQTY Lab) are cited from public references only in this artifact. If you are aware of additional public references that should be cited, please contribute.

### How to contribute

- **GitHub Issues / PRs** — file on the project that hosts this RFC (canonical location TBD; proposed: github.com/Mayur021/agentic-cross-walk or contribution to an existing OWASP / CoSAI / CSA project).
- **Mailing list / Slack** — coordination channels TBD per host project.
- **Direct DM** — Mayur Agnihotri on LinkedIn or via published GitHub handle Mayur021.

---

## 7. Citation discipline (for contributors)

Every substrate citation in your contribution MUST carry the appropriate qualifier. Examples of CORRECT form:

| Wrong | Correct |
|---|---|
| "AISVS C9.2.6" | "AISVS C9.2.6 (Proposed for v1.01; merged via PR #822 into research/ directory 2026-05-27)" |
| "CSA ATF 7 properties" | "CSA Agentic Trust Framework v0.9.1 Public Review Draft (5 Core Elements + 25 requirements + 4-tier maturity)" |
| "CSA NHI 6-property schema" | "CSA NHI 6-property chain audit schema (internal IAM WG joint Mayur Agnihotri + Mallikarjunarao Sunke; under review for v1.0)" |
| "Singapore IMDA 6 components" | "Singapore IMDA MGF Agentic AI v1.5 (8 components: Model / Instructions / Memory / Planning_Reasoning / Tools / Protocols / Controls / Logging_Monitoring; 20 May 2026)" |
| "MCP-I" | "MCP authorization model: OAuth 2.1 + RFC 9728 + RFC 8707 (no native VC/DID layer); 'MCP-I' is community label, not Anthropic spec" |
| "SPDX 3.1" | "SPDX 3.1-RC1 (pre-release, 2026-01-24); 3.0.1 stable" |
| "AISVS Multi-Agent Threat Modeling Guide" | "OWASP Multi-Agent threat content distributed across AISVS C9.8 + ASI Sprint 1 (ASI13/14) + lets-threat-model tool — no standalone repo" |
| "WIMSE IETF standard" | For WG drafts: "WIMSE WG I-D" (or specific draft name); for AI-agent drafts: "WIMSE individual I-D (NOT WG-adopted)" |

---

## 8. License and reuse

This RFC is offered under CC BY 4.0 (proposed). Contributors retain copyright on their contributions; attribution requested per the joint-credit anchor (Mallikarjunarao Sunke on CSA NHI 6-property; co-authors of CoSAI WS4 #99 when citing that RFC; project leaders of each named substrate when citing the substrate's property).

No SecSphere product references. No competitor vendor names. No proprietary content from any substrate. No private CSA / NIST / CoSAI / OWASP working-group content. No pre-launch private agentrust-io content (held until 2026-06-23 public launch).

---

## 9. Versioning and review

- **v1 (this document)** — 2026-06-11. First public RFC.
- **v1.x** — incorporate community contributions per Section 6.
- **v2** — after one quarter of community contribution cycle; refactor into stable artifact.

Review cadence: rolling. Each substantive contribution opens a new revision tracking thread.

---

## 10. Acknowledgments and provenance

This cross-walk is built from public sources verified against live GitHub state of each project as of 2026-06-11 via four parallel background-agent audits plus direct gh CLI verification of AISVS PR #822. All draft standards carry version-stamp qualifiers. CSA NHI 6-property chain audit schema is jointly credited to Mallikarjunarao Sunke on every reference. Substrates 13, 14, 16 are cited from public references only.

Companion artifacts:
- **Doc 1** (operational matrix v1.1) — internal Mayur reference, schema-property-level mapping.
- **Doc B** (whitepaper v1.1 chapter) — narrative refactor for thesis-led audience.
- **Doc C** (this document) — public RFC variant for community contribution.

---

**Contact for community contribution:**
- Mayur Agnihotri (Mayur021 on GitHub; resources@straightarc.com)
- Joint anchor for CSA NHI 6-property: Mallikarjunarao Sunke (please direct CSA NHI 6-property cross-walks to both names)
- Project leads of each named substrate (per substrate row in Doc 1) for substrate-specific corrections.

**END Doc C.**
