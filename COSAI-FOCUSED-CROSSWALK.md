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

## Mayur work × CoSAI Ecosystem Fit Map

This section maps where this preparation lens slots into the full CoSAI ecosystem. The cross-walk does not propose new CoSAI artifacts; it cross-references the standards landscape that CoSAI artifacts are already composing into. Each row below shows the CoSAI artifact, how the cross-walk supports it, and the natural contribution slot.

### TSC — Principles for Agentic Systems (parent doc)

| CoSAI artifact | How the cross-walk supports it | Contribution slot |
|---|---|---|
| `tsc-meeting-minutes`, `intro-agentic-security-principles.md`, `security-principles-for-agentic-systems.md` (Secure-by-Design parent doc), `the-future-of-agentic-security.md` | The 8-axis architectural taxonomy (identity / authority / chain / blast-radius / lifecycle / immutability / observability / governance-role) operationalizes Secure-by-Design at property-level. Each TSC principle resolves to one or more A-axes plus mitigated H-categories. | None proposed (parent-doc level work, not extension surface) |

### WS1 — Software Supply Chain for AI

| CoSAI artifact | How the cross-walk supports it | Contribution slot |
|---|---|---|
| `risks-and-controls-for-the-ai-supply-chain-v1` + `signing-ml-artifacts` (stable papers) | Cross-walk catalogs SPDX 3.0.1 AI Profile (AIPackage), SPDX 3.1-RC1 PRs #1259/#1267/#1257, G7 BSI SBOM for AI 7 core clusters, EU AI Act Article 53(1)(d) template — all directly compose with WS1 supply-chain controls | Future: cross-walk between WS1 risks-and-controls v1 + SPDX 3.1-RC1 dataset-size properties (token count, item count, content duration) for EU AI Act alignment |
| 9 open RFCs in WS1 (mostly Q1-25 contributions, slow pipeline) | Each WS1 RFC maps onto specific A-axes (A1 Identity, A5 Lifecycle, A6 Immutability) and H-categories (H8 Information Integrity, H12 Value Chain) — cross-walk provides the property-level lookup | RFC-by-RFC engagement opportunity when WS1 reopens active review |

### WS2 — Defenders (Preparing Defenders for a Changing Cybersecurity Landscape)

| CoSAI artifact | How the cross-walk supports it | Contribution slot |
|---|---|---|
| `preparing-defenders-of-ai-systems` (flagship paper), `AI-Incident-Response.md` v1.0, `AI-Shared-Responsibility-Framework` (May 2026) | Cross-walk's observability axis (A7) + AARM tamper-evident receipts + OWASP AOS AgBOM (extends CycloneDX/SWID/SPDX) directly compose with WS2 Telemetry framework (OCSF-aligned). Shared Responsibility Framework anchors A8 governance-role × persona mapping | Future: AOS AgBOM ↔ WS2 Telemetry framework cross-walk (post-AOS v1) |
| 12 open issues (AI-SPM, AI CAPEC, AI Telemetry OCSF, Behavioral Control Mechanisms) | Each composes with cross-walk's A4 Blast radius + A7 Observability + A8 Governance-role | Watch for substantive openings on specific Issues |

### WS3 — AI Risk Governance

