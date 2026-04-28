# Spreadsheet Contributor — `spreadsheet.contributor`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `last_update_date` **(datetime)** — Last update date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `document_id` **(many2one)** — Document → `documents.document`
- `user_id` **(many2one)** — User → `res.users`
