# Completed Document — `sign.completed.document`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `sign_request_id` **(many2one)** — Sign Request ⚠️ obrigatório → `sign.request`
- `document_id` **(many2one)** — Document ⚠️ obrigatório → `sign.document`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `file` **(binary)** — Completed Document 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
