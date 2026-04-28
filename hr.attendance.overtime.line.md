# Attendance Overtime Line — `hr.attendance.overtime.line`

**Ordenação padrão:** `time_start`

---

## Campos Obrigatórios

- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`
- `date` **(date)** — Day ⚠️ obrigatório
- `status` **(selection)** — Status ⚠️ obrigatório
  > Opções: `to_approve` (To Approve), `approved` (Approved), `refused` (Refused)
- `duration` **(float)** — Extra Hours ⚠️ obrigatório
- `amount_rate` **(float)** — Overtime pay rate ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `manual_duration` **(float)** — Extra Hours (encoded)
- `time_start` **(datetime)** — Start
- `time_stop` **(datetime)** — Stop
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `rule_ids` **(many2many)** — Applied Rules → `hr.attendance.overtime.rule`

## Campos Calculados (readonly)

- `is_manager` **(boolean)** — Is Manager 🔒 readonly
