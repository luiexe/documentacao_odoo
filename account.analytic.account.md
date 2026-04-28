# Analytic Account — `account.analytic.account`

**Ordenação padrão:** `plan_id, name asc`

---

## Campos Obrigatórios

- `name` **(char)** — Analytic Account ⚠️ obrigatório
- `plan_id` **(many2one)** — Plan ⚠️ obrigatório → `account.analytic.plan`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `code` **(char)** — Reference
- `active` **(boolean)** — Active
  > Deactivate the account.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `root_plan_id` **(many2one)** — Root Plan 🔒 readonly → `account.analytic.plan`
- `line_ids` **(one2many)** — Analytic Lines → `account.analytic.line`
- `company_id` **(many2one)** — Company → `res.company`
- `partner_id` **(many2one)** — Customer → `res.partner`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `project_ids` **(one2many)** — Projects → `project.project`
- `production_ids` **(many2many)** — Production → `mrp.production`
- `bom_ids` **(many2many)** — Bom → `mrp.bom`
- `workcenter_ids` **(many2many)** — Workcenter → `mrp.workcenter`
- `budget_line_ids` **(one2many)** — Budget Line → `budget.line`

## Campos Calculados (readonly)

- `color` **(integer)** — Color Index 🔒 readonly
- `balance` **(monetary)** — Balance 🔒 readonly
- `debit` **(monetary)** — Debit 🔒 readonly
- `credit` **(monetary)** — Credit 🔒 readonly
- `invoice_count` **(integer)** — Invoice Count 🔒 readonly
- `vendor_bill_count` **(integer)** — Vendor Bill Count 🔒 readonly
- `project_count` **(integer)** — Project Count 🔒 readonly
- `purchase_order_count` **(integer)** — Purchase Order Count 🔒 readonly
- `production_count` **(integer)** — Manufacturing Orders Count 🔒 readonly
- `bom_count` **(integer)** — BoM Count 🔒 readonly
- `workorder_count` **(integer)** — Work Order Count 🔒 readonly
