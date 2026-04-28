# Document / Partner — `documents.access`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `document_id` **(many2one)** — Document ⚠️ obrigatório → `documents.document`
- `partner_id` **(many2one)** — Partner ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `role` **(selection)** — Role
  > Opções: `view` (Viewer), `edit` (Editor)
- `last_access_date` **(datetime)** — Last Accessed On
- `expiration_date` **(datetime)** — Expiration
