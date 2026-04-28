# Signature Template — `sign.template`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `color` **(integer)** — Color
- `redirect_url` **(char)** — Redirect Link
  > Optional link for redirection after signature
- `redirect_url_text` **(char)** — Link Label
  > Optional text to display on the button link
- `signature_request_validity` **(integer)** — Default signature request validity
  > Specify the default validity period (in days) for signature requests. Set to 0 for requests that don't expire.
- `has_sign_requests` **(boolean)** — Has Sign Requests 🔒 readonly
- `message` **(html)** — Message
  > Message to be sent to signers of the specified document
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `document_ids` **(one2many)** — Documents → `sign.document`
- `sign_item_ids` **(one2many)** — Signature Items 🔒 readonly → `sign.item`
- `favorited_ids` **(many2many)** — Favorited Users → `res.users`
- `user_id` **(many2one)** — Responsible → `res.users`
- `sign_request_ids` **(one2many)** — Signature Requests → `sign.request`
- `tag_ids` **(many2many)** — Tags → `sign.template.tag`
- `authorized_ids` **(many2many)** — Authorized Users → `res.users`
- `group_ids` **(many2many)** — Authorized Groups → `res.groups`
- `model_id` **(many2one)** — Model → `ir.model`
- `folder_id` **(many2one)** — Signed Document Folder → `documents.document`
- `documents_tag_ids` **(many2many)** — Signed Document Tags → `documents.tag`

## Campos Calculados (readonly)

- `responsible_count` **(integer)** — Responsible Count 🔒 readonly
- `signed_count` **(integer)** — Signed Count 🔒 readonly
- `in_progress_count` **(integer)** — In Progress Count 🔒 readonly
- `is_sharing` **(boolean)** — Is Sharing 🔒 readonly
  > Checked if this template has created a shared document for you
- `model_name` **(char)** — Model Name 🔒 readonly
