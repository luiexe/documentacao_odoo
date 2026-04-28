# Sign document in recruitment — `hr.recruitment.sign.document.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `applicant_role_id` **(many2one)** — Applicant Role ⚠️ obrigatório → `sign.item.role`
  > Applicant's role on the templates to sign. The same role must be present in all the templates
- `sign_template_ids` **(many2many)** — Documents to sign ⚠️ obrigatório → `sign.template`
  > Documents to sign. Only documents with 1 or 2 different responsible are selectable.         Documents with 1 responsible will only have to be signed by the applicant while documents with 2 different responsible will have to be signed by both the applicant and the responsible.         
- `subject` **(char)** — Subject ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `template_warning` **(char)** — Template Warning
- `message` **(html)** — Message
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `applicant_ids` **(many2many)** — Applicants → `hr.applicant`
- `responsible_id` **(many2one)** — Responsible → `res.users`
- `sign_template_responsible_ids` **(many2many)** — Sign Template Responsible 🔒 readonly → `sign.item.role`
- `possible_template_ids` **(many2many)** — Possible Template 🔒 readonly → `sign.template`
- `cc_partner_ids` **(many2many)** — Copy to → `res.partner`
- `attachment_ids` **(many2many)** — Attachment → `ir.attachment`

## Campos Calculados (readonly)

- `has_both_template` **(boolean)** — Has Both Template 🔒 readonly
