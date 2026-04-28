# Spreadsheet Dashboard — `spreadsheet.dashboard`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `dashboard_group_id` **(many2one)** — Dashboard Group ⚠️ obrigatório → `spreadsheet.dashboard.group`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `spreadsheet_binary_data` **(binary)** — Spreadsheet file
- `spreadsheet_data` **(text)** — Spreadsheet Data
- `thumbnail` **(binary)** — Thumbnail
- `spreadsheet_snapshot` **(binary)** — Spreadsheet Snapshot
- `display_thumbnail` **(binary)** — Display Thumbnail
- `sequence` **(integer)** — Sequence
- `sample_dashboard_file_path` **(char)** — Sample Dashboard File Path
- `is_published` **(boolean)** — Is Published
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `spreadsheet_revision_ids` **(one2many)** — Spreadsheet Revision → `spreadsheet.revision`
- `company_ids` **(many2many)** — Companies → `res.company`
- `group_ids` **(many2many)** — Group → `res.groups`
- `favorite_user_ids` **(many2many)** — Favorite Users → `res.users`
  > Users who have favorited this dashboard
- `main_data_model_ids` **(many2many)** — Main Data Model → `ir.model`

## Campos Calculados (readonly)

- `spreadsheet_file_name` **(char)** — Spreadsheet File Name 🔒 readonly
- `current_revision_uuid` **(char)** — Current Revision Uuid 🔒 readonly
- `is_favorite` **(boolean)** — Is Favorite 🔒 readonly
  > Indicates whether the dashboard is favorited by the current user
- `is_from_data` **(boolean)** — Is From Data 🔒 readonly
