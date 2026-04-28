# Budget Line — `budget.line`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `budget_analytic_id` **(many2one)** — Budget Analytic ⚠️ obrigatório → `budget.analytic`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `date_from` **(date)** — Start Date 🔒 readonly
- `date_to` **(date)** — End Date 🔒 readonly
- `budget_amount` **(monetary)** — Budgeted
- `budget_analytic_state` **(selection)** — Budget State 🔒 readonly
  > Opções: `draft` (Draft), `confirmed` (Open), `revised` (Revised), `done` (Done), `canceled` (Canceled)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_id` **(many2one)** — Project → `account.analytic.account`
- `auto_account_id` **(many2one)** — Analytic Account → `account.analytic.account`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `name` **(char)** — Budget Name 🔒 readonly
- `achieved_amount` **(monetary)** — Achieved 🔒 readonly
  > Amount Billed/Invoiced.
- `achieved_percentage` **(float)** — Achieved (%) 🔒 readonly
- `theoritical_amount` **(monetary)** — Theoretical 🔒 readonly
  > Amount supposed to be Billed/Invoiced, formula = (Budget Amount / Budget Days) x Budget Days Completed
- `theoritical_percentage` **(float)** — Theoretical (%) 🔒 readonly
- `is_above_budget` **(boolean)** — Is Above Budget 🔒 readonly
- `committed_amount` **(monetary)** — Committed 🔒 readonly
  > Already Billed amount + Confirmed purchase orders.
- `committed_percentage` **(float)** — Committed (%) 🔒 readonly
