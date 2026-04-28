# Documents Operation — `documents.operation`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `operation` **(selection)** — Operation ⚠️ obrigatório
  > Opções: `move` (Move), `shortcut` (Create shortcuts), `copy` (Duplicate to), `add` (Add attachment to Documents)
- `destination` **(char)** — Destination ⚠️ obrigatório
- `user_permission` **(selection)** — Destination User Permission ⚠️ obrigatório
  > Opções: `edit` (Editor), `view` (Viewer), `none` (None)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `access_internal` **(char)** — Destination Access Internal
- `access_via_link` **(char)** — Destination Access Via Link
- `is_access_via_link_hidden` **(boolean)** — Destination Link Access Hidden
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `document_ids` **(many2many)** — Documents → `documents.document`
- `attachment_id` **(many2one)** — Attachment → `ir.attachment`
- `destination_children_ids` **(one2many)** — Siblings 🔒 readonly → `documents.document`
