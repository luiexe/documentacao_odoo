# Fields Selection — `ir.model.fields.selection`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `field_id` **(many2one)** — Field ⚠️ obrigatório → `ir.model.fields`
- `value` **(char)** — Value ⚠️ obrigatório
- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
