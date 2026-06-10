# Contributing to the Agentic Standards Cross-Walk

Thank you for considering contributing. This RFC depends on community validation across multiple standards bodies — your input strengthens the cross-walk and surfaces gaps that no single contributor can see.

## Three ways to contribute

1. **Issues** — file via the [Issue templates](.github/ISSUE_TEMPLATE/) for substrate additions, substrate corrections, cross-walk validations, and citation qualifier flags
2. **Pull Requests** — propose direct changes to RFC.md, SUBSTRATES.md, or EXAMPLES/
3. **Discussions** — for open-ended cross-walk questions or community contribution coordination

## Citation discipline (REQUIRED)

This is the most important contribution rule. Every substrate citation in your contribution MUST carry the appropriate version-stamp qualifier. Examples of correct vs incorrect form:

| Incorrect (no qualifier) | Correct (with qualifier) |
|---|---|
| "AISVS C9.2.6" | "AISVS C9.2.6 (Proposed for v1.01; merged via PR #822 into research/ directory 2026-05-27)" |
| "CSA ATF 7 properties" | "CSA Agentic Trust Framework v0.9.1 Public Review Draft (5 Core Elements + 25 requirements + 4-tier maturity)" |
| "CSA NHI 6-property schema" | "CSA NHI 6-property chain audit schema (internal IAM WG joint Mayur Agnihotri + Mallikarjunarao Sunke; under review for v1.0)" |
| "Singapore IMDA 6 components" | "Singapore IMDA MGF Agentic AI v1.5 (8 components — Model / Instructions / Memory / Planning_Reasoning / Tools / Protocols / Controls / Logging_Monitoring; 20 May 2026)" |
| "MCP-I" | "MCP authorization model: OAuth 2.1 + RFC 9728 + RFC 8707 (no native VC/DID layer); 'MCP-I' is community label, not Anthropic spec" |
| "SPDX 3.1" | "SPDX 3.1-RC1 (pre-release, 2026-01-24); 3.0.1 stable" |
| "OWASP Multi-Agent Threat Modeling Guide" | "OWASP Multi-Agent threat content distributed across AISVS C9.8 + ASI Sprint 1 ASI13/14 + lets-threat-model tool — no standalone repo" |
| "WIMSE IETF standard" | For WG drafts: "WIMSE WG I-D" (or specific draft name); for AI-agent drafts: "WIMSE individual I-D (NOT WG-adopted)" |

If you're unsure of the correct qualifier, leave a `[QUALIFIER?]` placeholder in your PR; we'll resolve in review.

## Joint credit anchors

**CSA NHI 6-property chain audit schema** is jointly authored by Mayur Agnihotri (fields 1-4 + chain-id binding R8) and Mallikarjunarao Sunke (field 5 parent-chain binding + property 6 immutability of originating principal). On every reference in the cross-walk artifact, both names must be cited together.

If you contribute a substrate where joint authorship applies, please name all authors of the substrate in the citation, not just the lead.

## Substrate-13 / 14 / 16 discipline

Three substrates are tracked with **public-references-only** discipline:

- **Substrate-13** — Anthropic Fable 5 + Mythos 5: cite from public Anthropic blog and public thesis posts only
- **Substrate-14** — agentrust-io (Imran Siddique / OPAQUE): pre-launch private until 2026-06-23; cite from public CoSAI WS4 #99 references + public github.com/agentrust-io/.github profile only. Do NOT include private repo content even if you have access.
- **Substrate-16** — EQTY Lab (Rithikha Rajamohan / Cameron Fyfe): cite from public CoSAI WS1 demos + public AgentCard demo + public SPDX-AI Slack joins only

Contributions that include private content from these substrates will be rejected.

## What we welcome

1. **Substrate completeness** — Are there standards, projects, RFCs, or guidance documents missing from the catalog? Examples we'd appreciate: IETF SCITT, additional EU member-state guidance, Australia AI Ethics Framework, Korea AI Basic Act, Japan AI Bill, Brazil AI Act, India DPDP Act + Digital India Act drafts.

2. **Schema property completeness** — Within each substrate row, which properties are missing from the cross-walk?

3. **Cross-walk validation** — Where is a cross-walk mapping incorrect or under-specified? If you maintain one of the named standards and disagree with the mapping, please correct.

4. **Citation qualifier flags** — Where a draft standard is cited without the correct qualifier, flag the issue.

5. **Gap-to-contribute slots** — Which Q3/Q4/2027 contribution slots in RFC.md are already in flight elsewhere that the cross-walk has missed? Which are no longer open?

6. **Additional worked examples** — The EXAMPLES/ folder has 3 worked cross-walks (action-class authority / chain audit / observability). Other axes deserve worked examples too — lifecycle, blast radius, immutability, governance-role.

## What we don't accept

- Citations without version-stamp qualifiers for draft standards
- Removing or weakening Mallikarjunarao Sunke joint credit on CSA NHI references
- Private working-group content from CSA, NIST, CoSAI, OWASP, or any other body
- Pre-launch private content from substrate-13/14/16
- Vendor product comparisons or competitive positioning
- "Happy to..." forward promises (the artifact does what it does; we don't promise additional unreleased work)
- Edits that overlay a single vendor's vocabulary across the unified taxonomy

## Pull Request workflow

1. Fork the repo
2. Create a branch named `contrib/<short-description>`
3. Make your changes
4. Verify every citation carries the correct qualifier (use this CONTRIBUTING.md as the lookup)
5. Open a PR with:
   - Description of what you're adding/correcting
   - Specific substrate row(s) affected
   - Source URL for verification
   - Citation qualifier you're applying
6. Review will check qualifier discipline + joint credit + substrate-13/14/16 discipline

## Code of conduct

This is a collaborative standards-track cross-walk artifact. Communication should be:

- Substantive (focus on the substrate, not the contributor)
- Respectful of working-group norms (do not leak private content even if you have access)
- Cross-walk oriented (find where vocabularies converge, do not advocate for one vendor's vocabulary over others)
- Discipline-first (qualifier on every citation, joint credit on every shared work)

## Maintainer review SLA

We aim for first-touch review within **5 business days**, full review and merge decision within **15 business days**. Complex cross-walks may take longer.

## License

By contributing you agree your contributions are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), the same as the project.

## Questions

- Open a [Discussion](https://github.com/Mayur021/agentic-standards-cross-walk/discussions)
- Tag @Mayur021 in an existing Issue for clarification

---

Thank you for contributing to making the agentic-AI standards landscape more navigable.
