# Survey Invitation Wizard — `survey.invite`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `existing_mode` **(selection)** — Handle existing ⚠️ obrigatório
  > Opções: `new` (New invite), `resend` (Resend invite)
- `survey_id` **(many2one)** — Survey ⚠️ obrigatório → `survey.survey`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `subject` **(char)** — Subject
- `body` **(html)** — Contents
- `emails` **(text)** — Additional emails
- `deadline` **(datetime)** — Answer deadline
- `send_email` **(boolean)** — Send Email
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Mail Template → `mail.template`
- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`
- `author_id` **(many2one)** — Author → `res.partner`
- `partner_ids` **(many2many)** — Recipients → `res.partner`
- `existing_partner_ids` **(many2many)** — Existing Partner 🔒 readonly → `res.partner`
- `mail_server_id` **(many2one)** — Outgoing mail server → `ir.mail_server`

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
- `body_has_template_value` **(boolean)** — Body content is the same as the template 🔒 readonly
- `is_mail_template_editor` **(boolean)** — Is Editor 🔒 readonly
- `can_edit_body` **(boolean)** — Can Edit Body 🔒 readonly
- `existing_emails` **(text)** — Existing emails 🔒 readonly
- `existing_text` **(text)** — Resend Comment 🔒 readonly
- `survey_start_url` **(char)** — Survey URL 🔒 readonly
- `survey_access_mode` **(selection)** — Access Mode 🔒 readonly
  > Opções: `public` (Anyone with the link), `token` (Invited people only)
- `survey_users_login_required` **(boolean)** — Require Login 🔒 readonly
  > If checked, users have to login before answering even with a valid token.
- `survey_users_can_signup` **(boolean)** — Users can signup 🔒 readonly
