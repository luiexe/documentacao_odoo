# Burndown Chart — `project.task.burndown.chart.report`

**Ordenação padrão:** `date`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `allocated_hours` **(float)** — Allocated Time 🔒 readonly
- `date` **(datetime)** — Date 🔒 readonly
- `date_assign` **(datetime)** — Assignment Date 🔒 readonly
- `date_deadline` **(date)** — Deadline 🔒 readonly
- `date_last_stage_update` **(date)** — Last Stage Update 🔒 readonly
- `state` **(selection)** — State 🔒 readonly
  > Opções: `01_in_progress` (In Progress), `1_done` (Done), `04_waiting_normal` (Waiting), `03_approved` (Approved), `1_canceled` (Cancelled), `02_changes_requested` (Changes Requested)
- `is_closed` **(selection)** — Closing Stage 🔒 readonly
  > Opções: `closed` (Closed tasks), `open` (Open tasks)

## Relacionamentos

- `milestone_id` **(many2one)** — Milestone 🔒 readonly → `project.milestone`
- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `project_id` **(many2one)** — Project 🔒 readonly → `project.project`
- `stage_id` **(many2one)** — Stage 🔒 readonly → `project.task.type`
- `tag_ids` **(many2many)** — Tags 🔒 readonly → `project.tags`
- `user_ids` **(many2many)** — Assignees 🔒 readonly → `res.users`
