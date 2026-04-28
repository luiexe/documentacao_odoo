# Project Milestone — `project.milestone`

**Ordenação padrão:** `sequence, deadline, is_reached desc, name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `project_id` **(many2one)** — Project ⚠️ obrigatório → `project.project`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `deadline` **(date)** — Deadline
- `is_reached` **(boolean)** — Reached
- `reached_date` **(date)** — Reached Date 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `quantity_percentage` **(float)** — Quantity (%) 🔒 readonly
  > Percentage of the ordered quantity that will automatically be delivered once the milestone is reached.
- `product_uom_qty` **(float)** — Quantity

## Relacionamentos

- `task_ids` **(one2many)** — Tasks → `project.task`
- `project_partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `sale_line_id` **(many2one)** — Sales Order Item → `sale.order.line`
  > Sales Order Item that will be updated once the milestone is reached.
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`

## Campos Calculados (readonly)

- `project_allow_milestones` **(boolean)** — Project Allow Milestones 🔒 readonly
- `is_deadline_exceeded` **(boolean)** — Is Deadline Exceeded 🔒 readonly
- `is_deadline_future` **(boolean)** — Is Deadline Future 🔒 readonly
- `task_count` **(integer)** — # of Tasks 🔒 readonly
- `done_task_count` **(integer)** — # of Done Tasks 🔒 readonly
- `can_be_marked_as_done` **(boolean)** — Can Be Marked As Done 🔒 readonly
- `allow_billable` **(boolean)** — Billable 🔒 readonly
- `sale_line_display_name` **(char)** — Sale Line Display Name 🔒 readonly
