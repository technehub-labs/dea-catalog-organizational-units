# Organizational Units Catalog Changelog

All notable changes to this catalog are recorded here. Format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

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
