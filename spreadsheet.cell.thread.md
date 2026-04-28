# Spreadsheet discussion thread — `spreadsheet.cell.thread`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `document_id` **(many2one)** — Document 🔒 readonly → `documents.document`
- `template_id` **(many2one)** — Template 🔒 readonly → `spreadsheet.template`
- `dashboard_id` **(many2one)** — Dashboard 🔒 readonly → `spreadsheet.dashboard`
- `sale_order_spreadsheet_id` **(many2one)** — Sale Order Spreadsheet 🔒 readonly → `sale.order.spreadsheet`