| CoSAI artifact | How the cross-walk supports it | Contribution slot |
|---|---|---|
| WS3 is early-stage scaffolding; 0 merged artifacts; 6 open RFCs | Three high-leverage WS3 RFCs (CoSAI-RM Interactive Risk Assessment #11, CoSAI Persona Model #12, Shared Responsibility Model #10) all directly benefit from cross-walk's 8-axis × 12-risk taxonomy + Raymond Sheh persona taxonomy (arXiv 2511.15763) + WhiteHouse M-24-10 dual-axis (Rights/Safety-impacting) | Future Persona Model RFC #12 + Interactive Risk Assessment RFC #11 substantive contribution paths |
| SIG-Security-AI-Assisted-Code-Development scope | Composes with OWASP AST10 Agentic Skills Top 10 (Incubator, March 2026) + OWASP Agent-Security-Regression-Harness | Cross-reference in scope refinement |

### WS4 — Secure-Design Agentic Systems

| CoSAI artifact | How the cross-walk supports it | Contribution slot |
|---|---|---|
| MCP Security paper v1 (Jan 2026) + V2 in flight (PR #108) | Cross-walk catalogs MCP 2025-11-25 spec (OAuth 2.1 + RFC 9728 + RFC 8707) explicitly distinguishing from community "MCP-I" label | Engaged via PR #108 review comment 2026-06-04 |
| Agentic Identity & Access Control paper (Apr 2026) | 6-layer pattern → A1 Identity through A7 Observability | Cross-referenced in PR #116 staged comment |
| `mcp-secure-tool-design.md` (read-only / reversible / commit tool classes + Two-Stage Commit + L1/L2/L3 Autonomy Matrix) | Tool design classes directly compose with action-class authority A2 axis (read-only / reversible / external-reversible / irreversible per AISVS C9.2.6 Proposed for v1.01) | Open extension: 4-class reversibility taxonomy as cross-walk evidence |
| **PR #117 ADLC Controls Checklist** (open) | Sample control rows already contributed (2026-06-10 comment): ADLC-RT-I01 (manifest-declared action class), I02 (worst-case chain rule per C9.2.7), I04 (AARM evidence stream); ADLC-AD-A01 (signature verification), A03 (reversibility taxonomy alignment) | Follow-on PR within 48h with full Phase 3 + Phase 4 population; add ADLC-RT-D01 "Data Quality Gate" per Microsoft AGT PR #2224 two-layer pattern |
| **PR #116 Identity Architecture Playbook** (WIP) | 6-layer pattern composes with action-class A2 axis cross-cuts (declared at Layer 2, gated at Layer 4, preserved at Layer 5, audited at Layer 6); cross-references ZeroID (Justin Albrethsen's suggestion) | Staged substantive comment ready (24-48h post Parul/Ian PR #117 response) |
| **#99 Agent Credentials RFC** (accepted, 8 co-authors) | Cross-walk catalogs A2A v1.0.1 AgentCard JWS+JCS+mTLS, W3C VC 2.0 + DID Core, MCP OAuth model, WIMSE WG drafts, CSA NHI 6-property chain audit schema (internal IAM WG joint with Mallikarjunarao) | 3 substantive comments already; W3C-CG #34 sequenced deployment gated on Lars |
| **#113 Multimodal Agentic Security RFC** (accepted) | 4-technique taxonomy maps to A4 Blast-radius + A7 Observability axes | Substantive comment 2026-06-05 already deployed |
| **ADLC SIG** (PR #101 merged 2026-06-01; 7-phase ownership locked 2026-06-03) | Cross-walk supports each of 7 phases via A1-A8 axis × H1-H12 risk mapping; proposed 8th phase System Governance (Doyin Awofodu) extends A8 | Mayur invited to elaborate on PR #117 at SIG ADLC meeting 2026-06-10 |
| 12-category MCP threat taxonomy (MCP-T1 through T12) | Each threat resolves to one or more cross-walk A-axes + H-categories | Cross-reference in future MCP V2 review |

### secure-ai-tooling (Risk Map v1, launched June 2026)

| CoSAI artifact | How the cross-walk supports it | Contribution slot |
|---|---|---|
| Risk Map v1: 23 components / 35 controls / 36 risks / 10 personas / 8 lifecycle stages | The 89-substrate × 8-axis × 12-risk cross-walk matrix is exactly the kind of map Risk Map cross-walks against (current cross-walks: MITRE ATLAS, NIST AI RMF, STRIDE, OWASP LLM Top 10, ISO 22989, EU AI Act) | Risk Map could pin to cross-walk SUBSTRATES.md as supplementary reference |
| **Issue #369 (Bill Stout) — controls → frameworks inversion proposal** (cites SecureControlsFramework, CSA AICM, NIST CPRT) | Cross-walk is LITERALLY the inversion pattern — mapping controls to frameworks across CSA, NIST, CoSAI, OWASP, SPDX, MCP, A2A, WIMSE families. The artifact's structure mirrors what Issue #369 proposes for Risk Map | Substantive comment ready on Issue #369 with cross-walk repo link as supporting evidence |
| **PR #376 (David LaBianca) — framework mappings to ADR-027 pinned form** | Cross-walk's substrate catalog is the kind of pinned framework mapping ADR-027 enables; could be cited as worked example | Future substantive comment opportunity |
| PR #362 (ISO 42001 mapping) + PR #329 (ETSI EN 304 223) — open proposals | Cross-walk catalogs ISO/IEC 42001 as substrate (in CSA AICM cross-walk row) | Cross-reference when reviewed |

### CoSAI Resources reference library (`cosai-oasis/resources`)

| CoSAI artifact | How the cross-walk supports it | Contribution slot |
|---|---|---|
| `ai-incidents/`, `ai-regulations/`, `ai-risks/`, `ai-security-and-risk-frameworks/`, `ai-vulnerabilities/`, `glossary/`, `PERSONA.md` | Cross-walk SUBSTRATES.md is a candidate reference for `ai-security-and-risk-frameworks/` index | Optional contribution PR (smaller than Risk Map; cleaner anchor surface) |

### Project CodeGuard (`cosai-oasis/project-codeguard`)

| CoSAI artifact | How the cross-walk supports it | Contribution slot |
|---|---|---|
| OWASP-aligned rule sets for AI coding agents | Composes with OWASP AISVS C9 (Autonomous Orchestration), C10 (MCP Security), AST10 Agentic Skills Top 10 | Lower priority; engaged only if natural opening |

### CoSAI TSC ↔ Workstreams convergence summary

Across the seven CoSAI organizational artifacts (TSC + 4 workstreams + secure-ai-tooling Risk Map + Resources), the cross-walk's 89 substrates × 8-axis × 12-risk matrix provides:

1. **Property-level lookup** for any CoSAI control needing cross-walk to other standards bodies
2. **Composability evidence** that CoSAI's principles + WS schemas don't conflict with adjacent standards (CSA / NIST / OWASP / SPDX / IETF / W3C)
3. **Contribution targeting** — explicit slots where Mayur substrate work composes with CoSAI work
4. **Convergence narrative** — vendor-neutral framing showing the agentic standards landscape is converging on shared structural primitives, of which CoSAI is one constellation

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
