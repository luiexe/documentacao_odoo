# Knowledge Stage — `knowledge.article.stage`

**Ordenação padrão:** `parent_id, sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `parent_id` **(many2one)** — Owner Article ⚠️ obrigatório → `knowledge.article`
  > Stages are shared among acommon parent and its children articles.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `fold` **(boolean)** — Folded in kanban view
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
