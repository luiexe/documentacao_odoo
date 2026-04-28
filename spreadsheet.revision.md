# Collaborative spreadsheet revision — `spreadsheet.revision`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_model` **(char)** — Model ⚠️ obrigatório
- `res_id` **(many2one_reference)** — Record id ⚠️ obrigatório
- `commands` **(char)** — Commands ⚠️ obrigatório
- `revision_uuid` **(char)** — Revision Uuid ⚠️ obrigatório
- `author_id` **(many2one)** — Author ⚠️ obrigatório → `res.users`
- `revision_date` **(datetime)** — Revision Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Revision name
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_revision_id` **(many2one)** — Parent Revision → `spreadsheet.revision`
