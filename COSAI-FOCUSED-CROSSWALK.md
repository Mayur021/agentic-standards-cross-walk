# Schema Cross-Walk for CoSAI WS4 — Preparation Notes for ADLC + Risk Map + #99 Integration

**Prepared by:** Mayur Agnihotri (Mayur021)
**Date:** 2026-06-11
**Purpose:** Cross-walk preparation supporting CoSAI WS4 ADLC PR #117 follow-on + Risk Map Issue #369 + WS4 #99 Agent Credentials work. Not a standalone artifact — preparation lens for integration into existing CoSAI substrates.
**Joint credit anchor:** Mallikarjunarao Sunke on CSA NHI 6-property chain audit schema (internal CSA IAM WG joint work, under review for v1.0).
**Discipline:** Every draft standard carries its version qualifier. Substrates 13/14/16 cited from public references only.

---

## The cross-walk axis

Across CoSAI WS4 and adjacent standards, three structural axes recur. This document maps each substrate's schema-property expression of the three axes:

- **Axis A2** — **Authority** (action-class declared at manifest, gated at verb-layer)
- **Axis A3** — **Chain** (delegation preservation across hops)
- **Axis A7** — **Observability** (trace + audit with cryptographic integrity)

Architectural axes mapped: A2 / A3 / A7 (focus) + secondary A1 Identity, A4 Blast-radius, A5 Lifecycle, A6 Immutability, A8 Governance-role.
Harm taxonomy: NIST AI 600-1 GenAI Profile 12-risk (H1-H12).

---

## CoSAI substrates (the integration targets)

