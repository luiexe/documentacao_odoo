# Project Task Stage Delete Wizard — `project.task.type.delete.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `project_ids` **(many2many)** — Projects → `project.project`
- `stage_ids` **(many2many)** — Stages To Delete → `project.task.type`

## Campos Calculados (readonly)

- `tasks_count` **(integer)** — Number of Tasks 🔒 readonly
- `stages_active` **(boolean)** — Stages Active 🔒 readonly
