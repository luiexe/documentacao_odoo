# Action Window View — `ir.actions.act_window.view`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `view_mode` **(selection)** — View Type ⚠️ obrigatório
  > Opções: `list` (List), `form` (Form), `graph` (Graph), `pivot` (Pivot), `calendar` (Calendar), `kanban` (Kanban), `cohort` (Cohort), `gantt` (Gantt), `grid` (Grid), `hierarchy` (Hierarchy), `map` (Map), `activity` (Activity)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `multi` **(boolean)** — On Multiple Doc.
  > If set to true, the action will not be displayed on the right toolbar of a form view.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `view_id` **(many2one)** — View → `ir.ui.view`
- `act_window_id` **(many2one)** — Action → `ir.actions.act_window`
