# Task Recurrence — `project.task.recurrence`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `repeat_interval` **(integer)** — Repeat Every
- `repeat_unit` **(selection)** — Repeat Unit
  > Opções: `day` (Days), `week` (Weeks), `month` (Months), `year` (Years)
- `repeat_type` **(selection)** — Until
  > Opções: `forever` (Forever), `until` (Until)
- `repeat_until` **(date)** — End Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `task_ids` **(one2many)** — Task → `project.task`
