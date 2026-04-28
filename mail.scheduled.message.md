# Scheduled Message — `mail.scheduled.message`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `scheduled_date` **(datetime)** — Scheduled Date ⚠️ obrigatório
- `model` **(char)** — Related Document Model ⚠️ obrigatório
- `res_id` **(many2one_reference)** — Related Document Id ⚠️ obrigatório
- `author_id` **(many2one)** — Author ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `subject` **(char)** — Subject
- `body` **(html)** — Contents
- `composition_comment_option` **(selection)** — Comment Options
  > Opções: `reply_all` (Reply-All), `forward` (Forward)
- `is_note` **(boolean)** — Is a note
  > If the message will be posted as a Note.
- `notification_parameters` **(text)** — Notification parameters
- `send_context` **(json)** — Sending Context
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `account_reports_annotation_date` **(date)** — Annotated For

## Relacionamentos

- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`
- `partner_ids` **(many2many)** — Recipients → `res.partner`
