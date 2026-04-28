# Skill Type — `hr.skill.type`

**Ordenação padrão:** `sequence, name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `color` **(integer)** — Color
- `levels_count` **(integer)** — Levels Count
  > Number of levels linked to this skill type
- `is_certification` **(boolean)** — Certification
  > if checked the skill type become a certification type
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `skill_ids` **(one2many)** — Skills → `hr.skill`
- `skill_level_ids` **(one2many)** — Levels → `hr.skill.level`
