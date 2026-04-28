# Skill — `hr.skill`

**Ordenação padrão:** `sequence, name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `skill_type_id` **(many2one)** — Skill Type ⚠️ obrigatório → `hr.skill.type`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `color` **(integer)** — Color 🔒 readonly
