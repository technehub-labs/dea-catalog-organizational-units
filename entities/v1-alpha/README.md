# v1-alpha Catalog Entries

This directory will hold Organizational Unit catalog entries once Phase 2 content population begins.

Each entry should be a YAML or JSON file following the schema in `../../schemas/entity.schema.json`. Example shape:

```yaml
id: dea:ou-customer-success-division
type: OrganizationalUnit
name: Customer Success Division
ou_type: division
ou_scope: enterprise
ou_lifecycle: permanent
ecf_domain: party-relationship
ecf_stage: operate
version: 1.0.0
description: Enterprise division accountable for customer success outcomes across all customer segments.
owned_capabilities:
  - dea:capability-manage-account
  - dea:capability-issue-refund
owned_processes:
  - dea:process-customer-onboarding
  - dea:process-refund-handling
owned_objects:
  - dea:object-customer-12345
actors:
  - dea:actor-customer-success-manager
  - dea:actor-account-management-team
cost_center: CC-CS-001
head_count: 42
```

See [DEA Metamodel OrganizationalUnit schema](https://github.com/technehub-labs/dea-metamodel/blob/main/schemas/entities/organizational-unit.json) for the canonical definition.
