# Ticket Analysis — `helpdesk.ticket.report.analysis`

**Ordenação padrão:** `create_date DESC`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description 🔒 readonly
- `ticket_ref` **(char)** — Ticket IDs Sequence 🔒 readonly
- `name` **(char)** — Subject 🔒 readonly
- `sla_success` **(boolean)** — SLA Status Success 🔒 readonly
- `create_date` **(datetime)** — Ticket Creation Date 🔒 readonly
- `priority` **(selection)** — Minimum Priority 🔒 readonly
  > Opções: `0` (Low priority), `1` (Medium priority), `2` (High priority), `3` (Urgent)
- `partner_name` **(char)** — Customer Name 🔒 readonly
- `partner_email` **(char)** — Customer Email 🔒 readonly
- `partner_phone` **(char)** — Customer Phone 🔒 readonly
- `sla_deadline` **(datetime)** — Ticket Deadline 🔒 readonly
- `ticket_deadline_hours` **(float)** — Working Hours until SLA Deadline 🔒 readonly
- `ticket_close_hours` **(float)** — Working Hours to Close 🔒 readonly
- `ticket_open_hours` **(float)** — Hours Open 🔒 readonly
- `ticket_assignation_hours` **(float)** — Working Hours to Assign 🔒 readonly
- `close_date` **(datetime)** — Closing Date 🔒 readonly
- `assign_date` **(datetime)** — First assignment date 🔒 readonly
- `rating_last_value` **(float)** — Rating (1-5) 🔒 readonly
- `active` **(boolean)** — Active 🔒 readonly
- `kanban_state` **(selection)** — Kanban State 🔒 readonly
  > Opções: `normal` (Grey), `done` (Green), `blocked` (Red)
- `first_response_hours` **(float)** — Hours to First Response 🔒 readonly
- `avg_response_hours` **(float)** — Average Hours to Respond 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly

## Relacionamentos

- `ticket_id` **(many2one)** — Ticket 🔒 readonly → `helpdesk.ticket`
- `tag_ids` **(many2many)** — Tags 🔒 readonly → `helpdesk.tag`
- `sla_ids` **(many2many)** — SLAs → `helpdesk.sla`
- `sla_status_ids` **(one2many)** — SLA Status → `helpdesk.sla.status`
- `user_id` **(many2one)** — Assigned To 🔒 readonly → `res.users`
- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `stage_id` **(many2one)** — Stage 🔒 readonly → `helpdesk.stage`
- `team_id` **(many2one)** — Helpdesk Team 🔒 readonly → `helpdesk.team`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `sale_order_id` **(many2one)** — Ref. Sales Order 🔒 readonly → `sale.order`

## Campos Calculados (readonly)

- `sla_fail` **(boolean)** — Failed SLA Policy 🔒 readonly
