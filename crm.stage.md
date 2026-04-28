# CRM Stages — `crm.stage`

**Ordenação padrão:** `sequence, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Stage Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > Used to order stages. Lower is better.
- `is_won` **(boolean)** — Is Won Stage?
- `rotting_threshold_days` **(integer)** — Days to rot
  > Highlight opportunities that haven't been updated for this many days.         Set to 0 to disable. Changing this parameter will not affect the rotting status/date of resources last updated before this change.
- `requirements` **(text)** — Requirements
  > Enter here the internal requirements for this stage (ex: Offer sent to customer). It will appear as a tooltip over the stage's name.
- `fold` **(boolean)** — Folded in Pipeline
  > This stage is folded in the kanban view when there are no records in that stage to display.
- `color` **(integer)** — Color
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `team_ids` **(many2many)** — Sales Teams → `crm.team`

## Campos Calculados (readonly)

- `team_count` **(integer)** — team_count 🔒 readonly
