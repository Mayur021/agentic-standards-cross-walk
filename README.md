# Agentic Standards Cross-Walk

> A research lens that cross-walks the agentic-AI standards landscape across CSA, NIST, CoSAI, OWASP, SPDX, Singapore IMDA, US WhiteHouse, EU AI Act, G7 BSI, MCP, A2A, WIMSE, W3C VCs+DIDs, AGENTS.md, and adjacent substrates — viewed through an action-class authority lens with companion 8-axis architectural and NIST 12-risk harm taxonomies.

> **What this is NOT:** Not a new standard, not a competing project, not a fork of any existing body's work. It is a research artifact that maps property-level convergence across existing standards bodies.

> **What this is FOR:** Supporting standards-track contributions to existing bodies (CSA, NIST, CoSAI, OWASP, SPDX, IETF, W3C) by making convergence visible across the landscape.

**Maintainer:** Mayur Agnihotri ([@Mayur021](https://github.com/Mayur021))
**Joint credit anchor:** Mallikarjunarao Sunke. CSA NHI v1.0 anchor reflects the four-element attribution language (delegator / agent / intent / actions) at paragraph 222 of the Working Draft (joint peer-review contribution; verified 2026-06-15). Full six-property chain audit schema (chain-id binding, originating-principal immutability, audit telemetry surface) is targeted for v2.0 inclusion (joint contribution with Mallikarjunarao Sunke).
**License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
**Status:** v1.1 research artifact — feedback welcome via Issues and PRs

---

## What this is

A research artifact that:

1. Names the structural axis — **action-class authority** (declared at manifest, gated at verb-layer, preserved across delegation chain, audited in trace) — that recurs across the agentic-AI standards landscape
2. Cross-walks each substrate's expression of the axis at schema-property level
3. Maps each property to both the **8-axis architectural taxonomy** (identity / authority / chain / blast-radius / lifecycle / immutability / observability / governance-role) and the **NIST AI 600-1 12-risk harm taxonomy**
4. Identifies **gap-to-contribute slots in existing standards bodies' work** across Q3/Q4 2026 and 2027
5. **Invites the community** to validate, correct, extend the cross-walk — and to file the contribution slots into the relevant existing body (CoSAI, OWASP, CSA, NIST, SPDX, IETF, W3C)

## Why

The agentic-AI standards landscape has converged on a shared structural primitive under multiple vocabularies — manifest-declared action class (OWASP AISVS C9.2.6, Proposed for v1.01), capability declaration (CSA Agentic Trust Framework I-5), tool risk classification (CSA NIST AI RMF Agentic Profile AG-MP.1), action boundaries (CSA Agentic Trust Framework S-2), permission scope (CSA NHI registry field 5), agentTrustLevel + agentPermissionScope (SPDX 3.1-RC1 PR #1257), Tools + Instructions components (Singapore IMDA MGF v1.5), Excessive Agency (OWASP LLM Top 10 LLM06). These are the same axis under different names.

This artifact names it explicitly and cross-walks it so contributors across standards bodies can see the convergence and fill the gaps.

## Navigation

| File | What it is | Audience |
|---|---|---|
| [COSAI-FOCUSED-CROSSWALK.md](COSAI-FOCUSED-CROSSWALK.md) | **Primary artifact** — condensed schema cross-walk focused on CoSAI WS4 / Risk Map / WS4 #99 integration | Anyone contributing to CoSAI / AISVS / CSA / SPDX agentic work |
| [SUBSTRATES.md](SUBSTRATES.md) | Substrate inventory with canonical URLs + status qualifiers | Validators / contributors checking completeness |
| [EXAMPLES/](EXAMPLES/) | 3 standalone cross-walk worked examples (action-class authority / chain audit / observability) | Citers / educators |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Contribution discipline — citation qualifier rules + joint-credit anchors + how to file | Anyone opening an Issue or PR |
| [LICENSE.md](LICENSE.md) | CC BY 4.0 license | Reusers |

## Quick start — for citers

Cite this cross-walk as:

> Mayur Agnihotri. "Agentic Standards Cross-Walk: An Action-Class Authority Lens." v1.1, 2026-06-11. https://github.com/Mayur021/agentic-standards-cross-walk

When citing the CSA NHI four-element attribution language (delegator / agent / intent / actions) anchored at paragraph 222 of the v1.0 Working Draft, or the full six-property chain audit schema (chain-id binding, originating-principal immutability, audit telemetry surface) targeted for v2.0 inclusion, also credit Mallikarjunarao Sunke (joint authorship).

## Quick start — for contributors

1. Read [CONTRIBUTING.md](CONTRIBUTING.md) for citation discipline + qualifier rules
2. Open an Issue (substrate addition / substrate correction / cross-walk validation / citation qualifier flag) or PR
3. Cite the existing standards body's canonical source URL for any addition or correction

## Scope

Substrate scope across these families:

- **CSA**: NHI v1 (registry whitepaper) / *Defining NHI v1.0* Working Draft (four-element attribution at para 222; joint Mayur + Mallikarjunarao Sunke) / *Defining NHI v2.0* (forthcoming; full six-property chain audit schema; joint) / Agentic Trust Framework v0.9.1 / AARM / AAGATE / NIST AI RMF Agentic Profile / OpenClaw / AICM v1.0 / MAESTRO / AI Safety Initiative / IAM WG
- **NIST**: AI RMF (AI 100-1) / AI 600-1 GenAI Profile / IR 8596 Cyber AI Profile / SP 800-53 COSAiS / AI 100-2e2025 / CSF 2.0 / CAISI AI Agent Standards Initiative / GitHub repos
- **CoSAI**: Risk Map v1 / WS4 ADLC 7-phase / WS4 Identity Architecture / WS4 #99 Agent Credentials / WS4 #113 Multimodal / WS1 / WS2 / WS3 / TSC / CodeGuard / Resources
- **OWASP**: AISVS v1.0 / AISVS C9.2.6+9.2.7 / LLM Top 10 v2 / ASI Agentic Top 10 / NHI Top 10 / SPVS 1.0+1.5-AI / AOS / AST10 / AIVSS / secure-agent-playbook / Agent-Security-Regression-Harness / AI Testing Guide / AI Security & Privacy Guide / AIMM
- **SPDX**: 3.0.1 AI Profile / 3.0.1 Dataset Profile / 3.1-RC1 PRs #1259 / #1267 / #1257 / #1249 / #1280 / active issues
- **Government / regulatory**: Singapore IMDA MGF v1.5 / WhiteHouse M-24-10 / EU AI Act Article 53(1)(d) / G7 BSI SBOM for AI / EU AI Act (full)
- **Identity protocols**: MCP 2025-11-25 / A2A v1.0.1 / WIMSE WG / WIMSE individual I-Ds / W3C VC 2.0 / W3C DID Core / AGENTS.md / OASF / Agent Trust Bench / SPIFFE-SPIRE / RFC 8693 + 9728 + 8707
- **Academic**: Atlas Framework / Raymond Sheh Persona Taxonomy / Orchestration Layer Regulation / Threat Modeling Asset-Centric / Model Openness Framework
- **Industry tooling**: AIUC-1 / NuGuard.ai / Pitloom AIBOM

## Discipline

This artifact applies strict citation discipline:

- Every draft standard carries its version-stamp qualifier ("Proposed for v1.01", "Public Review Draft v0.9.1", "Preliminary Draft", "I-D Exists", "research/ directory", "3.1-RC1")
- CSA NHI references distinguish the v1.0 four-element attribution language anchored at para 222 (joint Mayur + Mallikarjunarao Sunke) from the full six-property chain audit schema targeted for v2.0 (also joint); Mallikarjunarao Sunke is jointly credited on every reference to either
- Vendor-specific substrates are not cited; the cross-walk is vendor-neutral across standards bodies, RFCs, and academic substrate only
- No proprietary or pre-launch private content from any working group

If you spot a missing qualifier or attribution, open an Issue tagged `citation-qualifier-flag`.

## Versioning

- **v1.0** (2026-06-10) — Initial publication
- **v1.1** (2026-06-11) — Reframed as research lens; primary artifact narrowed to CoSAI-focused condensed cross-walk
- **v1.x** — incremental community contributions
- **v2** — quarterly consolidation

## Contact

- GitHub: [@Mayur021](https://github.com/Mayur021) — open Issues, PRs, or Discussions on this repo
- For CSA NHI cross-walks (v1.0 four-element attribution AND v2.0-targeted six-property formalization), please also direct to **Mallikarjunarao Sunke** (joint authorship anchor)
- For substrate-specific corrections, please direct to the project leads named in each substrate row of [SUBSTRATES.md](SUBSTRATES.md)

---

**Status:** v1.1 research artifact — feedback welcome via Issues and PRs. Validation, corrections, and additions help refine the cross-walk for everyone using it to navigate standards-track contributions.
