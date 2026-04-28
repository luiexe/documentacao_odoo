# Convert Ticket to Lead — `helpdesk.ticket.to.lead`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `ticket_id` **(many2one)** — Ticket ⚠️ obrigatório → `helpdesk.ticket`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `convert_to` **(selection)** — Conversion Action
  > Opções: `convert` (Convert to opportunity)
- `force_assignment` **(boolean)** — Force assignment
  > If checked, forces salesman to be updated on updated opportunities even if already set.
- `action` **(selection)** — Related Customer
  > Opções: `create` (Create a new customer), `exist` (Link to an existing customer), `nothing` (Do not link to a customer)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Customer → `res.partner`
- `team_id` **(many2one)** — Sales Team → `crm.team`
- `user_id` **(many2one)** — Salesperson → `res.users`
