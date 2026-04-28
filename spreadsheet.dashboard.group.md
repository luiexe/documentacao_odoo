# Group of dashboards — `spreadsheet.dashboard.group`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `dashboard_ids` **(one2many)** — Dashboard → `spreadsheet.dashboard`
- `published_dashboard_ids` **(one2many)** — Published Dashboard → `spreadsheet.dashboard`
