# Planning / Attendance Analysis — `planning.attendance.analysis.report`

**Ordenação padrão:** `entry_date desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `entry_date` **(date)** — Entry Date 🔒 readonly
- `effective_hours` **(float)** — Attendance Time 🔒 readonly
- `planned_hours` **(float)** — Planned Time 🔒 readonly
- `time_difference` **(float)** — Time Difference 🔒 readonly
- `effective_costs` **(float)** — Attendance Cost 🔒 readonly
- `planned_costs` **(float)** — Planned Cost 🔒 readonly
- `cost_difference` **(float)** — Cost Difference 🔒 readonly

## Relacionamentos

- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
