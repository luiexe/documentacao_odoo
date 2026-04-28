# Tag — `documents.tag`

**Ordenação padrão:** `sequence, name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `color` **(integer)** — Color
- `tooltip` **(char)** — Tooltip
  > Text shown when hovering on this tag
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `document_ids` **(many2many)** — Document → `documents.document`
