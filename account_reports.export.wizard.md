# Export wizard for accounting's reports — `account_reports.export.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `report_id` **(many2one)** — Parent Report Id ⚠️ obrigatório → `account.report`
- `folder_id` **(many2one)** — Folder ⚠️ obrigatório → `documents.document`
  > Folder where to save the generated file

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `doc_name` **(char)** — Documents Name
  > Name to give to the generated documents.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `export_format_ids` **(many2many)** — Export to → `account_reports.export.wizard.format`
- `tag_ids` **(many2many)** — Tags → `documents.tag`
