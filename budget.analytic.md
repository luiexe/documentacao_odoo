# Budget — `budget.analytic`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Budget Name ⚠️ obrigatório
- `date_from` **(date)** — Start Date ⚠️ obrigatório
- `date_to` **(date)** — End Date ⚠️ obrigatório
- `state` **(selection)** — Status ⚠️ obrigatório 🔒 readonly
  > Opções: `draft` (Draft), `confirmed` (Open), `revised` (Revised), `done` (Done), `canceled` (Canceled)
- `budget_type` **(selection)** — Budget Type ⚠️ obrigatório
  > Opções: `revenue` (Revenue), `expense` (Expense), `both` (Both)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_id` **(many2one)** — Revision Of → `budget.analytic`
- `children_ids` **(one2many)** — Revisions → `budget.analytic`
- `user_id` **(many2one)** — Responsible → `res.users`
- `budget_line_ids` **(one2many)** — Budget Lines → `budget.line`
- `company_id` **(many2one)** — Company → `res.company`
