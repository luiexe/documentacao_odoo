# Skill level — `hr.individual.skill.mixin`

**Ordenação padrão:** `skill_type_id, skill_level_id`

---

## Campos Obrigatórios

- `skill_id` **(many2one)** — Skill ⚠️ obrigatório → `hr.skill`
- `skill_level_id` **(many2one)** — Skill Level ⚠️ obrigatório → `hr.skill.level`
- `skill_type_id` **(many2one)** — Skill Type ⚠️ obrigatório → `hr.skill.type`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `valid_from` **(date)** — Validity Start
- `valid_to` **(date)** — Validity Stop
- `display_warning_message` **(boolean)** — Display Warning Message

## Campos Calculados (readonly)

- `level_progress` **(integer)** — Progress 🔒 readonly
  > Progress from zero knowledge (0%) to fully mastered (100%).
- `color` **(integer)** — Color 🔒 readonly
- `levels_count` **(integer)** — Levels Count 🔒 readonly
  > Number of levels linked to this skill type
- `certification_skill_type_count` **(integer)** — Certification Skill Type Count 🔒 readonly
- `is_certification` **(boolean)** — Certification 🔒 readonly
  > if checked the skill type become a certification type
