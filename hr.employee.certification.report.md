# Employee Certification Report — `hr.employee.certification.report`

**Ordenação padrão:** `employee_id, level_progress desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `skill_level` **(char)** — Skill Level 🔒 readonly
- `level_progress` **(float)** — Level Progress 🔒 readonly
- `active` **(boolean)** — Active

## Relacionamentos

- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `skill_id` **(many2one)** — Skill 🔒 readonly → `hr.skill`
- `skill_type_id` **(many2one)** — Skill Type 🔒 readonly → `hr.skill.type`

## Campos Calculados (readonly)

- `has_department_manager_access` **(boolean)** — Has Department Manager Access 🔒 readonly
