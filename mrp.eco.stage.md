# ECO Stage — `mrp.eco.stage`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `type_ids` **(many2many)** — Types ⚠️ obrigatório → `mrp.eco.type`
- `legend_blocked` **(char)** — Red Kanban Label ⚠️ obrigatório
  > Override the default value displayed for the blocked state for kanban selection, when the ECO is in that stage.
- `legend_done` **(char)** — Green Kanban Label ⚠️ obrigatório
  > Override the default value displayed for the done state for kanban selection, when the ECO is in that stage.
- `legend_normal` **(char)** — Grey Kanban Label ⚠️ obrigatório
  > Override the default value displayed for the normal state for kanban selection, when the ECO is in that stage.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `folded` **(boolean)** — Folded in kanban view
- `allow_apply_change` **(boolean)** — Allow to apply changes
  > Allow to apply changes from this stage.
- `final_stage` **(boolean)** — Final Stage
  > Once the changes are applied, the ECOs will be moved to this stage.
- `approval_roles` **(char)** — Approval Roles 🔒 readonly
- `is_blocking` **(boolean)** — Blocking Stage 🔒 readonly
- `description` **(text)** — Description
  > Description and tooltips of the stage states.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `approval_template_ids` **(one2many)** — Approvals → `mrp.eco.approval.template`
