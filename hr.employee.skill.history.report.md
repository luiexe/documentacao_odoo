# Employee Skills Report — `hr.employee.skill.history.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Date
- `level_progress` **(float)** — Level Progress 🔒 readonly

## Relacionamentos

- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `skill_id` **(many2one)** — Skill 🔒 readonly → `hr.skill`
- `skill_type_id` **(many2one)** — Skill Type 🔒 readonly → `hr.skill.type`
