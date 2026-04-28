# Project Update — `project.update`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Title ⚠️ obrigatório
- `status` **(selection)** — Status ⚠️ obrigatório
  > Opções: `on_track` (On Track), `at_risk` (At Risk), `off_track` (Off Track), `on_hold` (On Hold), `done` (Complete)
- `user_id` **(many2one)** — Author ⚠️ obrigatório → `res.users`
- `project_id` **(many2one)** — Project ⚠️ obrigatório → `project.project`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `email_cc` **(char)** — Email cc
- `progress` **(integer)** — Progress
- `description` **(html)** — Description
- `date` **(date)** — Date
- `task_count` **(integer)** — Task Count 🔒 readonly
- `closed_task_count` **(integer)** — Closed Task Count 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `allocated_time` **(integer)** — Allocated Time 🔒 readonly
- `timesheet_time` **(integer)** — Timesheet Time 🔒 readonly

## Relacionamentos

- `uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`

## Campos Calculados (readonly)

- `color` **(integer)** — Color 🔒 readonly
- `progress_percentage` **(float)** — Progress Percentage 🔒 readonly
- `name_cropped` **(char)** — Name Cropped 🔒 readonly
- `closed_task_percentage` **(integer)** — Closed Task Percentage 🔒 readonly
- `label_tasks` **(char)** — Use Tasks as 🔒 readonly
  > Name used to refer to the tasks of your project e.g. tasks, tickets, sprints, etc...
- `display_timesheet_stats` **(boolean)** — Display Timesheet Stats 🔒 readonly
- `timesheet_percentage` **(integer)** — Timesheet Percentage 🔒 readonly
