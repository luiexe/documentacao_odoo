# Project Sales line, employee mapping — `project.sale.line.employee.map`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `project_id` **(many2one)** — Project ⚠️ obrigatório → `project.project`
- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `price_unit` **(float)** — Unit Price 🔒 readonly
- `cost` **(monetary)** — Cost
  > This cost overrides the employee's default employee hourly wage in employee's HR Settings
- `display_cost` **(monetary)** — Hourly Cost
- `is_cost_changed` **(boolean)** — Is Cost Manually Changed 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `existing_employee_ids` **(many2many)** — Existing Employee 🔒 readonly → `hr.employee`
- `sale_line_id` **(many2one)** — Sales Order Item → `sale.order.line`
- `sale_order_id` **(many2one)** — Order Reference 🔒 readonly → `sale.order`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `currency_id` **(many2one)** — Currency → `res.currency`
- `cost_currency_id` **(many2one)** — Cost Currency 🔒 readonly → `res.currency`
