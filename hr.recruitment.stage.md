# Recruitment Stages — `hr.recruitment.stage`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Stage Name ⚠️ obrigatório
- `legend_blocked` **(char)** — Red Kanban Label ⚠️ obrigatório
- `legend_waiting` **(char)** — Orange Kanban Label ⚠️ obrigatório
- `legend_done` **(char)** — Green Kanban Label ⚠️ obrigatório
- `legend_normal` **(char)** — Grey Kanban Label ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `requirements` **(text)** — Requirements
- `fold` **(boolean)** — Folded in Kanban
  > This stage is folded in the kanban view when there are no records in that stage to display.
- `hired_stage` **(boolean)** — Hired Stage
  > If checked, this stage is used to determine the hire date of an applicant
- `rotting_threshold_days` **(integer)** — Days to rot
  > Day count before applicants in this stage become stale.         Set to 0 to disable.  Changing this parameter will not affect the rotting status/date of resources last updated before this change.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `job_ids` **(many2many)** — Job Specific → `hr.job`
  > Specific jobs that use this stage. Other jobs will not use this stage.
- `template_id` **(many2one)** — Email Template → `mail.template`
  > If set, a message is posted on the applicant using the template when the applicant is set to the stage.

## Campos Calculados (readonly)

- `is_warning_visible` **(boolean)** — Is Warning Visible 🔒 readonly
