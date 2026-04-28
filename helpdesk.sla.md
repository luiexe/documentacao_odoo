# Helpdesk SLA Policies — `helpdesk.sla`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `team_id` **(many2one)** — Helpdesk Team ⚠️ obrigatório → `helpdesk.team`
- `priority` **(selection)** — Priority ⚠️ obrigatório
  > Opções: `0` (Low priority), `1` (Medium priority), `2` (High priority), `3` (Urgent)
- `time` **(float)** — Within ⚠️ obrigatório
  > Maximum number of working hours a ticket should take to reach the target stage, starting from the date it was created.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(html)** — SLA Policy Description
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `tag_ids` **(many2many)** — Tags → `helpdesk.tag`
- `stage_id` **(many2one)** — Target Stage → `helpdesk.stage`
  > Minimum stage a ticket needs to reach in order to satisfy this SLA.
- `exclude_stage_ids` **(many2many)** — Excluding Stages → `helpdesk.stage`
  > The time spent in these stages won't be taken into account in the calculation of the SLA.
- `partner_ids` **(many2many)** — Customers → `res.partner`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `ticket_count` **(integer)** — Ticket Count 🔒 readonly
