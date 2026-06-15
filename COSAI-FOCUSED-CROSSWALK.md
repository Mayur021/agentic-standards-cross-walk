# Schema Cross-Walk for CoSAI WS4 — Preparation Notes for ADLC + Risk Map + #99 Integration

**Prepared by:** Mayur Agnihotri (Mayur021)
**Date:** 2026-06-11
**Purpose:** Cross-walk preparation supporting CoSAI WS4 ADLC PR #117 follow-on + Risk Map Issue #369 + WS4 #99 Agent Credentials work. Not a standalone artifact — preparation lens for integration into existing CoSAI substrates.
**Joint credit anchor:** Mallikarjunarao Sunke on the CSA NHI v1.0 four-element attribution language (delegator / agent / intent / actions) anchored at paragraph 222 of the Working Draft (joint peer-review contribution) AND the full six-property chain audit schema (chain-id binding, originating-principal immutability, audit telemetry surface) targeted for v2.0 inclusion. (Verified 2026-06-15 against `/root/Defining_Non-Human_Identity.docx`.)
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
| **OWASP AISVS C9.2.1-9.2.3** (v1.0 main chapter, post-2026-06-15 cleanup) | Execution gate + canonicalized parameters + cryptographic binding (former 9.2.4 compensating-actions requirement was removed in the PR #928 + #934 cleanup; Mohamad Khalil Yossif's 9.2.5 approval-evidence trust boundary proposed for v1.0 inclusion) | Published in AISVS v1.0 (release 2026-06-24) |
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
| **CSA NHI v1.0 four-element attribution (joint Mallikarjunarao Sunke + Mayur)** | "delegator / agent / intent / actions" at paragraph 222 | **Anchored verbatim in v1.0 Working Draft (joint peer-review contribution; in editorial closure)** |
| **CSA NHI six-property schema property 5 (chain-id binding; joint Mallikarjunarao + Mayur R8)** | "Parent-chain binding" | **NOT verbatim in v1.0; targeted for v2.0 inclusion (joint Mallikarjunarao Sunke)** |
| **CSA NHI six-property schema property 6 (Mallikarjunarao)** | "Immutability of originating principal as schema property" | **NOT verbatim in v1.0; targeted for v2.0 inclusion (joint Mallikarjunarao Sunke)** |
| **CSA Agentic Trust Framework I-3** | "Ownership Chain" (one of Identity Element 5 requirements) | Public Review Draft v0.9.1 |
| **CSA NIST AI RMF Agentic Profile AG-MS.3** | "Delegation Chain Integrity" | CSA Labs draft March 2026 |
| **OWASP AISVS C9.2.7** | "worst-case classification governing across a multi-step chain" | **Proposed for v1.01** (merged 2026-05-27 into research/ directory) |
| **OWASP AISVS C9.4** | "Agent and Orchestrator Identity, Signing, Tamper-Evident Audit" (5 requirements, 9.4.1-9.4.5 — count revised in 2026-06-15 PR #928 + #934 cleanup) | Published in AISVS v1.0 |
| **OWASP AISVS C9.5** | "Agent Authorization, Delegation, and Continuous Enforcement" (6 requirements, 9.5.1-9.5.6 — renumbered from former C9.6 in the 2026-06-15 PR #928 + #934 cleanup) | Published in AISVS v1.0 |
| **A2A Protocol v1.0.1** | "Delegation chain" + AgentCard JWS + JCS signature verification + mTLS | Published 28 May 2026 |
| **IETF RFC 8693** | "Actor claims" in OAuth token exchange | Published RFC |
| **WIMSE arch-07** | Section 3.3.9 — AI agents as delegated workloads inheriting upstream security context | WG I-D, March 2026 |
| **WIMSE workload-identity-practices-04** | SPIFFE JWT-SVID/X.509-SVID Workload API + delegation patterns | WG Consensus / Waiting for Write-Up |
| **W3C VC Data Model 2.0** | `proof` mechanism preserving issuer chain + `validFrom` / `validUntil` | W3C Recommendation 15 May 2025 |
| **Atlas Framework arXiv 2502.19567** | ML Lifecycle Provenance | Published Feb 2025 |

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

---

## CoSAI integration points (the deliverables)

Where this cross-walk maps into ongoing CoSAI work:

### CoSAI WS4 PR #117 (ADLC Controls Checklist)
- **Phase 3 Admission control rows** — ADLC-AD-A01 (Manifest signature verification) + ADLC-AD-A03 (Reversibility taxonomy alignment per AISVS C9.2.6 Proposed for v1.01)
- **Phase 4 Runtime control rows** — ADLC-RT-I01 (Manifest-declared action class evaluation) + ADLC-RT-I02 (Worst-case chain rule per AISVS C9.2.7 Proposed for v1.01) + ADLC-RT-I04 (AARM-conformant runtime evidence stream per Errico arXiv 2602.09433)
- **Phase 5 Reflection / Phase 6 Maintenance** — composition with CSA NHI v1.0 four-element attribution language (para 222; joint Mayur + Mallikarjunarao Sunke) and the full six-property chain audit schema targeted for v2.0 inclusion

### CoSAI Risk Map (Issue #369)
- **Controls → frameworks inversion** — when re-organized, the schema property-level cross-walks above become the operational lookup. AISVS C9.2.6/7, CSA NHI 6-property, AARM, IMDA Tools/Instructions all map to existing Risk Map controls (controlAgentExecutionBounds + controlAgentIntegrityManagement + controlAgentCredentialIsolation + controlOrchestratorAndRouteIntegrity).

### CoSAI WS4 #99 (Agent Credentials RFC)
- **Schema composition** — the cross-walk composes AISVS C9.2.6/7 (Proposed for v1.01) + CSA NHI 6-property (internal IAM WG) + CSAI Foundation AARM (Errico arXiv 2602.09433) + delegation scope-narrowing patterns with the existing 8-co-author RFC scope.

### CoSAI WS4 PR #116 (Identity Architecture Patterns)
- **6-layer architecture composition** — action-class authority axis is orthogonal: flows into Layer 2 as declared class (AgentCard), through Layer 3 as OAuth scope claim, preserved in Layer 5 as actor claim (chain), audited in Layer 6 as verdict.

### CoSAI WS4 #113 (Multimodal Agentic Security)
- **Tool design composition** — multimodal attack vectors (typographic/steganographic/adversarial perturbation/preprocessing exploit) cross-walk to AISVS C9.2.6 manifest-declared action class + Tool Design Principles 4 (Two-Stage Commit) + 5 (per-tool immutable audit).

### CoSAI WS1 (Supply Chain)
- **SBOM + AIBOM convergence** — SPDX 3.0.1 AIPackage + SPDX 3.1-RC1 PRs (#1259 dataset size for EU AI Act + #1267 additionalInformation extensibility) + G7 BSI SBOM for AI 7-cluster + OWASP AOS AgBOM (extends CycloneDX/SWID/SPDX). Direct cross-walk to ws1-supply-chain risks-and-controls v1 + signing-ml-artifacts.

### CoSAI WS2 (Defenders)
- **Telemetry + Shared Responsibility** — CoSAI WS2 Telemetry framework (OCSF-aligned) composes with OWASP AOS AgBOM + AARM tamper-evident receipts. Shared Responsibility Framework anchors persona × responsibility mapping for action-class authority enforcement.

---

## CoSAI Ecosystem Fit Map

This section maps how the cross-walk composes with the full CoSAI ecosystem. The cross-walk does not propose new CoSAI artifacts; it cross-references the standards landscape that CoSAI artifacts are already composing into.

### TSC — Principles for Agentic Systems (parent doc)

| CoSAI artifact | How the cross-walk composes |
|---|---|
| `tsc-meeting-minutes`, `intro-agentic-security-principles.md`, `security-principles-for-agentic-systems.md` (Secure-by-Design parent doc), `the-future-of-agentic-security.md` | The 8-axis architectural taxonomy (identity / authority / chain / blast-radius / lifecycle / immutability / observability / governance-role) operationalizes Secure-by-Design at property-level. Each TSC principle resolves to one or more A-axes plus mitigated H-categories. |

### WS1 — Software Supply Chain for AI

| CoSAI artifact | How the cross-walk composes |
|---|---|
| `risks-and-controls-for-the-ai-supply-chain-v1` + `signing-ml-artifacts` (stable papers) | Cross-walk catalogs SPDX 3.0.1 AI Profile (AIPackage), SPDX 3.1-RC1 PRs #1259/#1267/#1257, G7 BSI SBOM for AI 7 core clusters, EU AI Act Article 53(1)(d) template. All directly compose with WS1 supply-chain controls. |
| 9 open RFCs in WS1 | Each WS1 RFC maps onto specific A-axes (A1 Identity, A5 Lifecycle, A6 Immutability) and H-categories (H8 Information Integrity, H12 Value Chain). The cross-walk provides the property-level lookup. |

### WS2 — Defenders (Preparing Defenders for a Changing Cybersecurity Landscape)

| CoSAI artifact | How the cross-walk composes |
|---|---|
| `preparing-defenders-of-ai-systems` (flagship paper), `AI-Incident-Response.md` v1.0, `AI-Shared-Responsibility-Framework` (May 2026) | Cross-walk's observability axis (A7) + AARM tamper-evident receipts + OWASP AOS AgBOM (extends CycloneDX/SWID/SPDX) directly compose with WS2 Telemetry framework (OCSF-aligned). Shared Responsibility Framework anchors A8 governance-role × persona mapping. |
| 12 open issues (AI-SPM, AI CAPEC, AI Telemetry OCSF, Behavioral Control Mechanisms) | Each composes with cross-walk's A4 Blast-radius + A7 Observability + A8 Governance-role axes. |

### WS3 — AI Risk Governance

| CoSAI artifact | How the cross-walk composes |
|---|---|
| WS3 early-stage scaffolding; 6 open RFCs | Three high-leverage WS3 RFCs (CoSAI-RM Interactive Risk Assessment #11, CoSAI Persona Model #12, Shared Responsibility Model #10) compose with cross-walk's 8-axis × 12-risk taxonomy + Raymond Sheh persona taxonomy (arXiv 2511.15763) + WhiteHouse M-24-10 dual-axis (Rights/Safety-impacting). |
| SIG-Security-AI-Assisted-Code-Development scope | Composes with OWASP AST10 Agentic Skills Top 10 (Incubator, March 2026) + OWASP Agent-Security-Regression-Harness. |

### WS4 — Secure-Design Agentic Systems

| CoSAI artifact | How the cross-walk composes |
|---|---|
| MCP Security paper v1 (Jan 2026) + V2 in flight (PR #108) | Cross-walk catalogs MCP 2025-11-25 spec (OAuth 2.1 + RFC 9728 + RFC 8707), explicitly distinguishing from community "MCP-I" label. |
| Agentic Identity & Access Control paper (Apr 2026) | 6-layer pattern resolves to A1 Identity through A7 Observability. |
| `mcp-secure-tool-design.md` (read-only / reversible / commit tool classes + Two-Stage Commit + L1/L2/L3 Autonomy Matrix) | Tool design classes compose with action-class authority A2 axis (read-only / reversible / external-reversible / irreversible per OWASP AISVS C9.2.6 Proposed for v1.01). |
| PR #117 ADLC Controls Checklist (open) | Each control row resolves to a cross-walk substrate. Sample mappings: manifest-declared action class (AISVS C9.2.6), worst-case chain rule (AISVS C9.2.7), AARM evidence stream (Errico arXiv 2602.09433), signature verification (W3C VC 2.0 + DID Core), data-quality gate (policy-evaluation + external data-quality signal two-layer pattern). |
| PR #116 Identity Architecture Playbook (WIP) | 6-layer pattern composes with action-class A2 axis cross-cuts (declared at Layer 2, gated at Layer 4, preserved at Layer 5, audited at Layer 6). |
| #99 Agent Credentials RFC (accepted, 8 co-authors) | Cross-walk catalogs A2A v1.0.1 AgentCard (JWS+JCS+mTLS), W3C VC 2.0 + DID Core, MCP OAuth model, WIMSE WG drafts, CSA NHI 6-property chain audit schema (internal IAM WG joint with Mallikarjunarao Sunke). |
| #113 Multimodal Agentic Security RFC (accepted) | 4-technique taxonomy maps to A4 Blast-radius + A7 Observability axes. |
| ADLC SIG (PR #101 merged 2026-06-01; 7-phase ownership locked 2026-06-03) | Cross-walk supports each of 7 phases via A1-A8 axis × H1-H12 risk mapping. Proposed 8th phase System Governance (Doyin Awofodu) extends A8. |
| 12-category MCP threat taxonomy (MCP-T1 through T12) | Each threat resolves to one or more cross-walk A-axes + H-categories. |

### secure-ai-tooling (Risk Map v1, launched June 2026)

| CoSAI artifact | How the cross-walk composes |
|---|---|
| Risk Map v1: 23 components / 35 controls / 36 risks / 10 personas / 8 lifecycle stages | The cross-walk matrix follows the same inversion pattern (controls → frameworks) Risk Map cross-walks against (current cross-walks: MITRE ATLAS, NIST AI RMF, STRIDE, OWASP LLM Top 10, ISO 22989, EU AI Act). SUBSTRATES.md could serve as supplementary framework-side index. |
| Issue #369 (controls → frameworks inversion proposal; cites SecureControlsFramework, CSA AICM, NIST CPRT) | The cross-walk artifact follows the same inversion pattern across CSA, NIST, CoSAI, OWASP, SPDX, MCP, A2A, WIMSE families. |
| PR #376 (framework mappings to ADR-027 pinned form) | Cross-walk's substrate catalog is the kind of pinned framework mapping ADR-027 enables. |
| PR #362 (ISO 42001 mapping) + PR #329 (ETSI EN 304 223) — open proposals | Cross-walk catalogs ISO/IEC 42001 as substrate (in CSA AICM cross-walk row). |

### CoSAI Resources reference library (`cosai-oasis/resources`)

| CoSAI artifact | How the cross-walk composes |
|---|---|
| `ai-incidents/`, `ai-regulations/`, `ai-risks/`, `ai-security-and-risk-frameworks/`, `ai-vulnerabilities/`, `glossary/`, `PERSONA.md` | SUBSTRATES.md is a candidate reference for `ai-security-and-risk-frameworks/` index. |

### Project CodeGuard (`cosai-oasis/project-codeguard`)

| CoSAI artifact | How the cross-walk composes |
|---|---|
| OWASP-aligned rule sets for AI coding agents | Composes with OWASP AISVS C9 (Autonomous Orchestration), C10 (MCP Security), AST10 Agentic Skills Top 10. |

### CoSAI TSC ↔ Workstreams convergence summary

Across the seven CoSAI organizational artifacts (TSC + 4 workstreams + secure-ai-tooling Risk Map + Resources), the cross-walk provides:

1. **Property-level lookup** for any CoSAI control needing cross-walk to other standards bodies.
2. **Composability evidence** that CoSAI's principles + WS schemas don't conflict with adjacent standards (CSA / NIST / OWASP / SPDX / IETF / W3C).
3. **Convergence narrative** — vendor-neutral framing showing the agentic standards landscape is converging on shared structural primitives, of which CoSAI is one constellation.

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

Vendor-specific substrates are not cited in this artifact; the cross-walk is vendor-neutral across standards bodies, RFCs, and academic substrate only.

---

**Status:** Research lens cross-walking the agentic standards landscape. Not a standalone framework.

**Contact:** Mayur021 on GitHub.
**Joint credit anchor:** Mallikarjunarao Sunke (CSA NHI 6-property chain audit schema; internal CSA IAM WG joint work).

---

<!-- Control-ID currency note -->
> **Control-ID currency note:** AISVS C9 references in this document use the post-2026-06-15 v1.0 main chapter inventory (PR #928 + #934 cleanup). Earlier drafts referenced C9.7.x and C9.9.x sub-controls which were removed in the cleanup. Verify current main chapter before quoting any specific sub-ID.
