# SCHF SDK

Public contract repository shared by SCHF Core and SCHF Migration.

This repository contains schemas, contracts, OpenAPI models, and versioning rules. It contains no client-specific code, no backups, no databases, and no real client data.

## Contents

| Path | Purpose |
|------|---------|
| `schemas/bundle/` | Migration Bundle manifest and report schemas |
| `schemas/records/` | Record schemas accepted inside a Migration Bundle |
| `openapi/` | Core import API contract |
| `contracts/` | Bundle, plugin, connector, and version contracts |
| `examples/empty-bundle/` | Empty reference bundle with no real data |

## Core Rule

SCHF Core only imports the universal Migration Bundle format. It never knows a legacy database, ERP, connector, plugin, or client-specific rule.

SCHF Migration and its plugins generate Migration Bundles. They never write directly into the SCHF Core database.

## Migration Bundle Layout

```text
bundle/
├── manifest.json
├── organization.json
├── users.json
├── roles.json
├── permissions.json
├── suppliers.json
├── accounts.json
├── banks.json
├── categories.json
├── payments.json
├── expenses.json
├── attachments/
├── logs/
├── report.json
└── checksum.sha256
```

## Security

- Never commit real databases, dumps, backups, or client files.
- Never commit `.FDB`, `.FBK`, `.SQL`, `.RAR`, `.ZIP`, `.ENC`, or credentials.
- Run `gitleaks detect` before every push.
