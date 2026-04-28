# Documents Sharing — `documents.sharing`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `share_access_ids` **(one2many)** — Share Access ⚠️ obrigatório → `documents.sharing.access`
- `access_internal` **(selection)** — Internal users ⚠️ obrigatório
  > Opções: `view` (Viewer), `write_view` (Viewer), `edit` (Editor), `write_edit` (Editor), `none` (None), `write_none` (None), `mixed` (Mixed rights)
- `access_via_link` **(selection)** — Access through link ⚠️ obrigatório
  > Opções: `view` (Viewer), `write_view` (Viewer), `edit` (Editor), `write_edit` (Editor), `none` (None), `write_none` (None), `mixed` (Mixed rights)
- `access_via_link_mode` **(selection)** — Discoverable ⚠️ obrigatório
  > Opções: `mixed` (Mixed values), `link_required` (No), `write_link_required` (No), `discoverable` (Yes), `write_discoverable` (Yes)
- `invite_role` **(selection)** — Role ⚠️ obrigatório
  > Opções: `view` (Viewer), `edit` (Editor)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `invite_notify` **(boolean)** — Notify
- `invite_notify_message` **(html)** — Notification Message
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `document_ids` **(many2many)** — Document 🔒 readonly → `documents.document`
- `invite_partner_ids` **(many2many)** — Invite Partner → `res.partner`
- `owner_id` **(many2one)** — Owner of all documents 🔒 readonly → `res.users`

## Campos Calculados (readonly)

- `access_internal_help` **(char)** — Access Internal Help 🔒 readonly
- `access_via_link_help` **(char)** — Access Via Link Help 🔒 readonly
- `is_access_modified` **(boolean)** — Modified 🔒 readonly
- `access_urls` **(char)** — Access URLs 🔒 readonly
- `is_single` **(boolean)** — Single 🔒 readonly
- `is_folder_only` **(boolean)** — Folder Only 🔒 readonly
- `is_readonly` **(boolean)** — Readonly 🔒 readonly
- `has_warning_link_with_more_rights` **(char)** — Has Warning Link With More Rights 🔒 readonly
- `has_warning_partners_without_access` **(char)** — Has Warning Partners Without Access 🔒 readonly
- `error_message_spreadsheet` **(char)** — Error Message 🔒 readonly
