# Send Planning — `planning.send`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `start_datetime` **(datetime)** — Period ⚠️ obrigatório
- `end_datetime` **(datetime)** — Stop Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `include_unassigned` **(boolean)** — Include Open Shifts
- `note` **(text)** — Extra Message
  > Additional message displayed in the email sent to employees
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_ids` **(many2many)** — Employees → `hr.employee`
- `slot_ids` **(many2many)** — Slot 🔒 readonly → `planning.slot`
- `employees_no_email` **(many2many)** — Employees without email → `hr.employee`
