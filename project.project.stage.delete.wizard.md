# Project Stage Delete Wizard — `project.project.stage.delete.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `stage_ids` **(many2many)** — Stages To Delete → `project.project.stage`

## Campos Calculados (readonly)

- `projects_count` **(integer)** — Number of Projects 🔒 readonly
- `stages_active` **(boolean)** — Stages Active 🔒 readonly
