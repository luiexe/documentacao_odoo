# Documents share access — `documents.sharing.access`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `role` **(selection)** — Role ⚠️ obrigatório
  > Opções: `view` (Viewer), `write_view` (Viewer), `edit` (Editor), `write_edit` (Editor), `none` (None), `write_none` (None), `mixed` (Mixed rights)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `expiration_date` **(datetime)** — Expiration
- `original_expiration_date` **(datetime)** — Original Expiration
- `is_deleted` **(boolean)** — Is Deleted
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `documents_sharing_id` **(many2one)** — Documents share → `documents.sharing`
- `partner_id` **(many2one)** — Partner → `res.partner`

## Campos Calculados (readonly)

- `partner_is_me` **(boolean)** — Is me 🔒 readonly
- `has_user` **(boolean)** — Has User 🔒 readonly
- `has_warning_no_access` **(boolean)** — Has Warning No Access 🔒 readonly
- `is_on_single_document` **(boolean)** — Is On Single Document 🔒 readonly
- `is_readonly` **(boolean)** — Readonly 🔒 readonly