| ID | Name | Schema | A-axes |
|---|---|---|---|
| C-1 | **CoSAI Risk Map v1** | 23 components / 35 controls / 36 risks / 10 personas / 8 lifecycle stages / 6 frameworks (mitre-atlas + nist-ai-rmf + stride + owasp-top10-llm + iso-22989 + eu-ai-act) | A1-A8 (full) |
| C-2 | **CoSAI WS4 ADLC 7-phase (PR #117)** | Phases: Supply Chain / Development / Admission / Runtime / Reflection / Maintenance / Decommissioning. Control schema `ADLC-{Phase}-{Type}{Seq}` with L1/L2/L3. Cross-cutting families: Identity / Observability / Policy / Data. Proposed 8th phase System Governance (Doyin Awofodu) | A1-A8 (full) |
| C-3 | **CoSAI WS4 PR #116 Identity Architecture (WIP)** | 6 layers: Cryptographic Identity (SPIFFE/SPIRE) / Verifiable Agent Credentials (AgentCard, A2A) / Federated Identity Bridge / Transparent Authorization Proxy / Delegation Chain Preservation (RFC 8693) / Observable Trust (OpenTelemetry) | A1, A2, A3, A7 |
| C-4 | **CoSAI WS4 #99 Agent Credentials RFC (accepted)** | 8 co-authors (Lau + Singh + Siddique + Kolekar + Rajamohan + Evans + Taylor + Rajaraman). Integrates X.509 + SPIFFE/SVID + DIDs + W3C VCs + JWTs + OASF + AgentCard | A1, A2, A3 |
| C-5 | **CoSAI WS4 #113 Multimodal Agentic Security RFC (accepted)** | 4-technique taxonomy: typographic / steganographic / adversarial perturbation / preprocessing exploit. Incidents: EchoLeak CVE-2025-32711, Cursor Mermaid, image-scaling | A4, A7 |
| C-6 | **CoSAI WS2 Telemetry framework** | AI stack telemetry (OCSF-aligned). Includes collector + dashboards + integrations + sdk + spec | A7 |
| C-7 | **CoSAI WS2 Shared Responsibility Framework + AI Incident Response v1.0** | 7-framework cross-walk (CISA / MIT / MITRE / NIST / OASIS / OCSF / OWASP) | A8 (full) |
| C-8 | **CoSAI TSC Security Principles for Agentic Systems** | Parent doc for Secure-by-Design across WS1-4 | A1-A8 (foundational) |

---

## Authority axis (A2) — schema-property cross-walk

| Substrate | Schema property / vocabulary | Status qualifier |
|---|---|---|
| **CoSAI WS4 ADLC (PR #117)** sample row | ADLC-AD-A03 "Reversibility taxonomy alignment per AISVS C9.2.6" (Mayur's PR #117 comment 2026-06-10) | Open PR comment |
| **OWASP AISVS C9.2.6** | "manifest-declared reversibility classification" — actions carry a reversibility class (read-only / reversible / external-reversible / irreversible) declared in tool/action manifest | **Proposed for v1.01** (merged via PR #822 into AISVS research/ directory 2026-05-27) |
| **OWASP AISVS C9.2.7** | "worst-case chain rule + blast-radius independent axis" — blast radius can only raise authority within a class | **Proposed for v1.01** (same PR) |
| **OWASP AISVS C9.2.1-9.2.4** (v1.0 main chapter) | Execution gate + canonicalized parameters + cryptographic binding + rollback semantics | Published in AISVS v1.0 (release 2026-06-24) |
| **CSA Agentic Trust Framework I-5** | "Capability Manifest" (one of 5 Core Elements + 25 reqs) | Public Review Draft v0.9.1 |
| **CSA Agentic Trust Framework S-2** | "Action Boundaries" + S-5 "Blast Radius Containment" | Public Review Draft v0.9.1 |
| **CSA NIST AI RMF Agentic Profile AG-MP.1** | "Tool Risk Classification" (consequence scope, reversibility, auth, compositional risk) | CSA Labs draft March 2026 |
| **CSA NIST AI RMF Agentic Profile AG-GV.1** | "Autonomy Classification" 4-tier (fully supervised → full autonomy) | CSA Labs draft March 2026 |
| **CSAI Foundation AARM (Errico)** | Action classification: forbidden / context-dependent deny / context-dependent allow + tamper-evident receipts | arXiv 2602.09433; CSAI flagship adopted 2026-04-29 |
| **CSA AAGATE Tool-Gateway Chokepoint** | Unified tool invocation audit and authorization | arXiv 2510.25863 / CSA blog Dec 2025 |
| **Singapore IMDA MGF v1.5 components 2+5** | "Instructions" + "Tools" (of 8 components) | Published 20 May 2026 |
| **OWASP LLM Top 10 LLM06** | "Excessive Agency" — minimize functionality + permissions + autonomy | Published v2 (2025) |
| **OWASP ASI Sprint 1 ASI03** | "Identity & Privilege Abuse" | Sprint 1 draft |
| **OWASP AST10 AST03** | "Over-Privileged Skills" | Incubator v1.0-2026 (March 2026) |
| **SPDX 3.1-RC1 PR #1257 AIAgent** | `agentTrustLevel` (unverified/selfDeclared/thirdPartyReviewed/certified) + `agentPermissionScope` | Open PR |
| **MCP 2025-11-25** | OAuth 2.1 + RFC 9728 + RFC 8707 (resource indicators) | Published; donated to LF AAIF Dec 2025 |
| **CSA NHI v1 public** registry field 5 "Privilege scope" | Recommendation, not normative schema | Published May 2026 |

---

## Chain axis (A3) — schema-property cross-walk

| Substrate | Schema property / vocabulary | Status qualifier |
|---|---|---|
| **CoSAI WS4 #99 Agent Credentials RFC** | "Delegation chain" sub-section in 8-co-author RFC | Accepted 2026-06-04; 4-week draft window |
| **CoSAI WS4 PR #116 Layer 5** | "Delegation Chain Preservation (RFC 8693 token exchange + actor claims)" | WIP |
| **CSA NHI 6-property property 5** (Mallikarjunarao + Mayur chain-id binding R8 joint) | "Parent-chain binding" | **Internal CSA IAM WG joint work; under review for v1.0** |
| **CSA NHI 6-property property 6** (Mallikarjunarao) | "Immutability of originating principal" | Internal CSA IAM WG joint work; under review for v1.0 |
| **CSA Agentic Trust Framework I-3** | "Ownership Chain" (one of Identity Element 5 requirements) | Public Review Draft v0.9.1 |
| **CSA NIST AI RMF Agentic Profile AG-MS.3** | "Delegation Chain Integrity" | CSA Labs draft March 2026 |
| **OWASP AISVS C9.2.7** | "worst-case classification governing across a multi-step chain" | **Proposed for v1.01** (merged 2026-05-27 into research/ directory) |
| **OWASP AISVS C9.4** | "Agent and Orchestrator Identity, Signing, Tamper-Evident Audit" (6 requirements) | Published in AISVS v1.0 |
| **OWASP AISVS C9.6** | "Authorization, Delegation, Continuous Enforcement" (7 requirements) | Published in AISVS v1.0 |
| **A2A Protocol v1.0.1** | "Delegation chain" + AgentCard JWS + JCS signature verification + mTLS | Published 28 May 2026 |
| **IETF RFC 8693** | "Actor claims" in OAuth token exchange | Published RFC |
| **WIMSE arch-07** | Section 3.3.9 — AI agents as delegated workloads inheriting upstream security context | WG I-D, March 2026 |
| **WIMSE workload-identity-practices-04** | SPIFFE JWT-SVID/X.509-SVID Workload API + delegation patterns | WG Consensus / Waiting for Write-Up |
| **W3C VC Data Model 2.0** | `proof` mechanism preserving issuer chain + `validFrom` / `validUntil` | W3C Recommendation 15 May 2025 |
| **Atlas Framework arXiv 2502.19567** | ML Lifecycle Provenance | Published Feb 2025 |
| **agentrust-io** (public ref) | VADP scope-narrowing in artifact #8 — referenced in WS4 #99 | Pre-launch private until 2026-06-23; cite only public WS4 #99 reference |

---

## Observability axis (A7) — schema-property cross-walk

| Substrate | Schema property / vocabulary | Status qualifier |
|---|---|---|
| **CoSAI WS4 PR #116 Layer 6** | "Observable Trust (OpenTelemetry + runtime trace context)" | WIP |
| **CoSAI WS2 Telemetry framework** | AI stack telemetry schema (OCSF-aligned); collector + dashboards + sdk + spec | Merged 5/5 (PR #114) |
| **OWASP AOS v0.1** | Event interaction model (Observed Agent ↔ Guardian Agent) + AgBOM extending CycloneDX / SWID / SPDX | Public Preview |
| **CSAI Foundation AARM (Errico)** | "Tamper-evident receipts" recording the full action sequence | arXiv 2602.09433 |
| **CSA Agentic Trust Framework B-1 + B-2** | "Structured Logging" + "Action Attribution" (of 5 Behavior Element requirements) | Public Review Draft v0.9.1 |
| **CSA NIST AI RMF Agentic Profile AG-MS.1** | "Behavioral Telemetry" | CSA Labs draft March 2026 |
| **CSA AAGATE Janus Shadow-Monitor Agent** | "Pre-execution behavioral assessment" | arXiv 2510.25863 / Dec 2025 |
| **OWASP AISVS C13** | "Monitoring, Logging & Anomaly Detection" chapter | Published in AISVS v1.0 |
| **CSA OpenClaw** | "Behavioral monitoring/anomaly detection" (one of 8 control domains) | Published 2026 |
| **C2PA** | Cryptographic provenance for AI-generated content | Coalition spec |
| **SPDX 3.0.1 AIPackage** | `modelExplainability` + `informationAboutApplication` + `informationAboutTraining` | Stable |
| **OpenTelemetry trace context** | Trace context propagation | OpenTelemetry standard |
| **EQTY Lab Lineage Explorer** (public demo) | vLLM provenance visualization | Public demo at CoSAI WS1 |
| **agentrust-io TRACE** (public ref) | GatewayClaim append-only Merkle registry | Public reference via WS4 #99 |

---

## CoSAI integration points (the deliverables)

Where this cross-walk maps into ongoing CoSAI work:

### CoSAI WS4 PR #117 (ADLC Controls Checklist)
- **Phase 3 Admission control rows** — ADLC-AD-A01 (Manifest signature verification) + ADLC-AD-A03 (Reversibility taxonomy alignment per AISVS C9.2.6 Proposed for v1.01)
- **Phase 4 Runtime control rows** — ADLC-RT-I01 (Manifest-declared action class evaluation) + ADLC-RT-I02 (Worst-case chain rule per AISVS C9.2.7 Proposed for v1.01) + ADLC-RT-I04 (AARM-conformant runtime evidence stream per Errico arXiv 2602.09433)
- **Phase 5 Reflection / Phase 6 Maintenance** — composition with CSA NHI 6-property chain audit schema (internal IAM WG joint Mayur + Mallikarjunarao)

### CoSAI Risk Map (Issue #369 — Bill Stout)
- **Controls → frameworks inversion** — when re-organized, the schema property-level cross-walks above become the operational lookup. AISVS C9.2.6/7, CSA NHI 6-property, AARM, IMDA Tools/Instructions all map to existing Risk Map controls (controlAgentExecutionBounds + controlAgentIntegrityManagement + controlAgentCredentialIsolation + controlOrchestratorAndRouteIntegrity).

### CoSAI WS4 #99 (Agent Credentials RFC)
- **8-co-author RFC schema integration** — Mayur cross-walk adds AISVS C9.2.6/7 (Proposed for v1.01) + CSA NHI 6-property (internal IAM WG) + AARM (CSAI flagship) + agentrust-io VADP scope-narrowing (public reference via WS4 #99). All extend the existing 8-co-author RFC, no new RFC needed.

### CoSAI WS4 PR #116 (Identity Architecture Patterns)
- **6-layer architecture composition** — action-class authority axis is orthogonal: flows into Layer 2 as declared class (AgentCard), through Layer 3 as OAuth scope claim, preserved in Layer 5 as actor claim (chain), audited in Layer 6 as verdict. Composes with Justin Albrethsen's ZeroID reference (Layers 1, 2, 3, 5).

### CoSAI WS4 #113 (Multimodal Agentic Security)
- **Tool design composition** — multimodal attack vectors (typographic/steganographic/adversarial perturbation/preprocessing exploit) cross-walk to AISVS C9.2.6 manifest-declared action class + Tool Design Principles 4 (Two-Stage Commit) + 5 (per-tool immutable audit).

### CoSAI WS1 (Supply Chain)
- **SBOM + AIBOM convergence** — SPDX 3.0.1 AIPackage + SPDX 3.1-RC1 PRs (#1259 dataset size for EU AI Act + #1267 additionalInformation extensibility) + G7 BSI SBOM for AI 7-cluster + OWASP AOS AgBOM (extends CycloneDX/SWID/SPDX). Direct cross-walk to ws1-supply-chain risks-and-controls v1 + signing-ml-artifacts.

### CoSAI WS2 (Defenders)
- **Telemetry + Shared Responsibility** — CoSAI WS2 Telemetry framework (OCSF-aligned) composes with OWASP AOS AgBOM + AARM tamper-evident receipts + EQTY Lab Lineage Explorer (public demo). Shared Responsibility Framework anchors persona × responsibility mapping for action-class authority enforcement.

---

## Open contribution slots (for CoSAI consideration)

| Slot | Target | Action |
|---|---|---|
| Follow-on PR to #117 with full Phase 3 + 4 control population | CoSAI WS4 ADLC | Mayur to file within 48h (per discussion with Parul) |
| Risk Map Issue #369 — controls → frameworks inversion | CoSAI secure-ai-tooling | Mayur staged comment in RAG; deploy when path opens |
| Cross-walk reference attribution in CoSAI Resources repo | github.com/cosai-oasis/resources | Optional contribution; if Parul opens path |
| AISVS v1.01 promotion of C9.2.6/7 + Issue #828 (C14.2 bridge) | OWASP AISVS | Mayur post v1.0 release 2026-06-24 |
| CSA NHI v1.0 external publication path | CSA IAM WG | Coordinate with Mallikarjunarao |
| SPDX 3.1+ action-class authority dimension for AIPackage | spdx-3-model | Future PR Week 6+ (silent-observer norm) |
| IETF Internet-Draft `draft-agnihotri-action-class-authority-00` | IETF | Q3-Q4 2026 target (WIMSE-adjacent) |
| OWASP AOS AgBOM ↔ SPDX 3.1+ AIAgent cross-walk | OWASP AOS + SPDX | Future PR post 2026-06-23 |

---

## Citation discipline

Every reference in this document carries its version-stamp qualifier:
- **"Proposed for v1.01"** for AISVS C9.2.6 + C9.2.7 + Issue #828 (merged into research/ directory)
- **"Public Review Draft v0.9.1"** for CSA Agentic Trust Framework
- **"Internal CSA IAM WG joint Mayur + Mallikarjunarao Sunke; under review for v1.0"** for CSA NHI 6-property chain audit schema
- **"Open PR / WIP / accepted"** for CoSAI WS4 PRs and Issues
- **"Public Preview"** for OWASP AOS
- **"Incubator v1.0-2026"** for OWASP AST10
- **"Recommendation"** for W3C VCs 2.0 + DID Core 1.0
- **"WG I-D"** for IETF WIMSE WG drafts
- **"Individual I-D (NOT WG-adopted)"** for AI-agent WIMSE individual drafts
- **"3.1-RC1 / 3.0.1 stable"** for SPDX

Substrates 13 (Anthropic Fable 5 + Mythos 5) / 14 (agentrust-io, pre-launch private until 2026-06-23) / 16 (EQTY Lab) are cited from public references only.

---

**Status:** Preparation notes for CoSAI WS4 PR #117 follow-on + Risk Map Issue #369 + WS4 #99 integration discussion. Not a standalone artifact. Open to integrating into existing CoSAI substrates wherever makes sense.

**Contact for CoSAI integration coordination:** Mayur021 on GitHub; @Mayur Agnihotri on CoSAI Slack.
**Joint coordination for CSA NHI 6-property:** Mallikarjunarao Sunke (CSA IAM WG).
