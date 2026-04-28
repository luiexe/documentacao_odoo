# Helpdesk Stage — `helpdesk.stage`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `team_ids` **(many2many)** — Helpdesk Teams ⚠️ obrigatório → `helpdesk.team`
- `legend_blocked` **(char)** — Red Kanban Label ⚠️ obrigatório
- `legend_done` **(char)** — Green Kanban Label ⚠️ obrigatório
- `legend_normal` **(char)** — Grey Kanban Label ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `description` **(text)** — Description
- `sequence` **(integer)** — Sequence
- `fold` **(boolean)** — Folded
  > Tickets in a folded stage are considered as closed.
- `rotting_threshold_days` **(integer)** — Days to rot
  > Highlight tickets that haven't been updated for this many days.
- `color` **(integer)** — Color
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Email Template → `mail.template`
  > Email automatically sent to the customer when the ticket reaches this stage. By default, the email will be sent from the email alias of the helpdesk team. Otherwise it will be sent from the company's email address, or from the catchall (as defined in the System Parameters).
- `sms_template_id` **(many2one)** — SMS Template → `sms.template`
  > SMS automatically sent to the customer when the ticket reaches this stage.

## Campos Calculados (readonly)

- `ticket_count` **(integer)** — Ticket Count 🔒 readonly
