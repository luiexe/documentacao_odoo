# Skills for job positions — `hr.job.skill`

**Ordenação padrão:** `skill_type_id, skill_level_id desc`

---

## Campos Obrigatórios

- `skill_id` **(many2one)** — Skill ⚠️ obrigatório → `hr.skill`
- `skill_level_id` **(many2one)** — Skill Level ⚠️ obrigatório → `hr.skill.level`
- `skill_type_id` **(many2one)** — Skill Type ⚠️ obrigatório → `hr.skill.type`
- `job_id` **(many2one)** — Job ⚠️ obrigatório → `hr.job`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `valid_from` **(date)** — Validity Start
- `valid_to` **(date)** — Validity Stop
- `display_warning_message` **(boolean)** — Display Warning Message
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `level_progress` **(integer)** — Progress 🔒 readonly
  > Progress from zero knowledge (0%) to fully mastered (100%).
- `color` **(integer)** — Color 🔒 readonly
- `levels_count` **(integer)** — Levels Count 🔒 readonly
  > Number of levels linked to this skill type
- `certification_skill_type_count` **(integer)** — Certification Skill Type Count 🔒 readonly
- `is_certification` **(boolean)** — Certification 🔒 readonly
  > if checked the skill type become a certification type
