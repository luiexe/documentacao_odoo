# Channel Invitation Wizard — `slide.channel.invite`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `channel_id` **(many2one)** — Course ⚠️ obrigatório → `slide.channel`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `subject` **(char)** — Subject
- `body` **(html)** — Contents
- `send_email` **(boolean)** — Send Email
- `enroll_mode` **(boolean)** — Enroll partners 🔒 readonly
  > Whether invited partners will be added as enrolled. Otherwise, they will be added as invited.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Mail Template → `mail.template`
- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`
- `partner_ids` **(many2many)** — Recipients → `res.partner`

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
- `body_has_template_value` **(boolean)** — Body content is the same as the template 🔒 readonly
- `is_mail_template_editor` **(boolean)** — Is Editor 🔒 readonly
- `can_edit_body` **(boolean)** — Can Edit Body 🔒 readonly
- `channel_invite_url` **(char)** — Course Link 🔒 readonly
- `channel_visibility` **(selection)** — Show Course To 🔒 readonly
  > Defines who can access your courses and their content.
  > Opções: `public` (Everyone), `connected` (Signed In), `members` (Course Attendees), `link` (Anyone with the link)
- `channel_published` **(boolean)** — Is Published 🔒 readonly
