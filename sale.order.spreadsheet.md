# Quotation Spreadsheet — `sale.order.spreadsheet`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `spreadsheet_binary_data` **(binary)** — Spreadsheet file
- `spreadsheet_data` **(text)** — Spreadsheet Data
- `thumbnail` **(binary)** — Thumbnail
- `spreadsheet_snapshot` **(binary)** — Spreadsheet Snapshot
- `display_thumbnail` **(binary)** — Display Thumbnail
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `spreadsheet_revision_ids` **(one2many)** — Spreadsheet Revision → `spreadsheet.revision`
- `company_id` **(many2one)** — Company → `res.company`
- `order_id` **(many2one)** — Order → `sale.order`

## Campos Calculados (readonly)

- `spreadsheet_file_name` **(char)** — Spreadsheet File Name 🔒 readonly
- `current_revision_uuid` **(char)** — Current Revision Uuid 🔒 readonly
