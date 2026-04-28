# Project Tags — `project.tags`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(integer)** — Color
  > Transparent tags are not visible in the kanban view of your projects and tasks.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `project_ids` **(many2many)** — Projects → `project.project`
- `task_ids` **(many2many)** — Tasks → `project.task`
