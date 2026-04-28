# Budget Report — `budget.report`

**Ordenação padrão:** `false`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Date
- `res_model` **(char)** — Model 🔒 readonly
- `res_id` **(many2one_reference)** — Document 🔒 readonly
- `description` **(char)** — Description 🔒 readonly
- `line_type` **(selection)** — Type 🔒 readonly
  > Opções: `budget` (Budget), `achieved` (Achieved), `committed` (Committed)
- `budget` **(float)** — Budget 🔒 readonly
- `achieved` **(float)** — Achieved 🔒 readonly
- `theoretical` **(float)** — Theoretical 🔒 readonly
- `committed` **(float)** — Committed 🔒 readonly

## Relacionamentos

- `account_id` **(many2one)** — Project → `account.analytic.account`
- `auto_account_id` **(many2one)** — Analytic Account → `account.analytic.account`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `user_id` **(many2one)** — User 🔒 readonly → `res.users`
- `budget_analytic_id` **(many2one)** — Budget Analytic 🔒 readonly → `budget.analytic`
- `budget_line_id` **(many2one)** — Budget Line 🔒 readonly → `budget.line`
