# SLA Status Analysis — `helpdesk.sla.report.analysis`

**Ordenação padrão:** `create_date DESC`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description 🔒 readonly
- `ticket_ref` **(char)** — Ticket IDs Sequence 🔒 readonly
- `name` **(char)** — Subject 🔒 readonly
- `create_date` **(datetime)** — Ticket Creation Date 🔒 readonly
- `priority` **(selection)** — Minimum Priority 🔒 readonly
  > Opções: `0` (Low priority), `1` (Medium priority), `2` (High priority), `3` (Urgent)
- `partner_name` **(char)** — Customer Name 🔒 readonly
- `partner_email` **(char)** — Customer Email 🔒 readonly
- `partner_phone` **(char)** — Customer Phone 🔒 readonly
- `ticket_open_hours` **(float)** — Hours Open 🔒 readonly
- `ticket_closed` **(boolean)** — Ticket Closed 🔒 readonly
- `ticket_close_hours` **(integer)** — Working Hours to Close 🔒 readonly
- `ticket_assignation_hours` **(integer)** — Working Hours to Assign 🔒 readonly
- `close_date` **(datetime)** — Closing Date 🔒 readonly
- `sla_deadline` **(datetime)** — SLA Deadline 🔒 readonly
- `sla_status` **(selection)** — Status 🔒 readonly
  > Opções: `failed` (SLA Failed), `reached` (SLA Success), `ongoing` (SLA in Progress)
- `sla_fail` **(boolean)** — SLA Status Failed 🔒 readonly
- `sla_success` **(boolean)** — SLA Status Success 🔒 readonly
- `sla_exceeded_hours` **(integer)** — Working Hours until SLA Deadline 🔒 readonly
  > Day to reach the stage of the SLA, without taking the working calendar into account
- `sla_status_failed` **(integer)** — Number of SLAs Failed 🔒 readonly
- `active` **(boolean)** — Active 🔒 readonly
- `rating_last_value` **(float)** — Rating (1-5) 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly
- `kanban_state` **(selection)** — Kanban State 🔒 readonly
  > Opções: `normal` (Grey), `done` (Green), `blocked` (Red)
- `avg_response_hours` **(float)** — Average Hours to Respond 🔒 readonly
- `first_response_hours` **(float)** — Hours to First Response 🔒 readonly

## Relacionamentos

- `ticket_id` **(many2one)** — Ticket 🔒 readonly → `helpdesk.ticket`
- `tag_ids` **(many2many)** — Tags 🔒 readonly → `helpdesk.tag`
- `user_id` **(many2one)** — Assigned To 🔒 readonly → `res.users`
- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `stage_id` **(many2one)** — Stage 🔒 readonly → `helpdesk.stage`
- `sla_id` **(many2one)** — SLA 🔒 readonly → `helpdesk.sla`
- `sla_ids` **(many2many)** — SLAs → `helpdesk.sla`
- `sla_status_ids` **(one2many)** — SLA Status → `helpdesk.sla.status`
- `sla_stage_id` **(many2one)** — SLA Stage 🔒 readonly → `helpdesk.stage`
- `team_id` **(many2one)** — Helpdesk Team 🔒 readonly → `helpdesk.team`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `sale_order_id` **(many2one)** — Ref. Sales Order 🔒 readonly → `sale.order`
