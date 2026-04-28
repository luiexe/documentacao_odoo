# Ask Feedback for Appraisal — `appraisal.ask.feedback`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `author_id` **(many2one)** — Author ⚠️ obrigatório → `res.partner`
- `survey_template_id` **(many2one)** — Survey Template ⚠️ obrigatório → `survey.survey`
- `employee_ids` **(many2many)** — Recipients ⚠️ obrigatório → `hr.employee`
- `deadline` **(date)** — Answer Deadline ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `subject` **(char)** — Subject
- `body` **(html)** — Contents
- `user_body` **(html)** — User Contents
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Mail Template → `mail.template`
- `appraisal_id` **(many2one)** — Appraisal → `hr.appraisal`
- `employee_id` **(many2one)** — Appraisal Employee 🔒 readonly → `hr.employee`
- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`
- `allowed_survey_template_ids` **(many2many)** — Allowed Survey Template 🔒 readonly → `survey.survey`

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
- `body_has_template_value` **(boolean)** — Body content is the same as the template 🔒 readonly
- `is_mail_template_editor` **(boolean)** — Is Editor 🔒 readonly
- `can_edit_body` **(boolean)** — Can Edit Body 🔒 readonly
