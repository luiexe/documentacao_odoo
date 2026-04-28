# Appraisal Skills — `hr.appraisal.skill`

**Ordenação padrão:** `skill_type_id, skill_level_id`

---

## Campos Obrigatórios

- `skill_id` **(many2one)** — Skill ⚠️ obrigatório → `hr.skill`
- `skill_type_id` **(many2one)** — Skill Type ⚠️ obrigatório → `hr.skill.type`
- `appraisal_id` **(many2one)** — Appraisal ⚠️ obrigatório → `hr.appraisal`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `valid_from` **(date)** — Validity Start
- `valid_to` **(date)** — Validity Stop
- `display_warning_message` **(boolean)** — Display Warning Message
- `justification` **(char)** — Justification
- `goals_completion_percentage` **(integer)** — Current Goals 🔒 readonly
- `target_job_skill_progress` **(float)** — Job Target 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `skill_level_id` **(many2one)** — Skill Level → `hr.skill.level`
- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `previous_skill_level_id` **(many2one)** — Previous Skill Level → `hr.skill.level`
- `manager_ids` **(many2many)** — Manager 🔒 readonly → `hr.employee`
- `goal_ids` **(many2many)** — Goal 🔒 readonly → `hr.appraisal.goal`

## Campos Calculados (readonly)

- `level_progress` **(integer)** — Progress 🔒 readonly
  > Progress from zero knowledge (0%) to fully mastered (100%).
- `color` **(integer)** — Color 🔒 readonly
- `levels_count` **(integer)** — Levels Count 🔒 readonly
  > Number of levels linked to this skill type
- `certification_skill_type_count` **(integer)** — Certification Skill Type Count 🔒 readonly
- `is_certification` **(boolean)** — Certification 🔒 readonly
  > if checked the skill type become a certification type
- `number_of_recommended_goals` **(integer)** — Number Of Recommended Goals 🔒 readonly
