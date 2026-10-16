# Organizational Units Catalog Changelog

All notable changes to this catalog are recorded here. Format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### CR-OU-04: Entity System Stage 5-6 (Organizational Units Slice)

OU slice of the General Entity System institutionalisation (cross-repo cascade T7 of the umbrella programme). New `reconciliation/entity-system-registry.yaml` (per-repo; generic; no profiles; canonical pattern `^dea:ou-[a-z0-9-]+$`). New `scripts/check_entity_system.py` (5-rule umbrella gate; copied verbatim from `dea-catalog-processes`). New `tests/test_check_entity_system.py` (32 tests; 4 pilot-specific tests made generic for cross-repo portability; all pass). New `.github/workflows/validate-entity-system.yml` (CI). Live: gate vacuously CONFORMANT (0 entities in file_globs). D-004 clean. 118a/b/c authorship gates remain CONFORMANT.

### CR-OU-03: Authorship Cardinal Rule (R1, R2) - Org-Wide Propagation Slice

User directive 2026-10-13: "no `Coder` / `Agent` / agent or tool names in any
authorship field of any published artifact". The CR-BP-118 cardinal rules (R1
and R2) are propagated to this repo. New blocking gate
`scripts/check_authorship.py` (CR-BP-118 / AUT-001..003), data-driven from
`reconciliation/authorship-fields.yaml` (allowlist
`{Emmanuel A. Otchere, TechNeHub Labs}`; denylist
`{Coder, Agent, Hermes, Claude, GPT, Cline, OpenAI, MiniMax, MiniMax-M3}`).
A retroactive sweep rewrites every authorship-metadata hit in the repo: 2
files (CR-OU-01, CR-OU-02), 2 textual replacements (one per file). 0 entity
content changes; 0 id changes; 0 cross-reference changes. The OU repo shares
the 118a field shape (CR-doc metadata only) and uses the same registry
fields; no per-repo extension is needed. CI wiring: new workflow
`.github/workflows/validate-authorship.yml` runs the gate in `--strict` mode
on every push and PR. 21/21 `test_check_authorship` pass. Carrier:
`change-requests/CR-OU-03-authorship-cardinal-rule.md`.

## [v2.5.0-migration] - 2026-09-08

CR-OU-02 implementation: ECF Domain enum migration to the v2.5.0 canonical Domain set (carried by `technehub-labs/dea-metaframework` v2.5.0; CR-ECF-008 + ADR-ECF-003). One of seven Domains renamed: Domain 6 `operations-enablement` → `enablement-operations` (kebab-case), driven by the Domain/Stage Orthogonality Stress Test. 3 files re-keyed. See `change-requests/CR-OU-02-ecf-domain-enum-migration-v250.md` for the full mapping.

## [v2.4.0-migration] - 2026-09-07

CR-OU-01 implementation: bundled ECF Domain enum migration to the v2.4.0
canonical Domain set (carried by `technehub-labs/dea-metaframework` v2.4.0;
CR-ECF-006 + CR-ECF-007, governed by ADR-ECF-001 + ADR-ECF-002). This repo
was missed by the v2.3.0 wave ground-truth scan and was still carrying the
v2.2.0 Domain enum; both waves applied in a single step. `supply-resources`
-> `strategy-direction`; `people-organization` -> `agency-organization`;
`customer-demand` -> `party-relationship`; `product-offering` ->
`product-value`; `operations-delivery` -> `enablement-operations`;
`finance-value` -> `finance-accounting`. 2 files re-keyed
(entity.schema.json, entities/v1-alpha/README.md). No entity YAMLs exist
yet; nothing to migrate at the entity level.
