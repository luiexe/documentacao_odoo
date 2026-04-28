# Ticket SLA Status — `helpdesk.sla.status`

**Ordenação padrão:** `deadline ASC, sla_stage_id`

---

## Campos Obrigatórios

- `ticket_id` **(many2one)** — Ticket ⚠️ obrigatório → `helpdesk.ticket`
- `sla_id` **(many2one)** — Sla ⚠️ obrigatório → `helpdesk.sla`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `deadline` **(datetime)** — Deadline 🔒 readonly
- `reached_datetime` **(datetime)** — Reached Date
  > Datetime at which the SLA stage was reached for the first time
- `exceeded_hours` **(float)** — Exceeded Working Hours 🔒 readonly
  > Working hours exceeded for reached SLAs compared with deadline. Positive number means the SLA was reached after the deadline.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `sla_stage_id` **(many2one)** — Target Stage 🔒 readonly → `helpdesk.stage`
  > Minimum stage a ticket needs to reach in order to satisfy this SLA.

## Campos Calculados (readonly)

- `status` **(selection)** — Status 🔒 readonly
  > Opções: `failed` (Failed), `reached` (Reached), `ongoing` (Ongoing)
- `color` **(integer)** — Color Index 🔒 readonly
