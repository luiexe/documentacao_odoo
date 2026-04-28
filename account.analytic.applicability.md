# Analytic Plan's Applicabilities — `account.analytic.applicability`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `business_domain` **(selection)** — Domain ⚠️ obrigatório
  > Opções: `general` (Miscellaneous), `invoice` (Invoice), `bill` (Vendor Bill), `expense` (Expense), `purchase_order` (Purchase Order), `timesheet` (Timesheet), `manufacturing_order` (Manufacturing Order), `stock_picking` (Stock Picking), `sale_order` (Sale Order)
- `applicability` **(selection)** — Applicability ⚠️ obrigatório
  > Opções: `optional` (Optional), `mandatory` (Mandatory), `unavailable` (Unavailable)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `account_prefix` **(char)** — Financial Accounts Prefixes
  > Prefix that defines which accounts from the financial accounting this applicability should apply on.

## Relacionamentos

- `analytic_plan_id` **(many2one)** — Analytic Plan → `account.analytic.plan`
- `company_id` **(many2one)** — Company → `res.company`
- `product_categ_id` **(many2one)** — Product Category → `product.category`

## Campos Calculados (readonly)

- `display_account_prefix` **(boolean)** — Display Account Prefix 🔒 readonly
  > Defines if the field account prefix should be displayed
- `account_prefix_placeholder` **(char)** — Account Prefix Placeholder 🔒 readonly
