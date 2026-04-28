# Workcenter Productivity Log — `mrp.workcenter.productivity`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `workcenter_id` **(many2one)** — Work Center ⚠️ obrigatório → `mrp.workcenter`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `loss_id` **(many2one)** — Loss Reason ⚠️ obrigatório → `mrp.workcenter.productivity.loss`
- `date_start` **(datetime)** — Start Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `loss_type` **(selection)** — Effectiveness
  > Opções: `availability` (Availability), `performance` (Performance), `quality` (Quality), `productive` (Productive)
- `description` **(text)** — Description
- `date_end` **(datetime)** — End Date
- `duration` **(float)** — Duration 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `employee_cost` **(monetary)** — employee_cost 🔒 readonly

## Relacionamentos

- `production_id` **(many2one)** — Manufacturing Order 🔒 readonly → `mrp.production`
- `workorder_id` **(many2one)** — Work Order → `mrp.workorder`
- `user_id` **(many2one)** — User → `res.users`
- `account_move_line_id` **(many2one)** — Account Move Line → `account.move.line`
- `employee_id` **(many2one)** — Employee → `hr.employee`
  > employee that record this working time
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `total_cost` **(float)** — Cost 🔒 readonly
