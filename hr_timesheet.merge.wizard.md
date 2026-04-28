# Merge Timesheets — `hr_timesheet.merge.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Description
- `date` **(date)** — Date
- `unit_amount` **(float)** — Quantity
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `timesheet_ids` **(many2many)** — Timesheets → `account.analytic.line`
- `encoding_uom_id` **(many2one)** — Encoding Uom 🔒 readonly → `uom.uom`
- `project_id` **(many2one)** — Project → `project.project`
- `task_id` **(many2one)** — Task → `project.task`
- `employee_id` **(many2one)** — Employee → `hr.employee`
