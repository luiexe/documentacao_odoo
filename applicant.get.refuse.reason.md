# Get Refuse Reason — `applicant.get.refuse.reason`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `refuse_reason_id` **(many2one)** — Refuse Reason ⚠️ obrigatório → `hr.applicant.refuse.reason`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `subject` **(char)** — Subject
- `body` **(html)** — Contents
- `send_mail` **(boolean)** — Send Email
- `duplicates` **(boolean)** — Refuse Duplicate Applications
- `scheduled_date` **(char)** — Scheduled Date
  > send emails after that date. This date is considered as being in UTC timezone.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Email Template → `mail.template`
- `applicant_ids` **(many2many)** — Applicant → `hr.applicant`
- `duplicate_applicant_ids` **(many2many)** — Duplicate Applications → `hr.applicant`
- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
- `body_has_template_value` **(boolean)** — Body content is the same as the template 🔒 readonly
- `is_mail_template_editor` **(boolean)** — Is Editor 🔒 readonly
- `can_edit_body` **(boolean)** — Can Edit Body 🔒 readonly
- `applicant_without_email` **(text)** — Applicant(s) not having email 🔒 readonly
- `duplicates_count` **(integer)** — Duplicates Count 🔒 readonly
- `duplicate_applicant_ids_domain` **(binary)** — Duplicate Applicant Ids Domain 🔒 readonly
