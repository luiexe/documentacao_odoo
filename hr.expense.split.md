# Expense Split — `hr.expense.split`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Description ⚠️ obrigatório
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `total_amount_currency` **(monetary)** — Total In Currency ⚠️ obrigatório
- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `product_has_cost` **(boolean)** — Is product with non zero cost selected 🔒 readonly
- `approval_state` **(selection)** — Approval State 🔒 readonly
  > Opções: `submitted` (Submitted), `approved` (Approved), `refused` (Refused)
- `approval_date` **(datetime)** — Approval Date 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
- `wizard_id` **(many2one)** — Wizard → `hr.expense.split.wizard`
- `expense_id` **(many2one)** — Expense → `hr.expense`
- `tax_ids` **(many2many)** — Tax → `account.tax`
- `company_id` **(many2one)** — Company → `res.company`
- `currency_id` **(many2one)** — Currency → `res.currency`
- `manager_id` **(many2one)** — Manager 🔒 readonly → `res.users`
- `sale_order_id` **(many2one)** — Customer to Reinvoice → `sale.order`

## Campos Calculados (readonly)

- `tax_amount_currency` **(monetary)** — Tax amount in Currency 🔒 readonly
- `product_has_tax` **(boolean)** — Whether tax is defined on a selected product 🔒 readonly
- `can_be_reinvoiced` **(boolean)** — Can be reinvoiced 🔒 readonly
