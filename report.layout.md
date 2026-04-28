# Report Layout — `report.layout`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `view_id` **(many2one)** — Document Template ⚠️ obrigatório → `ir.ui.view`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `image` **(char)** — Preview image src
- `pdf` **(char)** — Preview pdf src
- `sequence` **(integer)** — Sequence
- `name` **(char)** — Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
