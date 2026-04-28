# Confirm timesheet creation when stop timer — `hr.timesheet.stop.timer.confirmation.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `timesheet_name` **(char)** — Name
- `time_spent` **(float)** — Time Spent
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `timesheet_id` **(many2one)** — Timesheet → `account.analytic.line`
