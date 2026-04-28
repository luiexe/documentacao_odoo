# Email Templates — `mail.template`

**Ordenação padrão:** `user_id, name, id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `template_fs` **(char)** — Template Filename
  > File from where the template originates. Used to reset broken template.
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `name` **(char)** — Name
- `description` **(text)** — Template Description
  > This field is used for internal description of the template's usage.
- `active` **(boolean)** — Active
- `model` **(char)** — Related Document Model 🔒 readonly
- `subject` **(char)** — Subject
  > Subject (placeholders may be used here)
- `email_from` **(char)** — Send From
  > Sender address (placeholders may be used here). If not set, the default value will be the author's email alias if configured, or email address.
- `use_default_to` **(boolean)** — Default Recipients
  > Default recipients of the record: - partner (using id on a partner or the partner_id field) OR - email (using email_from or email field)
- `email_to` **(char)** — To (Emails)
  > Comma-separated recipient addresses (placeholders may be used here)
- `partner_to` **(char)** — To (Partners)
  > Comma-separated ids of recipient partners (placeholders may be used here)
- `email_cc` **(char)** — Cc
  > Carbon copy recipients (placeholders may be used here)
- `reply_to` **(char)** — Reply To
  > Email address to which replies will be redirected when sending emails in mass; only used when the reply is not logged in the original discussion thread.
- `body_html` **(html)** — Body
- `email_layout_xmlid` **(char)** — Email Notification Layout
- `scheduled_date` **(char)** — Scheduled Date
  > If set, the queue manager will send the email after the date. If not set, the email will be send as soon as possible. You can use dynamic expression.
- `auto_delete` **(boolean)** — Auto Delete
  > This option permanently removes any track of email after it's been sent, including from the Technical menu in the Settings, in order to preserve storage space of your Odoo database.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `model_id` **(many2one)** — Applies to → `ir.model`
- `user_id` **(many2one)** — Owner → `res.users`
- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`
- `report_template_ids` **(many2many)** — Dynamic Reports → `ir.actions.report`
- `mail_server_id` **(many2one)** — Outgoing Mail Server → `ir.mail_server`
  > Optional preferred server for outgoing mails. If not set, the highest priority one will be used.
- `ref_ir_act_window` **(many2one)** — Sidebar action 🔒 readonly → `ir.actions.act_window`
  > Sidebar action to make this template available on records of the related document model

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
- `template_category` **(selection)** — Template Category 🔒 readonly
  > Opções: `base_template` (Base Template), `hidden_template` (Hidden Template), `custom_template` (Custom Template)
- `can_write` **(boolean)** — Can Write 🔒 readonly
  > The current user can edit the template.
- `is_template_editor` **(boolean)** — Is Template Editor 🔒 readonly
- `has_dynamic_reports` **(boolean)** — Has Dynamic Reports 🔒 readonly
- `has_mail_server` **(boolean)** — Has Mail Server 🔒 readonly
