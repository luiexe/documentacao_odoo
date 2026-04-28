# Employee Delete Wizard — `hr.employee.delete.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_ids` **(many2many)** — Employees → `hr.employee`

## Campos Calculados (readonly)

- `has_active_employee` **(boolean)** — Has Active Employee 🔒 readonly
- `has_timesheet` **(boolean)** — Has Timesheet 🔒 readonly
