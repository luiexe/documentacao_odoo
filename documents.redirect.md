# Document Redirect — `documents.redirect`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `access_token` **(char)** — Access Token ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `document_id` **(many2one)** — Document → `documents.document`
- `employee_id` **(many2one)** — Employee → `hr.employee`
