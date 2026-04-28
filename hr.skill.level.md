# Skill Level — `hr.skill.level`

**Ordenação padrão:** `level_progress`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `level_progress` **(integer)** — Progress
  > Progress from zero knowledge (0%) to fully mastered (100%).
- `default_level` **(boolean)** — Default Level
  > If checked, this level will be the default one selected when choosing this skill.
- `technical_is_new_default` **(boolean)** — Technical Is New Default
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `skill_type_id` **(many2one)** — Skill Type → `hr.skill.type`
