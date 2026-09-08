# CR-OU-02: ECF Domain Enum v2.5.0 Migration (Domain 6 Enablement & Operations)

**Status**: Accepted
**Layer**: Catalog (organizational units)
**Owner**: Coder (for eaojnr)
**Date**: 2026-09-08
**Depends on**: CR-OU-01 (v2.4.0 migration carrier); dea-metaframework CR-ECF-008; dea-metamodel CR-MM-ECF-03
**Related**: dea-metaframework ADR-ECF-003; dea-catalog-processes CR-BP-23; dea-catalog-business-capabilities CR-BC-ECF-03

## 1. What this CR is

This CR is the **v2.5.0 migration carrier** for `technehub-labs/dea-catalog-organizational-units`. ECF Domain 6 is renamed from `operations-enablement` (v2.4.0 kebab-case) to `enablement-operations` (v2.5.0), driven by the Domain/Stage Orthogonality Stress Test (`dea-metaframework` ADR-ECF-003 §5; CR-ECF-008).

## 2. Mapping

| Old form (v2.4.0) | New form (v2.5.0) |
|---|---|
| `OperationsAndEnablement` (PascalCase) | `EnablementAndOperations` |
| `operations-enablement` (kebab-case) | `enablement-operations` |
| `operationsEnablement` (lowerCamelCase identifier suffix) | `enablementAndOperations` |
| `Operations & Enablement` (display) | `Enablement & Operations` |

## 3. Files changed

- `schemas/entity.schema.json` — `ecf_domain` enum updated.
- `change-requests/CR-OU-01-ecf-domain-enum-migration.md` — narrative updated.
- `CHANGELOG.md` — `[v2.5.0-migration]` section.

Total: **3 files modified** + 1 new CR.

## 4. Verification

- Schema enum matches `dea-metaframework` v2.5.0 canonical set exactly.
- Zero remaining references to v2.4.0 Domain 6 identifier.

## 5. Backward compatibility

`dea-metaframework` v2.5.0 preserves the deprecated identifiers in `tools/ecf_coordinates.py:DOMAIN_ALIASES` for at least 2 release cycles (CR-ECF-008 §17).

## 6. Companion CRs

- `dea-metaframework` CR-ECF-008 (PR #30) — merged 2026-09-08
- `dea-metamodel` CR-MM-ECF-03 (PR #167) — open
- `dea-catalog-processes` CR-BP-23 (PR #61) — open
- `dea-catalog-business-capabilities` CR-BC-ECF-03 (PR #56) — open
- `dea-catalog-business-objects` CR-BO-02 (PR #6) — open

Repos audited as having zero footprint (no migration needed): `dea-catalog-actors`, `dea-catalog-stakeholders`, `dea-catalog-digital-business-service-factory`, `dea-architecture-framework`.