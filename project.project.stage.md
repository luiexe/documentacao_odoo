# Project Stage — `project.project.stage`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `fold` **(boolean)** — Folded
  > If enabled, this stage will be displayed as folded in the Kanban and List views of your projects. Projects in a folded stage are considered as closed.
- `color` **(integer)** — Color
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `mail_template_id` **(many2one)** — Email Template → `mail.template`
  > If set, an email will be automatically sent to the customer when the project reaches this stage.
- `company_id` **(many2one)** — Company → `res.company`
- `sms_template_id` **(many2one)** — SMS Template → `sms.template`
  > If set, an SMS Text Message will be automatically sent to the customer when the project reaches this stage.
