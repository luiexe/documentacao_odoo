# Sign document in contract — `hr.contract.sign.document.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `employee_role_id` **(many2one)** — Employee Role ⚠️ obrigatório → `sign.item.role`
  > Employee's role on the templates to sign. The same role must be present in all the templates
- `sign_template_ids` **(many2many)** — Documents to sign ⚠️ obrigatório → `sign.template`
  > Select only documents with either 1 or 2 different signatories.         Documents with 1 signatory require only the employee's signature, while those with 2 signatories require signatures from both the employee and the HR responsible.         
- `subject` **(char)** — Subject ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `template_warning` **(char)** — Template Warning
- `message` **(html)** — Message
- `mail_to` **(selection)** — Email
  > Email used to send the signature request.                 - Work takes the email defined in "work email"                 - Private takes the email defined in Private Information                 - If the selected email is not defined, the available one will be used.
  > Opções: `work` (Work), `private` (Private)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `version_id` **(many2one)** — Contract → `hr.version`
- `employee_ids` **(many2many)** — Employees → `hr.employee`
- `responsible_id` **(many2one)** — Responsible → `res.users`
- `sign_template_responsible_ids` **(many2many)** — Sign Template Responsible 🔒 readonly → `sign.item.role`
- `possible_template_ids` **(many2many)** — Possible Template 🔒 readonly → `sign.template`
- `cc_partner_ids` **(many2many)** — Copy to → `res.partner`
- `attachment_ids` **(many2many)** — Attachment → `ir.attachment`

## Campos Calculados (readonly)

- `has_both_template` **(boolean)** — Has Both Template 🔒 readonly
- `mail_displayed` **(char)** — Mail Displayed 🔒 readonly
