# Create a dashboard from a spreadsheet document — `spreadsheet.document.to.dashboard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Dashboard Name ⚠️ obrigatório
- `document_id` **(many2one)** — Document ⚠️ obrigatório 🔒 readonly → `documents.document`
- `dashboard_group_id` **(many2one)** — Dashboard Section ⚠️ obrigatório → `spreadsheet.dashboard.group`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `group_ids` **(many2many)** — Access Groups → `res.groups`
