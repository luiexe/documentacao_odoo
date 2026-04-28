# Timesheet Attendance Report — `hr.timesheet.attendance.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Date 🔒 readonly
- `total_timesheet` **(float)** — Timesheets Time 🔒 readonly
- `total_attendance` **(float)** — Attendance Time 🔒 readonly
- `total_difference` **(float)** — Time Difference 🔒 readonly
- `timesheets_cost` **(float)** — Timesheet Cost 🔒 readonly
- `attendance_cost` **(float)** — Attendance Cost 🔒 readonly
- `cost_difference` **(float)** — Cost Difference 🔒 readonly

## Relacionamentos

- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
