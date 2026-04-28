# Appraisal Skills Report — `hr.appraisal.skill.report`

**Ordenação padrão:** `employee_id, evolution_sequence asc, current_level_progress desc, skill_type_id asc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(date)** — Create Date 🔒 readonly
- `previous_level_progress` **(float)** — Previous Progress 🔒 readonly
- `current_level_progress` **(float)** — Current Progress 🔒 readonly
- `justification` **(char)** — Justification 🔒 readonly
- `evolution_sequence` **(integer)** — Evolution Sequence
- `evolution` **(selection)** — Evolution
  > Opções: `improvement` (Improvement), `same` (Same), `just_added` (Just added), `decline` (Decline)
- `progress_evolution` **(float)** — Progress Evolution 🔒 readonly

## Relacionamentos

- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `skill_id` **(many2one)** — Skill 🔒 readonly → `hr.skill`
- `skill_type_id` **(many2one)** — Skill Type 🔒 readonly → `hr.skill.type`
- `previous_skill_level_id` **(many2one)** — Previous Level 🔒 readonly → `hr.skill.level`
- `current_skill_level_id` **(many2one)** — Current Level 🔒 readonly → `hr.skill.level`
