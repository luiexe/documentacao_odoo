# Account Report Send — `account.report.send`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `mode` **(selection)** — Mode
  > Opções: `single` (Single Recipient), `multi` (Multiple Recipients)
- `enable_download` **(boolean)** — Enable Download
- `checkbox_download` **(boolean)** — Download
- `enable_send_mail` **(boolean)** — Enable Send Mail
- `checkbox_send_mail` **(boolean)** — Email
- `report_options` **(json)** — Report Options
- `mail_subject` **(char)** — Subject
- `mail_body` **(html)** — Contents
- `mail_attachments_widget` **(json)** — Mail Attachments Widget
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_ids` **(many2many)** — Partner 🔒 readonly → `res.partner`
- `mail_template_id` **(many2one)** — Email template → `mail.template`
- `account_report_id` **(many2one)** — Report → `account.report`
- `mail_partner_ids` **(many2many)** — Recipients → `res.partner`

## Campos Calculados (readonly)

- `display_mail_composer` **(boolean)** — Display Mail Composer 🔒 readonly
- `warnings` **(json)** — Warnings 🔒 readonly
- `send_mail_readonly` **(boolean)** — Send Mail Readonly 🔒 readonly
- `mail_lang` **(char)** — Lang 🔒 readonly
