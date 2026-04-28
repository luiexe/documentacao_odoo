# Project Template create Wizard — `project.template.create.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date_start` **(date)** — Start Date
- `date` **(date)** — Expiration Date
- `alias_name` **(char)** — Alias Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `template_id` **(many2one)** — Template → `project.project`
- `role_to_users_ids` **(one2many)** — Role To Users → `project.template.role.to.users.map`
- `partner_id` **(many2one)** — Partner → `res.partner`

## Campos Calculados (readonly)

- `template_has_dates` **(boolean)** — Template Has Dates 🔒 readonly
- `allow_billable` **(boolean)** — Billable 🔒 readonly
