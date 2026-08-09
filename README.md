# Organizational Units

> Units of organisation — accountability containers that own capabilities, run processes, and are custodians for business objects.

**Layer:** L2 · **Entity:** `OU` · **Metamodel:** [v1.0.0-alpha](https://github.com/technehub-labs/dea-metamodel)

[![View in Metamodel Explorer](https://img.shields.io/badge/Metamodel%20Explorer-View%20Entity-2C3E50?style=shield)](https://technehub-labs.github.io/metamodel/?entity=OrganizationalUnit)

## Status

This is a **scaffold** repository — created during the Organizational Unit relocation rollout. Content population is planned for a subsequent phase.

## Entity Definition

| Field | Value |
|-------|-------|
| Entity ID | `dea:entity-organizational-unit` |
| Class Alias | `OU` |
| Layer | L2 (Business Operating Model) |
| Metamodel Version | v1.0.0-alpha |

## Classification — Three Orthogonal Structural Axes

### Axis 1 — `ou_type` (structural kind)

| Value | Meaning |
|---|---|
| `business-unit` | P&L-bearing organisational entity |
| `division` | Top-level grouping under the enterprise |
| `department` | Function-aligned grouping |
| `team` | Stable working group |
| `role-cluster` | Group defined by shared role rather than hierarchy |
| `virtual-team` | Crosses formal boundaries for a specific purpose |
| `governance-body` | Decision-making forum (committee, board, council) |
| `external-partner-role` | External party acting as a unit |

### Axis 2 — `ou_scope` (vertical span)

`individual` · `team` · `departmental` · `division` · `enterprise` · `ecosystem`

### Axis 3 — `ou_lifecycle` (time horizon)

`permanent` · `temporary` · `ad-hoc` · `sunsetting`

### Optional ECF coordinates

`ecf_domain` and `ecf_stage` are **optional** — units spanning multiple domains (COO office, PMO) leave them unset. This separates OUs (accountability containers that *serve* matrix cells) from BusinessObjects (which *populate* matrix cells).

## Typed References

| Field | Reference | Catalog |
|---|---|---|
| `parent_ou` | Parent unit | (self-reference) |
| `child_ous[]` | Child units | (self-reference, inverse of parent_ou) |
| `owned_capabilities[]` | Capabilities this OU owns (accountability) | [`dea-catalog-business-capabilities`](https://github.com/technehub-labs/dea-catalog-business-capabilities) |
| `owned_processes[]` | Processes this OU runs (execution) | [`dea-catalog-processes`](https://github.com/technehub-labs/dea-catalog-processes) |
| `owned_objects[]` | Business Objects this OU is custodian for | [`dea-catalog-business-objects`](https://github.com/technehub-labs/dea-catalog-business-objects) |
| `actors[]` | Members of this OU | [`dea-catalog-actors`](https://github.com/technehub-labs/dea-catalog-actors) |
| `stakeholders[]` | External parties served by this OU | [`dea-catalog-stakeholders`](https://github.com/technehub-labs/dea-catalog-stakeholders) |

## Finance / HR anchors

| Field | Type | Purpose |
|---|---|---|
| `cost_center` | string | Finance cost-center code |
| `head_count` | integer | Planned headcount snapshot (actual derived from `actors[]`) |

## Catalog Structure

```
dea-catalog-organizational-units/
├── metamodel-pointer.yaml         ← entity mapping (do not edit manually)
├── README.md
├── LICENSE + NOTICE
├── entities/
│   └── v1-alpha/                  ← catalog entries go here
│       └── README.md
├── schemas/
│   └── entity.schema.json         ← mirrors dea-metamodel/schemas/entities/organizational-unit.json
└── .github/
    └── workflows/
        └── ci.yml                 ← validates entries against schema
```

## Contributing

See [DEA Metamodel OrganizationalUnit schema](https://github.com/technehub-labs/dea-metamodel/blob/main/schemas/entities/organizational-unit.json) for the canonical definition.
